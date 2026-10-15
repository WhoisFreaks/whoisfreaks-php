# WhoisFreaks PHP SDK: WHOIS API Client for PHP

[![Packagist](https://img.shields.io/packagist/v/whoisfreaks/whoisfreaks-php.svg)](https://packagist.org/packages/whoisfreaks/whoisfreaks-php)
[![License: MIT](https://img.shields.io/badge/license-MIT-green.svg)](LICENSE)
[![API status](https://img.shields.io/badge/API%20status-live-brightgreen.svg)](https://status.whois.whoisfreaks.com/)

The official PHP client for the [WhoisFreaks WHOIS API](https://whoisfreaks.com/products/whois-api). Look up live WHOIS records for any domain across 1,529+ TLDs, pull WHOIS history back to 1986, search registrants with reverse WHOIS and run bulk WHOIS lookups from PHP code.

The same package covers the [DNS lookup API](https://whoisfreaks.com/products/dns-checker-api), [domain availability API](https://whoisfreaks.com/products/domain-availability-api), [typosquatting API](https://whoisfreaks.com/products/domain-typosquats-api), [SSL certificate API](https://whoisfreaks.com/products/ssl-certificate-api), IP geolocation and IP reputation.

A live WHOIS lookup returns structured JSON like this (trimmed):

```json
{
  "status": true,
  "domain_name": "whoisfreaks.com",
  "domain_registered": "yes",
  "create_date": "2019-03-19",
  "update_date": "2026-02-17",
  "expiry_date": "2027-03-19",
  "domain_registrar": {
    "iana_id": "1068",
    "registrar_name": "NAMECHEAP INC",
    "normalized_name": "namecheap, inc.",
    "website_url": "http://www.namecheap.com"
  },
  "registrant_contact": {
    "city": "Lewes",
    "state": "Delaware",
    "zip_code": "19958",
    "country_name": "United States",
    "country_code": "US"
  },
  "name_servers": ["albert.ns.cloudflare.com", "sue.ns.cloudflare.com"],
  "domain_status": ["clienttransferprohibited"]
}
```

## Contents

- [Installation](#installation)
- [Get an API key](#get-an-api-key)
- [WHOIS lookup](#whois-lookup)
- [Normalized registrar, address and date fields](#normalized-registrar-address-and-date-fields)
- [Bulk WHOIS lookup](#bulk-whois-lookup)
- [WHOIS history](#whois-history)
- [Reverse WHOIS](#reverse-whois)
- [DNS lookup](#dns-lookup)
- [Domain availability check](#domain-availability-check)
- [Typosquatting detection](#typosquatting-detection)
- [Error handling](#error-handling)
- [All endpoints](#all-endpoints)
- [Requirements](#requirements)
- [Support](#support)

## Installation

```sh
composer require whoisfreaks/whoisfreaks-php
```

## Get an API key

Create a free account at [billing.whoisfreaks.com/signup](https://billing.whoisfreaks.com/signup). New accounts get 500 free credits with no credit card, usable across the live WHOIS, WHOIS history and reverse WHOIS APIs.

Keep the key out of source control. The examples read it from an environment variable:

```sh
export WHOISFREAKS_API_KEY="your_api_key"
```

Every example below assumes this setup:

```php
<?php
require __DIR__ . '/vendor/autoload.php';

$config = WhoisFreaks\Configuration::getDefaultConfiguration()
    ->setApiKey('apiKey', getenv('WHOISFREAKS_API_KEY'));
$http = new GuzzleHttp\Client();
```

## WHOIS lookup

Each request queries WHOIS servers and RDAP live, so you get the current record rather than a cached copy. One lookup costs 1 credit.

```php
$whois = new WhoisFreaks\Api\WHOISApi($http, $config);
$record = $whois->whoisLive('whoisfreaks.com');

echo $record->getCreateDate(), ' ', $record->getExpiryDate(), PHP_EOL; // 2019-03-19 2027-03-19
echo $record->getDomainRegistrar()->getRegistrarName(), PHP_EOL;       // NAMECHEAP INC
print_r($record->getNameServers());
```

## Normalized registrar, address and date fields

Registries and registrars write the same facts in different formats. The API returns normalized fields so records from different TLDs line up without your own parsing code.

| What you get | Field | Example |
|---|---|---|
| One registrar name, however the registry spells it | `domain_registrar.normalized_name` | `namecheap, inc.` for both "NAMECHEAP INC" and "NameCheap, Inc" |
| A parsed and geocoded contact address | `registrant_contact.street`, `city`, `state`, `zip_code`, `country_name`, `country_code` | `Lewes`, `Delaware`, `19958`, `United States`, `US` |
| One date format | `create_date`, `update_date`, `expiry_date` | `2019-03-19` |

```php
$registrant = $record->getRegistrantContact();

echo $record->getDomainRegistrar()->getNormalizedName(), PHP_EOL;   // namecheap, inc.
echo $registrant->getCity(), ' ', $registrant->getState(), PHP_EOL; // Lewes Delaware
echo $registrant->getCountryCode(), PHP_EOL;                        // US
```

Use these fields to group a domain portfolio by registrar, filter registrants by country code or sort domains by expiry date across every TLD.

## Bulk WHOIS lookup

Look up to 100 domains in one call.

```php
$request = new WhoisFreaks\Model\BulkWhoisRequest([
    'domainNames' => ['example.com', 'whoisfreaks.com', 'github.com'],
]);
$result = $whois->bulkWhois($request);
```

For larger jobs, the [Bulk WHOIS API](https://whoisfreaks.com/products/bulk-whois-api) accepts file uploads of up to 3M domains.

## WHOIS history

Get every recorded ownership change for a domain in one request. A new record is stored only when the WHOIS data changed, and history goes back to 1986.

```php
$history = $whois->whoisHistory('whoisfreaks.com');
```

## Reverse WHOIS

Find every domain registered with a keyword, such as a company name or registrant email, across 4.5B+ WHOIS records.

```php
$matches = $whois->whoisReverse('whoisfreaks', 1);
```

## DNS lookup

Pull live DNS records for a domain. Pass `all` or a comma-separated list of record types: `A`, `AAAA`, `MX`, `NS`, `TXT`, `SOA`, `SPF`, `CNAME`.

```php
$dns = new WhoisFreaks\Api\DNSApi($http, $config);
$records = $dns->dnsLive('A,MX,TXT', 'whoisfreaks.com');
```

The same class also covers bulk DNS, historical DNS and reverse DNS lookups.

## Domain availability check

Check whether a domain is registered and, with suggestions turned on, get up to 100 available alternatives on other TLDs.

```php
$availability = new WhoisFreaks\Api\DomainAvailabilityApi($http, $config);
$result = $availability->domainAvailabilityV2('whoisfreaks.io', true, 5);
```

## Typosquatting detection

Find registered domains that look like typo variants of a brand name. Search by a brand `keyword`, or by a wildcard `pattern` such as `whois*` (up to 3 asterisks). Results come 100 domains per page with registration date, expiry date and drop status, across 1,529+ TLDs.

```php
$typosquatting = new WhoisFreaks\Api\TyposquattingApi($http, $config);
$typos = $typosquatting->typosquatting('whoisfreaks');
```

To get the next page, pass the `nextPageToken` value from the response as `$pageToken`, along with the same keyword or pattern.

## Error handling

Failed requests raise `WhoisFreaks\ApiException` with the HTTP status code and response body.

```php
try {
    $record = $whois->whoisLive('whoisfreaks.com');
} catch (WhoisFreaks\ApiException $e) {
    echo $e->getCode(), ' ', $e->getResponseBody(), PHP_EOL;
}
```

Live API uptime and incident history are on the [status page](https://status.whois.whoisfreaks.com/).

## All endpoints

All URIs are relative to `https://api.whoisfreaks.com`. Each method links to its parameters and response model.

### WHOIS

| Class | Method | HTTP request | Description |
|---|---|---|---|
| WHOISApi | [bulkWhois](docs/Api/WHOISApi.md#bulkwhois) | POST /v2.0/bulkwhois/live | Bulk WHOIS Lookup |
| WHOISApi | [whoisHistory](docs/Api/WHOISApi.md#whoishistory) | GET /v2.0/whois/history | Historical WHOIS records for a domain |
| WHOISApi | [whoisLive](docs/Api/WHOISApi.md#whoislive) | GET /v2.0/whois/live | Live WHOIS Lookup |
| WHOISApi | [whoisReverse](docs/Api/WHOISApi.md#whoisreverse) | GET /v2.0/whois/reverse | Reverse WHOIS lookup by keyword |
| ASNWHOISApi | [asnWhois](docs/Api/ASNWHOISApi.md#asnwhois) | GET /v2.0/asn-whois | ASN WHOIS Lookup |
| IPWHOISApi | [ipWhois](docs/Api/IPWHOISApi.md#ipwhois) | GET /v1.0/ip-whois | IP WHOIS Lookup |

### DNS, SSL and subdomains

| Class | Method | HTTP request | Description |
|---|---|---|---|
| DNSApi | [dnsBulk](docs/Api/DNSApi.md#dnsbulk) | POST /v2.0/dns/bulk/live | Bulk DNS Lookup |
| DNSApi | [dnsHistorical](docs/Api/DNSApi.md#dnshistorical) | GET /v2.0/dns/historical | Historical DNS Lookup |
| DNSApi | [dnsLive](docs/Api/DNSApi.md#dnslive) | GET /v2.0/dns/live | Live DNS Lookup |
| DNSApi | [dnsReverse](docs/Api/DNSApi.md#dnsreverse) | GET /v2.1/dns/reverse | Reverse DNS Lookup |
| SSLApi | [sslLookup](docs/Api/SSLApi.md#ssllookup) | GET /v1.0/ssl/live | SSL Certificate Lookup |
| SubdomainsApi | [subdomains](docs/Api/SubdomainsApi.md#subdomains) | GET /v1.0/subdomains | Subdomains Lookup |

### Domain availability, typosquatting and reputation

| Class | Method | HTTP request | Description |
|---|---|---|---|
| DomainAvailabilityApi | [bulkDomainAvailabilityV2](docs/Api/DomainAvailabilityApi.md#bulkdomainavailabilityv2) | POST /v2.0/domain/availability | Bulk Domain Availability Check |
| DomainAvailabilityApi | [domainAvailabilityV2](docs/Api/DomainAvailabilityApi.md#domainavailabilityv2) | GET /v2.0/domain/availability | Domain Availability Check with Suggestions |
| TyposquattingApi | [typosquatting](docs/Api/TyposquattingApi.md#typosquatting) | GET /v3.0/domain/typos | Typosquatting Lookup |
| DomainReputationApi | [domainReputation](docs/Api/DomainReputationApi.md#domainreputation) | GET /v1/domain/security | Domain Reputation Lookup |

### IP geolocation and reputation

| Class | Method | HTTP request | Description |
|---|---|---|---|
| GeolocationApi | [bulkGeolocation](docs/Api/GeolocationApi.md#bulkgeolocation) | POST /v1.0/geolocation | Bulk IP Geolocation |
| GeolocationApi | [geolocation](docs/Api/GeolocationApi.md#geolocation) | GET /v1.0/geolocation | IP Geolocation Lookup |
| IPReputationApi | [bulkIpReputation](docs/Api/IPReputationApi.md#bulkipreputation) | POST /v1.0/security | Bulk IP Reputation |
| IPReputationApi | [ipReputation](docs/Api/IPReputationApi.md#ipreputation) | GET /v1.0/security | IP Reputation Lookup |

### Account

| Class | Method | HTTP request | Description |
|---|---|---|---|
| AccountApi | [accountUsage](docs/Api/AccountApi.md#accountusage) | GET /v1.0/whoisapi/usage | Account Usage |
| AccountApi | [databaseFileStatus](docs/Api/AccountApi.md#databasefilestatus) | GET /v3.4/status | Database File Status (Public) |
| AccountApi | [rotateApiKey](docs/Api/AccountApi.md#rotateapikey) | GET /v1.0/api-key/rotate | Rotate API Key |

### Database downloads

WHOIS, DNS, subdomain, IP, newly registered, expiring and dropped domain databases, plus the phishing, malware and spam threat feeds, are available through the `Databases*` classes. See the [full method list](docs/) for every download and status endpoint.

## Requirements

PHP 7.4 or later, PHP 8 supported. Uses Guzzle 7 for HTTP.

## Support

- WHOIS API documentation: [whoisfreaks.com/documentation/whois-api](https://whoisfreaks.com/documentation/whois-api)
- All API documentation: [whoisfreaks.com/documentation](https://whoisfreaks.com/documentation)
- Product page: [WhoisFreaks WHOIS API](https://whoisfreaks.com/products/whois-api)
- API status: [status.whois.whoisfreaks.com](https://status.whois.whoisfreaks.com/)
- Email: support@whoisfreaks.com
- Quick start: [WHOIS API examples](https://github.com/WhoisFreaks/whois-api)
- Other languages: [Python](https://github.com/WhoisFreaks/whoisfreaks-python), [JavaScript](https://github.com/WhoisFreaks/whoisfreaks-javascript), [TypeScript](https://github.com/WhoisFreaks/whoisfreaks-typescript), [Java](https://github.com/WhoisFreaks/whoisfreaks-java), [Go](https://github.com/WhoisFreaks/whoisfreaks-go), [C#](https://github.com/WhoisFreaks/whoisfreaks-csharp), [Ruby](https://github.com/WhoisFreaks/whoisfreaks-ruby), [PHP](https://github.com/WhoisFreaks/whoisfreaks-php), [Swift](https://github.com/WhoisFreaks/whoisfreaks-swift), [Kotlin](https://github.com/WhoisFreaks/whoisfreaks-kotlin)

## License

MIT. See [LICENSE](LICENSE).

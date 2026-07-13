# whoisfreaks

Complete WhoisFreaks API — WHOIS, DNS, SSL, Geolocation, Typosquatting,
IP Intelligence, Domain Reputation, and bulk database downloads.

## Authentication
All requests require an `apiKey` query parameter.

## Resources
- Docs: https://whoisfreaks.com/documentation
- Billing: https://billing.whoisfreaks.com
- Support: support@whoisfreaks.com


For more information, please visit [https://whoisfreaks.com](https://whoisfreaks.com).

## Installation & Usage

### Requirements

PHP 7.4 and later.
Should also work with PHP 8.0.

### Composer

To install the bindings via [Composer](https://getcomposer.org/), add the following to `composer.json`:

```json
{
  "repositories": [
    {
      "type": "vcs",
      "url": "https://github.com/GIT_USER_ID/GIT_REPO_ID.git"
    }
  ],
  "require": {
    "GIT_USER_ID/GIT_REPO_ID": "*@dev"
  }
}
```

Then run `composer install`

### Manual Installation

Download the files and include `autoload.php`:

```php
<?php
require_once('/path/to/whoisfreaks/vendor/autoload.php');
```

## Getting Started

Please follow the [installation procedure](#installation--usage) and then run the following:

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\ASNWHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$asn = as15169; // string
$format = 'json'; // string

try {
    $result = $apiInstance->asnWhois($apiKey, $asn, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ASNWHOISApi->asnWhois: ', $e->getMessage(), PHP_EOL;
}

```

## API Endpoints

All URIs are relative to *https://api.whoisfreaks.com*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*ASNWHOISApi* | [**asnWhois**](docs/Api/ASNWHOISApi.md#asnwhois) | **GET** /v2.0/asn-whois | ASN WHOIS Lookup
*AccountApi* | [**accountUsage**](docs/Api/AccountApi.md#accountusage) | **GET** /v1.0/whoisapi/usage | Account Usage
*AccountApi* | [**databaseFileStatus**](docs/Api/AccountApi.md#databasefilestatus) | **GET** /v3.3/status | Database File Status (Public)
*AccountApi* | [**rotateApiKey**](docs/Api/AccountApi.md#rotateapikey) | **GET** /v1.0/api-key/rotate | Rotate API Key
*DNSApi* | [**dnsBulk**](docs/Api/DNSApi.md#dnsbulk) | **POST** /v2.0/dns/bulk/live | Bulk DNS Lookup
*DNSApi* | [**dnsHistorical**](docs/Api/DNSApi.md#dnshistorical) | **GET** /v2.0/dns/historical | Historical DNS Lookup
*DNSApi* | [**dnsLive**](docs/Api/DNSApi.md#dnslive) | **GET** /v2.0/dns/live | Live DNS Lookup
*DNSApi* | [**dnsReverse**](docs/Api/DNSApi.md#dnsreverse) | **GET** /v2.1/dns/reverse | Reverse DNS Lookup
*DatabasesASNWHOISApi* | [**dbAsnWhois**](docs/Api/DatabasesASNWHOISApi.md#dbasnwhois) | **GET** /v3.3/download/snapshot/asn/whois | ASN WHOIS Snapshot
*DatabasesASNWHOISApi* | [**dbAsnWhoisStatus**](docs/Api/DatabasesASNWHOISApi.md#dbasnwhoisstatus) | **GET** /v3.3/status/snapshot/asn/whois | ASN WHOIS Snapshot Status
*DatabasesDNSApi* | [**dbDnsDaily**](docs/Api/DatabasesDNSApi.md#dbdnsdaily) | **GET** /v3.2/download/dbupdate/daily/dns | DNS Database Daily
*DatabasesDNSApi* | [**dbDnsMonthly**](docs/Api/DatabasesDNSApi.md#dbdnsmonthly) | **GET** /v3.2/download/dbupdate/monthly/dns | DNS Database Monthly
*DatabasesDNSApi* | [**dbDnsWeekly**](docs/Api/DatabasesDNSApi.md#dbdnsweekly) | **GET** /v3.2/download/dbupdate/weekly/dns | DNS Database Weekly
*DatabasesExpiringDroppedApi* | [**dbDropped**](docs/Api/DatabasesExpiringDroppedApi.md#dbdropped) | **GET** /v3.1/download/domainer/dropped | Dropped Domains
*DatabasesExpiringDroppedApi* | [**dbDroppedBacklinks**](docs/Api/DatabasesExpiringDroppedApi.md#dbdroppedbacklinks) | **GET** /v3.3/download/domainer/dropped/backlinks | Dropped With Backlinks
*DatabasesExpiringDroppedApi* | [**dbDroppedJson**](docs/Api/DatabasesExpiringDroppedApi.md#dbdroppedjson) | **GET** /v3.1/domains/dropped | Dropped Domains (JSON)
*DatabasesExpiringDroppedApi* | [**dbExpired**](docs/Api/DatabasesExpiringDroppedApi.md#dbexpired) | **GET** /v3.1/download/domainer/expired | Expiring Domains
*DatabasesExpiringDroppedApi* | [**dbExpiredCleaned**](docs/Api/DatabasesExpiringDroppedApi.md#dbexpiredcleaned) | **GET** /v3.1/download/domainer/expired/cleaned | Expiring Cleaned WHOIS
*DatabasesIPGeolocationApi* | [**dbIpCity**](docs/Api/DatabasesIPGeolocationApi.md#dbipcity) | **GET** /v3.3/download/snapshot/ip/city | IP to City Snapshot
*DatabasesIPGeolocationApi* | [**dbIpCityStatus**](docs/Api/DatabasesIPGeolocationApi.md#dbipcitystatus) | **GET** /v3.3/status/snapshot/ip/city | IP to City Snapshot Status
*DatabasesIPGeolocationApi* | [**dbIpCountry**](docs/Api/DatabasesIPGeolocationApi.md#dbipcountry) | **GET** /v3.3/download/snapshot/ip/country | IP to Country Snapshot
*DatabasesIPGeolocationApi* | [**dbIpCountryStatus**](docs/Api/DatabasesIPGeolocationApi.md#dbipcountrystatus) | **GET** /v3.3/status/snapshot/ip/country | IP to Country Snapshot Status
*DatabasesIPSecurityApi* | [**dbIpSecurity**](docs/Api/DatabasesIPSecurityApi.md#dbipsecurity) | **GET** /v3.3/download/snapshot/ip/security | IP Security Snapshot
*DatabasesIPSecurityApi* | [**dbIpSecurityStatus**](docs/Api/DatabasesIPSecurityApi.md#dbipsecuritystatus) | **GET** /v3.3/status/snapshot/ip/security | IP Security Snapshot Status
*DatabasesIPWHOISApi* | [**dbIpWhois**](docs/Api/DatabasesIPWHOISApi.md#dbipwhois) | **GET** /v3.3/download/snapshot/ip/whois | IP WHOIS Snapshot
*DatabasesIPWHOISApi* | [**dbIpWhoisStatus**](docs/Api/DatabasesIPWHOISApi.md#dbipwhoisstatus) | **GET** /v3.3/status/snapshot/ip/whois | IP WHOIS Snapshot Status
*DatabasesNewlyRegisteredApi* | [**dbNewlyCctld**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlycctld) | **GET** /v3.1/download/domainer/cctld | Newly Registered ccTLD (CSV)
*DatabasesNewlyRegisteredApi* | [**dbNewlyCctldCleaned**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlycctldcleaned) | **GET** /v3.1/download/domainer/cctld/cleaned | Newly Registered ccTLD Cleaned WHOIS (CSV)
*DatabasesNewlyRegisteredApi* | [**dbNewlyCctldJson**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlycctldjson) | **GET** /v3.1/domains/newly/cctld | Newly Registered ccTLD (JSON)
*DatabasesNewlyRegisteredApi* | [**dbNewlyDns**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlydns) | **GET** /v3.1/download/domainer/newly/dns | Newly Registered With DNS
*DatabasesNewlyRegisteredApi* | [**dbNewlyGtld**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlygtld) | **GET** /v3.1/download/domainer/gtld | Newly Registered gTLD (CSV)
*DatabasesNewlyRegisteredApi* | [**dbNewlyGtldCleaned**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlygtldcleaned) | **GET** /v3.1/download/domainer/gtld/cleaned | Newly Registered gTLD Cleaned WHOIS (CSV)
*DatabasesNewlyRegisteredApi* | [**dbNewlyGtldJson**](docs/Api/DatabasesNewlyRegisteredApi.md#dbnewlygtldjson) | **GET** /v3.1/domains/newly/gtld | Newly Registered gTLD (JSON)
*DatabasesSubdomainsApi* | [**dbSubdomainsDaily**](docs/Api/DatabasesSubdomainsApi.md#dbsubdomainsdaily) | **GET** /v3.2/download/dbupdate/daily/subdomains | Subdomains Daily
*DatabasesSubdomainsApi* | [**dbSubdomainsMonthly**](docs/Api/DatabasesSubdomainsApi.md#dbsubdomainsmonthly) | **GET** /v3.2/download/dbupdate/monthly/subdomains | Subdomains Monthly
*DatabasesSubdomainsApi* | [**dbSubdomainsWeekly**](docs/Api/DatabasesSubdomainsApi.md#dbsubdomainsweekly) | **GET** /v3.2/download/dbupdate/weekly/subdomains | Subdomains Weekly
*DatabasesWHOISApi* | [**dbWhoisDaily**](docs/Api/DatabasesWHOISApi.md#dbwhoisdaily) | **GET** /v3.3/download/dbupdate/daily/domains/whois | WHOIS Database Daily
*DatabasesWHOISApi* | [**dbWhoisMonthly**](docs/Api/DatabasesWHOISApi.md#dbwhoismonthly) | **GET** /v3.3/download/dbupdate/monthly/domains/whois | WHOIS Database Monthly
*DatabasesWHOISApi* | [**dbWhoisWeekly**](docs/Api/DatabasesWHOISApi.md#dbwhoisweekly) | **GET** /v3.3/download/dbupdate/weekly/domains/whois | WHOIS Database Weekly
*DomainAvailabilityApi* | [**bulkDomainAvailabilityV2**](docs/Api/DomainAvailabilityApi.md#bulkdomainavailabilityv2) | **POST** /v2.0/domain/availability | Bulk Domain Availability Check
*DomainAvailabilityApi* | [**domainAvailabilityV2**](docs/Api/DomainAvailabilityApi.md#domainavailabilityv2) | **GET** /v2.0/domain/availability | Domain Availability Check with Suggestions
*DomainReputationApi* | [**domainReputation**](docs/Api/DomainReputationApi.md#domainreputation) | **GET** /v1/domain/security | Domain Reputation Lookup
*GeolocationApi* | [**bulkGeolocation**](docs/Api/GeolocationApi.md#bulkgeolocation) | **POST** /v1.0/geolocation | Bulk IP Geolocation
*GeolocationApi* | [**geolocation**](docs/Api/GeolocationApi.md#geolocation) | **GET** /v1.0/geolocation | IP Geolocation Lookup
*IPReputationApi* | [**bulkIpReputation**](docs/Api/IPReputationApi.md#bulkipreputation) | **POST** /v1.0/security | Bulk IP Reputation
*IPReputationApi* | [**ipReputation**](docs/Api/IPReputationApi.md#ipreputation) | **GET** /v1.0/security | IP Reputation Lookup
*IPWHOISApi* | [**ipWhois**](docs/Api/IPWHOISApi.md#ipwhois) | **GET** /v1.0/ip-whois | IP WHOIS Lookup
*SSLApi* | [**sslLookup**](docs/Api/SSLApi.md#ssllookup) | **GET** /v1.0/ssl/live | SSL Certificate Lookup
*SubdomainsApi* | [**subdomains**](docs/Api/SubdomainsApi.md#subdomains) | **GET** /v1.0/subdomains | Subdomains Lookup
*TyposquattingApi* | [**typosquatting**](docs/Api/TyposquattingApi.md#typosquatting) | **GET** /v3.0/domain/typos | Typosquatting Lookup
*WHOISApi* | [**bulkWhois**](docs/Api/WHOISApi.md#bulkwhois) | **POST** /v2.0/bulkwhois/live | Bulk WHOIS Lookup
*WHOISApi* | [**whoisHistoricalOrReverse**](docs/Api/WHOISApi.md#whoishistoricalorreverse) | **GET** /v1.0/whois | WHOIS Historical or Reverse Lookup
*WHOISApi* | [**whoisLive**](docs/Api/WHOISApi.md#whoislive) | **GET** /v2.0/whois/live | Live WHOIS Lookup

## Models

- [AccountUsageResponse](docs/Model/AccountUsageResponse.md)
- [ApiCredits](docs/Model/ApiCredits.md)
- [ApiSubscription](docs/Model/ApiSubscription.md)
- [AsnInfo](docs/Model/AsnInfo.md)
- [AsnPeer](docs/Model/AsnPeer.md)
- [AsnWhoisResponse](docs/Model/AsnWhoisResponse.md)
- [BulkDnsResponse](docs/Model/BulkDnsResponse.md)
- [BulkDomainAvailabilityRequest](docs/Model/BulkDomainAvailabilityRequest.md)
- [BulkDomainAvailabilityResponse](docs/Model/BulkDomainAvailabilityResponse.md)
- [BulkGeolocationRequest](docs/Model/BulkGeolocationRequest.md)
- [BulkWhoisItem](docs/Model/BulkWhoisItem.md)
- [BulkWhoisRequest](docs/Model/BulkWhoisRequest.md)
- [BulkWhoisResponse](docs/Model/BulkWhoisResponse.md)
- [CountryMetadata](docs/Model/CountryMetadata.md)
- [Currency](docs/Model/Currency.md)
- [DatabaseFileStatus](docs/Model/DatabaseFileStatus.md)
- [DatabaseUpdates](docs/Model/DatabaseUpdates.md)
- [DateRangeStatus](docs/Model/DateRangeStatus.md)
- [DgaFeatures](docs/Model/DgaFeatures.md)
- [DgaScore](docs/Model/DgaScore.md)
- [DnsBulkRequest](docs/Model/DnsBulkRequest.md)
- [DnsRecord](docs/Model/DnsRecord.md)
- [DnsResponse](docs/Model/DnsResponse.md)
- [DomainAvailabilityItem](docs/Model/DomainAvailabilityItem.md)
- [DomainAvailabilityResponse](docs/Model/DomainAvailabilityResponse.md)
- [DomainReputationInput](docs/Model/DomainReputationInput.md)
- [DomainReputationResponse](docs/Model/DomainReputationResponse.md)
- [EligibilityInfo](docs/Model/EligibilityInfo.md)
- [ErrorResponse](docs/Model/ErrorResponse.md)
- [EvidenceSummary](docs/Model/EvidenceSummary.md)
- [GeoAsn](docs/Model/GeoAsn.md)
- [GeoCompany](docs/Model/GeoCompany.md)
- [GeoNetwork](docs/Model/GeoNetwork.md)
- [GeolocationResponse](docs/Model/GeolocationResponse.md)
- [HistoricalDnsResponse](docs/Model/HistoricalDnsResponse.md)
- [InetNum](docs/Model/InetNum.md)
- [IpLocation](docs/Model/IpLocation.md)
- [IpReputationResponse](docs/Model/IpReputationResponse.md)
- [IpSecurity](docs/Model/IpSecurity.md)
- [IpSecurityAsn](docs/Model/IpSecurityAsn.md)
- [IpSecurityNetwork](docs/Model/IpSecurityNetwork.md)
- [IpWhoisResponse](docs/Model/IpWhoisResponse.md)
- [Irt](docs/Model/Irt.md)
- [NewlyStatus](docs/Model/NewlyStatus.md)
- [PersonalInformation](docs/Model/PersonalInformation.md)
- [PivotMatch](docs/Model/PivotMatch.md)
- [RegistrarInformation](docs/Model/RegistrarInformation.md)
- [RegistryData](docs/Model/RegistryData.md)
- [RelatedIoc](docs/Model/RelatedIoc.md)
- [ReputationIndicators](docs/Model/ReputationIndicators.md)
- [ReputationIntelligence](docs/Model/ReputationIntelligence.md)
- [ReputationSignal](docs/Model/ReputationSignal.md)
- [ReputationSignals](docs/Model/ReputationSignals.md)
- [ResellerContact](docs/Model/ResellerContact.md)
- [ReverseDnsResponse](docs/Model/ReverseDnsResponse.md)
- [ReverseWhoisResponse](docs/Model/ReverseWhoisResponse.md)
- [RiskCategory](docs/Model/RiskCategory.md)
- [Route](docs/Model/Route.md)
- [SnapshotStatus](docs/Model/SnapshotStatus.md)
- [SslAlternateNames](docs/Model/SslAlternateNames.md)
- [SslAuthorityInfo](docs/Model/SslAuthorityInfo.md)
- [SslCertificate](docs/Model/SslCertificate.md)
- [SslCertificatePolicy](docs/Model/SslCertificatePolicy.md)
- [SslExtensionsInfo](docs/Model/SslExtensionsInfo.md)
- [SslPublicKeyInfo](docs/Model/SslPublicKeyInfo.md)
- [SslResponse](docs/Model/SslResponse.md)
- [SslUnitInfo](docs/Model/SslUnitInfo.md)
- [Subdomain](docs/Model/Subdomain.md)
- [SubdomainsResponse](docs/Model/SubdomainsResponse.md)
- [ThreatSource](docs/Model/ThreatSource.md)
- [TrustSignals](docs/Model/TrustSignals.md)
- [TyposquattingDomain](docs/Model/TyposquattingDomain.md)
- [TyposquattingResponse](docs/Model/TyposquattingResponse.md)
- [UpdateFrequencies](docs/Model/UpdateFrequencies.md)
- [WhoisHistoricalItem](docs/Model/WhoisHistoricalItem.md)
- [WhoisHistoricalResponse](docs/Model/WhoisHistoricalResponse.md)
- [WhoisOrganization](docs/Model/WhoisOrganization.md)
- [WhoisPerson](docs/Model/WhoisPerson.md)
- [WhoisResponse](docs/Model/WhoisResponse.md)
- [WhoisRole](docs/Model/WhoisRole.md)

## Authorization

Authentication schemes defined for the API:
### ApiKeyAuth

- **Type**: API key
- **API key parameter name**: apiKey
- **Location**: URL query string


## Tests

To run the tests, use:

```bash
composer install
vendor/bin/phpunit
```

## Author

support@whoisfreaks.com

## About this package

This PHP package is automatically generated by the [OpenAPI Generator](https://openapi-generator.tech) project:

- API version: `1.0.0`
    - Package version: `0.17.0`
    - Generator version: `7.11.0`
- Build package: `org.openapitools.codegen.languages.PhpClientCodegen`

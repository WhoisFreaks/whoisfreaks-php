# WhoisFreaks\DNSApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**dnsBulk()**](DNSApi.md#dnsBulk) | **POST** /v2.0/dns/bulk/live | Bulk DNS Lookup |
| [**dnsHistorical()**](DNSApi.md#dnsHistorical) | **GET** /v2.0/dns/historical | Historical DNS Lookup |
| [**dnsLive()**](DNSApi.md#dnsLive) | **GET** /v2.0/dns/live | Live DNS Lookup |
| [**dnsReverse()**](DNSApi.md#dnsReverse) | **GET** /v2.1/dns/reverse | Reverse DNS Lookup |


## `dnsBulk()`

```php
dnsBulk($type, $dnsBulkRequest, $format): \WhoisFreaks\Model\BulkDnsResponse
```

Bulk DNS Lookup

Up to 100 domains + 100 IPs in one request.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DNSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$type = 'all'; // string
$dnsBulkRequest = new \WhoisFreaks\Model\DnsBulkRequest(); // \WhoisFreaks\Model\DnsBulkRequest
$format = 'json'; // string

try {
    $result = $apiInstance->dnsBulk($type, $dnsBulkRequest, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DNSApi->dnsBulk: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **type** | **string**|  | [default to &#39;all&#39;] |
| **dnsBulkRequest** | [**\WhoisFreaks\Model\DnsBulkRequest**](../Model/DnsBulkRequest.md)|  | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\BulkDnsResponse**](../Model/BulkDnsResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dnsHistorical()`

```php
dnsHistorical($domainName, $type, $page, $format): \WhoisFreaks\Model\HistoricalDnsResponse
```

Historical DNS Lookup

All historical DNS records. 2 credits per page (100 records/page).

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DNSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$domainName = 'domainName_example'; // string
$type = 'all'; // string
$page = 1; // int
$format = 'json'; // string

try {
    $result = $apiInstance->dnsHistorical($domainName, $type, $page, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DNSApi->dnsHistorical: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domainName** | **string**|  | |
| **type** | **string**|  | [default to &#39;all&#39;] |
| **page** | **int**|  | [optional] [default to 1] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\HistoricalDnsResponse**](../Model/HistoricalDnsResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dnsLive()`

```php
dnsLive($type, $domainName, $ipAddress, $format): \WhoisFreaks\Model\DnsResponse
```

Live DNS Lookup

Real-time DNS record lookup. 1 credit per query.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DNSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$type = 'all'; // string | all or comma-separated: A,MX,NS,TXT,SOA,SPF,AAAA,CNAME
$domainName = 'domainName_example'; // string
$ipAddress = 'ipAddress_example'; // string | Use for PTR lookups
$format = 'json'; // string

try {
    $result = $apiInstance->dnsLive($type, $domainName, $ipAddress, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DNSApi->dnsLive: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **type** | **string**| all or comma-separated: A,MX,NS,TXT,SOA,SPF,AAAA,CNAME | [default to &#39;all&#39;] |
| **domainName** | **string**|  | [optional] |
| **ipAddress** | **string**| Use for PTR lookups | [optional] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\DnsResponse**](../Model/DnsResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dnsReverse()`

```php
dnsReverse($value, $type, $exact, $page, $format): \WhoisFreaks\Model\ReverseDnsResponse
```

Reverse DNS Lookup

Search domains by IP or DNS value. 5 credits per page.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DNSApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$value = 'value_example'; // string | IP, CIDR, or record value
$type = 'type_example'; // string
$exact = true; // bool
$page = 1; // int
$format = 'json'; // string

try {
    $result = $apiInstance->dnsReverse($value, $type, $exact, $page, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DNSApi->dnsReverse: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **value** | **string**| IP, CIDR, or record value | |
| **type** | **string**|  | |
| **exact** | **bool**|  | [optional] [default to true] |
| **page** | **int**|  | [optional] [default to 1] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\ReverseDnsResponse**](../Model/ReverseDnsResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

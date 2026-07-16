# WhoisFreaks\WHOISApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkWhois()**](WHOISApi.md#bulkWhois) | **POST** /v2.0/bulkwhois/live | Bulk WHOIS Lookup |
| [**whoisHistory()**](WHOISApi.md#whoisHistory) | **GET** /v2.0/whois/history | Historical WHOIS records for a domain |
| [**whoisLive()**](WHOISApi.md#whoisLive) | **GET** /v2.0/whois/live | Live WHOIS Lookup |
| [**whoisReverse()**](WHOISApi.md#whoisReverse) | **GET** /v2.0/whois/reverse | Reverse WHOIS lookup by keyword |


## `bulkWhois()`

```php
bulkWhois($bulkWhoisRequest, $format): \WhoisFreaks\Model\BulkWhoisResponse
```

Bulk WHOIS Lookup

Up to 100 domains in one request. 1 credit per successful domain.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$bulkWhoisRequest = new \WhoisFreaks\Model\BulkWhoisRequest(); // \WhoisFreaks\Model\BulkWhoisRequest
$format = 'json'; // string

try {
    $result = $apiInstance->bulkWhois($bulkWhoisRequest, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->bulkWhois: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **bulkWhoisRequest** | [**\WhoisFreaks\Model\BulkWhoisRequest**](../Model/BulkWhoisRequest.md)|  | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\BulkWhoisResponse**](../Model/BulkWhoisResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `whoisHistory()`

```php
whoisHistory($domainName, $page, $format): \WhoisFreaks\Model\WhoisHistoricalResponse
```

Historical WHOIS records for a domain

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$domainName = 'domainName_example'; // string | Domain to fetch historical WHOIS records for
$page = 56; // int | Page number
$format = 'format_example'; // string

try {
    $result = $apiInstance->whoisHistory($domainName, $page, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->whoisHistory: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domainName** | **string**| Domain to fetch historical WHOIS records for | |
| **page** | **int**| Page number | [optional] |
| **format** | **string**|  | [optional] |

### Return type

[**\WhoisFreaks\Model\WhoisHistoricalResponse**](../Model/WhoisHistoricalResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `whoisLive()`

```php
whoisLive($domainName, $format): \WhoisFreaks\Model\WhoisResponse
```

Live WHOIS Lookup

Real-time WHOIS lookup from authoritative servers. Cost 1 credit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$domainName = whoisfreaks.com; // string
$format = 'json'; // string

try {
    $result = $apiInstance->whoisLive($domainName, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->whoisLive: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domainName** | **string**|  | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\WhoisResponse**](../Model/WhoisResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `whoisReverse()`

```php
whoisReverse($keyword, $page, $format): \WhoisFreaks\Model\ReverseWhoisResponse
```

Reverse WHOIS lookup by keyword

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$keyword = 'keyword_example'; // string | Keyword to search across WHOIS records
$page = 56; // int | Page number
$format = 'format_example'; // string

try {
    $result = $apiInstance->whoisReverse($keyword, $page, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->whoisReverse: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **keyword** | **string**| Keyword to search across WHOIS records | |
| **page** | **int**| Page number | [optional] |
| **format** | **string**|  | [optional] |

### Return type

[**\WhoisFreaks\Model\ReverseWhoisResponse**](../Model/ReverseWhoisResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

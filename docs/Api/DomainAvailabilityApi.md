# WhoisFreaks\DomainAvailabilityApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkDomainAvailabilityV2()**](DomainAvailabilityApi.md#bulkDomainAvailabilityV2) | **POST** /v2.0/domain/availability | Bulk Domain Availability Check |
| [**domainAvailabilityV2()**](DomainAvailabilityApi.md#domainAvailabilityV2) | **GET** /v2.0/domain/availability | Domain Availability Check with Suggestions |


## `bulkDomainAvailabilityV2()`

```php
bulkDomainAvailabilityV2($apiKey, $bulkDomainAvailabilityRequest, $domain, $format): \WhoisFreaks\Model\BulkDomainAvailabilityResponse
```

Bulk Domain Availability Check

Two bulk modes. Mode 1: POST domainNames array. Mode 2: POST tld array plus domain query param. Max 100 domains per request. 1 credit per domain checked.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DomainAvailabilityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$bulkDomainAvailabilityRequest = new \WhoisFreaks\Model\BulkDomainAvailabilityRequest(); // \WhoisFreaks\Model\BulkDomainAvailabilityRequest
$domain = google.com; // string | Required for TLD-mode bulk check (base domain).
$format = 'json'; // string

try {
    $result = $apiInstance->bulkDomainAvailabilityV2($apiKey, $bulkDomainAvailabilityRequest, $domain, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DomainAvailabilityApi->bulkDomainAvailabilityV2: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **bulkDomainAvailabilityRequest** | [**\WhoisFreaks\Model\BulkDomainAvailabilityRequest**](../Model/BulkDomainAvailabilityRequest.md)|  | |
| **domain** | **string**| Required for TLD-mode bulk check (base domain). | [optional] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\BulkDomainAvailabilityResponse**](../Model/BulkDomainAvailabilityResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `domainAvailabilityV2()`

```php
domainAvailabilityV2($apiKey, $domain, $sug, $count, $format): \WhoisFreaks\Model\DomainAvailabilityResponse
```

Domain Availability Check with Suggestions

Check availability of a single domain and optionally get suggestions across multiple TLDs. 1 credit per domain checked. sug=false checks only the queried domain; sug=true returns up to `count` (max 100) TLD suggestions.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DomainAvailabilityApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$domain = google.com; // string | The domain name to check
$sug = false; // bool | Whether to return TLD suggestions alongside the queried domain.
$count = 5; // int | Number of TLD suggestions to return when sug=true. Maximum is 100.
$format = 'json'; // string

try {
    $result = $apiInstance->domainAvailabilityV2($apiKey, $domain, $sug, $count, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DomainAvailabilityApi->domainAvailabilityV2: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **domain** | **string**| The domain name to check | |
| **sug** | **bool**| Whether to return TLD suggestions alongside the queried domain. | [optional] [default to false] |
| **count** | **int**| Number of TLD suggestions to return when sug&#x3D;true. Maximum is 100. | [optional] [default to 5] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\DomainAvailabilityResponse**](../Model/DomainAvailabilityResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

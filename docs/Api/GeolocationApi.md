# WhoisFreaks\GeolocationApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkGeolocation()**](GeolocationApi.md#bulkGeolocation) | **POST** /v1.0/geolocation | Bulk IP Geolocation |
| [**geolocation()**](GeolocationApi.md#geolocation) | **GET** /v1.0/geolocation | IP Geolocation Lookup |


## `bulkGeolocation()`

```php
bulkGeolocation($apiKey, $bulkGeolocationRequest): \WhoisFreaks\Model\GeolocationResponse[]
```

Bulk IP Geolocation

Up to 100 IPs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\GeolocationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$bulkGeolocationRequest = new \WhoisFreaks\Model\BulkGeolocationRequest(); // \WhoisFreaks\Model\BulkGeolocationRequest

try {
    $result = $apiInstance->bulkGeolocation($apiKey, $bulkGeolocationRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GeolocationApi->bulkGeolocation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **bulkGeolocationRequest** | [**\WhoisFreaks\Model\BulkGeolocationRequest**](../Model/BulkGeolocationRequest.md)|  | |

### Return type

[**\WhoisFreaks\Model\GeolocationResponse[]**](../Model/GeolocationResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `geolocation()`

```php
geolocation($apiKey, $ip): \WhoisFreaks\Model\GeolocationResponse
```

IP Geolocation Lookup

Get location, ASN, currency for an IP. 1 credit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\GeolocationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$ip = 'ip_example'; // string

try {
    $result = $apiInstance->geolocation($apiKey, $ip);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling GeolocationApi->geolocation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **ip** | **string**|  | |

### Return type

[**\WhoisFreaks\Model\GeolocationResponse**](../Model/GeolocationResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

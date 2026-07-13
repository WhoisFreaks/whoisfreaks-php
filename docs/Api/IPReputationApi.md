# WhoisFreaks\IPReputationApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkIpReputation()**](IPReputationApi.md#bulkIpReputation) | **POST** /v1.0/security | Bulk IP Reputation |
| [**ipReputation()**](IPReputationApi.md#ipReputation) | **GET** /v1.0/security | IP Reputation Lookup |


## `bulkIpReputation()`

```php
bulkIpReputation($apiKey, $bulkGeolocationRequest): \WhoisFreaks\Model\IpReputationResponse[]
```

Bulk IP Reputation

Up to 100 IPs.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\IPReputationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$bulkGeolocationRequest = new \WhoisFreaks\Model\BulkGeolocationRequest(); // \WhoisFreaks\Model\BulkGeolocationRequest

try {
    $result = $apiInstance->bulkIpReputation($apiKey, $bulkGeolocationRequest);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling IPReputationApi->bulkIpReputation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **bulkGeolocationRequest** | [**\WhoisFreaks\Model\BulkGeolocationRequest**](../Model/BulkGeolocationRequest.md)|  | |

### Return type

[**\WhoisFreaks\Model\IpReputationResponse[]**](../Model/IpReputationResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `ipReputation()`

```php
ipReputation($apiKey, $ip): \WhoisFreaks\Model\IpReputationResponse
```

IP Reputation Lookup

Threat intel for IP — VPN, proxy, Tor, bots. 1 credit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\IPReputationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$ip = 'ip_example'; // string

try {
    $result = $apiInstance->ipReputation($apiKey, $ip);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling IPReputationApi->ipReputation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **ip** | **string**|  | |

### Return type

[**\WhoisFreaks\Model\IpReputationResponse**](../Model/IpReputationResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

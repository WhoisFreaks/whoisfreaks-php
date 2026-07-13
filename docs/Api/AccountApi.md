# WhoisFreaks\AccountApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**accountUsage()**](AccountApi.md#accountUsage) | **GET** /v1.0/whoisapi/usage | Account Usage |
| [**databaseFileStatus()**](AccountApi.md#databaseFileStatus) | **GET** /v3.3/status | Database File Status (Public) |
| [**rotateApiKey()**](AccountApi.md#rotateApiKey) | **GET** /v1.0/api-key/rotate | Rotate API Key |


## `accountUsage()`

```php
accountUsage($apiKey): \WhoisFreaks\Model\AccountUsageResponse
```

Account Usage

Account Usage. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key

try {
    $result = $apiInstance->accountUsage($apiKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->accountUsage: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |

### Return type

[**\WhoisFreaks\Model\AccountUsageResponse**](../Model/AccountUsageResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `databaseFileStatus()`

```php
databaseFileStatus(): \WhoisFreaks\Model\DatabaseFileStatus
```
### URI(s):
- https://files.whoisfreaks.com 
Database File Status (Public)

No API key required. Returns freshness of all downloadable files.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');



$apiInstance = new WhoisFreaks\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client()
);

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->databaseFileStatus($hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->databaseFileStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

[**\WhoisFreaks\Model\DatabaseFileStatus**](../Model/DatabaseFileStatus.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `rotateApiKey()`

```php
rotateApiKey($apiKey): string
```

Rotate API Key

Rotate API Key. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\AccountApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key

try {
    $result = $apiInstance->rotateApiKey($apiKey);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling AccountApi->rotateApiKey: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |

### Return type

**string**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `text/plain`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

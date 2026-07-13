# WhoisFreaks\DatabasesIPGeolocationApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**dbIpCity()**](DatabasesIPGeolocationApi.md#dbIpCity) | **GET** /v3.3/download/snapshot/ip/city | IP to City Snapshot |
| [**dbIpCityStatus()**](DatabasesIPGeolocationApi.md#dbIpCityStatus) | **GET** /v3.3/status/snapshot/ip/city | IP to City Snapshot Status |
| [**dbIpCountry()**](DatabasesIPGeolocationApi.md#dbIpCountry) | **GET** /v3.3/download/snapshot/ip/country | IP to Country Snapshot |
| [**dbIpCountryStatus()**](DatabasesIPGeolocationApi.md#dbIpCountryStatus) | **GET** /v3.3/status/snapshot/ip/country | IP to Country Snapshot Status |


## `dbIpCity()`

```php
dbIpCity($apiKey, $date): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
IP to City Snapshot

IP to City Snapshot. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesIPGeolocationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbIpCity($apiKey, $date, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesIPGeolocationApi->dbIpCity: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **date** | **\DateTime**|  | |
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dbIpCityStatus()`

```php
dbIpCityStatus($apiKey): \WhoisFreaks\Model\SnapshotStatus
```
### URI(s):
- https://files.whoisfreaks.com 
IP to City Snapshot Status

IP to City Snapshot Status. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesIPGeolocationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbIpCityStatus($apiKey, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesIPGeolocationApi->dbIpCityStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

[**\WhoisFreaks\Model\SnapshotStatus**](../Model/SnapshotStatus.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dbIpCountry()`

```php
dbIpCountry($apiKey, $date): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
IP to Country Snapshot

IP to Country Snapshot. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesIPGeolocationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbIpCountry($apiKey, $date, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesIPGeolocationApi->dbIpCountry: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **date** | **\DateTime**|  | |
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`, `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dbIpCountryStatus()`

```php
dbIpCountryStatus($apiKey): \WhoisFreaks\Model\SnapshotStatus
```
### URI(s):
- https://files.whoisfreaks.com 
IP to Country Snapshot Status

IP to Country Snapshot Status. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesIPGeolocationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbIpCountryStatus($apiKey, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesIPGeolocationApi->dbIpCountryStatus: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

[**\WhoisFreaks\Model\SnapshotStatus**](../Model/SnapshotStatus.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

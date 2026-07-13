# WhoisFreaks\DatabasesASNWHOISApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**dbAsnWhois()**](DatabasesASNWHOISApi.md#dbAsnWhois) | **GET** /v3.3/download/snapshot/asn/whois | ASN WHOIS Snapshot |
| [**dbAsnWhoisStatus()**](DatabasesASNWHOISApi.md#dbAsnWhoisStatus) | **GET** /v3.3/status/snapshot/asn/whois | ASN WHOIS Snapshot Status |


## `dbAsnWhois()`

```php
dbAsnWhois($apiKey, $date): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
ASN WHOIS Snapshot

ASN WHOIS Snapshot. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesASNWHOISApi(
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
    $result = $apiInstance->dbAsnWhois($apiKey, $date, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesASNWHOISApi->dbAsnWhois: ', $e->getMessage(), PHP_EOL;
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

## `dbAsnWhoisStatus()`

```php
dbAsnWhoisStatus($apiKey): \WhoisFreaks\Model\SnapshotStatus
```
### URI(s):
- https://files.whoisfreaks.com 
ASN WHOIS Snapshot Status

ASN WHOIS Snapshot Status. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesASNWHOISApi(
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
    $result = $apiInstance->dbAsnWhoisStatus($apiKey, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesASNWHOISApi->dbAsnWhoisStatus: ', $e->getMessage(), PHP_EOL;
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

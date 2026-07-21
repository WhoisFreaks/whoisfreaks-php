# WhoisFreaks\DatabasesThreatFeedApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**downloadThreatFeedMalware()**](DatabasesThreatFeedApi.md#downloadThreatFeedMalware) | **GET** /v3.4/download/threat-feed/malware | Download the daily malware threat feed (CSV) |
| [**downloadThreatFeedMalwareSample()**](DatabasesThreatFeedApi.md#downloadThreatFeedMalwareSample) | **GET** /v3.4/download/threat-feed/malware/sample | Download a sample of the malware threat feed (CSV) |
| [**downloadThreatFeedPhishing()**](DatabasesThreatFeedApi.md#downloadThreatFeedPhishing) | **GET** /v3.4/download/threat-feed/phishing | Download the daily phishing threat feed (CSV) |
| [**downloadThreatFeedPhishingSample()**](DatabasesThreatFeedApi.md#downloadThreatFeedPhishingSample) | **GET** /v3.4/download/threat-feed/phishing/sample | Download a sample of the phishing threat feed (CSV) |
| [**downloadThreatFeedSpam()**](DatabasesThreatFeedApi.md#downloadThreatFeedSpam) | **GET** /v3.4/download/threat-feed/spam | Download the daily spam threat feed (CSV) |
| [**downloadThreatFeedSpamSample()**](DatabasesThreatFeedApi.md#downloadThreatFeedSpamSample) | **GET** /v3.4/download/threat-feed/spam/sample | Download a sample of the spam threat feed (CSV) |


## `downloadThreatFeedMalware()`

```php
downloadThreatFeedMalware($date): \SplFileObject
```

Download the daily malware threat feed (CSV)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesThreatFeedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = 'date_example'; // string | Feed date (yyyy-MM-dd); defaults to latest available

try {
    $result = $apiInstance->downloadThreatFeedMalware($date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesThreatFeedApi->downloadThreatFeedMalware: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **string**| Feed date (yyyy-MM-dd); defaults to latest available | [optional] |

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadThreatFeedMalwareSample()`

```php
downloadThreatFeedMalwareSample(): \SplFileObject
```

Download a sample of the malware threat feed (CSV)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesThreatFeedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->downloadThreatFeedMalwareSample();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesThreatFeedApi->downloadThreatFeedMalwareSample: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadThreatFeedPhishing()`

```php
downloadThreatFeedPhishing($date): \SplFileObject
```

Download the daily phishing threat feed (CSV)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesThreatFeedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = 'date_example'; // string | Feed date (yyyy-MM-dd); defaults to latest available

try {
    $result = $apiInstance->downloadThreatFeedPhishing($date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesThreatFeedApi->downloadThreatFeedPhishing: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **string**| Feed date (yyyy-MM-dd); defaults to latest available | [optional] |

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadThreatFeedPhishingSample()`

```php
downloadThreatFeedPhishingSample(): \SplFileObject
```

Download a sample of the phishing threat feed (CSV)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesThreatFeedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->downloadThreatFeedPhishingSample();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesThreatFeedApi->downloadThreatFeedPhishingSample: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadThreatFeedSpam()`

```php
downloadThreatFeedSpam($date): \SplFileObject
```

Download the daily spam threat feed (CSV)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesThreatFeedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = 'date_example'; // string | Feed date (yyyy-MM-dd); defaults to latest available

try {
    $result = $apiInstance->downloadThreatFeedSpam($date);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesThreatFeedApi->downloadThreatFeedSpam: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **string**| Feed date (yyyy-MM-dd); defaults to latest available | [optional] |

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `downloadThreatFeedSpamSample()`

```php
downloadThreatFeedSpamSample(): \SplFileObject
```

Download a sample of the spam threat feed (CSV)

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesThreatFeedApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);

try {
    $result = $apiInstance->downloadThreatFeedSpamSample();
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesThreatFeedApi->downloadThreatFeedSpamSample: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

This endpoint does not need any parameter.

### Return type

**\SplFileObject**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/octet-stream`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

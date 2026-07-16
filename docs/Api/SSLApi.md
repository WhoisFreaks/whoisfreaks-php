# WhoisFreaks\SSLApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**sslLookup()**](SSLApi.md#sslLookup) | **GET** /v1.0/ssl/live | SSL Certificate Lookup |


## `sslLookup()`

```php
sslLookup($domainName, $chain, $sslRaw, $format): \WhoisFreaks\Model\SslResponse
```

SSL Certificate Lookup

Real-time SSL cert with optional chain.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\SSLApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$domainName = 'domainName_example'; // string
$chain = false; // bool
$sslRaw = false; // bool
$format = 'json'; // string

try {
    $result = $apiInstance->sslLookup($domainName, $chain, $sslRaw, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SSLApi->sslLookup: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domainName** | **string**|  | |
| **chain** | **bool**|  | [optional] [default to false] |
| **sslRaw** | **bool**|  | [optional] [default to false] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\SslResponse**](../Model/SslResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

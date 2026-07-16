# WhoisFreaks\TyposquattingApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**typosquatting()**](TyposquattingApi.md#typosquatting) | **GET** /v3.0/domain/typos | Typosquatting Lookup |


## `typosquatting()`

```php
typosquatting($keyword, $pattern, $pageToken): \WhoisFreaks\Model\TyposquattingResponse
```

Typosquatting Lookup

Find typo variants of a brand. 5 credits per page.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\TyposquattingApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$keyword = 'keyword_example'; // string
$pattern = 'pattern_example'; // string
$pageToken = 'pageToken_example'; // string

try {
    $result = $apiInstance->typosquatting($keyword, $pattern, $pageToken);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling TyposquattingApi->typosquatting: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **keyword** | **string**|  | [optional] |
| **pattern** | **string**|  | [optional] |
| **pageToken** | **string**|  | [optional] |

### Return type

[**\WhoisFreaks\Model\TyposquattingResponse**](../Model/TyposquattingResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

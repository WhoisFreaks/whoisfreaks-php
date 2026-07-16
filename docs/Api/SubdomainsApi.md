# WhoisFreaks\SubdomainsApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**subdomains()**](SubdomainsApi.md#subdomains) | **GET** /v1.0/subdomains | Subdomains Lookup |


## `subdomains()`

```php
subdomains($domain, $after, $before, $status, $page, $format): \WhoisFreaks\Model\SubdomainsResponse
```

Subdomains Lookup

All subdomains including nested. 2 credits per query.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\SubdomainsApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$domain = 'domain_example'; // string
$after = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$before = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime
$status = 'status_example'; // string
$page = 1; // int
$format = 'json'; // string

try {
    $result = $apiInstance->subdomains($domain, $after, $before, $status, $page, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling SubdomainsApi->subdomains: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **domain** | **string**|  | |
| **after** | **\DateTime**|  | [optional] |
| **before** | **\DateTime**|  | [optional] |
| **status** | **string**|  | [optional] |
| **page** | **int**|  | [optional] [default to 1] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\SubdomainsResponse**](../Model/SubdomainsResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

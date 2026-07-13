# WhoisFreaks\DomainReputationApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**domainReputation()**](DomainReputationApi.md#domainReputation) | **GET** /v1/domain/security | Domain Reputation Lookup |


## `domainReputation()`

```php
domainReputation($apiKey, $domainName, $format): \WhoisFreaks\Model\DomainReputationResponse
```

Domain Reputation Lookup

Real-time domain threat assessment. Returns risk verdict, trust score, DGA analysis, threat intelligence matches, and security signals. 1 credit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DomainReputationApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$domainName = amazon.com; // string | The domain name to assess
$format = 'json'; // string

try {
    $result = $apiInstance->domainReputation($apiKey, $domainName, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DomainReputationApi->domainReputation: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **domainName** | **string**| The domain name to assess | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\DomainReputationResponse**](../Model/DomainReputationResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

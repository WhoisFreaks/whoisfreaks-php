# WhoisFreaks\ASNWHOISApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**asnWhois()**](ASNWHOISApi.md#asnWhois) | **GET** /v2.0/asn-whois | ASN WHOIS Lookup |


## `asnWhois()`

```php
asnWhois($apiKey, $asn, $format): \WhoisFreaks\Model\AsnWhoisResponse
```

ASN WHOIS Lookup

WHOIS for an ASN. 1 credit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\ASNWHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$asn = as15169; // string
$format = 'json'; // string

try {
    $result = $apiInstance->asnWhois($apiKey, $asn, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling ASNWHOISApi->asnWhois: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **asn** | **string**|  | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\AsnWhoisResponse**](../Model/AsnWhoisResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

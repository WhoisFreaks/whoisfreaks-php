# WhoisFreaks\WHOISApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**bulkWhois()**](WHOISApi.md#bulkWhois) | **POST** /v2.0/bulkwhois/live | Bulk WHOIS Lookup |
| [**whoisHistoricalOrReverse()**](WHOISApi.md#whoisHistoricalOrReverse) | **GET** /v1.0/whois | WHOIS Historical or Reverse Lookup |
| [**whoisLive()**](WHOISApi.md#whoisLive) | **GET** /v2.0/whois/live | Live WHOIS Lookup |


## `bulkWhois()`

```php
bulkWhois($apiKey, $bulkWhoisRequest, $format): \WhoisFreaks\Model\BulkWhoisResponse
```

Bulk WHOIS Lookup

Up to 100 domains in one request. 1 credit per successful domain.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$bulkWhoisRequest = new \WhoisFreaks\Model\BulkWhoisRequest(); // \WhoisFreaks\Model\BulkWhoisRequest
$format = 'json'; // string

try {
    $result = $apiInstance->bulkWhois($apiKey, $bulkWhoisRequest, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->bulkWhois: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **bulkWhoisRequest** | [**\WhoisFreaks\Model\BulkWhoisRequest**](../Model/BulkWhoisRequest.md)|  | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\BulkWhoisResponse**](../Model/BulkWhoisResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: `application/json`
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `whoisHistoricalOrReverse()`

```php
whoisHistoricalOrReverse($apiKey, $whois, $domainName, $keyword, $email, $owner, $company, $mode, $exact, $page, $format): \WhoisFreaks\Model\WhoisHistoricalResponse
```

WHOIS Historical or Reverse Lookup

Historical WHOIS (all records since 1986) or Reverse WHOIS (search by keyword/email/owner/company). Historical: 2 credits/page (100 records). Reverse: 5 credits/page.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$whois = 'whois_example'; // string
$domainName = 'domainName_example'; // string | Required for historical lookup
$keyword = 'keyword_example'; // string | For reverse — domain keyword search
$email = 'email_example'; // string | For reverse — registrant email search
$owner = 'owner_example'; // string | For reverse — registrant name search
$company = 'company_example'; // string | For reverse — company name search
$mode = 'default'; // string
$exact = true; // bool
$page = 1; // int
$format = 'json'; // string

try {
    $result = $apiInstance->whoisHistoricalOrReverse($apiKey, $whois, $domainName, $keyword, $email, $owner, $company, $mode, $exact, $page, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->whoisHistoricalOrReverse: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **whois** | **string**|  | |
| **domainName** | **string**| Required for historical lookup | [optional] |
| **keyword** | **string**| For reverse — domain keyword search | [optional] |
| **email** | **string**| For reverse — registrant email search | [optional] |
| **owner** | **string**| For reverse — registrant name search | [optional] |
| **company** | **string**| For reverse — company name search | [optional] |
| **mode** | **string**|  | [optional] [default to &#39;default&#39;] |
| **exact** | **bool**|  | [optional] [default to true] |
| **page** | **int**|  | [optional] [default to 1] |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\WhoisHistoricalResponse**](../Model/WhoisHistoricalResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `whoisLive()`

```php
whoisLive($apiKey, $domainName, $format): \WhoisFreaks\Model\WhoisResponse
```

Live WHOIS Lookup

Real-time WHOIS lookup from authoritative servers. Cost 1 credit.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\WHOISApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$apiKey = 'apiKey_example'; // string | Your WHOISFreaks API key
$domainName = whoisfreaks.com; // string
$format = 'json'; // string

try {
    $result = $apiInstance->whoisLive($apiKey, $domainName, $format);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling WHOISApi->whoisLive: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **apiKey** | **string**| Your WHOISFreaks API key | |
| **domainName** | **string**|  | |
| **format** | **string**|  | [optional] [default to &#39;json&#39;] |

### Return type

[**\WhoisFreaks\Model\WhoisResponse**](../Model/WhoisResponse.md)

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

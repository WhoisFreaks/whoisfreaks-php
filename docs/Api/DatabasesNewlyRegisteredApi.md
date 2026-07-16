# WhoisFreaks\DatabasesNewlyRegisteredApi

All URIs are relative to https://api.whoisfreaks.com, except if the operation defines another base path.

| Method | HTTP request | Description |
| ------------- | ------------- | ------------- |
| [**dbNewlyCctld()**](DatabasesNewlyRegisteredApi.md#dbNewlyCctld) | **GET** /v3.1/download/domainer/cctld | Newly Registered ccTLD (CSV) |
| [**dbNewlyCctldCleaned()**](DatabasesNewlyRegisteredApi.md#dbNewlyCctldCleaned) | **GET** /v3.1/download/domainer/cctld/cleaned | Newly Registered ccTLD Cleaned WHOIS (CSV) |
| [**dbNewlyCctldJson()**](DatabasesNewlyRegisteredApi.md#dbNewlyCctldJson) | **GET** /v3.1/domains/newly/cctld | Newly Registered ccTLD (JSON) |
| [**dbNewlyDns()**](DatabasesNewlyRegisteredApi.md#dbNewlyDns) | **GET** /v3.1/download/domainer/newly/dns | Newly Registered With DNS |
| [**dbNewlyGtld()**](DatabasesNewlyRegisteredApi.md#dbNewlyGtld) | **GET** /v3.1/download/domainer/gtld | Newly Registered gTLD (CSV) |
| [**dbNewlyGtldCleaned()**](DatabasesNewlyRegisteredApi.md#dbNewlyGtldCleaned) | **GET** /v3.1/download/domainer/gtld/cleaned | Newly Registered gTLD Cleaned WHOIS (CSV) |
| [**dbNewlyGtldJson()**](DatabasesNewlyRegisteredApi.md#dbNewlyGtldJson) | **GET** /v3.1/domains/newly/gtld | Newly Registered gTLD (JSON) |


## `dbNewlyCctld()`

```php
dbNewlyCctld($whois, $date, $tlds): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered ccTLD (CSV)

Newly Registered ccTLD (CSV). Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$whois = True; // bool
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest
$tlds = 'tlds_example'; // string

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyCctld($whois, $date, $tlds, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyCctld: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **whois** | **bool**|  | |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
| **tlds** | **string**|  | [optional] |
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

## `dbNewlyCctldCleaned()`

```php
dbNewlyCctldCleaned($date): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered ccTLD Cleaned WHOIS (CSV)

Newly Registered ccTLD Cleaned WHOIS (CSV). Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyCctldCleaned($date, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyCctldCleaned: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
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

## `dbNewlyCctldJson()`

```php
dbNewlyCctldJson($date, $tlds): string[]
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered ccTLD (JSON)

Newly Registered ccTLD (JSON). Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest
$tlds = 'tlds_example'; // string

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyCctldJson($date, $tlds, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyCctldJson: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
| **tlds** | **string**|  | [optional] |
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

**string[]**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

## `dbNewlyDns()`

```php
dbNewlyDns($date): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered With DNS

Newly Registered With DNS. Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyDns($date, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyDns: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
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

## `dbNewlyGtld()`

```php
dbNewlyGtld($whois, $date, $tlds): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered gTLD (CSV)

Newly Registered gTLD (CSV). Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$whois = True; // bool
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest
$tlds = 'tlds_example'; // string

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyGtld($whois, $date, $tlds, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyGtld: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **whois** | **bool**|  | |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
| **tlds** | **string**|  | [optional] |
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

## `dbNewlyGtldCleaned()`

```php
dbNewlyGtldCleaned($date): \SplFileObject
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered gTLD Cleaned WHOIS (CSV)

Newly Registered gTLD Cleaned WHOIS (CSV). Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyGtldCleaned($date, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyGtldCleaned: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
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

## `dbNewlyGtldJson()`

```php
dbNewlyGtldJson($date, $tlds): string[]
```
### URI(s):
- https://files.whoisfreaks.com 
Newly Registered gTLD (JSON)

Newly Registered gTLD (JSON). Returns the file/snapshot described by this operation.

### Example

```php
<?php
require_once(__DIR__ . '/vendor/autoload.php');


// Configure API key authorization: ApiKeyAuth
$config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKey('apiKey', 'YOUR_API_KEY');
// Uncomment below to setup prefix (e.g. Bearer) for API key, if needed
// $config = WhoisFreaks\Configuration::getDefaultConfiguration()->setApiKeyPrefix('apiKey', 'Bearer');


$apiInstance = new WhoisFreaks\Api\DatabasesNewlyRegisteredApi(
    // If you want use custom http client, pass your client which implements `GuzzleHttp\ClientInterface`.
    // This is optional, `GuzzleHttp\Client` will be used as default.
    new GuzzleHttp\Client(),
    $config
);
$date = new \DateTime('2013-10-20T19:20:30+01:00'); // \DateTime | yyyy-MM-dd; omit for latest
$tlds = 'tlds_example'; // string

$hostIndex = 0;
$variables = [
];

try {
    $result = $apiInstance->dbNewlyGtldJson($date, $tlds, $hostIndex, $variables);
    print_r($result);
} catch (Exception $e) {
    echo 'Exception when calling DatabasesNewlyRegisteredApi->dbNewlyGtldJson: ', $e->getMessage(), PHP_EOL;
}
```

### Parameters

| Name | Type | Description  | Notes |
| ------------- | ------------- | ------------- | ------------- |
| **date** | **\DateTime**| yyyy-MM-dd; omit for latest | [optional] |
| **tlds** | **string**|  | [optional] |
| hostIndex | null|int | Host index. Defaults to null. If null, then the library will use $this->hostIndex instead | [optional] |
| variables | array | Associative array of variables to pass to the host. Defaults to empty array. | [optional] |

### Return type

**string[]**

### Authorization

[ApiKeyAuth](../../README.md#ApiKeyAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: `application/json`

[[Back to top]](#) [[Back to API list]](../../README.md#endpoints)
[[Back to Model list]](../../README.md#models)
[[Back to README]](../../README.md)

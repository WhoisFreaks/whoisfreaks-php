# # DnsRecord

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**type** | **int** | Numeric DNS record type: 1 A, 2 NS, 5 CNAME, 6 SOA, 12 PTR, 15 MX, 16 TXT, 28 AAAA, 99 SPF. | [optional]
**dnsType** | **string** | Record type name, e.g. A, MX, TXT | [optional]
**name** | **string** |  | [optional]
**ttl** | **int** |  | [optional]
**rawText** | **string** | The record in zone-file format | [optional]
**rRsetType** | **int** |  | [optional]
**singleName** | **string** | Target host for NS, CNAME and PTR records | [optional]
**address** | **string** |  | [optional]
**priority** | **int** |  | [optional]
**exchange** | **string** |  | [optional]
**target** | **string** |  | [optional]
**strings** | **string[]** |  | [optional]
**host** | **string** |  | [optional]
**admin** | **string** |  | [optional]
**serial** | **int** | SOA serial; values above 2^31 are common, so it is 64-bit | [optional]
**refresh** | **int** |  | [optional]
**retry** | **int** |  | [optional]
**expire** | **int** |  | [optional]
**minimum** | **int** |  | [optional]

[[Back to Model list]](../../README.md#models) [[Back to API list]](../../README.md#endpoints) [[Back to README]](../../README.md)

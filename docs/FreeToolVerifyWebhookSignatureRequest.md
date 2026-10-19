# FreeToolVerifyWebhookSignatureRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**body** | **String** | The raw request body exactly as received (up to 64 KB). Use a test payload, not production data. | 
**secret** | **String** | The webhook secret. Use a test secret: never send a production secret to any third-party service. | 
**signature** | **String** | The received signature header value, e.g. X-Signature. | 
**algorithm** | Option<**String**> |  | [optional][default to Sha256]
**encoding** | Option<**String**> |  | [optional][default to Hex]
**prefix** | Option<**String**> | A prefix the sender puts before the signature, e.g. \"sha256=\" (GitHub). | [optional][default to ]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



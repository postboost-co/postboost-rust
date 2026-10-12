# CreateWebhookSubscription201ResponseData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**name** | **String** |  | 
**callback_url** | **String** |  | 
**events** | **Vec<String>** |  | 
**active** | **bool** |  | 
**created_at** | Option<**String**> |  | [optional]
**secret** | **String** | Signing secret for `X-Signature`. Returned once. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# WebhookSubscriptionInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**callback_url** | **String** | Public `https://` URL that receives the deliveries. | 
**events** | [**Vec<models::WebhookEventName>**](WebhookEventName.md) |  | 
**name** | Option<**String**> | Label shown in Settings → Webhooks. Defaults to \"<Source> trigger\". | [optional]
**source** | Option<**String**> | The tool creating the subscription. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



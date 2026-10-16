# WebhookEnvelope

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**event** | **String** |  | 
**id** | [**uuid::Uuid**](uuid::Uuid.md) | Delivery ID, one per event. Retries and manual resends repeat it. | 
**occurred_at** | **String** | When the event happened (ISO 8601, UTC). | 
**workspace_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | The workspace the event belongs to (null only on instance-wide system webhooks). Also sent as the `X-PostBoost-Workspace` header. | 
**data** | [**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md) | The post (`post.*`, as `getPost` returns it, plus `account` on per-account events), the account (`account.*`) or the reply draft (`inbox.*`). | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



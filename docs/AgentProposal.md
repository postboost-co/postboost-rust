# AgentProposal

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**run_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> |  | [optional]
**post_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> |  | [optional]
**account_id** | Option<**i32**> |  | [optional]
**kind** | **String** | `hold_post` moves the post back to draft; `edit_caption` replaces one caption. | 
**severity** | **String** |  | 
**reason** | **String** |  | 
**payload** | [**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md) | The proposed change. `hold_post`: `reasons[]` (`code`, `account_id`, `message`, `severity`) and `scheduled_at`. `edit_caption`: `version_account_id` (0 = original), `item_index`, `before`, `after`. Both carry `post_updated_at`.  | 
**status** | **String** |  | 
**decided_at** | Option<**String**> |  | [optional]
**applied_at** | Option<**String**> |  | [optional]
**note** | Option<**String**> |  | [optional]
**error** | Option<**String**> | Why a proposal went stale or failed. | [optional]
**created_at** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# InboxReplyDraft

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **String** | Draft UUID. | 
**status** | **String** |  | 
**body** | **String** |  | 
**source** | **String** |  | 
**conversation_id** | Option<**String**> |  | [optional]
**provider** | Option<**String**> |  | [optional]
**in_reply_to** | Option<[**serde_json::Value**](.md)> | The incoming message this replies to (same shape as `InboxMessage`). | [optional]
**created_by** | Option<**String**> | Name of the user whose API key wrote the draft. | [optional]
**reviewed_by** | Option<**String**> |  | [optional]
**reviewed_at** | Option<**String**> |  | [optional]
**sent_message_id** | Option<**String**> | The sent reply's message UUID, once sent. | [optional]
**error** | Option<**String**> | Why sending failed. | [optional]
**created_at** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



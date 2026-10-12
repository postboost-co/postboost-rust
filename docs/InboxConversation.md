# InboxConversation

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **String** | Conversation UUID. | 
**provider** | **String** |  | 
**r#type** | Option<**String**> |  | [optional]
**status** | **String** |  | 
**unread** | **bool** |  | 
**sentiment** | Option<**String**> |  | [optional]
**ai_label** | Option<**String**> |  | [optional]
**is_spam** | Option<**bool**> |  | [optional]
**is_hidden** | Option<**bool**> |  | [optional]
**provider_post_id** | Option<**String**> |  | [optional]
**account** | Option<[**models::InboxConversationAccount**](InboxConversation_account.md)> |  | [optional]
**author** | Option<[**models::InboxMessageAuthor**](InboxMessage_author.md)> |  | [optional]
**latest_message** | Option<[**serde_json::Value**](.md)> | Only in lists. | [optional]
**messages** | Option<[**Vec<models::InboxMessage>**](InboxMessage.md)> | Only on `GET inbox/conversations/{conversationId}`. | [optional]
**last_message_at** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



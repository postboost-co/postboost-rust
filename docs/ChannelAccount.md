# ChannelAccount

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**name** | **String** |  | 
**username** | Option<**String**> | Telegram public channel username; null for private channels, Discord and Slack. | [optional]
**image** | Option<**String**> |  | [optional]
**provider** | **String** |  | 
**data** | Option<[**serde_json::Value**](.md)> | Provider metadata (Telegram `chat_id`, Discord `channel_id`/`guild_id`, Slack `team_id`). | 
**authorized** | **bool** |  | 
**profile_url** | Option<**String**> |  | [optional]
**created_at** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



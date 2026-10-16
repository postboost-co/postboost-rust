# CreatePost201Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**status** | [**models::PostStatus**](PostStatus.md) |  | 
**publish_progress** | Option<[**models::PublishProgress**](PublishProgress.md)> | Only present while the post is publishing. | [optional]
**accounts** | [**Vec<models::Account>**](Account.md) |  | 
**versions** | [**Vec<models::PostVersion>**](PostVersion.md) |  | 
**tags** | [**Vec<models::Tag>**](Tag.md) |  | 
**scheduled_at** | Option<**String**> | `Y-m-d H:i:s` in UTC (not RFC 3339). | [optional]
**published_at** | Option<**String**> | `Y-m-d H:i:s` in UTC (not RFC 3339). | [optional]
**created_at** | **String** | `Y-m-d H:i:s` in UTC (not RFC 3339). | 
**trashed** | **bool** |  | 
**warnings** | Option<[**Vec<models::PostWarning>**](PostWarning.md)> | Present only when there is at least one warning. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



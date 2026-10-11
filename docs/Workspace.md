# Workspace

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**name** | **String** |  | 
**hex_color** | Option<**String**> | Deprecated. Workspaces no longer have a colour (workspaces now use `avatar`); the API returns the constant `4f46e5` so existing clients keep working. Will be removed in API v2. | [optional]
**avatar** | Option<**String**> | URL of the workspace avatar, or null when none is set. Supersedes `hex_color`. | [optional]
**owner** | Option<[**models::User**](User.md)> |  | [optional]
**access_status** | **String** |  | 
**created_at** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



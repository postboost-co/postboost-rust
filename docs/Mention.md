# Mention

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**reference** | **i32** | Write `{{mention:<reference>}}` in a post body to mention this entry; it is resolved to each network's identity at publish time. | 
**name** | **String** |  | 
**avatar** | Option<**String**> |  | [optional]
**identities** | Option<[**Vec<models::MentionIdentity>**](MentionIdentity.md)> |  | [optional]
**created_at** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



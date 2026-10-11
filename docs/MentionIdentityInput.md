# MentionIdentityInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**provider** | **String** | Mention provider key. One identity per provider. | 
**handle** | **String** | Profile handle; a leading `@` is stripped. | 
**label** | Option<**String**> |  | [optional]
**token** | Option<**String**> | Sealed lookup result that names the profile's network ID. | [optional]
**account_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | A connected account of this workspace that names the profile. Wins over `token` when both are sent. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



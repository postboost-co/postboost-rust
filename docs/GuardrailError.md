# GuardrailError

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**message** | **String** |  | 
**code** | Option<**String**> |  | [optional]
**account_id** | Option<**i32**> | The account the problem is about. | [optional]
**existing_post_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | `duplicate_post` only: the earlier post with the same content. | [optional]
**limit** | Option<**i32**> | `account_daily_cap_reached` only: the account's daily cap. | [optional]
**used** | Option<**i32**> | `account_daily_cap_reached` only: posts already counted on that UTC day. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



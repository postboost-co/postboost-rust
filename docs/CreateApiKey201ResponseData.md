# CreateApiKey201ResponseData

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**name** | **String** |  | 
**abilities** | [**Vec<models::ApiKeyAbility>**](ApiKeyAbility.md) |  | 
**account_ids** | Option<**Vec<i32>**> |  | [optional]
**created_by** | Option<**String**> | Name of the user the key acts as. | [optional]
**last_used_at** | Option<**String**> |  | [optional]
**expires_at** | Option<[**String**](string.md)> |  | [optional]
**created_at** | Option<**String**> |  | [optional]
**token** | **String** | The plain API key. Shown only in this response. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



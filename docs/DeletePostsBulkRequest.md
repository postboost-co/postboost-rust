# DeletePostsBulkRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**posts** | [**Vec<uuid::Uuid>**](uuid::Uuid.md) | Array of post UUIDs to delete. | 
**trash** | Option<**bool**> | Move to trash instead of permanent delete. | [optional][default to false]
**delete_mode** | Option<[**models::DeleteMode**](DeleteMode.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# RssFeed

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**url** | **String** |  | 
**name** | Option<**String**> |  | 
**account_ids** | **Vec<i32>** |  | 
**mode** | **String** |  | 
**template** | **String** |  | 
**max_items_per_run** | **i32** |  | 
**active** | **bool** |  | 
**last_polled_at** | Option<**String**> |  | 
**last_error** | Option<**String**> | Error of the last check; after 5 failures in a row the feed is checked every 6 hours. | 
**created_at** | Option<**String**> |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



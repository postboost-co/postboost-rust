# PostingSchedule

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **i32** | The account asked for; 0 for the workspace schedule. | 
**source_account_id** | **i32** | Whose schedule applies; 0 when the workspace schedule applies. | 
**inherited** | **bool** | True when the account follows the workspace schedule. | 
**timezone** | Option<**String**> |  | 
**auto_tune** | **bool** | Adjust times automatically from engagement data. | 
**times** | [**Vec<models::PostingScheduleDay>**](PostingScheduleDay.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



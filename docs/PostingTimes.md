# PostingTimes

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**has_data** | **bool** |  | 
**timezone** | **String** |  | 
**offset_hours** | **i32** |  | 
**accounts** | **i32** | Accounts that contributed scores. | 
**samples** | **i32** |  | 
**days** | [**Vec<models::PostingTimesDaysInner>**](PostingTimes_days_inner.md) | One entry per weekday (`day` 0 = Sunday). | 
**day_intervals** | [**Vec<Vec<models::PostingTimesDayIntervalsInnerInner>>**](Vec.md) | Per weekday, 2-hour intervals. | 
**best** | [**Vec<models::PostingTimesBestInner>**](PostingTimes_best_inner.md) | Up to three recommended slots, at most one per weekday. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



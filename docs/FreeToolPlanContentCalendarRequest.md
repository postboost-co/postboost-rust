# FreeToolPlanContentCalendarRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**start_date** | **String** | First day of the calendar (YYYY-MM-DD). Each week starts on this weekday. | 
**weeks** | Option<**i32**> |  | [optional][default to 4]
**posts_per_week** | [**models::FreeToolPlanContentCalendarRequestPostsPerWeek**](FreeToolPlanContentCalendarRequest_posts_per_week.md) |  | 
**times** | Option<[**models::FreeToolPlanContentCalendarRequestTimes**](FreeToolPlanContentCalendarRequest_times.md)> |  | [optional]
**pillars** | Option<**Vec<String>**> | Content themes, rotated over the posts in date order. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



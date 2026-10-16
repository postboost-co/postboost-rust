# FreeToolPlanContentCalendarResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**end_date** | Option<**String**> | Last day of the calendar (YYYY-MM-DD). | [optional]
**total** | Option<**i32**> | Number of posts planned. | [optional]
**slots** | Option<[**Vec<models::FreeToolPlanContentCalendarResponseSlotsInner>**](FreeToolPlanContentCalendarResponse_slots_inner.md)> |  | [optional]
**csv** | Option<**String**> | The calendar as CSV (UTF-8 with BOM): Date, Day, Time, Network, Pillar, Idea. | [optional]
**ics** | Option<**String**> | The calendar as an iCalendar file: one 15-minute event per post, in floating local time. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



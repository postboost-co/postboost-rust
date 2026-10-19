# FreeToolSummarizeReportResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**posts** | Option<**i32**> |  | [optional]
**date_range** | Option<[**models::FreeToolSummarizeReportResponseDateRange**](FreeToolSummarizeReportResponse_date_range.md)> |  | [optional]
**views** | Option<**i32**> |  | [optional]
**engagements** | Option<**i32**> |  | [optional]
**engagement_rate** | Option<**f64**> | Percent, 2 decimals; null without views. | [optional]
**engagements_from** | Option<**Vec<String>**> | The counts added up as engagements. | [optional]
**networks** | Option<[**Vec<models::FreeToolSummarizeReportResponseNetworksInner>**](FreeToolSummarizeReportResponse_networks_inner.md)> |  | [optional]
**top_posts** | Option<[**Vec<models::FreeToolSummarizeReportResponseTopPostsInner>**](FreeToolSummarizeReportResponse_top_posts_inner.md)> |  | [optional]
**weekdays** | Option<[**Vec<models::FreeToolSummarizeReportResponseWeekdaysInner>**](FreeToolSummarizeReportResponse_weekdays_inner.md)> |  | [optional]
**best_weekday** | Option<**String**> | The weekday with the highest average engagements per post. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



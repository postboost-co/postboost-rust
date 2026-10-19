# FreeToolCalculateSmmPricingResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**currency** | Option<**String**> |  | [optional]
**pricing_model** | Option<**String**> |  | [optional]
**posts_per_month** | Option<**f64**> | Networks × posts per week × 52 ÷ 12, 1 decimal. | [optional]
**hours_per_month** | Option<**f64**> | Estimated working hours a month, 1 decimal. | [optional]
**hourly_rate** | Option<**f64**> |  | [optional]
**monthly_retainer** | Option<**f64**> | Hours a month × hourly rate, whole currency units. | [optional]
**per_post** | Option<**f64**> | Monthly retainer ÷ posts a month, 2 decimals; null with no posts. | [optional]
**range** | Option<[**models::FreeToolCalculateSmmPricingResponseRange**](FreeToolCalculateSmmPricingResponse_range.md)> |  | [optional]
**line_items** | Option<[**Vec<models::FreeToolCalculateSmmPricingResponseLineItemsInner>**](FreeToolCalculateSmmPricingResponse_line_items_inner.md)> | Every task with hours above 0. | [optional]
**assumptions** | Option<**Vec<String>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# FreeToolCalculateSocialRoiResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**period** | Option<**String**> |  | [optional]
**revenue** | Option<**f64**> |  | [optional]
**total_cost** | Option<**f64**> | Sum of every cost, labor = hours × hourly rate. 2 decimals. | [optional]
**net_return** | Option<**f64**> | Revenue minus total cost. 2 decimals. | [optional]
**roi_percent** | Option<**f64**> | (revenue − total cost) ÷ total cost × 100, 1 decimal; null when the total cost is 0. | [optional]
**cost_breakdown** | Option<[**Vec<models::FreeToolCalculateSocialRoiResponseCostBreakdownInner>**](FreeToolCalculateSocialRoiResponse_cost_breakdown_inner.md)> | Every cost above 0, with its share of the total cost (percent, 1 decimal). | [optional]
**warnings** | Option<**Vec<String>**> |  | [optional]
**formula** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



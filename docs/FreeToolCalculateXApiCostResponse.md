# FreeToolCalculateXApiCostResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**line_items** | Option<[**Vec<models::FreeToolCalculateXApiCostResponseLineItemsInner>**](FreeToolCalculateXApiCostResponse_line_items_inner.md)> | One row per billed resource: count × unit price. | [optional]
**total_usd** | Option<**f64**> | Sum of every line item. | [optional]
**link_premium_usd** | Option<**f64**> | What the link posts cost on top of the plain post price. | [optional]
**notes** | Option<**Vec<String>**> |  | [optional]
**prices_last_verified** | Option<[**String**](string.md)> | When the prices were last checked against the source. | [optional]
**source** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



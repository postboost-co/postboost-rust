# FreeToolCalculateAspectRatioResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**ratio** | Option<**String**> | Simplified ratio, e.g. `4:5`. Decimal ratios stay as given. | [optional]
**decimal** | Option<**f64**> | Width divided by height, 4 decimals. | [optional]
**width** | Option<**i32**> |  | [optional]
**height** | Option<**i32**> |  | [optional]
**rounding** | Option<[**models::FreeToolCalculateAspectRatioResponseRounding**](FreeToolCalculateAspectRatioResponse_rounding.md)> |  | [optional]
**orientation** | Option<**String**> |  | [optional]
**matches** | Option<[**Vec<models::FreeToolCalculateAspectRatioResponseMatchesInner>**](FreeToolCalculateAspectRatioResponse_matches_inner.md)> | Social media image presets with the same ratio, else the nearest. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



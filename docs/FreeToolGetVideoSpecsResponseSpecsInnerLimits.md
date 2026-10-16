# FreeToolGetVideoSpecsResponseSpecsInnerLimits

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**min_seconds** | Option<**f64**> | Shortest length. Null when the source states no figure. | [optional]
**max_seconds** | Option<**f64**> | Longest length. Null when the source states no figure. | [optional]
**warn_over_seconds** | Option<**f64**> | Longer videos need a check (account type, reach), see `length`. Null when the source states no figure. | [optional]
**min_ratio** | Option<**f64**> | Narrowest width / height. Null when the source states no figure. | [optional]
**max_ratio** | Option<**f64**> | Widest width / height. Null when the source states no figure. | [optional]
**recommended_ratio** | Option<**String**> | Recommended ratio, e.g. `9:16`. | [optional]
**max_mb** | Option<**f64**> | Largest file in MB. Null when the source states no figure. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



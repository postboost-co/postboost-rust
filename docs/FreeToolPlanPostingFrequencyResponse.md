# FreeToolPlanPostingFrequencyResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**posts_per_week_capacity** | Option<**i32**> |  | [optional]
**sum_of_minimums** | Option<**i32**> | The recommended minimums of the chosen networks added up. | [optional]
**networks** | Option<[**Vec<models::FreeToolPlanPostingFrequencyResponseNetworksInner>**](FreeToolPlanPostingFrequencyResponse_networks_inner.md)> | One row per chosen network, in a fixed network order. | [optional]
**slots** | Option<[**Vec<models::FreeToolPlanPostingFrequencyResponseSlotsInner>**](FreeToolPlanPostingFrequencyResponse_slots_inner.md)> | The weekly grid: each network's posts spread evenly from Monday, sorted by day. | [optional]
**warnings** | Option<**Vec<String>**> |  | [optional]
**last_verified** | Option<[**String**](string.md)> | When the ranges were last checked against their sources. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



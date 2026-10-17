# FreeToolPlanPostingFrequencyResponseNetworksInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | Option<**String**> |  | [optional]
**label** | Option<**String**> |  | [optional]
**recommended_per_week** | Option<[**models::FreeToolPlanPostingFrequencyResponseNetworksInnerRecommendedPerWeek**](FreeToolPlanPostingFrequencyResponse_networks_inner_recommended_per_week.md)> |  | [optional]
**recommended_label** | Option<**String**> | The range as text, e.g. \"3-5 per week\" or \"1+ per week\". | [optional]
**allocated_per_week** | Option<**i32**> | Your posts for this network: capacity split in proportion to the range midpoints (the minimum for an open-ended range). | [optional]
**fit** | Option<**String**> | Where the allocation sits against the recommended range. | [optional]
**source_type** | Option<**String**> | measured = a study of real posts; vendor = a software vendor's guidance; platform = the network's own guidance. | [optional]
**sources** | Option<[**Vec<models::FreeToolPlanPostingFrequencyResponseNetworksInnerSourcesInner>**](FreeToolPlanPostingFrequencyResponse_networks_inner_sources_inner.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



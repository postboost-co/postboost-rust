# FreeToolCalculateInfluencerRateResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**tier** | Option<**String**> |  | [optional]
**tier_label** | Option<**String**> |  | [optional]
**deliverable** | Option<**String**> |  | [optional]
**guide_low** | Option<**i32**> | USD, low end of the vendor price-guide range after the adjustments. | [optional]
**guide_high** | Option<**i32**> | USD, high end; null when the guide is open-ended (e.g. 10,000+). | [optional]
**guide_source** | Option<[**models::FreeToolCalculateInfluencerRateResponseGuideSource**](FreeToolCalculateInfluencerRateResponse_guide_source.md)> |  | [optional]
**marketplace_median** | Option<**i32**> | USD, the measured median paid deliverable for this tier, all networks, before adjustments. | [optional]
**marketplace_note** | Option<**String**> |  | [optional]
**marketplace_source** | Option<[**models::FreeToolCalculateInfluencerRateResponseGuideSource**](FreeToolCalculateInfluencerRateResponse_guide_source.md)> |  | [optional]
**cpm_estimate** | Option<**i32**> | USD, avg_views / 1,000 × cpm_usd (half up); null without both. | [optional]
**multipliers** | Option<[**Vec<models::FreeToolCalculateInfluencerRateResponseMultipliersInner>**](FreeToolCalculateInfluencerRateResponse_multipliers_inner.md)> | Every adjustment applied, as a percent of the base price. | [optional]
**method** | Option<**String**> |  | [optional]
**warnings** | Option<**Vec<String>**> |  | [optional]
**currency** | Option<**String**> |  | [optional]
**last_verified** | Option<[**String**](string.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



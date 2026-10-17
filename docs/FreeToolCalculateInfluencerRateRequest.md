# FreeToolCalculateInfluencerRateRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | **String** | LinkedIn is not offered: no primary source for its rates. | 
**followers** | **i32** | Followers (subscribers on YouTube). Sets the tier. | 
**deliverable** | Option<**String**> | Instagram: post (default), reel, carousel. TikTok: video. X and Facebook: post. YouTube: integration (default), dedicated, short. | [optional]
**avg_views** | Option<**i32**> | Expected views of the deliverable. Required on YouTube, which is priced per 1,000 views; with cpm_usd it gives your own CPM estimate on any network. | [optional]
**cpm_usd** | Option<**i32**> | Your own price per 1,000 views, in whole USD, for the CPM estimate. | [optional]
**usage_rights_months** | Option<**i32**> | Months the brand may reuse the content. | [optional][default to 0]
**exclusivity** | Option<**bool**> | The creator agrees not to work with competitors for the campaign. | [optional][default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# FreeToolPickSocialMediaToolResponseResultsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slug** | Option<**String**> |  | [optional]
**name** | Option<**String**> |  | [optional]
**score** | Option<**i32**> | How many of your needs the tool meets. | [optional]
**matched** | Option<**Vec<String>**> |  | [optional]
**missing** | Option<**Vec<String>**> |  | [optional]
**unknown** | Option<**Vec<String>**> | Needs the tool's public docs did not show either way (\"not documented\"). | [optional]
**compare_url** | Option<**String**> | Path of the full PostBoost comparison page; null for PostBoost. | [optional]
**checked_at** | Option<[**String**](string.md)> | When the tool's data was last checked. | [optional]
**pick_if** | Option<**String**> | When this tool is the better choice; null for PostBoost. | [optional]
**postboost_if** | Option<**String**> | When PostBoost is the better choice; null for PostBoost. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



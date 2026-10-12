# RssFeedInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | **String** | Public http(s) URL of an RSS 2.0 or Atom feed. | 
**name** | Option<**String**> |  | [optional]
**account_ids** | **Vec<i32>** |  | 
**mode** | Option<**String**> |  | [optional][default to Draft]
**template** | Option<**String**> | Post text. Placeholders: `{title}`, `{link}`, `{summary}` (up to 280 characters). Default `{title}` + blank line + `{link}`. | [optional]
**max_items_per_run** | Option<**i32**> |  | [optional][default to 3]
**active** | Option<**bool**> |  | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



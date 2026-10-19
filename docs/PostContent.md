# PostContent

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**body** | Option<**String**> | Post text/caption. For a second item on Facebook Page, Instagram or LinkedIn this is the first comment. | [optional]
**url** | Option<**String**> | Link shown as a preview card on LinkedIn, Bluesky and Facebook Pages (Facebook builds the card from the page's own Open Graph tags). If omitted and the item has no media, the first link in `body` is used. | [optional]
**media** | Option<**Vec<i32>**> | Array of media IDs from the media library. | [optional]
**video_thumbs** | Option<[**Vec<serde_json::Value>**](serde_json::Value.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



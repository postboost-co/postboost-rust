# FreeToolGenerateSocialPostsFromBlogRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | Option<**String**> | Public http(s) address of the blog post. Give `url` or `text`. | [optional]
**text** | Option<**String**> | The blog post itself, instead of `url`. | [optional]
**platforms** | **Vec<String>** | Networks to write for, at most 4 per call (one AI credit each). | 
**tone** | Option<**String**> |  | [optional][default to Casual]
**length** | Option<**String**> |  | [optional][default to Short]
**hashtags** | Option<**String**> | How many hashtags to include. | [optional][default to No]
**cta** | Option<**String**> | Call to action to end with. | [optional][default to No]
**workspace** | Option<**String**> | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



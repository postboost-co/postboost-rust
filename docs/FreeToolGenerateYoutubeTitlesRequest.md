# FreeToolGenerateYoutubeTitlesRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **String** | What the video is about. | 
**style** | Option<**String**> | how-to (\"How to ...\"), listicle (\"7 ways to ...\"), question, story (first person) or news. | [optional][default to HowTo]
**workspace** | Option<**String**> | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]
**transcript** | Option<**String**> | Optional: your video's captions (.srt, .vtt or the Show transcript text) as context; timestamps are removed and the first 6,000 characters are used. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



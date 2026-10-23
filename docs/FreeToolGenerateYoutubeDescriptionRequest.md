# FreeToolGenerateYoutubeDescriptionRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **String** | What the video is about: a summary or the main points. | 
**keywords** | Option<**String**> | Optional search keywords to use naturally, comma separated. | [optional]
**chapters** | Option<**bool**> | Add a chapters block after the first paragraph. | [optional][default to false]
**chapter_lines** | Option<**Vec<String>**> | Your chapters as `m:ss Title` lines, the first at 0:00. Used verbatim when `chapters` is true; without them the block has fill-in placeholders. Timestamps are never generated. | [optional]
**cta** | Option<**String**> | The closing call to action: subscribe, link (a [link] placeholder) or none. | [optional][default to Subscribe]
**workspace** | Option<**String**> | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]
**transcript** | Option<**String**> | Optional: your video's captions (.srt, .vtt, .sbv or the Show transcript text) as context; timestamps are removed and the first 6,000 characters are used. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



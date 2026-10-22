# FreeToolGenerateSocialPostsFromVideoRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **String** | The captions of your video: an .srt or .vtt file's text, or the text of YouTube's \"Show transcript\" panel. Timestamps, cue numbers and sound tags like [Music] are removed; 100 to 24,000 characters must remain. | 
**video_url** | Option<**String**> | The video's YouTube link (watch, youtu.be, Shorts or live). Each output links it once, the X thread in its last post; without it the posts have no link. | [optional]
**title** | Option<**String**> | The video's title, as context for the posts. | [optional]
**outputs** | Option<**Vec<String>**> | What to write, 1 to 4 different keys. | [optional][default to [x_thread, linkedin, instagram]]
**tone** | Option<**String**> |  | [optional][default to Friendly]
**workspace** | Option<**String**> | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# FreeToolGenerateSocialPostsFromVideoResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**outputs** | Option<[**models::FreeToolGenerateSocialPostsFromVideoResponseOutputs**](FreeToolGenerateSocialPostsFromVideoResponse_outputs.md)> |  | [optional]
**outputs_skipped** | Option<**Vec<String>**> | Requested outputs that came back empty: generate again to get them. | [optional]
**warnings** | Option<**Vec<String>**> | What to know before posting, in plain words. | [optional]
**video_url** | Option<**String**> | The normalised video link the posts use, or null. | [optional]
**cleaned_chars** | Option<**i32**> | Characters of caption text left after cleaning; the model read these. | [optional]
**removed_timestamps** | Option<**bool**> | True when timestamps, cue numbers, tags or repeated caption lines were removed. | [optional]
**credits_spent** | Option<**i32**> | AI credits this call took from the workspace: 1, or 0 for a cached result. | [optional]
**cached** | Option<**bool**> | True when the same request was answered before (free). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



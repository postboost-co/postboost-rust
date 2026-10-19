# FreeToolGenerateYoutubeDescriptionResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**descriptions** | Option<**Vec<String>**> | Two or three different descriptions, each under 5,000 UTF-8 bytes (YouTube's limit) and without `<` or `>`. Links are `[link]` placeholders. | [optional]
**credits_spent** | Option<**i32**> | AI credits this call took from the workspace: 1, or 0 for a cached result. | [optional]
**cached** | Option<**bool**> | True when the same request was answered before (free). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



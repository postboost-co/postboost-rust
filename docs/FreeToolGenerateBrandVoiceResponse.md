# FreeToolGenerateBrandVoiceResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**voice** | Option<[**models::FreeToolGenerateBrandVoiceResponseVoice**](FreeToolGenerateBrandVoiceResponse_voice.md)> |  | [optional]
**evidence** | Option<[**std::collections::HashMap<String, Vec<String>>**](Vec.md)> | Per trait key, up to 2 quotes from your posts that show it; only quotes found in your posts are kept, so a list can be empty. | [optional]
**system_prompt** | Option<**String**> | The system prompt PostBoost's AI uses for this voice; paste it into ChatGPT, Claude or your agent. | [optional]
**markdown** | Option<**String**> | The voice as a Markdown guide with its quotes, ending with the system prompt. | [optional]
**credits_spent** | Option<**i32**> | AI credits this call took from the workspace: 1, or 0 for a cached result. | [optional]
**cached** | Option<**bool**> | True when the same request was answered before (free). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



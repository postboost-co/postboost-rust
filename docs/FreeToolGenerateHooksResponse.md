# FreeToolGenerateHooksResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hooks** | Option<[**Vec<models::FreeToolGenerateHooksResponseHooksInner>**](FreeToolGenerateHooksResponse_hooks_inner.md)> | `count` hooks in several styles. | [optional]
**notice** | Option<**String**> | Only while AI is switched off: the hooks are templates from the free library (getHookTemplates) with the topic filled in, free of charge. | [optional]
**credits_spent** | Option<**i32**> | AI credits this call took from the workspace: 1, or 0 for a cached result. | [optional]
**cached** | Option<**bool**> | True when the same request was answered before (free). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



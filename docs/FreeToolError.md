# FreeToolError

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**message** | **String** |  | 
**retry_after** | Option<**i32**> | 429 only: seconds until the limit resets. | [optional]
**register_url** | Option<**String**> | 429 for guests: sign up for a token with higher limits. | [optional]
**upgrade_url** | Option<**String**> | 429 when a token user reached the plan's daily cap. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



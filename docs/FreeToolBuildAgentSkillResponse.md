# FreeToolBuildAgentSkillResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**format** | Option<**String**> |  | [optional]
**filename** | Option<**String**> |  | [optional]
**content** | Option<**String**> | The file, in Markdown. | [optional]
**install** | Option<**Vec<String>**> | Where to put the file. | [optional]
**tools_used** | Option<**Vec<String>**> | The connector tool names the content names, in first-appearance order; empty with api_token. | [optional]
**lines** | Option<**i32**> |  | [optional]
**warnings** | Option<[**Vec<models::FreeToolCheckPostResponseNetworksInnerErrorsInner>**](FreeToolCheckPostResponse_networks_inner_errors_inner.md)> | Codes: name_normalized, task_limited_by_autonomy, autonomy_high, too_long. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



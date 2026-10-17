# PreflightResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**valid** | **bool** | True when create-post with the same body would succeed. Warnings do not change it. | 
**errors** | [**std::collections::HashMap<String, Vec<String>>**](Vec.md) | Validation and network-requirement errors keyed by field, as create-post would report them in a `422`. | 
**issues** | [**Vec<models::GuardrailError>**](GuardrailError.md) | Guardrail problems, in the order create-post would report the first of them. | 
**warnings** | [**Vec<models::PostWarning>**](PostWarning.md) | The warnings create-post would return for the same body (same codes and messages); empty when there are none. | 
**publish_at** | Option<**String**> | UTC time the post would publish at; null for a draft. | 
**accounts** | [**Vec<models::AccountHealth>**](AccountHealth.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



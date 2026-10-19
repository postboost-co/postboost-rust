# FreeToolFindAutomationRecipesResponseRecipesInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slug** | Option<**String**> | Stable key of the recipe, also its anchor on the page. | [optional]
**title** | Option<**String**> | What the recipe does. | [optional]
**trigger** | Option<**String**> | What starts it. | [optional]
**goal** | Option<**String**> | The result in one or two sentences. | [optional]
**native** | Option<[**models::FreeToolFindAutomationRecipesResponseRecipesInnerNative**](FreeToolFindAutomationRecipesResponse_recipes_inner_native.md)> |  | [optional]
**api_operations** | Option<[**Vec<models::FreeToolFindAutomationRecipesResponseRecipesInnerApiOperationsInner>**](FreeToolFindAutomationRecipesResponse_recipes_inner_api_operations_inner.md)> | The PostBoost API operations the recipe calls. | [optional]
**steps** | Option<[**models::FreeToolFindAutomationRecipesResponseRecipesInnerSteps**](FreeToolFindAutomationRecipesResponse_recipes_inner_steps.md)> |  | [optional]
**n8n_workflow** | Option<[**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md)> | Importable n8n workflow (core nodes only; add a Header Auth credential named \"PostBoost API token\") when `platform` is `n8n`; null otherwise. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



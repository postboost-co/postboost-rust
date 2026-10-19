# FreeToolGetGlossaryResponseTermsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**term** | Option<**String**> | The term. | [optional]
**slug** | Option<**String**> | Stable key of the term, also its anchor on the page. | [optional]
**category** | Option<**String**> | Category. | [optional]
**definition** | Option<**String**> | Plain-language definition in one to three sentences. | [optional]
**networks** | Option<**Vec<String>**> | Networks the term is specific to (provider keys); empty when it applies to all. | [optional]
**related** | Option<**Vec<String>**> | Slugs of related terms. | [optional]
**url** | Option<**String**> | The term on the glossary page. | [optional]
**learn_url** | Option<**String**> | A PostBoost guide that goes deeper, or null. | [optional]
**tool_url** | Option<**String**> | A free tool for the job, or null. | [optional]
**feature_url** | Option<**String**> | The PostBoost feature page, or null. | [optional]
**source** | Option<**String**> | Where a platform rule or number in the definition comes from, or null. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



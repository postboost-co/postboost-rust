# WorkspaceAgentSettings

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**horizon_hours** | Option<**i32**> | Check posts scheduled within this many hours. | [optional][default to 24]
**check_links** | Option<**bool**> | Flag links in captions that answer an HTTP error. | [optional][default to true]
**banned_phrases** | Option<**Vec<String>**> | Phrases to propose removing from captions. | [optional][default to []]
**ai_review** | Option<**bool**> | Ask AI to review captions (one AI credit per reviewed post). | [optional][default to false]
**max_ai_reviews_per_run** | Option<**i32**> |  | [optional][default to 10]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



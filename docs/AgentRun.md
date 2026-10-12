# AgentRun

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**agent_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> |  | 
**agent_type** | Option<**String**> |  | 
**trigger** | **String** |  | 
**status** | **String** |  | 
**started_at** | Option<**String**> |  | [optional]
**finished_at** | Option<**String**> |  | [optional]
**items_checked** | **i32** |  | 
**proposals_created** | **i32** |  | 
**credits_used** | **i32** | AI credits this run used. | 
**summary** | Option<**String**> |  | [optional]
**error** | Option<**String**> |  | [optional]
**created_at** | Option<**String**> |  | [optional]
**proposals** | Option<[**Vec<models::AgentProposal>**](AgentProposal.md)> | Only on `GET /agent-runs/{runUuid}`. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# ApiActivity

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**user_id** | Option<**i32**> |  | [optional]
**token_ref** | Option<**String**> | First 12 hex characters of the SHA-256 of the API token used, to tell tokens apart. | [optional]
**client** | Option<**String**> | `X-PostBoost-Client` header, else the `User-Agent`. | [optional]
**route_name** | Option<**String**> |  | [optional]
**method** | **String** |  | 
**post_uuid** | Option<**String**> |  | [optional]
**outcome** | [**models::ApiActivityOutcome**](ApiActivityOutcome.md) |  | 
**http_status** | **i32** |  | 
**created_at** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



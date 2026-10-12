# \ActivityApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**list_api_activity**](ActivityApi.md#list_api_activity) | **GET** /{workspaceUuid}/activity | List API activity



## list_api_activity

> models::ListApiActivity200Response list_api_activity(workspace_uuid, outcome, client, since, page)
List API activity

Every write request (`POST`, `PUT`, `DELETE`) made through the API in this workspace, newest first, with the client that made it and its outcome. Kept for 90 days. Send an `X-PostBoost-Client` header (for example `my-agent/1.2`) to label your requests; otherwise the `User-Agent` is recorded. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**outcome** | Option<[**ApiActivityOutcome**](.md)> |  |  |
**client** | Option<**String**> | Client label prefix, for example `mcp`. |  |
**since** | Option<**String**> | Only entries at or after this time (UTC). |  |
**page** | Option<**i32**> |  |  |[default to 1]

### Return type

[**models::ListApiActivity200Response**](listApiActivity_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \WorkspacesApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_user_to_workspace**](WorkspacesApi.md#add_user_to_workspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
[**create_workspace**](WorkspacesApi.md#create_workspace) | **POST** /panel/workspaces | Create workspace
[**delete_workspace**](WorkspacesApi.md#delete_workspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
[**delete_workspaces_bulk**](WorkspacesApi.md#delete_workspaces_bulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
[**get_workspace**](WorkspacesApi.md#get_workspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
[**list_workspaces**](WorkspacesApi.md#list_workspaces) | **GET** /panel/workspaces | List workspaces
[**remove_user_from_workspace**](WorkspacesApi.md#remove_user_from_workspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
[**update_workspace**](WorkspacesApi.md#update_workspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
[**update_workspace_user**](WorkspacesApi.md#update_workspace_user) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace



## add_user_to_workspace

> serde_json::Value add_user_to_workspace(workspace_uuid, workspace_user_input)
Add user to workspace

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**workspace_user_input** | [**WorkspaceUserInput**](WorkspaceUserInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_workspace

> models::Workspace create_workspace(workspace_input)
Create workspace

Create a new workspace. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_input** | [**WorkspaceInput**](WorkspaceInput.md) |  | [required] |

### Return type

[**models::Workspace**](Workspace.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_workspace

> serde_json::Value delete_workspace(workspace_uuid)
Delete workspace

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_workspaces_bulk

> serde_json::Value delete_workspaces_bulk(delete_workspaces_bulk_request)
Delete workspaces (bulk)

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**delete_workspaces_bulk_request** | [**DeleteWorkspacesBulkRequest**](DeleteWorkspacesBulkRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_workspace

> models::Workspace get_workspace(workspace_uuid)
Get workspace

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::Workspace**](Workspace.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_workspaces

> models::ListWorkspaces200Response list_workspaces(keyword, subscription_status, access_status)
List workspaces

Returns a paginated list of all workspaces. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**keyword** | Option<**String**> |  |  |
**subscription_status** | Option<**String**> |  |  |
**access_status** | Option<**String**> |  |  |

### Return type

[**models::ListWorkspaces200Response**](listWorkspaces_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## remove_user_from_workspace

> serde_json::Value remove_user_from_workspace(workspace_uuid, remove_user_from_workspace_request)
Remove user from workspace

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**remove_user_from_workspace_request** | [**RemoveUserFromWorkspaceRequest**](RemoveUserFromWorkspaceRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_workspace

> serde_json::Value update_workspace(workspace_uuid, workspace_input)
Update workspace

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**workspace_input** | [**WorkspaceInput**](WorkspaceInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_workspace_user

> serde_json::Value update_workspace_user(workspace_uuid, workspace_user_input)
Update user role in workspace

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**workspace_user_input** | [**WorkspaceUserInput**](WorkspaceUserInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


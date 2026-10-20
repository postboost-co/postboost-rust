# \WorkspacesApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_user_to_workspace**](WorkspacesApi.md#add_user_to_workspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
[**create_api_key**](WorkspacesApi.md#create_api_key) | **POST** /{workspaceUuid}/api-keys | Create a scoped API key
[**create_reseller_client**](WorkspacesApi.md#create_reseller_client) | **POST** /{workspaceUuid}/clients | Create a client workspace
[**create_workspace**](WorkspacesApi.md#create_workspace) | **POST** /panel/workspaces | Create workspace
[**delete_api_key**](WorkspacesApi.md#delete_api_key) | **DELETE** /{workspaceUuid}/api-keys/{apiKeyId} | Revoke a scoped API key
[**delete_workspace**](WorkspacesApi.md#delete_workspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
[**delete_workspaces_bulk**](WorkspacesApi.md#delete_workspaces_bulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
[**get_workspace**](WorkspacesApi.md#get_workspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
[**get_workspace_ai_credits**](WorkspacesApi.md#get_workspace_ai_credits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits
[**get_x_usage**](WorkspacesApi.md#get_x_usage) | **GET** /{workspaceUuid}/usage/x | X (Twitter) usage
[**list_api_keys**](WorkspacesApi.md#list_api_keys) | **GET** /{workspaceUuid}/api-keys | List scoped API keys
[**list_my_workspaces**](WorkspacesApi.md#list_my_workspaces) | **GET** /workspaces | List my workspaces
[**list_reseller_clients**](WorkspacesApi.md#list_reseller_clients) | **GET** /{workspaceUuid}/clients | List client workspaces
[**list_workspaces**](WorkspacesApi.md#list_workspaces) | **GET** /panel/workspaces | List workspaces
[**remove_user_from_workspace**](WorkspacesApi.md#remove_user_from_workspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
[**update_workspace**](WorkspacesApi.md#update_workspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
[**update_workspace_user**](WorkspacesApi.md#update_workspace_user) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace



## add_user_to_workspace

> serde_json::Value add_user_to_workspace(workspace_uuid, workspace_user_input)
Add user to workspace

Adds an existing user to the workspace with a specified role. Admin only.

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


## create_api_key

> models::CreateApiKey201Response create_api_key(workspace_uuid, api_key_input)
Create a scoped API key

Creates a least-privilege API key for the calling user, bound to this workspace. Pick the abilities it gets and, optionally, the accounts it may act on. The plain key is in `data.token` of this response only; store it safely.  | Ability | Allows | |---|---| | `read` | Every `GET`, plus the `posts/validate` dry run | | `write` | Creating and changing drafts, media, tags, mentions, the brand voice | | `publish` | Scheduling, queueing, publishing now, approving and retrying posts, and editing a post that is already scheduled | | `ai` | The `/ai/_*` endpoints, running agents and turning on agent AI review (they also need AI credits) | | `webhooks` | Webhook subscription endpoints |  A scoped key is refused on other workspaces, on the admin panel, on API key management and on the app's built-in MCP endpoint (use `/mcp/postboost`). With `account_ids`, it may only name those accounts (in the URL, `accounts`, `account_ids` or post versions), cannot touch posts on other accounts, and `GET accounts` / `GET posts` only list matching items (pagination counts are computed before that filter). Workspace admins only, called with an unscoped key. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**api_key_input** | [**ApiKeyInput**](ApiKeyInput.md) |  | [required] |

### Return type

[**models::CreateApiKey201Response**](createApiKey_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_reseller_client

> models::CreateResellerClient201Response create_reseller_client(workspace_uuid, reseller_client_input)
Create a client workspace

Creates a client workspace on the Reseller client plan, with the caller as its owner and admin, and links it to this workspace. Fails with `422` and `code: client_limit_reached` once the plan's client limit is used (archived clients do not count). Archive clients on the Client workspaces page. Workspace admins with an unscoped key only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**reseller_client_input** | [**ResellerClientInput**](ResellerClientInput.md) |  | [required] |

### Return type

[**models::CreateResellerClient201Response**](createResellerClient_201_response.md)

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


## delete_api_key

> serde_json::Value delete_api_key(workspace_uuid, api_key_id)
Revoke a scoped API key

Revokes a scoped key bound to this workspace. It stops working at once. Workspace admins only, called with an unscoped key.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**api_key_id** | **i32** | The key's `id` from `GET api-keys`. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_workspace

> serde_json::Value delete_workspace(workspace_uuid)
Delete workspace

Permanently deletes a single workspace and all its associated data. Admin only.

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

Permanently deletes one or more workspaces and all their associated data. Admin only.

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

Returns a single workspace by UUID including its subscription status. Admin only.

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


## get_workspace_ai_credits

> models::AiCredits get_workspace_ai_credits(workspace_uuid)
Get workspace AI credits

Returns whether the workspace can use AI credits, its remaining balance, and whether the balance is low. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::AiCredits**](AICredits.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_x_usage

> models::XUsage get_x_usage(workspace_uuid)
X (Twitter) usage

The workspace's X posts this calendar month (UTC) against its monthly X allowance. Every thread part is one X post; a part with a link also counts as a link post. Once enforcement is switched on (`enforced: true`), scheduling to X is refused when the allowance is used up (`429`, `code: x_monthly_cap_reached`) and X posts that come due fail with \"Monthly X allowance reached\". Until then usage is tracked only. Other networks are not affected. See the X policy in the developer docs. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::XUsage**](XUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_api_keys

> models::ListApiKeys200Response list_api_keys(workspace_uuid)
List scoped API keys

Scoped API keys bound to this workspace, newest first. The secret is never shown again after creation. Workspace admins only, called with an unscoped key (a scoped key gets `403` with `code: insufficient_scope`). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListApiKeys200Response**](listApiKeys_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_my_workspaces

> models::ListMyWorkspaces200Response list_my_workspaces()
List my workspaces

Returns the workspaces the authenticated user belongs to, most recently updated first, with the caller's role in each. Use a returned `uuid` as `workspaceUuid`.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::ListMyWorkspaces200Response**](listMyWorkspaces_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_reseller_clients

> models::ListResellerClients200Response list_reseller_clients(workspace_uuid)
List client workspaces

Client workspaces this workspace created on the Reseller plan, active first, then archived. `accounts_needing_reconnect` counts accounts whose connection must be renewed. `meta` gives the active clients and the plan's client limit. Workspace admins with an unscoped key only; other workspaces get `403` with `code: not_a_reseller`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListResellerClients200Response**](listResellerClients_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_workspaces

> models::ListWorkspaces200Response list_workspaces(keyword, subscription_status, access_status, page)
List workspaces

Returns a paginated list of all workspaces. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**keyword** | Option<**String**> |  |  |
**subscription_status** | Option<**String**> |  |  |
**access_status** | Option<**String**> |  |  |
**page** | Option<**i32**> | Page number (15 items per page). |  |[default to 1]

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

Removes a user's access to the workspace. The user account is not deleted. Admin only.

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

Updates a workspace's name, owner, or access status. Admin only. `hex_color` is accepted but ignored.

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

Changes a user's role or permissions within the workspace. Admin only.

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


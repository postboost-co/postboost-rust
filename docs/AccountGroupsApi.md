# \AccountGroupsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_account_group**](AccountGroupsApi.md#create_account_group) | **POST** /{workspaceUuid}/account-groups | Create an account group
[**delete_account_group**](AccountGroupsApi.md#delete_account_group) | **DELETE** /{workspaceUuid}/account-groups/{accountGroupUuid} | Delete an account group
[**get_account_group**](AccountGroupsApi.md#get_account_group) | **GET** /{workspaceUuid}/account-groups/{accountGroupUuid} | Get an account group
[**list_account_groups**](AccountGroupsApi.md#list_account_groups) | **GET** /{workspaceUuid}/account-groups | List account groups
[**update_account_group**](AccountGroupsApi.md#update_account_group) | **PUT** /{workspaceUuid}/account-groups/{accountGroupUuid} | Update an account group



## create_account_group

> models::CreateAccountGroup201Response create_account_group(workspace_uuid, account_group_input)
Create an account group

Creates a named set of accounts of this workspace. Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_group_input** | [**AccountGroupInput**](AccountGroupInput.md) |  | [required] |

### Return type

[**models::CreateAccountGroup201Response**](createAccountGroup_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_account_group

> delete_account_group(workspace_uuid, account_group_uuid)
Delete an account group

Deletes the group, not its accounts. Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_group_uuid** | **String** | The account group `uuid`. | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_account_group

> models::CreateAccountGroup201Response get_account_group(workspace_uuid, account_group_uuid)
Get an account group

One account group. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_group_uuid** | **String** | The account group `uuid`. | [required] |

### Return type

[**models::CreateAccountGroup201Response**](createAccountGroup_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_account_groups

> models::ListAccountGroups200Response list_account_groups(workspace_uuid, page, per_page)
List account groups

Named sets of accounts, sorted by name, with their account ids. Pass `account_ids` as `accounts` when you create a post to publish to the whole group. Paginated with `page` and `per_page` (default 100). A key limited to some accounts only sees groups whose accounts are all among its accounts, and `meta.total` counts only those. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> | Page number (1-based). |  |[default to 1]
**per_page** | Option<**i32**> | Items per page, 1-100. |  |[default to 100]

### Return type

[**models::ListAccountGroups200Response**](listAccountGroups_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_account_group

> models::CreateAccountGroup201Response update_account_group(workspace_uuid, account_group_uuid, account_group_input)
Update an account group

Replaces the name and the accounts of the group (accounts you leave out are removed). Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_group_uuid** | **String** | The account group `uuid`. | [required] |
**account_group_input** | [**AccountGroupInput**](AccountGroupInput.md) |  | [required] |

### Return type

[**models::CreateAccountGroup201Response**](createAccountGroup_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \AccountsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_account**](AccountsApi.md#get_account) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
[**list_accounts**](AccountsApi.md#list_accounts) | **GET** /{workspaceUuid}/accounts | List accounts



## get_account

> models::Account get_account(workspace_uuid, account_uuid)
Get account

Returns a single social media account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_uuid** | **uuid::Uuid** | UUID of the social media account. | [required] |

### Return type

[**models::Account**](Account.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_accounts

> models::ListAccounts200Response list_accounts(workspace_uuid, keyword, group, providers_left_square_bracket_right_square_bracket, unauthorized)
List accounts

Returns all social media accounts connected to the workspace, newest first. Optional filters narrow the list.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**keyword** | Option<**String**> | Match the account name or username. |  |
**group** | Option<**String**> | Only accounts in this account group. |  |
**providers_left_square_bracket_right_square_bracket** | Option<[**Vec<String>**](String.md)> | Only accounts of these providers (for example `instagram`, `linkedin`). |  |
**unauthorized** | Option<**bool**> | When `true`, only accounts that need to be reconnected. |  |

### Return type

[**models::ListAccounts200Response**](listAccounts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


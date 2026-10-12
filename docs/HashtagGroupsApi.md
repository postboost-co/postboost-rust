# \HashtagGroupsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_hashtag_group**](HashtagGroupsApi.md#create_hashtag_group) | **POST** /{workspaceUuid}/hashtag-groups | Create a hashtag group
[**delete_hashtag_group**](HashtagGroupsApi.md#delete_hashtag_group) | **DELETE** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Delete a hashtag group
[**get_hashtag_group**](HashtagGroupsApi.md#get_hashtag_group) | **GET** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Get a hashtag group
[**list_hashtag_groups**](HashtagGroupsApi.md#list_hashtag_groups) | **GET** /{workspaceUuid}/hashtag-groups | List hashtag groups
[**update_hashtag_group**](HashtagGroupsApi.md#update_hashtag_group) | **PUT** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Update a hashtag group



## create_hashtag_group

> models::CreateHashtagGroup201Response create_hashtag_group(workspace_uuid, hashtag_group_input)
Create a hashtag group

Saves a named set of hashtags (up to 3000 characters). Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**hashtag_group_input** | [**HashtagGroupInput**](HashtagGroupInput.md) |  | [required] |

### Return type

[**models::CreateHashtagGroup201Response**](createHashtagGroup_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_hashtag_group

> delete_hashtag_group(workspace_uuid, hashtag_group_id)
Delete a hashtag group

Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**hashtag_group_id** | **String** | The hashtag group `id`. | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_hashtag_group

> models::CreateHashtagGroup201Response get_hashtag_group(workspace_uuid, hashtag_group_id)
Get a hashtag group

One hashtag group. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**hashtag_group_id** | **String** | The hashtag group `id`. | [required] |

### Return type

[**models::CreateHashtagGroup201Response**](createHashtagGroup_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_hashtag_groups

> models::ListHashtagGroups200Response list_hashtag_groups(workspace_uuid, page, per_page)
List hashtag groups

Saved hashtag sets of the workspace, newest first. Paginated with `page` and `per_page` (default 100). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> | Page number (1-based). |  |[default to 1]
**per_page** | Option<**i32**> | Items per page, 1-100. |  |[default to 100]

### Return type

[**models::ListHashtagGroups200Response**](listHashtagGroups_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_hashtag_group

> models::CreateHashtagGroup201Response update_hashtag_group(workspace_uuid, hashtag_group_id, hashtag_group_input)
Update a hashtag group

Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**hashtag_group_id** | **String** | The hashtag group `id`. | [required] |
**hashtag_group_input** | [**HashtagGroupInput**](HashtagGroupInput.md) |  | [required] |

### Return type

[**models::CreateHashtagGroup201Response**](createHashtagGroup_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


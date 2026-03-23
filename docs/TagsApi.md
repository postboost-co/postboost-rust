# \TagsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_tag**](TagsApi.md#create_tag) | **POST** /{workspaceUuid}/tags | Create tag
[**delete_tag**](TagsApi.md#delete_tag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
[**get_tag**](TagsApi.md#get_tag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
[**list_tags**](TagsApi.md#list_tags) | **GET** /{workspaceUuid}/tags | List tags
[**update_tag**](TagsApi.md#update_tag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag



## create_tag

> models::Tag create_tag(workspace_uuid, tag_input)
Create tag

Creates a new color-coded tag in the workspace for organizing posts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**tag_input** | [**TagInput**](TagInput.md) |  | [required] |

### Return type

[**models::Tag**](Tag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_tag

> serde_json::Value delete_tag(workspace_uuid, tag_uuid)
Delete tag

Permanently deletes a tag. Posts that had this tag attached are unaffected.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**tag_uuid** | **uuid::Uuid** | UUID of the tag. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_tag

> models::Tag get_tag(workspace_uuid, tag_uuid)
Get tag

Returns a single tag by UUID.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**tag_uuid** | **uuid::Uuid** | UUID of the tag. | [required] |

### Return type

[**models::Tag**](Tag.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_tags

> models::ListTags200Response list_tags(workspace_uuid)
List tags

Returns all tags defined in the workspace.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListTags200Response**](listTags_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_tag

> serde_json::Value update_tag(workspace_uuid, tag_uuid, tag_input)
Update tag

Updates a tag's name or color.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**tag_uuid** | **uuid::Uuid** | UUID of the tag. | [required] |
**tag_input** | [**TagInput**](TagInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


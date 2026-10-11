# \MentionsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_mention**](MentionsApi.md#create_mention) | **POST** /{workspaceUuid}/mentions | Create mention
[**delete_mention**](MentionsApi.md#delete_mention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention
[**get_mention**](MentionsApi.md#get_mention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention
[**list_mentions**](MentionsApi.md#list_mentions) | **GET** /{workspaceUuid}/mentions | List mentions
[**update_mention**](MentionsApi.md#update_mention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention



## create_mention

> models::CreateMention201Response create_mention(workspace_uuid, mention_input)
Create mention

Adds a person or page to the mention book. When one of the submitted identities already belongs to a stored mention, that mention is reused and the identities are added to it (status `200` instead of `201`). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**mention_input** | [**MentionInput**](MentionInput.md) |  | [required] |

### Return type

[**models::CreateMention201Response**](createMention_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_mention

> serde_json::Value delete_mention(workspace_uuid, mention_id)
Delete mention

Removes a mention from the mention book. `success` is false when nothing was deleted.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**mention_id** | **uuid::Uuid** | The mention's `id` (a UUID). | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_mention

> models::CreateMention201Response get_mention(workspace_uuid, mention_id)
Get mention

Returns a single mention with its identities.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**mention_id** | **uuid::Uuid** | The mention's `id` (a UUID). | [required] |

### Return type

[**models::CreateMention201Response**](createMention_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_mentions

> models::ListMentions200Response list_mentions(workspace_uuid, q, per_page, page)
List mentions

Returns a paginated list of the workspace's mention book, ranked, with each entry's network identities.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**q** | Option<**String**> | Search keyword. |  |
**per_page** | Option<**i32**> |  |  |[default to 25]
**page** | Option<**i32**> |  |  |[default to 1]

### Return type

[**models::ListMentions200Response**](listMentions_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_mention

> models::CreateMention201Response update_mention(workspace_uuid, mention_id, mention_input)
Update mention

Replaces the mention's name, avatar and identities. Identities for providers not in the payload are removed. An identity already held by another mention returns `422`.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**mention_id** | **uuid::Uuid** | The mention's `id` (a UUID). | [required] |
**mention_input** | [**MentionInput**](MentionInput.md) |  | [required] |

### Return type

[**models::CreateMention201Response**](createMention_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


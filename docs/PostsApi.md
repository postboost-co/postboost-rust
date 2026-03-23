# \PostsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_post_to_queue**](PostsApi.md#add_post_to_queue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
[**approve_post**](PostsApi.md#approve_post) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
[**create_post**](PostsApi.md#create_post) | **POST** /{workspaceUuid}/posts | Create post
[**delete_post**](PostsApi.md#delete_post) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
[**delete_posts_bulk**](PostsApi.md#delete_posts_bulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
[**get_post**](PostsApi.md#get_post) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
[**list_posts**](PostsApi.md#list_posts) | **GET** /{workspaceUuid}/posts | List posts
[**schedule_post**](PostsApi.md#schedule_post) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
[**update_post**](PostsApi.md#update_post) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post



## add_post_to_queue

> models::ScheduleResult add_post_to_queue(workspace_uuid, post_uuid)
Add post to queue

Add an existing post to the smart publishing queue.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |

### Return type

[**models::ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## approve_post

> models::ScheduleResult approve_post(workspace_uuid, post_uuid)
Approve post

Approve a post that is pending review.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |

### Return type

[**models::ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_post

> models::Post create_post(workspace_uuid, post_input)
Create post

Create a new post. Use `schedule: true` with `date` and `time` to schedule, `schedule_now: true` to publish immediately, or `queue: true` to add to the smart publishing queue. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_input** | [**PostInput**](PostInput.md) |  | [required] |

### Return type

[**models::Post**](Post.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_post

> models::DeleteResult delete_post(workspace_uuid, post_uuid, delete_post_request)
Delete post

Deletes a post. Use `delete_mode` to control whether to also remove the published content from social platforms.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**delete_post_request** | Option<[**DeletePostRequest**](DeletePostRequest.md)> |  |  |

### Return type

[**models::DeleteResult**](DeleteResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_posts_bulk

> models::DeleteResult delete_posts_bulk(workspace_uuid, delete_posts_bulk_request)
Delete posts (bulk)

Delete multiple posts at once.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**delete_posts_bulk_request** | [**DeletePostsBulkRequest**](DeletePostsBulkRequest.md) |  | [required] |

### Return type

[**models::DeleteResult**](DeleteResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_post

> models::Post get_post(workspace_uuid, post_uuid)
Get post

Returns a single post with all its versions and associated accounts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |

### Return type

[**models::Post**](Post.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_posts

> models::ListPosts200Response list_posts(workspace_uuid, page)
List posts

Returns a paginated list of posts in the workspace.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> |  |  |[default to 1]

### Return type

[**models::ListPosts200Response**](listPosts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## schedule_post

> models::ScheduleResult schedule_post(workspace_uuid, post_uuid, schedule_post_request)
Schedule post

Schedule an existing post. Set `postNow: true` to publish immediately.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**schedule_post_request** | [**SchedulePostRequest**](SchedulePostRequest.md) |  | [required] |

### Return type

[**models::ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_post

> serde_json::Value update_post(workspace_uuid, post_uuid, post_input)
Update post

Replaces a post's versions, accounts, tags, and scheduling options. The post must not be in a published state.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**post_input** | [**PostInput**](PostInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


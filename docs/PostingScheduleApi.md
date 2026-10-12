# \PostingScheduleApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_posting_schedule**](PostingScheduleApi.md#get_posting_schedule) | **GET** /{workspaceUuid}/posting-schedule | Get the posting schedule
[**get_recommended_posting_times**](PostingScheduleApi.md#get_recommended_posting_times) | **GET** /{workspaceUuid}/posting-schedule/recommended | Get recommended posting times
[**list_queue_slots**](PostingScheduleApi.md#list_queue_slots) | **GET** /{workspaceUuid}/queue/slots | List upcoming queue slots
[**reset_account_posting_schedule**](PostingScheduleApi.md#reset_account_posting_schedule) | **DELETE** /{workspaceUuid}/posting-schedule/{accountId} | Reset an account schedule
[**update_posting_schedule**](PostingScheduleApi.md#update_posting_schedule) | **PUT** /{workspaceUuid}/posting-schedule | Set the posting schedule



## get_posting_schedule

> models::GetPostingSchedule200Response get_posting_schedule(workspace_uuid, account_id)
Get the posting schedule

The queue's posting times: per weekday, a list of clock times in the schedule's timezone. `account_id=0` is the workspace schedule. An account without its own schedule follows the workspace one (`inherited: true`, `source_account_id: 0`). Posts added to the queue take the next free time. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_id** | Option<**i32**> | `0` (default) for the workspace schedule, or an account `id`. |  |[default to 0]

### Return type

[**models::GetPostingSchedule200Response**](getPostingSchedule_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_recommended_posting_times

> models::RecommendedPostingTimes get_recommended_posting_times(workspace_uuid, account_id, slots_per_day)
Get recommended posting times

Suggested posting times from past engagement, in the schedule's timezone. `has_data` is false until there is enough analytics history. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_id** | Option<**i32**> | `0` (default) for the workspace schedule, or an account `id`. |  |[default to 0]
**slots_per_day** | Option<**i32**> | Times to suggest per day (1 to 6). |  |

### Return type

[**models::RecommendedPostingTimes**](RecommendedPostingTimes.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_queue_slots

> models::QueueSlots list_queue_slots(workspace_uuid, account_id, after)
List upcoming queue slots

The queue read forward: upcoming posting times, filled by scheduled posts where they land on one. Page with `after` set to the previous `next_cursor`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_id** | Option<**i32**> | `0` (default) for the workspace schedule, or an account `id`. |  |[default to 0]
**after** | Option<**String**> | Start after this time (`Y-m-d H:i:s`, UTC), from `next_cursor`. |  |

### Return type

[**models::QueueSlots**](QueueSlots.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reset_account_posting_schedule

> models::GetPostingSchedule200Response reset_account_posting_schedule(workspace_uuid, account_id)
Reset an account schedule

Removes the account's own schedule so it follows the workspace schedule again. Workspace admins only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_id** | **i32** | The account `id`. | [required] |

### Return type

[**models::GetPostingSchedule200Response**](getPostingSchedule_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_posting_schedule

> models::GetPostingSchedule200Response update_posting_schedule(workspace_uuid, posting_schedule_input)
Set the posting schedule

Sets the workspace schedule (`account_id: 0`) or gives one account its own schedule. Send all seven weekdays (ids 1 to 6 for Monday to Saturday, 0 for Sunday). Workspace admins only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**posting_schedule_input** | [**PostingScheduleInput**](PostingScheduleInput.md) |  | [required] |

### Return type

[**models::GetPostingSchedule200Response**](getPostingSchedule_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


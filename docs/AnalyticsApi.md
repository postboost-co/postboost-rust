# \AnalyticsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**get_account_analytics**](AnalyticsApi.md#get_account_analytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
[**get_analytics_summary**](AnalyticsApi.md#get_analytics_summary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
[**get_best_posting_times**](AnalyticsApi.md#get_best_posting_times) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
[**get_post_analytics_0**](AnalyticsApi.md#get_post_analytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**get_posting_times**](AnalyticsApi.md#get_posting_times) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap



## get_account_analytics

> models::AccountAnalytics get_account_analytics(workspace_uuid, account_uuid, period, date_from, date_to, r#type, page, per_page, sort_by, sort_dir)
Get account analytics

Analytics for one account. `type` selects one of the tabs the account supports (listed in `tabs` of the response); returns `422` when the account does not support analytics.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_uuid** | **uuid::Uuid** | UUID of the social media account. | [required] |
**period** | Option<**String**> | Preset reporting period. Ignored when `date_from` and `date_to` are given. |  |[default to this_month]
**date_from** | Option<**String**> | Start of a custom range (Y-m-d). Required with `date_to`; the range may span at most 366 days. |  |
**date_to** | Option<**String**> | End of a custom range (Y-m-d). Required with `date_from`; must not be before it. |  |
**r#type** | Option<**String**> | Analytics tab. Defaults to the account's default tab. |  |
**page** | Option<**i32**> | Page for list-style tabs (for example per-post metrics). |  |[default to 1]
**per_page** | Option<**i32**> |  |  |
**sort_by** | Option<**String**> |  |  |
**sort_dir** | Option<**String**> |  |  |[default to desc]

### Return type

[**models::AccountAnalytics**](AccountAnalytics.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_analytics_summary

> models::AnalyticsSummary get_analytics_summary(workspace_uuid, period, date_from, date_to)
Get analytics summary

Cross-platform summary (followers, growth, posts, leaderboard, posting streak) over every account that supports analytics, for a preset period or a custom date range.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**period** | Option<**String**> | Preset reporting period. Ignored when `date_from` and `date_to` are given. |  |[default to this_month]
**date_from** | Option<**String**> | Start of a custom range (Y-m-d). Required with `date_to`; the range may span at most 366 days. |  |
**date_to** | Option<**String**> | End of a custom range (Y-m-d). Required with `date_from`; must not be before it. |  |

### Return type

[**models::AnalyticsSummary**](AnalyticsSummary.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_best_posting_times

> models::BestPostingTimes get_best_posting_times(workspace_uuid, accounts_left_square_bracket_right_square_bracket, from, timezone)
Get best posting times

The next recommended date and time per account, on or after `from` (never in the past), within the next 14 days.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**accounts_left_square_bracket_right_square_bracket** | Option<[**Vec<uuid::Uuid>**](uuid::Uuid.md)> | Account UUIDs. Defaults to every account in the workspace. |  |
**from** | Option<**String**> | Earliest date to recommend (Y-m-d). Defaults to now. |  |
**timezone** | Option<**String**> | Timezone for `from` and the returned times. Defaults to the workspace timezone. |  |

### Return type

[**models::BestPostingTimes**](BestPostingTimes.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_post_analytics_0

> models::PostAnalytics get_post_analytics_0(workspace_uuid, post_uuid)
Get post analytics

Engagement metrics for a published post across its accounts (also works for trashed posts), with totals, trends and the best-performing account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |

### Return type

[**models::PostAnalytics**](PostAnalytics.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_posting_times

> models::PostingTimes get_posting_times(workspace_uuid, accounts_left_square_bracket_right_square_bracket, timezone)
Get posting times heatmap

Engagement scores per weekday and hour, merged across the given accounts (all accounts when none is given), in the requested timezone. Also returns up to three recommended slots.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**accounts_left_square_bracket_right_square_bracket** | Option<[**Vec<uuid::Uuid>**](uuid::Uuid.md)> | Account UUIDs. Defaults to every account in the workspace. |  |
**timezone** | Option<**String**> | Timezone the grid is expressed in. Defaults to the workspace timezone. |  |

### Return type

[**models::PostingTimes**](PostingTimes.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


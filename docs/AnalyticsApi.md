# \AnalyticsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_report_export**](AnalyticsApi.md#create_report_export) | **POST** /{workspaceUuid}/reports/exports | Create a report export
[**download_report_export**](AnalyticsApi.md#download_report_export) | **GET** /{workspaceUuid}/reports/exports/{exportUuid}/download | Download a report file
[**get_account_analytics**](AnalyticsApi.md#get_account_analytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
[**get_analytics_summary**](AnalyticsApi.md#get_analytics_summary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
[**get_best_posting_times**](AnalyticsApi.md#get_best_posting_times) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
[**get_post_analytics_0**](AnalyticsApi.md#get_post_analytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**get_posting_times**](AnalyticsApi.md#get_posting_times) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap
[**get_report_branding**](AnalyticsApi.md#get_report_branding) | **GET** /{workspaceUuid}/report-branding | Get the report branding
[**get_report_export**](AnalyticsApi.md#get_report_export) | **GET** /{workspaceUuid}/reports/exports/{exportUuid} | Get a report export
[**list_report_exports**](AnalyticsApi.md#list_report_exports) | **GET** /{workspaceUuid}/reports/exports | List report exports
[**update_report_branding**](AnalyticsApi.md#update_report_branding) | **PUT** /{workspaceUuid}/report-branding | Update the report branding
[**upload_report_branding_logo**](AnalyticsApi.md#upload_report_branding_logo) | **POST** /{workspaceUuid}/report-branding/logo | Upload the report logo



## create_report_export

> models::CreateReportExport201Response create_report_export(workspace_uuid, report_export_input)
Create a report export

Generates a report for a period (default `last_month`) or a custom `date_from`/`date_to` range: a branded PDF (summary, accounts, top 10 posts; the header uses the report branding) or a CSV with one row per published post and account (`dataset: posts`, default) or per account (`dataset: accounts`). CSV files are UTF-8 with a byte order mark. At most 500 posts per report. The file is ready when the call returns; fetch it from `download_url` with the same token. Admins and members only; 20 per minute. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**report_export_input** | [**ReportExportInput**](ReportExportInput.md) |  | [required] |

### Return type

[**models::CreateReportExport201Response**](createReportExport_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## download_report_export

> std::path::PathBuf download_report_export(workspace_uuid, export_uuid)
Download a report file

The PDF or CSV file. `410` once it expired (7 days) or if the export failed.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**export_uuid** | **uuid::Uuid** | UUID of the report export. | [required] |

### Return type

[**std::path::PathBuf**](std::path::PathBuf.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/pdf, text/csv, application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


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


## get_report_branding

> models::GetReportBranding200Response get_report_branding(workspace_uuid)
Get the report branding

The white-label header of the workspace's PDF reports. Unset fields are `null`; the workspace name is used then.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::GetReportBranding200Response**](getReportBranding_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_report_export

> models::CreateReportExport201Response get_report_export(workspace_uuid, export_uuid)
Get a report export

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**export_uuid** | **uuid::Uuid** | UUID of the report export. | [required] |

### Return type

[**models::CreateReportExport201Response**](createReportExport_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_report_exports

> models::ListReportExports200Response list_report_exports(workspace_uuid)
List report exports

The workspace's latest 50 report exports, newest first. Files can be downloaded for 7 days.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListReportExports200Response**](listReportExports_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_report_branding

> models::GetReportBranding200Response update_report_branding(workspace_uuid, report_branding_input)
Update the report branding

Name, colour and footer of PDF reports. Fields you leave out keep their value. Upload the logo with `uploadReportBrandingLogo`. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**report_branding_input** | [**ReportBrandingInput**](ReportBrandingInput.md) |  | [required] |

### Return type

[**models::GetReportBranding200Response**](getReportBranding_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## upload_report_branding_logo

> models::GetReportBranding200Response upload_report_branding_logo(workspace_uuid, logo)
Upload the report logo

PNG or JPEG, up to 1 MB (SVG is not accepted). Replaces the current logo. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**logo** | **std::path::PathBuf** |  | [required] |

### Return type

[**models::GetReportBranding200Response**](getReportBranding_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \CompetitorsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_competitor**](CompetitorsApi.md#add_competitor) | **POST** /{workspaceUuid}/competitors | Track a competitor
[**delete_competitor**](CompetitorsApi.md#delete_competitor) | **DELETE** /{workspaceUuid}/competitors/{competitorId} | Stop tracking a competitor
[**get_competitor**](CompetitorsApi.md#get_competitor) | **GET** /{workspaceUuid}/competitors/{competitorId} | Get a competitor
[**list_competitors**](CompetitorsApi.md#list_competitors) | **GET** /{workspaceUuid}/competitors | List competitors



## add_competitor

> models::AddCompetitor202Response add_competitor(workspace_uuid, competitor_input)
Track a competitor

Starts tracking a public Instagram business or creator account from one of your Instagram accounts (connected through a Facebook Page). Returns `202` at once; followers, snapshots and recent media appear after the background import. `409` if that account already tracks the username. Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**competitor_input** | [**CompetitorInput**](CompetitorInput.md) |  | [required] |

### Return type

[**models::AddCompetitor202Response**](addCompetitor_202_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_competitor

> delete_competitor(workspace_uuid, competitor_id)
Stop tracking a competitor

Deletes the competitor with its snapshots and media. Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**competitor_id** | **i32** | The competitor `id`. | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_competitor

> models::GetCompetitor200Response get_competitor(workspace_uuid, competitor_id)
Get a competitor

The competitor with daily follower snapshots for the last 90 days and its 12 most recent posts. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**competitor_id** | **i32** | The competitor `id`. | [required] |

### Return type

[**models::GetCompetitor200Response**](getCompetitor_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_competitors

> models::ListCompetitors200Response list_competitors(workspace_uuid, account_id)
List competitors

Instagram business or creator accounts the workspace tracks, by follower count. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_id** | Option<**i32**> | Only competitors tracked from this Instagram account `id`. |  |

### Return type

[**models::ListCompetitors200Response**](listCompetitors_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


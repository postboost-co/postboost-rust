# \TemplatesApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_template**](TemplatesApi.md#create_template) | **POST** /{workspaceUuid}/templates | Create a template
[**delete_template**](TemplatesApi.md#delete_template) | **DELETE** /{workspaceUuid}/templates/{templateId} | Delete a template
[**get_template**](TemplatesApi.md#get_template) | **GET** /{workspaceUuid}/templates/{templateId} | Get a template
[**list_templates**](TemplatesApi.md#list_templates) | **GET** /{workspaceUuid}/templates | List templates
[**update_template**](TemplatesApi.md#update_template) | **PUT** /{workspaceUuid}/templates/{templateId} | Update a template



## create_template

> models::CreateTemplate201Response create_template(workspace_uuid, template_input)
Create a template

Creates a post template: a name and one or more content items (body plus media ids from the media library). Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**template_input** | [**TemplateInput**](TemplateInput.md) |  | [required] |

### Return type

[**models::CreateTemplate201Response**](createTemplate_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_template

> delete_template(workspace_uuid, template_id)
Delete a template

Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**template_id** | **String** | The template `id`. | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_template

> models::CreateTemplate201Response get_template(workspace_uuid, template_id)
Get a template

One template. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**template_id** | **String** | The template `id`. | [required] |

### Return type

[**models::CreateTemplate201Response**](createTemplate_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_templates

> models::ListTemplates200Response list_templates(workspace_uuid, page, per_page)
List templates

Post templates of the workspace, newest first. The same templates as the Templates page in the app. Paginated with `page` and `per_page` (default 100). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> | Page number (1-based). |  |[default to 1]
**per_page** | Option<**i32**> | Items per page, 1-100. |  |[default to 100]

### Return type

[**models::ListTemplates200Response**](listTemplates_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_template

> models::CreateTemplate201Response update_template(workspace_uuid, template_id, template_input)
Update a template

Replaces the name and content of a template. Admins and members only (not viewers). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**template_id** | **String** | The template `id`. | [required] |
**template_input** | [**TemplateInput**](TemplateInput.md) |  | [required] |

### Return type

[**models::CreateTemplate201Response**](createTemplate_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


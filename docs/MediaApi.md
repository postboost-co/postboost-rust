# \MediaApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**abort_chunked_upload**](MediaApi.md#abort_chunked_upload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
[**complete_chunked_upload**](MediaApi.md#complete_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
[**delete_media_bulk**](MediaApi.md#delete_media_bulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
[**get_media**](MediaApi.md#get_media) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
[**get_remote_upload_status**](MediaApi.md#get_remote_upload_status) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
[**initiate_chunked_upload**](MediaApi.md#initiate_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
[**initiate_remote_upload**](MediaApi.md#initiate_remote_upload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
[**list_media**](MediaApi.md#list_media) | **GET** /{workspaceUuid}/media | List media
[**update_media**](MediaApi.md#update_media) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
[**upload_chunk**](MediaApi.md#upload_chunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
[**upload_media**](MediaApi.md#upload_media) | **POST** /{workspaceUuid}/media | Upload media (binary)



## abort_chunked_upload

> abort_chunked_upload(workspace_uuid, upload_uuid)
Abort chunked upload

Cancel an in-progress chunked upload session and clean up uploaded chunks.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**upload_uuid** | **uuid::Uuid** |  | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## complete_chunked_upload

> models::Media complete_chunked_upload(workspace_uuid, upload_uuid)
Complete chunked upload

Signal that all chunks have been uploaded. Returns the final media object.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**upload_uuid** | **uuid::Uuid** |  | [required] |

### Return type

[**models::Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_media_bulk

> serde_json::Value delete_media_bulk(workspace_uuid, delete_media_bulk_request)
Delete media (bulk)

Delete one or more media items by their IDs.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**delete_media_bulk_request** | [**DeleteMediaBulkRequest**](DeleteMediaBulkRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_media

> models::Media get_media(workspace_uuid, media_uuid)
Get media

Returns a single media asset.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**media_uuid** | **uuid::Uuid** | UUID of the media asset. | [required] |

### Return type

[**models::Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_remote_upload_status

> models::GetRemoteUploadStatus200Response get_remote_upload_status(workspace_uuid, download_id)
Get remote upload status

Poll the status of an in-progress remote media download.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**download_id** | **String** |  | [required] |

### Return type

[**models::GetRemoteUploadStatus200Response**](getRemoteUploadStatus_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## initiate_chunked_upload

> models::InitiateChunkedUpload200Response initiate_chunked_upload(workspace_uuid, initiate_chunked_upload_request)
Initiate chunked upload

Start a chunked upload session for large files. Returns an `upload_uuid`, `chunk_size`, and `total_chunks` to use for subsequent chunk requests. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**initiate_chunked_upload_request** | [**InitiateChunkedUploadRequest**](InitiateChunkedUploadRequest.md) |  | [required] |

### Return type

[**models::InitiateChunkedUpload200Response**](initiateChunkedUpload_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## initiate_remote_upload

> models::InitiateRemoteUpload200Response initiate_remote_upload(workspace_uuid, initiate_remote_upload_request)
Initiate remote upload

Download a file from a remote URL into the media library. For small files the media object is returned immediately. For large files a `download_id` is returned — poll the status endpoint. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**initiate_remote_upload_request** | [**InitiateRemoteUploadRequest**](InitiateRemoteUploadRequest.md) |  | [required] |

### Return type

[**models::InitiateRemoteUpload200Response**](initiateRemoteUpload_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_media

> models::ListMedia200Response list_media(workspace_uuid, page)
List media

Returns a paginated list of media assets in the workspace library.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> | Page number (20 items per page). |  |[default to 1]

### Return type

[**models::ListMedia200Response**](listMedia_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_media

> serde_json::Value update_media(workspace_uuid, media_uuid, update_media_request)
Update media

Update the alt text of a media asset.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**media_uuid** | **uuid::Uuid** | UUID of the media asset. | [required] |
**update_media_request** | [**UpdateMediaRequest**](UpdateMediaRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## upload_chunk

> models::UploadChunk200Response upload_chunk(workspace_uuid, upload_uuid, chunk, chunk_index)
Upload a chunk

Upload a single chunk of a chunked upload session.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**upload_uuid** | **uuid::Uuid** |  | [required] |
**chunk** | **std::path::PathBuf** |  | [required] |
**chunk_index** | **i32** | Zero-based index of this chunk. | [required] |

### Return type

[**models::UploadChunk200Response**](uploadChunk_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## upload_media

> models::Media upload_media(workspace_uuid, file, alt_text)
Upload media (binary)

Upload a file directly as multipart form data.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**file** | **std::path::PathBuf** | The file to upload. | [required] |
**alt_text** | Option<**String**> | Alternative text for accessibility. |  |

### Return type

[**models::Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


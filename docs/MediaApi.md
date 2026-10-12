# \MediaApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**abort_chunked_upload**](MediaApi.md#abort_chunked_upload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
[**complete_chunked_upload**](MediaApi.md#complete_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
[**create_media_folder**](MediaApi.md#create_media_folder) | **POST** /{workspaceUuid}/media/folders | Create media folder
[**delete_media_bulk**](MediaApi.md#delete_media_bulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
[**delete_media_folder**](MediaApi.md#delete_media_folder) | **DELETE** /{workspaceUuid}/media/folders/{folderUuid} | Delete media folder
[**get_media**](MediaApi.md#get_media) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
[**get_remote_upload_status**](MediaApi.md#get_remote_upload_status) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
[**initiate_chunked_upload**](MediaApi.md#initiate_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
[**initiate_remote_upload**](MediaApi.md#initiate_remote_upload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
[**list_media**](MediaApi.md#list_media) | **GET** /{workspaceUuid}/media | List media
[**list_media_folders**](MediaApi.md#list_media_folders) | **GET** /{workspaceUuid}/media/folders | List media folders
[**update_media**](MediaApi.md#update_media) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
[**update_media_folder**](MediaApi.md#update_media_folder) | **PUT** /{workspaceUuid}/media/folders/{folderUuid} | Update media folder
[**upload_chunk**](MediaApi.md#upload_chunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
[**upload_media**](MediaApi.md#upload_media) | **POST** /{workspaceUuid}/media | Upload media (binary)
[**upload_media_base64**](MediaApi.md#upload_media_base64) | **POST** /{workspaceUuid}/media/base64 | Upload media (base64 JSON)



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

> models::Media complete_chunked_upload(workspace_uuid, upload_uuid, complete_chunked_upload_request)
Complete chunked upload

Signal that all chunks have been uploaded. Returns the final media object. A video may come back with `is_processing` set to `true` while its conversion runs.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**upload_uuid** | **uuid::Uuid** |  | [required] |
**complete_chunked_upload_request** | Option<[**CompleteChunkedUploadRequest**](CompleteChunkedUploadRequest.md)> |  |  |

### Return type

[**models::Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_media_folder

> models::MediaFolder create_media_folder(workspace_uuid, create_media_folder_request, idempotency_key)
Create media folder

Creates a folder at the top level or under `parent`. The name must be unique among its siblings.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**create_media_folder_request** | [**CreateMediaFolderRequest**](CreateMediaFolderRequest.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::MediaFolder**](MediaFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_media_bulk

> serde_json::Value delete_media_bulk(workspace_uuid, delete_media_bulk_request)
Delete media (bulk)

Delete one or more media items by their numeric IDs or UUIDs (both may be mixed, up to 500 per request).

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


## delete_media_folder

> serde_json::Value delete_media_folder(workspace_uuid, folder_uuid, delete_media_folder_request)
Delete media folder

Deletes a folder. By default its media and sub-folders move up to the folder's parent; with `delete_media` set to true every media item below the folder is deleted as well.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**folder_uuid** | **uuid::Uuid** | UUID of the media folder. | [required] |
**delete_media_folder_request** | Option<[**DeleteMediaFolderRequest**](DeleteMediaFolderRequest.md)> |  |  |

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

> models::InitiateChunkedUpload201Response initiate_chunked_upload(workspace_uuid, initiate_chunked_upload_request, idempotency_key)
Initiate chunked upload

Start a chunked upload session for large files. Returns an `upload_uuid`, `chunk_size`, and `total_chunks` to use for subsequent chunk requests. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**initiate_chunked_upload_request** | [**InitiateChunkedUploadRequest**](InitiateChunkedUploadRequest.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::InitiateChunkedUpload201Response**](initiateChunkedUpload_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## initiate_remote_upload

> models::InitiateRemoteUpload201Response initiate_remote_upload(workspace_uuid, initiate_remote_upload_request, idempotency_key)
Initiate remote upload

Download a file from a remote URL into the media library. For small files the media object is returned immediately. For large files a `download_id` is returned — poll the status endpoint. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**initiate_remote_upload_request** | [**InitiateRemoteUploadRequest**](InitiateRemoteUploadRequest.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::InitiateRemoteUpload201Response**](initiateRemoteUpload_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_media

> models::ListMedia200Response list_media(workspace_uuid, page, limit, folder, mime_types_left_square_bracket_right_square_bracket, r#type, keyword, usage, favorite, sort)
List media

Returns a paginated list of media assets in the workspace library. Without `folder` every item is listed, whatever folder it is filed in. A `keyword` search always looks at the whole library and ignores `folder` and `favorite`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> | Page number. |  |[default to 1]
**limit** | Option<**i32**> | Items per page. Values below 1 fall back to 50; values above 100 are capped at 100. |  |[default to 50]
**folder** | Option<**String**> | Media folder UUID, or `root` for items not filed in any folder. |  |
**mime_types_left_square_bracket_right_square_bracket** | Option<[**Vec<String>**](String.md)> | Only these MIME types (for example `image/png`). |  |
**r#type** | Option<**String**> | Only this media type. |  |
**keyword** | Option<**String**> | Search media by name. |  |
**usage** | Option<**String**> | Filter by how the media is used in posts. |  |
**favorite** | Option<**bool**> | When `true`, only media the caller marked as favorite. |  |
**sort** | Option<**String**> |  |  |[default to newest]

### Return type

[**models::ListMedia200Response**](listMedia_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_media_folders

> models::ListMediaFolders200Response list_media_folders(workspace_uuid)
List media folders

Returns the whole folder tree of the media library in one response (not paginated). Rebuild the tree from each folder's `parent`.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListMediaFolders200Response**](listMediaFolders_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_media

> serde_json::Value update_media(workspace_uuid, media_uuid, update_media_request)
Update media

Update the name, alt text, or folder of a media asset. Only the keys present in the body are written. Sending `folder: null` moves the item to the library root; omitting `folder` leaves it where it is. 

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


## update_media_folder

> models::MediaFolder update_media_folder(workspace_uuid, folder_uuid, media_folder_input)
Update media folder

Renames a folder and/or moves it. Sending `parent` moves the folder (null = top level); omitting it keeps the current parent. A folder cannot be moved into itself or one of its descendants.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**folder_uuid** | **uuid::Uuid** | UUID of the media folder. | [required] |
**media_folder_input** | [**MediaFolderInput**](MediaFolderInput.md) |  | [required] |

### Return type

[**models::MediaFolder**](MediaFolder.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## upload_chunk

> models::UploadChunk201Response upload_chunk(workspace_uuid, upload_uuid, chunk, chunk_index)
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

[**models::UploadChunk201Response**](uploadChunk_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## upload_media

> models::Media upload_media(workspace_uuid, file, idempotency_key, alt_text, folder)
Upload media (binary)

Upload a file directly as multipart form data. Images and videos, plus a PDF (up to 100 MB) for LinkedIn document posts: a post that attaches a PDF must have it as the only media item and may only go to LinkedIn profiles and pages. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**file** | **std::path::PathBuf** | The file to upload. | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |
**alt_text** | Option<**String**> | Alternative text for accessibility. |  |
**folder** | Option<**uuid::Uuid**> | UUID of the media folder to file the upload in. Omit or null for the library root. |  |

### Return type

[**models::Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: multipart/form-data
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## upload_media_base64

> models::Media upload_media_base64(workspace_uuid, media_base64_input, idempotency_key)
Upload media (base64 JSON)

Upload a file as base64 inside a JSON body, for agents and tools that cannot send multipart form data. The decoded file is checked exactly like `POST media` (allowed types and size limits; a PDF is accepted for LinkedIn document posts). Decoded size is capped at 20 MB; for larger files use remote upload by URL or chunked upload. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**media_base64_input** | [**MediaBase64Input**](MediaBase64Input.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::Media**](Media.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


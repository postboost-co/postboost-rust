# GetRemoteUploadStatus200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **String** |  | 
**progress** | **i32** | Percent done. It stays `0` until the file is stored and is `100` once `status` is `completed`, so poll on `status`. | 
**media** | Option<[**models::Media**](Media.md)> | Present when `status` is `completed` (absent if the item was deleted before this poll). | [optional]
**error** | Option<**String**> | Why the download failed. Present when `status` is `failed`. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



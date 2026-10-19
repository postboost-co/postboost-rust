# InitiateRemoteUpload200Response

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **String** | `completed` and `failed` are final; `pending` means the file downloads in the background. | 
**media** | Option<[**models::Media**](Media.md)> | Present when `status` is `completed`. This copy has no `size`; `getMedia` returns it. | [optional]
**error** | Option<**String**> | Why the download failed. Present when `status` is `failed`. | [optional]
**download_id** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | Present when `status` is `pending`. Pass it to `getRemoteUploadStatus`. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



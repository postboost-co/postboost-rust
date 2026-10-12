# MediaBase64Input

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**content** | **String** | The file as base64. A `data:<mime>;base64,` prefix is accepted. At most 20 MB once decoded. | 
**filename** | **String** | File name with extension, for example `cover.png`. No folders. | 
**alt_text** | Option<**String**> | Alternative text for accessibility. | [optional]
**folder** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | UUID of the media folder to file the upload in. Omit or null for the library root. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



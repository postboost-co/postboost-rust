# ImagePromptInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**caption** | **String** |  | 
**platform** | **String** |  | 
**template** | Option<**String**> |  | [optional]
**style** | Option<**String**> |  | [optional]
**brand_voice** | Option<**String**> | Free-text tone for the image. When sent, it replaces the stored workspace brand voice for this call. | [optional]
**use_brand_voice** | Option<**bool**> | When `brand_voice` is not sent, derive the image tone from the workspace brand voice. Ignored in developer mode (`prompt`). | [optional][default to true]
**custom_instructions** | Option<**String**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



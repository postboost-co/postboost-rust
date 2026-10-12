# ImageGenerateInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**caption** | Option<**String**> | Social media caption. Triggers standard mode. Takes priority over prompt. | [optional]
**platform** | Option<**String**> | Required when caption is provided. | [optional]
**template** | Option<**String**> |  | [optional]
**style** | Option<**String**> |  | [optional]
**brand_voice** | Option<**String**> | Free-text tone for the image. When sent, it replaces the stored workspace brand voice for this call. | [optional]
**use_brand_voice** | Option<**bool**> | When `brand_voice` is not sent, derive the image tone from the workspace brand voice. Ignored in developer mode (`prompt`). | [optional][default to true]
**custom_instructions** | Option<**String**> |  | [optional]
**prompt** | Option<**String**> | Developer escape hatch. Bypasses internal prompt builder. Ignored if caption is present. | [optional]
**aspect_ratio** | Option<**String**> |  | [optional][default to Variant1Colon1]
**count** | Option<**i32**> |  | [optional][default to 1]
**quality** | Option<**String**> |  | [optional][default to Standard]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



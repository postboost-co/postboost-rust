# ImageEditInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**media_uuid** | [**uuid::Uuid**](uuid::Uuid.md) | UUID of the source media item to edit | 
**prompt** | **String** | Describe what to change in the image | 
**mask_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | UUID of a mask image. Transparent areas will be edited. | [optional]
**aspect_ratio** | Option<**String**> |  | [optional][default to Variant1Colon1]
**count** | Option<**i32**> |  | [optional][default to 1]
**quality** | Option<**String**> |  | [optional][default to Standard]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



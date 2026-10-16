# ImageGenerationResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**images** | [**Vec<models::Media>**](Media.md) |  | 
**prompt_used** | **String** |  | 
**revised_prompt** | Option<**String**> |  | [optional]
**aspect_ratio** | **String** |  | 
**quality** | **String** |  | 
**credits_used** | **i32** | Text credits only. 0 while the image credit pool is on; `count × credit_weight` when it is switched off. | 
**credits_remaining** | Option<**i32**> | Text credits left this billing cycle (null = no limit). | [optional]
**image_credits_used** | **i32** | Image credits this call spent (1 per image; 0 when the image credit pool is switched off). | 
**image_credits_remaining** | Option<**i32**> | Image credits left this month (null = no limit, or the image credit pool is switched off). | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



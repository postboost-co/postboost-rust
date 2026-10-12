# RepurposeResult

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source** | [**models::RepurposeResultSource**](RepurposeResult_source.md) |  | 
**captions** | [**Vec<models::BlogToSocialCaption>**](BlogToSocialCaption.md) |  | 
**slides** | [**Vec<models::RepurposeSlide>**](RepurposeSlide.md) | Carousel slides in order (hook first, call to action last). Empty without a carousel. | 
**media** | Option<[**models::RepurposeResultMedia**](RepurposeResult_media.md)> |  | [optional]
**post_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | The draft post; null when `create_post` was false. | 
**credits_used** | **i32** |  | 
**credits_remaining** | Option<**i32**> | Null for unlimited plans. | 
**warnings** | **Vec<String>** | Parts that were skipped (for example a network that gets no carousel). | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



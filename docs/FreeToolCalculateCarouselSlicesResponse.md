# FreeToolCalculateCarouselSlicesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**slides** | Option<[**Vec<models::FreeToolCalculateCarouselSlicesResponseSlidesInner>**](FreeToolCalculateCarouselSlicesResponse_slides_inner.md)> | The part of the source image each slide shows, left to right, in source pixels. | [optional]
**output** | Option<[**models::FreeToolCalculateCarouselSlicesResponseOutput**](FreeToolCalculateCarouselSlicesResponse_output.md)> |  | [optional]
**scale** | Option<**f64**> | Output pixels per source pixel, 4 decimals. | [optional]
**upscaled** | Option<**bool**> | True when the source is enlarged (scale above 1), which can look soft. | [optional]
**warnings** | Option<**Vec<String>**> | Upscaling and how much of the source is cropped away. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



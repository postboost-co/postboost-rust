# FreeToolBuildLinkedinCarouselRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **String** | The post or outline. Blank lines separate slides; a first line starting with # (or a short first line without closing punctuation that is not a list item) is the slide heading; - * • lines become bullets. | 
**max_slides** | Option<**i32**> | Most slides to return, 3 to 20. The cover and the CTA slide are always kept. | [optional][default to 10]
**size** | Option<**String**> | Slide shape: `4:5` (1080 × 1350) or `1:1` (1080 × 1080). Every page of a LinkedIn document has the same size. | [optional][default to Variant4Colon5]
**cover** | Option<**bool**> | Start with a cover slide: the first heading, or the first line of the text. | [optional][default to true]
**cta** | Option<**String**> | Text of a closing call-to-action slide. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



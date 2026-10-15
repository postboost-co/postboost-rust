# FreeToolCalculateCropRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**width** | **i32** | Source image width in pixels. | 
**height** | **i32** | Source image height in pixels. | 
**network** | Option<**String**> | Network key from getImageSizes (`network_key`), e.g. `instagram`. With `format`, picks the target size. | [optional]
**format** | Option<**String**> | Format key from getImageSizes (`format_key`), e.g. `feed-square`. | [optional]
**target_width** | Option<**i32**> | Target width in pixels, instead of `network` + `format`. | [optional]
**target_height** | Option<**i32**> | Target height in pixels, instead of `network` + `format`. | [optional]
**fit** | Option<**String**> | `cover` crops to fill the target; `contain` keeps the whole image and centres it. | [optional][default to Cover]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



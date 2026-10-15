# FreeToolGetImageSizesResponseSizesInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | Option<**String**> | Network name. | [optional]
**network_key** | Option<**String**> | Key for `network` here and in calculateCrop. | [optional]
**placement** | Option<**String**> | Where the image appears. | [optional]
**format_key** | Option<**String**> | Key for `format` in calculateCrop. | [optional]
**size** | Option<**String**> | The size as the network states it, ranges included. | [optional]
**width** | Option<**i32**> | Recommended width in pixels, when the size is one fixed size. | [optional]
**height** | Option<**i32**> | Recommended height in pixels, when the size is one fixed size. | [optional]
**ratio** | Option<**String**> | Aspect ratio. | [optional]
**limits** | Option<**String**> | File type and size limits. | [optional]
**basis** | Option<**String**> | `official` when the network itself states it, else how it was found. | [optional]
**source** | Option<**String**> | URL of the source. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



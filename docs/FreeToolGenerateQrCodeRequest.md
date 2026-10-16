# FreeToolGenerateQrCodeRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**data** | **String** | The link or text to encode. | 
**utm** | Option<[**models::FreeToolGenerateQrCodeRequestUtm**](FreeToolGenerateQrCodeRequest_utm.md)> |  | [optional]
**error_correction** | Option<**String**> | How much of the code can be damaged and still scan: L 7%, M 15%, Q 25%, H 30%. | [optional][default to M]
**size** | Option<**i32**> | Width and height of the SVG in pixels. | [optional][default to 512]
**foreground** | Option<**String**> | Colour of the modules, #RRGGBB. | [optional][default to #000000]
**background** | Option<**String**> | Background colour, #RRGGBB. | [optional][default to #FFFFFF]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



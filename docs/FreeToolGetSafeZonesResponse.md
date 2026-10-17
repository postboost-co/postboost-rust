# FreeToolGetSafeZonesResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**platform** | Option<**String**> |  | [optional]
**label** | Option<**String**> | Platform name. | [optional]
**width** | Option<**i32**> |  | [optional]
**height** | Option<**i32**> |  | [optional]
**unsafe_areas** | Option<[**Vec<models::FreeToolGetSafeZonesResponseUnsafeAreasInner>**](FreeToolGetSafeZonesResponse_unsafe_areas_inner.md)> | Areas the app's UI usually covers, in frame pixels from the top-left corner. Edges are scaled from 1080 × 1920 and rounded to the nearest pixel (halves up), so neighbouring boxes stay edge to edge. | [optional]
**safe_area** | Option<[**models::FreeToolGetSafeZonesResponseSafeArea**](FreeToolGetSafeZonesResponse_safe_area.md)> |  | [optional]
**source** | Option<[**models::FreeToolGetSafeZonesResponseSource**](FreeToolGetSafeZonesResponse_source.md)> |  | [optional]
**last_verified** | Option<**String**> | Date the sources were last checked (YYYY-MM-DD). | [optional]
**caveat** | Option<**String**> |  | [optional]
**warnings** | Option<**Vec<String>**> | Set when the frame is not 9:16, so the boxes are stretched. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



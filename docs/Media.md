# Media

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**name** | **String** |  | 
**mime_type** | **String** |  | 
**r#type** | **String** |  | 
**url** | **String** |  | 
**thumb_url** | Option<**String**> |  | [optional]
**is_video** | **bool** |  | 
**is_processing** | Option<**bool**> | True while an uploaded video is still being converted. | [optional]
**width** | Option<**i32**> | Width in pixels, when stored. | [optional]
**height** | Option<**i32**> | Height in pixels, when stored. | [optional]
**duration_ms** | Option<**i32**> | Video duration in milliseconds; null for images or videos not read yet. | [optional]
**size** | Option<**i32**> | File size in bytes. | [optional]
**alt_text** | Option<**String**> |  | [optional]
**folder** | Option<[**models::MediaFolderRef**](MediaFolderRef.md)> |  | [optional]
**created_at** | **String** |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



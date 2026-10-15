# FreeToolCheckPostResponseNetworksInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | Option<**String**> |  | [optional]
**label** | Option<**String**> |  | [optional]
**ok** | Option<**bool**> | False when an error would stop the post from publishing. | [optional]
**count** | Option<**i32**> | Characters as this network counts them. | [optional]
**limit** | Option<**i32**> |  | [optional]
**errors** | Option<[**Vec<models::FreeToolCheckPostResponseNetworksInnerErrorsInner>**](FreeToolCheckPostResponse_networks_inner_errors_inner.md)> | Codes: too_long, too_many_hashtags, media_required, too_many_media, media_type, video_too_long, video_too_short. | [optional]
**warnings** | Option<[**Vec<models::FreeToolCheckPostResponseNetworksInnerErrorsInner>**](FreeToolCheckPostResponse_networks_inner_errors_inner.md)> | Codes: cut_by_fold, link_not_clickable. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



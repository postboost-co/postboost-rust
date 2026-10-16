# FreeToolCheckLinkPreviewResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**final_url** | Option<**String**> | The URL after redirects. | [optional]
**status** | Option<**i32**> | HTTP status of the final response. | [optional]
**redirects** | Option<[**Vec<models::FreeToolCheckLinkPreviewResponseRedirectsInner>**](FreeToolCheckLinkPreviewResponse_redirects_inner.md)> |  | [optional]
**content_type** | Option<**String**> |  | [optional]
**tags** | Option<[**models::FreeToolCheckLinkPreviewResponseTags**](FreeToolCheckLinkPreviewResponse_tags.md)> |  | [optional]
**image** | Option<[**models::FreeToolCheckLinkPreviewResponseImage**](FreeToolCheckLinkPreviewResponse_image.md)> |  | [optional]
**previews** | Option<[**std::collections::HashMap<String, models::FreeToolCheckLinkPreviewResponsePreviewsValue>**](FreeToolCheckLinkPreviewResponse_previews_value.md)> | The card each network would show. | [optional]
**warnings** | Option<**Vec<String>**> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



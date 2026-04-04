# BlogToSocialResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**blog_title** | Option<**String**> | The blog post title (scraped or provided directly). | [optional]
**blog_excerpt** | Option<**String**> | A short excerpt from the blog post content. | [optional]
**captions** | Option<[**Vec<models::BlogToSocialCaption>**](BlogToSocialCaption.md)> | Generated captions, one per target account. | [optional]
**post_uuid** | Option<[**uuid::Uuid**](uuid::Uuid.md)> | UUID of the created draft post. Only present when `create_post` was `true`. | [optional]
**media** | Option<[**models::BlogToSocialMedia**](BlogToSocialMedia.md)> |  | [optional]
**credits_used** | Option<**i32**> | Number of AI credits consumed by this request (one per successful caption). | [optional]
**credits_remaining** | Option<**i32**> | Remaining AI credits for the current billing period. `null` for unlimited plans. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



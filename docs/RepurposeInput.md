# RepurposeInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**source_type** | **String** |  | 
**url** | Option<**String**> | Article URL (`url`) or YouTube video URL (`youtube`). For `text`, an optional link to mention. | [optional]
**pdf_url** | Option<**String**> | Public URL of a PDF (`pdf`), at most 20 MB. | [optional]
**title** | Option<**String**> | Required for `text`. For `youtube`, overrides the video title. | [optional]
**text** | Option<**String**> | Required for `text`. Long sources are cut to about 12,000 characters. | [optional]
**transcript** | Option<**String**> | Video transcript for `youtube`. | [optional]
**platforms** | Option<**Vec<String>**> | Limit to connected accounts of these networks. Ignored when `account_ids` is set. | [optional]
**account_ids** | Option<**Vec<i32>**> | Target accounts. Default is every connected account. | [optional]
**tone** | Option<**String**> |  | [optional][default to Engaging]
**content_length** | Option<**String**> |  | [optional][default to Medium]
**hashtags** | Option<**String**> |  | [optional][default to Few]
**cta** | Option<**String**> |  | [optional][default to None]
**language** | Option<**String**> |  | [optional][default to auto]
**custom_instructions** | Option<**String**> |  | [optional]
**carousel** | Option<**bool**> | Render carousel slides (one extra AI credit for the outline). | [optional][default to true]
**slide_count** | Option<**i32**> | Total slides including the hook and call-to-action slides. | [optional][default to 7]
**theme** | Option<[**models::RepurposeInputTheme**](RepurposeInput_theme.md)> |  | [optional]
**create_post** | Option<**bool**> | Create the draft post. `false` returns captions and slides only. | [optional][default to true]
**use_brand_voice** | Option<**bool**> |  | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



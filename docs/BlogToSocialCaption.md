# BlogToSocialCaption

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | Option<**i32**> | ID of the social account this caption was generated for. | [optional]
**provider** | Option<**String**> | Social media platform identifier. | [optional]
**content** | Option<**String**> | The generated caption text. `null` if generation failed for this account. | [optional]
**character_count** | Option<**i32**> | Character count of the generated content. `null` if generation failed. | [optional]
**character_limit** | Option<**i32**> | Maximum allowed character count for this platform. | [optional]
**error** | Option<**String**> | Error message if caption generation failed for this account. `null` on success. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



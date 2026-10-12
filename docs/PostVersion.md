# PostVersion

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account_id** | **i32** | Use `0` for the original/default version. | 
**is_original** | **bool** | Must be `true` for the first version. | 
**synced_with** | Option<**i32**> | Account ID of the version this version follows (`0` = the original), or null when it is edited independently. Ignored on the original version. | [optional]
**content** | [**Vec<models::PostContent>**](PostContent.md) | Ordered content items. Item 0 is the post. Item 1 is the first comment on Facebook Page, Instagram and LinkedIn, or the next thread post on X, Threads, Bluesky, Mastodon and Pixelfed. See `PostContent`.  | 
**options** | Option<[**models::PostVersionOptions**](PostVersion_options.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



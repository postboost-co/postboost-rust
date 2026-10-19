# FreeToolBuildHashtagGroupsRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **String** | Hashtags or words, separated by spaces, commas or new lines. A missing # is added. | 
**network** | Option<**String**> | Network whose hashtag cap applies. | [optional][default to Instagram]
**group_size** | Option<**i32**> | Hashtags per group. Default: the network's cap, or 5 when it has no hard cap. | [optional]
**case** | Option<**String**> | keep the first spelling of each hashtag, or lower-case all of them. | [optional][default to Keep]
**format** | Option<**String**> | inline: one line of tags. first_comment: five \".\" lines, then the tags. | [optional][default to Inline]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



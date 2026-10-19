# FreeToolBuildHashtagGroupsResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**hashtags** | Option<**Vec<String>**> | Clean hashtags in input order, duplicates removed. | [optional]
**removed** | Option<[**Vec<models::FreeToolBuildHashtagGroupsResponseRemovedInner>**](FreeToolBuildHashtagGroupsResponse_removed_inner.md)> | Entries that were dropped, with the reason. | [optional]
**cap** | Option<**i32**> | Hashtags PostBoost allows per post on the network; null = no hard limit. | [optional]
**group_size** | Option<**i32**> | Hashtags per group that was used. | [optional]
**groups** | Option<[**Vec<models::FreeToolBuildHashtagGroupsResponseGroupsInner>**](FreeToolBuildHashtagGroupsResponse_groups_inner.md)> |  | [optional]
**over_cap** | Option<**bool**> | A group holds more hashtags than the cap. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



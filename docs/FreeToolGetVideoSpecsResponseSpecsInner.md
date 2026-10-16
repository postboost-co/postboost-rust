# FreeToolGetVideoSpecsResponseSpecsInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**network** | Option<**String**> | Network name. | [optional]
**network_key** | Option<**String**> | Key for `network`. | [optional]
**placement** | Option<**String**> | Placement; `(app)` and `(publishing API)` rows differ where the network says so. | [optional]
**placement_key** | Option<**String**> | Key for `placement`. | [optional]
**ratio** | Option<**String**> | Aspect ratios as the source states them. | [optional]
**resolution** | Option<**String**> | Resolution, frame rate and codec notes. | [optional]
**length** | Option<**String**> | Length limits. | [optional]
**max_size** | Option<**String**> | File size limit. | [optional]
**formats** | Option<**String**> | Container and codec formats. | [optional]
**safe_zone** | Option<**String**> | Text safe zone, only where the network publishes one. | [optional]
**basis** | Option<**String**> | `official` when the network itself states it, else how it was found. | [optional]
**sources** | Option<**Vec<String>**> | URLs of the sources. | [optional]
**limits** | Option<[**models::FreeToolGetVideoSpecsResponseSpecsInnerLimits**](FreeToolGetVideoSpecsResponse_specs_inner_limits.md)> |  | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# FreeToolPickGiveawayWinnersRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**entrants** | [**Vec<models::FreeToolPickGiveawayWinnersRequestEntrantsInner>**](FreeToolPickGiveawayWinnersRequest_entrants_inner.md) | The comments, one item each. The request body is capped at 128 KB. | 
**seed** | Option<**String**> | The secret seed, 64 hex characters (32 bytes), whose fingerprint you published before the entries closed. Without it, a seed is generated and pre_committed is false. The steps of the draw (pb-draw-v1) and a test vector are on the web tool page. | [optional]
**one_per_person** | Option<**bool**> | Count each username once. Off: every comment is an entry, so one person can win more than once. | [optional][default to true]
**keywords** | Option<**Vec<String>**> | Keep only comments that contain at least one of these, case-insensitive. | [optional][default to []]
**min_mentions** | Option<**i32**> | Keep only comments that tag at least this many other @handles. | [optional][default to 0]
**exclude** | Option<**Vec<String>**> | Usernames to leave out of the draw, such as the host account. | [optional][default to []]
**winners** | Option<**i32**> |  | [optional][default to 1]
**alternates** | Option<**i32**> | Runners-up drawn after the winners, in order. | [optional][default to 0]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



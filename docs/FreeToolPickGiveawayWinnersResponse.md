# FreeToolPickGiveawayWinnersResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**winners** | Option<**Vec<String>**> | Entrant keys in the drawn order. | [optional]
**alternates** | Option<**Vec<String>**> | Entrant keys drawn after the winners, in order. | [optional]
**entrants_before** | Option<**i32**> | Comments received. | [optional]
**entrants_after** | Option<**i32**> | Entries left after the filters: the length of entrant_list. | [optional]
**entrant_list** | Option<**Vec<String>**> | The canonical entrant list to publish: keys sorted by UTF-8 bytes. Joined with \"\\n\" it is what entrants_hash hashes. | [optional]
**entrants_hash** | Option<**String**> | SHA-256 (hex) of the canonical entrant list. | [optional]
**fingerprint** | Option<**String**> | SHA-256 (hex) of the seed bytes: what to publish before the entries close. | [optional]
**seed** | Option<**String**> | The seed used, lowercase hex. Publish it after the draw. | [optional]
**pre_committed** | Option<**bool**> | False when the seed was generated for this draw, so no fingerprint could be published before it. | [optional]
**algorithm** | Option<**String**> |  | [optional]
**warnings** | Option<[**Vec<models::FreeToolCheckPostResponseNetworksInnerErrorsInner>**](FreeToolCheckPostResponse_networks_inner_errors_inner.md)> | Codes: not_enough_entrants, not_pre_committed. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# FreeToolFormatCrossPostResponseNetworksInner

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**key** | Option<**String**> |  | [optional]
**label** | Option<**String**> |  | [optional]
**limit** | Option<**i32**> |  | [optional]
**count** | Option<**i32**> | Length as the network counts it. | [optional]
**fits** | Option<**bool**> |  | [optional]
**over_by** | Option<**i32**> | Characters over the limit; 0 when it fits. | [optional]
**links** | Option<**i32**> | Unique http(s) links in the text (trailing punctuation trimmed), as Threads counts them. | [optional]
**warnings** | Option<[**Vec<models::FreeToolCheckPostResponseNetworksInnerErrorsInner>**](FreeToolCheckPostResponse_networks_inner_errors_inner.md)> | Codes: threads_too_many_links, cut_by_fold, mentions_not_portable. | [optional]
**thread** | Option<[**Vec<models::FreeToolFormatCrossPostResponseNetworksInnerThreadInner>**](FreeToolFormatCrossPostResponse_networks_inner_thread_inner.md)> | The thread for a text that does not fit (X, Threads, Bluesky, Mastodon); null when it fits or on LinkedIn. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# FreeToolScoreSocialAuditResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**score** | Option<**i32**> | Overall score: all points over the maximum, as 0-100 rounded half up. | [optional]
**networks** | Option<[**Vec<models::FreeToolScoreSocialAuditResponseNetworksInner>**](FreeToolScoreSocialAuditResponse_networks_inner.md)> | One row per audited network, in a fixed network order. | [optional]
**top_fixes** | Option<[**Vec<models::FreeToolScoreSocialAuditResponseTopFixesInner>**](FreeToolScoreSocialAuditResponse_top_fixes_inner.md)> | Up to 3 questions with the fewest points over all audited networks (ties: checklist order); only questions answered below yes somewhere. | [optional]
**report_markdown** | Option<**String**> | The scorecard as a Markdown report: overall score, top fixes and every answer per network. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# Account

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**name** | **String** |  | 
**username** | **String** |  | 
**image** | Option<**String**> |  | [optional]
**provider** | **String** |  | 
**data** | [**serde_json::Value**](.md) | Provider-specific metadata. | 
**authorized** | **bool** |  | 
**profile_url** | Option<**String**> | Public URL of the account's profile on the network, when known. | [optional]
**publish_status** | Option<**String**> | Only present when the account is embedded in a post. Publishing state of this account for the post. | [optional]
**published_parts** | Option<**i32**> | Only present when the account is embedded in a post. How many parts (for example thread items or a first comment) are live on the network. | [optional]
**external_url** | Option<**String**> | Only present when the account is embedded in a post. URL of the published post on the network, null until it is live. | [optional]
**errors** | Option<[**Vec<models::AccountErrorsInner>**](Account_errors_inner.md)> | Only present when the account is embedded in a post. Why publishing to this account failed. A raw network error is stored as two entries: a readable line (`\"<Network>: <message> (code <code>)\"`) and an object `{platform, code, message, raw}` with the network's original response in `raw`. Other failures are a single readable string.  | [optional]
**created_at** | **String** | UTC, formatted `Y-m-d H:i:s`. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



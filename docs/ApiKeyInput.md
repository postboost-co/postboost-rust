# ApiKeyInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**name** | **String** |  | 
**abilities** | [**Vec<models::ApiKeyAbility>**](ApiKeyAbility.md) |  | 
**account_ids** | Option<**Vec<i32>**> | Limit the key to these account ids of the workspace. Omit or null for every account. A limited key must send `account_ids` on recycling rules, report exports and AI drafts, and its lists show only its accounts. | [optional]
**expires_at** | Option<[**String**](string.md)> | Last day the key works. Must be after today. Omit for no expiry. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



# AccountHealth

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**id** | **i32** |  | 
**uuid** | [**uuid::Uuid**](uuid::Uuid.md) |  | 
**name** | **String** |  | 
**provider** | **String** |  | 
**authorized** | **bool** | False when the account must be reconnected. | 
**has_token** | **bool** | Whether an access token is stored for the account. | 
**healthy** | **bool** | `authorized` and `has_token`: the account can publish. | 
**daily_cap** | [**models::AccountHealthDailyCap**](AccountHealth_daily_cap.md) |  | 
**connection** | [**models::AccountConnectionHealth**](AccountConnectionHealth.md) |  | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



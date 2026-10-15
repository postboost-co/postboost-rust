# AccountConnectionHealth

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**status** | **String** | `expired`: must be reconnected now. `expiring`: the connection hits its hard expiry within 7 days. `failing`: the latest publish attempt failed. `healthy`: none of these.  | 
**expiry_kind** | **String** | What limits the connection: `access` (the access token), `refresh` (the refresh token), `expired`, `unknown` (refreshed automatically, no known hard limit) or `none` (the network's connections do not expire on a schedule).  | 
**expires_at** | Option<**String**> | When the connection stops working unless reconnected; null without a hard expiry. | 
**days_left** | Option<**i32**> | Whole days until `expires_at` (0 = less than a day). | 
**refreshable** | **bool** | PostBoost refreshes the token automatically until the hard expiry. | 
**note** | **String** | Plain-language explanation of the prediction. | 
**reconnect_reason** | [**models::AccountConnectionHealthReconnectReason**](AccountConnectionHealth_reconnect_reason.md) |  | 
**last_success_at** | Option<**String**> | When the account last published successfully. | 
**last_error** | Option<**String**> | The error of the account's latest failed publish, shortened to 300 characters. | 
**reconnect_url** | **String** | Where a workspace member reconnects the account. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



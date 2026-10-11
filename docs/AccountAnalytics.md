# AccountAnalytics

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**account** | [**models::Account**](Account.md) |  | 
**r#type** | **String** | The analytics tab returned. | 
**tabs** | **Vec<String>** | Tabs this account supports; any of them can be passed as `type`. | 
**period** | [**models::AnalyticsPeriod**](AnalyticsPeriod.md) |  | 
**initial_sync** | [**models::AccountAnalyticsInitialSync**](AccountAnalytics_initial_sync.md) |  | 
**data** | [**std::collections::HashMap<String, serde_json::Value>**](serde_json::Value.md) | Provider- and tab-specific metrics. Chart series are lists of `{date, value}` points. | 

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



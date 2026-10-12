# RecyclingRuleSettings

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**interval_days** | **i32** | Days between copies. | 
**max_runs** | Option<**i32**> | Copies to create before the rule stops; null = no limit. | [optional]
**placement** | Option<**String**> | `queue`: each account's next free queue slot (skipped when the queue is full for 14 days). `same_time`: the source post's time of day. `draft`: a draft only. | [optional][default to Queue]
**account_ids** | Option<**Vec<i32>**> | Accounts for the copies; default the source post's accounts. For a tag pool, limits each picked post's accounts. | [optional]
**start_at** | Option<**String**> | First run; default one interval from now. | [optional]
**active** | Option<**bool**> |  | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



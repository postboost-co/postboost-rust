# ApprovePostRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**date** | Option<[**String**](string.md)> | New date for the post (Y-m-d). Use together with `time`. | [optional]
**time** | Option<**String**> | New time for the post (H:i). | [optional]
**timezone** | Option<**String**> | Timezone `date`, `time` and `accounts_schedule` are read in. Defaults to the workspace timezone. | [optional]
**accounts_schedule** | Option<[**Vec<models::AccountSchedule>**](AccountSchedule.md)> | Per-account departure times. When omitted, accounts keep their offsets from the post time. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



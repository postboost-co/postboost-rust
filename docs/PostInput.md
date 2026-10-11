# PostInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**versions** | [**Vec<models::PostVersion>**](PostVersion.md) | At least one version with `is_original: true` is required. | 
**accounts** | Option<**Vec<i32>**> | Account IDs to publish to. | [optional]
**tags** | Option<**Vec<i32>**> | Tag IDs to attach. | [optional]
**date** | Option<[**String**](string.md)> |  | [optional]
**time** | Option<**String**> |  | [optional]
**timezone** | Option<**String**> | Timezone `date`, `time` and `accounts_schedule` are read in. Defaults to the workspace timezone. | [optional]
**accounts_schedule** | Option<[**Vec<models::AccountSchedule>**](AccountSchedule.md)> | Per-account departure times. When omitted on update, accounts keep their offsets from the post time. | [optional]
**schedule** | Option<**bool**> | Schedule the post for the given date/time. | [optional]
**schedule_now** | Option<**bool**> | Publish immediately. | [optional]
**queue** | Option<**bool**> | Add to the smart publishing queue. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



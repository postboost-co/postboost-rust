# ReportExportInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**format** | **String** |  | 
**dataset** | Option<**String**> | CSV rows; default `posts`. Ignored for PDF. | [optional]
**period** | Option<**String**> | Default `last_month`. Ignored when `date_from` and `date_to` are sent. | [optional]
**date_from** | Option<[**String**](string.md)> |  | [optional]
**date_to** | Option<[**String**](string.md)> | At most 366 days after `date_from`. | [optional]
**account_ids** | Option<**Vec<i32>**> | Limit the report to these accounts; default all. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



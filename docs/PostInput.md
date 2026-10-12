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
**ai_generated** | Option<**bool**> | Declares the post AI-generated (or, with `false`, not). PostBoost sets each network's own AI label: TikTok's `is_aigc` for every TikTok account in `accounts`, Instagram's \"AI info\" label (`instagram.ai_generated`) and YouTube's synthetic-media disclosure (`youtube.contains_synthetic_media`). The other networks have no API label. The response carries `X-AI-Disclosure: applied` when every network with a label got it. When omitted, a post that attaches images made by the AI image endpoints is labelled automatically. See the AI disclosure guide.  | [optional]
**allow_duplicate** | Option<**bool**> | Skip the duplicate guard. By default the API refuses (`409`, `code: duplicate_post`) content that matches a post created for the same account in the last 24 hours. The header `X-Allow-Duplicate: true` does the same.  | [optional][default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



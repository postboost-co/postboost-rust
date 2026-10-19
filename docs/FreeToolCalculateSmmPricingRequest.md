# FreeToolCalculateSmmPricingRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**networks** | **i32** | Number of social networks managed. | 
**posts_per_week** | **i32** | Posts per week on each network. | 
**content_type** | Option<**String**> | What goes into a post. Assumed minutes per post: copy 30, copy_design 60, copy_design_video 120. | [optional][default to CopyDesign]
**community_hours_per_week** | Option<**f64**> | Community management (replies, comments, DMs), hours per week. | [optional][default to 0]
**reporting_hours_per_month** | Option<**f64**> | Reporting, hours per month. | [optional][default to 0]
**ad_hours_per_month** | Option<**f64**> | Paid social ad management, hours per month. | [optional][default to 0]
**hourly_rate** | Option<**f64**> | Your hourly rate. The default 50 is a round placeholder, not a market rate. | [optional][default to 50]
**currency** | Option<**String**> | Currency for formatting only; nothing is converted. | [optional][default to Usd]
**pricing_model** | Option<**String**> | Which price leads the quote: hourly, monthly retainer or per post. | [optional][default to Retainer]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



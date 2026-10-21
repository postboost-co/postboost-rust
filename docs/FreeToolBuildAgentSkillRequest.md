# FreeToolBuildAgentSkillRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**format** | Option<**String**> | skill_md (an Agent Skills SKILL.md), agents_md (AGENTS.md) or system_prompt. | [optional][default to SkillMd]
**name** | Option<**String**> | The skill name, normalised to lowercase letters, digits and hyphens and cut to 64 characters. | [optional][default to postboost-social-media]
**brand** | Option<**String**> | The brand the agent works for; omitted when empty. | [optional][default to ]
**tasks** | Option<**Vec<String>**> | What the agent does; the output keeps this enum's order. | [optional][default to [draft_posts, schedule_posts]]
**networks** | Option<**Vec<String>**> | Networks to add character-limit rules for; none leaves the section out. | [optional][default to []]
**autonomy** | Option<**String**> | How much the agent may do without asking. | [optional][default to DraftsOnly]
**daily_cap** | Option<**i32**> | Posts per day the agent may create; 0 adds no cap line. | [optional][default to 5]
**brand_voice** | Option<**bool**> | Read the workspace brand voice before writing captions. | [optional][default to true]
**connection** | Option<**String**> | connector (the OAuth MCP connector) or api_token (the advanced MCP server with an API key). | [optional][default to Connector]
**rules** | Option<**Vec<String>**> | Your own do's and don'ts, one per item. | [optional][default to []]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



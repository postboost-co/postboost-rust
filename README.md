# PostBoost Rust SDK

Official Rust client for the [PostBoost API](https://postboost.co/docs/api).

## Install

```toml
[dependencies]
postboost = "1.27.0"
```

Or with cargo:

```bash
cargo add postboost
```

| | |
|---|---|
| **crates.io** | [crates.io/crates/postboost](https://crates.io/crates/postboost) |
| **GitHub** | [postboost-co/postboost-rust](https://github.com/postboost-co/postboost-rust) |
| **Docs** | [postboost.co/docs/api](https://postboost.co/docs/api) |
| **Version** | v1.27.0 |

## Quick start

```rust
use postboost::apis::posts_api;
use postboost::apis::configuration::Configuration;

let config = Configuration {
    bearer_access_token: Some("YOUR_API_TOKEN".to_string()),
    ..Default::default()
};

let posts = posts_api::list_posts(&config, "YOUR_WORKSPACE_UUID").await?;
for post in posts {
    println!("{}", post.uuid.unwrap_or_default());
}
```

---

## Documentation for API Endpoints

All URIs are relative to *https://postboost.co/app/api*

Class | Method | HTTP request | Description
------------ | ------------- | ------------- | -------------
*AiApi* | [**blog_to_social**](docs/AiApi.md#blog_to_social) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
*AiApi* | [**delete_brand_voice**](docs/AiApi.md#delete_brand_voice) | **DELETE** /{workspaceUuid}/brand-voice | Delete the brand voice
*AiApi* | [**get_ai_usage**](docs/AiApi.md#get_ai_usage) | **GET** /{workspaceUuid}/usage/ai | AI credit usage
*AiApi* | [**get_brand_voice**](docs/AiApi.md#get_brand_voice) | **GET** /{workspaceUuid}/brand-voice | Get the brand voice
*AiApi* | [**get_repurpose_run**](docs/AiApi.md#get_repurpose_run) | **GET** /{workspaceUuid}/ai/repurpose/runs/{runId} | Get a repurpose run
*AiApi* | [**image_alt_text**](docs/AiApi.md#image_alt_text) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
*AiApi* | [**image_edit**](docs/AiApi.md#image_edit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
*AiApi* | [**image_generate**](docs/AiApi.md#image_generate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
*AiApi* | [**image_prompt**](docs/AiApi.md#image_prompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
*AiApi* | [**image_variations**](docs/AiApi.md#image_variations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image
*AiApi* | [**learn_brand_voice**](docs/AiApi.md#learn_brand_voice) | **POST** /{workspaceUuid}/brand-voice/learn | Learn a brand voice from past posts
*AiApi* | [**repurpose_content**](docs/AiApi.md#repurpose_content) | **POST** /{workspaceUuid}/ai/repurpose | Repurpose long-form content into a draft post set with a carousel
*AiApi* | [**update_brand_voice**](docs/AiApi.md#update_brand_voice) | **PUT** /{workspaceUuid}/brand-voice | Create or update the brand voice
*AccountGroupsApi* | [**create_account_group**](docs/AccountGroupsApi.md#create_account_group) | **POST** /{workspaceUuid}/account-groups | Create an account group
*AccountGroupsApi* | [**delete_account_group**](docs/AccountGroupsApi.md#delete_account_group) | **DELETE** /{workspaceUuid}/account-groups/{accountGroupUuid} | Delete an account group
*AccountGroupsApi* | [**get_account_group**](docs/AccountGroupsApi.md#get_account_group) | **GET** /{workspaceUuid}/account-groups/{accountGroupUuid} | Get an account group
*AccountGroupsApi* | [**list_account_groups**](docs/AccountGroupsApi.md#list_account_groups) | **GET** /{workspaceUuid}/account-groups | List account groups
*AccountGroupsApi* | [**update_account_group**](docs/AccountGroupsApi.md#update_account_group) | **PUT** /{workspaceUuid}/account-groups/{accountGroupUuid} | Update an account group
*AccountsApi* | [**connect_channel**](docs/AccountsApi.md#connect_channel) | **POST** /{workspaceUuid}/accounts/connect/{provider} | Connect a Telegram, Discord or Slack channel
*AccountsApi* | [**create_connect_link**](docs/AccountsApi.md#create_connect_link) | **POST** /{workspaceUuid}/accounts/connect-links | Create a connect link
*AccountsApi* | [**create_reconnect_link**](docs/AccountsApi.md#create_reconnect_link) | **POST** /{workspaceUuid}/accounts/{accountUuid}/reconnect-links | Create a reconnect link
*AccountsApi* | [**get_account**](docs/AccountsApi.md#get_account) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
*AccountsApi* | [**get_account_health**](docs/AccountsApi.md#get_account_health) | **GET** /{workspaceUuid}/account-health | Account health
*AccountsApi* | [**list_accounts**](docs/AccountsApi.md#list_accounts) | **GET** /{workspaceUuid}/accounts | List accounts
*ActivityApi* | [**list_api_activity**](docs/ActivityApi.md#list_api_activity) | **GET** /{workspaceUuid}/activity | List API activity
*AgentsApi* | [**approve_agent_proposal**](docs/AgentsApi.md#approve_agent_proposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/approve | Approve and apply an agent proposal
*AgentsApi* | [**create_agent**](docs/AgentsApi.md#create_agent) | **POST** /{workspaceUuid}/agents | Switch on a background agent
*AgentsApi* | [**delete_agent**](docs/AgentsApi.md#delete_agent) | **DELETE** /{workspaceUuid}/agents/{agentUuid} | Delete a background agent
*AgentsApi* | [**get_agent_run**](docs/AgentsApi.md#get_agent_run) | **GET** /{workspaceUuid}/agent-runs/{runUuid} | Get an agent run with its proposals
*AgentsApi* | [**list_agent_proposals**](docs/AgentsApi.md#list_agent_proposals) | **GET** /{workspaceUuid}/agent-proposals | List agent proposals (approval queue)
*AgentsApi* | [**list_agent_runs**](docs/AgentsApi.md#list_agent_runs) | **GET** /{workspaceUuid}/agents/{agentUuid}/runs | Run history of an agent
*AgentsApi* | [**list_agents**](docs/AgentsApi.md#list_agents) | **GET** /{workspaceUuid}/agents | List background agents
*AgentsApi* | [**reject_agent_proposal**](docs/AgentsApi.md#reject_agent_proposal) | **POST** /{workspaceUuid}/agent-proposals/{proposalUuid}/reject | Reject an agent proposal
*AgentsApi* | [**run_agent**](docs/AgentsApi.md#run_agent) | **POST** /{workspaceUuid}/agents/{agentUuid}/run | Run a background agent now
*AgentsApi* | [**update_agent**](docs/AgentsApi.md#update_agent) | **PUT** /{workspaceUuid}/agents/{agentUuid} | Update a background agent
*AnalyticsApi* | [**create_report_export**](docs/AnalyticsApi.md#create_report_export) | **POST** /{workspaceUuid}/reports/exports | Create a report export
*AnalyticsApi* | [**download_report_export**](docs/AnalyticsApi.md#download_report_export) | **GET** /{workspaceUuid}/reports/exports/{exportUuid}/download | Download a report file
*AnalyticsApi* | [**get_account_analytics**](docs/AnalyticsApi.md#get_account_analytics) | **GET** /{workspaceUuid}/analytics/accounts/{accountUuid} | Get account analytics
*AnalyticsApi* | [**get_analytics_summary**](docs/AnalyticsApi.md#get_analytics_summary) | **GET** /{workspaceUuid}/analytics | Get analytics summary
*AnalyticsApi* | [**get_best_posting_times**](docs/AnalyticsApi.md#get_best_posting_times) | **GET** /{workspaceUuid}/analytics/best-times | Get best posting times
*AnalyticsApi* | [**get_post_analytics_0**](docs/AnalyticsApi.md#get_post_analytics_0) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*AnalyticsApi* | [**get_posting_times**](docs/AnalyticsApi.md#get_posting_times) | **GET** /{workspaceUuid}/analytics/posting-times | Get posting times heatmap
*AnalyticsApi* | [**get_report_branding**](docs/AnalyticsApi.md#get_report_branding) | **GET** /{workspaceUuid}/report-branding | Get the report branding
*AnalyticsApi* | [**get_report_export**](docs/AnalyticsApi.md#get_report_export) | **GET** /{workspaceUuid}/reports/exports/{exportUuid} | Get a report export
*AnalyticsApi* | [**list_report_exports**](docs/AnalyticsApi.md#list_report_exports) | **GET** /{workspaceUuid}/reports/exports | List report exports
*AnalyticsApi* | [**update_report_branding**](docs/AnalyticsApi.md#update_report_branding) | **PUT** /{workspaceUuid}/report-branding | Update the report branding
*AnalyticsApi* | [**upload_report_branding_logo**](docs/AnalyticsApi.md#upload_report_branding_logo) | **POST** /{workspaceUuid}/report-branding/logo | Upload the report logo
*CompetitorsApi* | [**add_competitor**](docs/CompetitorsApi.md#add_competitor) | **POST** /{workspaceUuid}/competitors | Track a competitor
*CompetitorsApi* | [**delete_competitor**](docs/CompetitorsApi.md#delete_competitor) | **DELETE** /{workspaceUuid}/competitors/{competitorId} | Stop tracking a competitor
*CompetitorsApi* | [**get_competitor**](docs/CompetitorsApi.md#get_competitor) | **GET** /{workspaceUuid}/competitors/{competitorId} | Get a competitor
*CompetitorsApi* | [**list_competitors**](docs/CompetitorsApi.md#list_competitors) | **GET** /{workspaceUuid}/competitors | List competitors
*FreeToolsApi* | [**build_utm_url**](docs/FreeToolsApi.md#build_utm_url) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL
*FreeToolsApi* | [**calculate_engagement_rate**](docs/FreeToolsApi.md#calculate_engagement_rate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate
*FreeToolsApi* | [**check_post**](docs/FreeToolsApi.md#check_post) | **POST** /tools/social-media-post-checker | Check a post against each network's publishing rules
*FreeToolsApi* | [**clean_text**](docs/FreeToolsApi.md#clean_text) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown
*FreeToolsApi* | [**count_characters**](docs/FreeToolsApi.md#count_characters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them
*FreeToolsApi* | [**format_linked_in_post**](docs/FreeToolsApi.md#format_linked_in_post) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists
*FreeToolsApi* | [**generate_fancy_text**](docs/FreeToolsApi.md#generate_fancy_text) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles
*FreeToolsApi* | [**list_free_tools**](docs/FreeToolsApi.md#list_free_tools) | **GET** /tools | List the free tools
*FreeToolsApi* | [**split_thread**](docs/FreeToolsApi.md#split_thread) | **POST** /tools/x-thread-maker | Split long text into a thread
*HashtagGroupsApi* | [**create_hashtag_group**](docs/HashtagGroupsApi.md#create_hashtag_group) | **POST** /{workspaceUuid}/hashtag-groups | Create a hashtag group
*HashtagGroupsApi* | [**delete_hashtag_group**](docs/HashtagGroupsApi.md#delete_hashtag_group) | **DELETE** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Delete a hashtag group
*HashtagGroupsApi* | [**get_hashtag_group**](docs/HashtagGroupsApi.md#get_hashtag_group) | **GET** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Get a hashtag group
*HashtagGroupsApi* | [**list_hashtag_groups**](docs/HashtagGroupsApi.md#list_hashtag_groups) | **GET** /{workspaceUuid}/hashtag-groups | List hashtag groups
*HashtagGroupsApi* | [**update_hashtag_group**](docs/HashtagGroupsApi.md#update_hashtag_group) | **PUT** /{workspaceUuid}/hashtag-groups/{hashtagGroupId} | Update a hashtag group
*InboxApi* | [**approve_inbox_reply_draft**](docs/InboxApi.md#approve_inbox_reply_draft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/approve | Approve and send a reply draft
*InboxApi* | [**create_inbox_reply_draft**](docs/InboxApi.md#create_inbox_reply_draft) | **POST** /{workspaceUuid}/inbox/conversations/{conversationId}/drafts | Draft a reply
*InboxApi* | [**delete_inbox_reply_draft**](docs/InboxApi.md#delete_inbox_reply_draft) | **DELETE** /{workspaceUuid}/inbox/drafts/{draftId} | Withdraw a reply draft
*InboxApi* | [**get_inbox_conversation**](docs/InboxApi.md#get_inbox_conversation) | **GET** /{workspaceUuid}/inbox/conversations/{conversationId} | Get an inbox conversation
*InboxApi* | [**get_inbox_reply_draft**](docs/InboxApi.md#get_inbox_reply_draft) | **GET** /{workspaceUuid}/inbox/drafts/{draftId} | Get a reply draft
*InboxApi* | [**list_inbox_conversations**](docs/InboxApi.md#list_inbox_conversations) | **GET** /{workspaceUuid}/inbox/conversations | List inbox conversations
*InboxApi* | [**list_inbox_reply_drafts**](docs/InboxApi.md#list_inbox_reply_drafts) | **GET** /{workspaceUuid}/inbox/drafts | List reply drafts
*InboxApi* | [**reject_inbox_reply_draft**](docs/InboxApi.md#reject_inbox_reply_draft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/reject | Reject a reply draft
*InboxApi* | [**update_inbox_conversation**](docs/InboxApi.md#update_inbox_conversation) | **PATCH** /{workspaceUuid}/inbox/conversations/{conversationId} | Update an inbox conversation
*InboxApi* | [**update_inbox_reply_draft**](docs/InboxApi.md#update_inbox_reply_draft) | **PUT** /{workspaceUuid}/inbox/drafts/{draftId} | Edit a reply draft
*MediaApi* | [**abort_chunked_upload**](docs/MediaApi.md#abort_chunked_upload) | **DELETE** /{workspaceUuid}/media/chunked/{uploadUuid} | Abort chunked upload
*MediaApi* | [**complete_chunked_upload**](docs/MediaApi.md#complete_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/complete | Complete chunked upload
*MediaApi* | [**create_media_folder**](docs/MediaApi.md#create_media_folder) | **POST** /{workspaceUuid}/media/folders | Create media folder
*MediaApi* | [**delete_media_bulk**](docs/MediaApi.md#delete_media_bulk) | **DELETE** /{workspaceUuid}/media | Delete media (bulk)
*MediaApi* | [**delete_media_folder**](docs/MediaApi.md#delete_media_folder) | **DELETE** /{workspaceUuid}/media/folders/{folderUuid} | Delete media folder
*MediaApi* | [**get_media**](docs/MediaApi.md#get_media) | **GET** /{workspaceUuid}/media/{mediaUuid} | Get media
*MediaApi* | [**get_remote_upload_status**](docs/MediaApi.md#get_remote_upload_status) | **GET** /{workspaceUuid}/media/remote/{downloadId}/status | Get remote upload status
*MediaApi* | [**initiate_chunked_upload**](docs/MediaApi.md#initiate_chunked_upload) | **POST** /{workspaceUuid}/media/chunked/initiate | Initiate chunked upload
*MediaApi* | [**initiate_remote_upload**](docs/MediaApi.md#initiate_remote_upload) | **POST** /{workspaceUuid}/media/remote/initiate | Initiate remote upload
*MediaApi* | [**list_media**](docs/MediaApi.md#list_media) | **GET** /{workspaceUuid}/media | List media
*MediaApi* | [**list_media_folders**](docs/MediaApi.md#list_media_folders) | **GET** /{workspaceUuid}/media/folders | List media folders
*MediaApi* | [**update_media**](docs/MediaApi.md#update_media) | **PUT** /{workspaceUuid}/media/{mediaUuid} | Update media
*MediaApi* | [**update_media_folder**](docs/MediaApi.md#update_media_folder) | **PUT** /{workspaceUuid}/media/folders/{folderUuid} | Update media folder
*MediaApi* | [**upload_chunk**](docs/MediaApi.md#upload_chunk) | **POST** /{workspaceUuid}/media/chunked/{uploadUuid}/upload | Upload a chunk
*MediaApi* | [**upload_media**](docs/MediaApi.md#upload_media) | **POST** /{workspaceUuid}/media | Upload media (binary)
*MediaApi* | [**upload_media_base64**](docs/MediaApi.md#upload_media_base64) | **POST** /{workspaceUuid}/media/base64 | Upload media (base64 JSON)
*MentionsApi* | [**create_mention**](docs/MentionsApi.md#create_mention) | **POST** /{workspaceUuid}/mentions | Create mention
*MentionsApi* | [**delete_mention**](docs/MentionsApi.md#delete_mention) | **DELETE** /{workspaceUuid}/mentions/{mentionId} | Delete mention
*MentionsApi* | [**get_mention**](docs/MentionsApi.md#get_mention) | **GET** /{workspaceUuid}/mentions/{mentionId} | Get mention
*MentionsApi* | [**list_mentions**](docs/MentionsApi.md#list_mentions) | **GET** /{workspaceUuid}/mentions | List mentions
*MentionsApi* | [**update_mention**](docs/MentionsApi.md#update_mention) | **PUT** /{workspaceUuid}/mentions/{mentionId} | Update mention
*PostingScheduleApi* | [**get_posting_schedule**](docs/PostingScheduleApi.md#get_posting_schedule) | **GET** /{workspaceUuid}/posting-schedule | Get the posting schedule
*PostingScheduleApi* | [**get_recommended_posting_times**](docs/PostingScheduleApi.md#get_recommended_posting_times) | **GET** /{workspaceUuid}/posting-schedule/recommended | Get recommended posting times
*PostingScheduleApi* | [**list_queue_slots**](docs/PostingScheduleApi.md#list_queue_slots) | **GET** /{workspaceUuid}/queue/slots | List upcoming queue slots
*PostingScheduleApi* | [**reset_account_posting_schedule**](docs/PostingScheduleApi.md#reset_account_posting_schedule) | **DELETE** /{workspaceUuid}/posting-schedule/{accountId} | Reset an account schedule
*PostingScheduleApi* | [**update_posting_schedule**](docs/PostingScheduleApi.md#update_posting_schedule) | **PUT** /{workspaceUuid}/posting-schedule | Set the posting schedule
*PostsApi* | [**add_post_to_queue**](docs/PostsApi.md#add_post_to_queue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
*PostsApi* | [**approve_post**](docs/PostsApi.md#approve_post) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
*PostsApi* | [**create_post**](docs/PostsApi.md#create_post) | **POST** /{workspaceUuid}/posts | Create post
*PostsApi* | [**create_recycling_rule**](docs/PostsApi.md#create_recycling_rule) | **POST** /{workspaceUuid}/recycling-rules | Create a recycling rule
*PostsApi* | [**create_rss_feed**](docs/PostsApi.md#create_rss_feed) | **POST** /{workspaceUuid}/rss-feeds | Add an RSS feed
*PostsApi* | [**delete_post**](docs/PostsApi.md#delete_post) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
*PostsApi* | [**delete_posts_bulk**](docs/PostsApi.md#delete_posts_bulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
*PostsApi* | [**delete_recycling_rule**](docs/PostsApi.md#delete_recycling_rule) | **DELETE** /{workspaceUuid}/recycling-rules/{ruleUuid} | Delete a recycling rule
*PostsApi* | [**delete_rss_feed**](docs/PostsApi.md#delete_rss_feed) | **DELETE** /{workspaceUuid}/rss-feeds/{feedUuid} | Delete an RSS feed
*PostsApi* | [**get_post**](docs/PostsApi.md#get_post) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
*PostsApi* | [**get_post_analytics**](docs/PostsApi.md#get_post_analytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
*PostsApi* | [**get_recycling_rule**](docs/PostsApi.md#get_recycling_rule) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid} | Get a recycling rule
*PostsApi* | [**get_rss_feed**](docs/PostsApi.md#get_rss_feed) | **GET** /{workspaceUuid}/rss-feeds/{feedUuid} | Get an RSS feed
*PostsApi* | [**list_posts**](docs/PostsApi.md#list_posts) | **GET** /{workspaceUuid}/posts | List posts
*PostsApi* | [**list_recycling_rules**](docs/PostsApi.md#list_recycling_rules) | **GET** /{workspaceUuid}/recycling-rules | List recycling rules
*PostsApi* | [**list_recycling_runs**](docs/PostsApi.md#list_recycling_runs) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid}/runs | List a recycling rule's runs
*PostsApi* | [**list_rss_feeds**](docs/PostsApi.md#list_rss_feeds) | **GET** /{workspaceUuid}/rss-feeds | List RSS feeds
*PostsApi* | [**poll_rss_feed**](docs/PostsApi.md#poll_rss_feed) | **POST** /{workspaceUuid}/rss-feeds/{feedUuid}/poll | Check an RSS feed now
*PostsApi* | [**recycle_post**](docs/PostsApi.md#recycle_post) | **POST** /{workspaceUuid}/posts/{postUuid}/recycle | Recycle a post on an interval
*PostsApi* | [**retry_post_account**](docs/PostsApi.md#retry_post_account) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
*PostsApi* | [**schedule_post**](docs/PostsApi.md#schedule_post) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
*PostsApi* | [**update_post**](docs/PostsApi.md#update_post) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
*PostsApi* | [**update_recycling_rule**](docs/PostsApi.md#update_recycling_rule) | **PUT** /{workspaceUuid}/recycling-rules/{ruleUuid} | Update, pause or resume a recycling rule
*PostsApi* | [**update_rss_feed**](docs/PostsApi.md#update_rss_feed) | **PUT** /{workspaceUuid}/rss-feeds/{feedUuid} | Update, pause or resume an RSS feed
*PostsApi* | [**validate_post**](docs/PostsApi.md#validate_post) | **POST** /{workspaceUuid}/posts/validate | Validate post (dry run)
*ReceiptsApi* | [**create_receipt**](docs/ReceiptsApi.md#create_receipt) | **POST** /panel/receipts | Create receipt
*ReceiptsApi* | [**delete_receipt**](docs/ReceiptsApi.md#delete_receipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
*ReceiptsApi* | [**delete_receipts_bulk**](docs/ReceiptsApi.md#delete_receipts_bulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
*ReceiptsApi* | [**get_receipt**](docs/ReceiptsApi.md#get_receipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
*ReceiptsApi* | [**list_receipts**](docs/ReceiptsApi.md#list_receipts) | **GET** /panel/receipts | List receipts
*ReceiptsApi* | [**update_receipt**](docs/ReceiptsApi.md#update_receipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt
*SubscriptionsApi* | [**add_generic_subscription**](docs/SubscriptionsApi.md#add_generic_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
*SubscriptionsApi* | [**cancel_subscription**](docs/SubscriptionsApi.md#cancel_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
*SubscriptionsApi* | [**change_subscription_plan**](docs/SubscriptionsApi.md#change_subscription_plan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
*SubscriptionsApi* | [**checkout_subscription**](docs/SubscriptionsApi.md#checkout_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
*SubscriptionsApi* | [**create_subscription**](docs/SubscriptionsApi.md#create_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
*SubscriptionsApi* | [**delete_subscription**](docs/SubscriptionsApi.md#delete_subscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
*SubscriptionsApi* | [**get_subscription**](docs/SubscriptionsApi.md#get_subscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
*SubscriptionsApi* | [**remove_generic_subscription**](docs/SubscriptionsApi.md#remove_generic_subscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
*SubscriptionsApi* | [**resume_subscription**](docs/SubscriptionsApi.md#resume_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
*SubscriptionsApi* | [**update_subscription**](docs/SubscriptionsApi.md#update_subscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription
*TagsApi* | [**create_tag**](docs/TagsApi.md#create_tag) | **POST** /{workspaceUuid}/tags | Create tag
*TagsApi* | [**delete_tag**](docs/TagsApi.md#delete_tag) | **DELETE** /{workspaceUuid}/tags/{tagUuid} | Delete tag
*TagsApi* | [**get_tag**](docs/TagsApi.md#get_tag) | **GET** /{workspaceUuid}/tags/{tagUuid} | Get tag
*TagsApi* | [**list_tags**](docs/TagsApi.md#list_tags) | **GET** /{workspaceUuid}/tags | List tags
*TagsApi* | [**update_tag**](docs/TagsApi.md#update_tag) | **PUT** /{workspaceUuid}/tags/{tagUuid} | Update tag
*TemplatesApi* | [**create_template**](docs/TemplatesApi.md#create_template) | **POST** /{workspaceUuid}/templates | Create a template
*TemplatesApi* | [**delete_template**](docs/TemplatesApi.md#delete_template) | **DELETE** /{workspaceUuid}/templates/{templateId} | Delete a template
*TemplatesApi* | [**get_template**](docs/TemplatesApi.md#get_template) | **GET** /{workspaceUuid}/templates/{templateId} | Get a template
*TemplatesApi* | [**list_templates**](docs/TemplatesApi.md#list_templates) | **GET** /{workspaceUuid}/templates | List templates
*TemplatesApi* | [**update_template**](docs/TemplatesApi.md#update_template) | **PUT** /{workspaceUuid}/templates/{templateId} | Update a template
*UsersApi* | [**create_user**](docs/UsersApi.md#create_user) | **POST** /panel/users | Create user
*UsersApi* | [**delete_user**](docs/UsersApi.md#delete_user) | **DELETE** /panel/users/{userId} | Delete user
*UsersApi* | [**delete_users_bulk**](docs/UsersApi.md#delete_users_bulk) | **DELETE** /panel/users | Delete users (bulk)
*UsersApi* | [**get_user**](docs/UsersApi.md#get_user) | **GET** /panel/users/{userId} | Get user
*UsersApi* | [**list_users**](docs/UsersApi.md#list_users) | **GET** /panel/users | List users
*UsersApi* | [**update_user**](docs/UsersApi.md#update_user) | **PUT** /panel/users/{userId} | Update user
*WebhooksApi* | [**create_webhook_subscription**](docs/WebhooksApi.md#create_webhook_subscription) | **POST** /{workspaceUuid}/webhooks/subscriptions | Subscribe a webhook
*WebhooksApi* | [**delete_webhook_subscription**](docs/WebhooksApi.md#delete_webhook_subscription) | **DELETE** /{workspaceUuid}/webhooks/subscriptions/{subscriptionUuid} | Unsubscribe a webhook
*WebhooksApi* | [**list_webhook_subscriptions**](docs/WebhooksApi.md#list_webhook_subscriptions) | **GET** /{workspaceUuid}/webhooks/subscriptions | List webhook subscriptions
*WorkspacesApi* | [**add_user_to_workspace**](docs/WorkspacesApi.md#add_user_to_workspace) | **POST** /panel/workspaces/{workspaceUuid}/users | Add user to workspace
*WorkspacesApi* | [**create_api_key**](docs/WorkspacesApi.md#create_api_key) | **POST** /{workspaceUuid}/api-keys | Create a scoped API key
*WorkspacesApi* | [**create_reseller_client**](docs/WorkspacesApi.md#create_reseller_client) | **POST** /{workspaceUuid}/clients | Create a client workspace
*WorkspacesApi* | [**create_workspace**](docs/WorkspacesApi.md#create_workspace) | **POST** /panel/workspaces | Create workspace
*WorkspacesApi* | [**delete_api_key**](docs/WorkspacesApi.md#delete_api_key) | **DELETE** /{workspaceUuid}/api-keys/{apiKeyId} | Revoke a scoped API key
*WorkspacesApi* | [**delete_workspace**](docs/WorkspacesApi.md#delete_workspace) | **DELETE** /panel/workspaces/{workspaceUuid} | Delete workspace
*WorkspacesApi* | [**delete_workspaces_bulk**](docs/WorkspacesApi.md#delete_workspaces_bulk) | **DELETE** /panel/workspaces | Delete workspaces (bulk)
*WorkspacesApi* | [**get_workspace**](docs/WorkspacesApi.md#get_workspace) | **GET** /panel/workspaces/{workspaceUuid} | Get workspace
*WorkspacesApi* | [**get_workspace_ai_credits**](docs/WorkspacesApi.md#get_workspace_ai_credits) | **GET** /panel/workspaces/{workspaceUuid}/ai-credits | Get workspace AI credits
*WorkspacesApi* | [**get_x_usage**](docs/WorkspacesApi.md#get_x_usage) | **GET** /{workspaceUuid}/usage/x | X (Twitter) usage
*WorkspacesApi* | [**list_api_keys**](docs/WorkspacesApi.md#list_api_keys) | **GET** /{workspaceUuid}/api-keys | List scoped API keys
*WorkspacesApi* | [**list_my_workspaces**](docs/WorkspacesApi.md#list_my_workspaces) | **GET** /workspaces | List my workspaces
*WorkspacesApi* | [**list_reseller_clients**](docs/WorkspacesApi.md#list_reseller_clients) | **GET** /{workspaceUuid}/clients | List client workspaces
*WorkspacesApi* | [**list_workspaces**](docs/WorkspacesApi.md#list_workspaces) | **GET** /panel/workspaces | List workspaces
*WorkspacesApi* | [**remove_user_from_workspace**](docs/WorkspacesApi.md#remove_user_from_workspace) | **DELETE** /panel/workspaces/{workspaceUuid}/users | Remove user from workspace
*WorkspacesApi* | [**update_workspace**](docs/WorkspacesApi.md#update_workspace) | **PUT** /panel/workspaces/{workspaceUuid} | Update workspace
*WorkspacesApi* | [**update_workspace_user**](docs/WorkspacesApi.md#update_workspace_user) | **PUT** /panel/workspaces/{workspaceUuid}/users | Update user role in workspace

---

## Links

- Docs and quick start: https://postboost.co/docs/quickstart
- API reference: https://postboost.co/docs/api
- MCP server for AI agents: https://postboost.co/docs/mcp
- All PostBoost open-source projects: https://github.com/postboost-co
- Awesome PostBoost: https://github.com/postboost-co/awesome-postboost

## Authentication

Create an API token in PostBoost under **Settings → Access Tokens** and pass it as a Bearer token. Never commit tokens; read them from an environment variable such as `POSTBOOST_API_TOKEN`.

## Contributing

This Rust SDK is generated from the [PostBoost OpenAPI spec](https://postboost.co/docs/api). Bugs and feature requests: open an issue in [postboost-rust](https://github.com/postboost-co/postboost-rust/issues). Generated code is overwritten on every release, so fixes usually land in the spec or the generator templates; see [CONTRIBUTING.md](CONTRIBUTING.md).

Security issues: see [SECURITY.md](SECURITY.md). Questions: hi@postboost.co.

## License

MIT, see [LICENSE](LICENSE).

---

## Links

- Docs and quick start: https://postboost.co/docs/quickstart
- API reference: https://postboost.co/docs/api
- MCP server for AI agents: https://postboost.co/docs/mcp
- All PostBoost open-source projects: https://github.com/postboost-co
- Awesome PostBoost: https://github.com/postboost-co/awesome-postboost

## Authentication

Create an API token in PostBoost under **Settings → Access Tokens** and pass it as a Bearer token. Never commit tokens; read them from an environment variable such as `POSTBOOST_API_TOKEN`.

## Contributing

This Rust SDK is generated from the [PostBoost OpenAPI spec](https://postboost.co/docs/api). Bugs and feature requests: open an issue in [postboost-rust](https://github.com/postboost-co/postboost-rust/issues). Generated code is overwritten on every release, so fixes usually land in the spec or the generator templates; see [CONTRIBUTING.md](CONTRIBUTING.md).

Security issues: see [SECURITY.md](SECURITY.md). Questions: hi@postboost.co.

## License

MIT, see [LICENSE](LICENSE).

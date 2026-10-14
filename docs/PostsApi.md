# \PostsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_post_to_queue**](PostsApi.md#add_post_to_queue) | **POST** /{workspaceUuid}/posts/add-to-queue/{postUuid} | Add post to queue
[**approve_post**](PostsApi.md#approve_post) | **POST** /{workspaceUuid}/posts/approve/{postUuid} | Approve post
[**create_post**](PostsApi.md#create_post) | **POST** /{workspaceUuid}/posts | Create post
[**create_recycling_rule**](PostsApi.md#create_recycling_rule) | **POST** /{workspaceUuid}/recycling-rules | Create a recycling rule
[**create_rss_feed**](PostsApi.md#create_rss_feed) | **POST** /{workspaceUuid}/rss-feeds | Add an RSS feed
[**delete_post**](PostsApi.md#delete_post) | **DELETE** /{workspaceUuid}/posts/{postUuid} | Delete post
[**delete_posts_bulk**](PostsApi.md#delete_posts_bulk) | **DELETE** /{workspaceUuid}/posts | Delete posts (bulk)
[**delete_recycling_rule**](PostsApi.md#delete_recycling_rule) | **DELETE** /{workspaceUuid}/recycling-rules/{ruleUuid} | Delete a recycling rule
[**delete_rss_feed**](PostsApi.md#delete_rss_feed) | **DELETE** /{workspaceUuid}/rss-feeds/{feedUuid} | Delete an RSS feed
[**get_post**](PostsApi.md#get_post) | **GET** /{workspaceUuid}/posts/{postUuid} | Get post
[**get_post_analytics**](PostsApi.md#get_post_analytics) | **GET** /{workspaceUuid}/posts/{postUuid}/analytics | Get post analytics
[**get_recycling_rule**](PostsApi.md#get_recycling_rule) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid} | Get a recycling rule
[**get_rss_feed**](PostsApi.md#get_rss_feed) | **GET** /{workspaceUuid}/rss-feeds/{feedUuid} | Get an RSS feed
[**list_posts**](PostsApi.md#list_posts) | **GET** /{workspaceUuid}/posts | List posts
[**list_recycling_rules**](PostsApi.md#list_recycling_rules) | **GET** /{workspaceUuid}/recycling-rules | List recycling rules
[**list_recycling_runs**](PostsApi.md#list_recycling_runs) | **GET** /{workspaceUuid}/recycling-rules/{ruleUuid}/runs | List a recycling rule's runs
[**list_rss_feeds**](PostsApi.md#list_rss_feeds) | **GET** /{workspaceUuid}/rss-feeds | List RSS feeds
[**poll_rss_feed**](PostsApi.md#poll_rss_feed) | **POST** /{workspaceUuid}/rss-feeds/{feedUuid}/poll | Check an RSS feed now
[**recycle_post**](PostsApi.md#recycle_post) | **POST** /{workspaceUuid}/posts/{postUuid}/recycle | Recycle a post on an interval
[**retry_post_account**](PostsApi.md#retry_post_account) | **POST** /{workspaceUuid}/posts/retry/{postUuid}/{accountUuid} | Retry publishing to one account
[**schedule_post**](PostsApi.md#schedule_post) | **POST** /{workspaceUuid}/posts/schedule/{postUuid} | Schedule post
[**update_post**](PostsApi.md#update_post) | **PUT** /{workspaceUuid}/posts/{postUuid} | Update post
[**update_recycling_rule**](PostsApi.md#update_recycling_rule) | **PUT** /{workspaceUuid}/recycling-rules/{ruleUuid} | Update, pause or resume a recycling rule
[**update_rss_feed**](PostsApi.md#update_rss_feed) | **PUT** /{workspaceUuid}/rss-feeds/{feedUuid} | Update, pause or resume an RSS feed
[**validate_post**](PostsApi.md#validate_post) | **POST** /{workspaceUuid}/posts/validate | Validate post (dry run)



## add_post_to_queue

> models::ScheduleResult add_post_to_queue(workspace_uuid, post_uuid, idempotency_key, add_post_to_queue_request)
Add post to queue

Add an existing post to the smart publishing queue. Each account of the post gets its own next free queue slot. Returns `422` when the post has no accounts, the posting schedule has no available times, or provider requirements are not met. The guardrails check the saved post as publishing at the queue slot it will get (the earliest next free slot of its accounts), as on create: `409` duplicate (override with `X-Allow-Duplicate: true`), `422` account cannot publish, `429` daily cap on that slot's UTC day or X cap. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |
**add_post_to_queue_request** | Option<[**AddPostToQueueRequest**](AddPostToQueueRequest.md)> |  |  |

### Return type

[**models::ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## approve_post

> models::ScheduleResult approve_post(workspace_uuid, post_uuid, idempotency_key, approve_post_request)
Approve post

Approve a post that is pending review. The approver may move the post with `date`/`time` (read in `timezone`) and set per-account times with `accounts_schedule`; without them the post keeps the time it was submitted with. Provider requirements are validated and reported as `422`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |
**approve_post_request** | Option<[**ApprovePostRequest**](ApprovePostRequest.md)> |  |  |

### Return type

[**models::ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_post

> models::CreatePost201Response create_post(workspace_uuid, post_input, idempotency_key)
Create post

Create a new post. Use `schedule: true` with `date` and `time` to schedule, `schedule_now: true` to publish immediately, or `queue: true` to add to the smart publishing queue (each account gets its own queue slot).  `date`, `time` and `accounts_schedule` are read in `timezone` when given, otherwise in the workspace timezone. Use `accounts_schedule` to give individual accounts their own departure time.  Post bodies may reference mentions with `{{mention:<reference>}}` (see the Mentions endpoints). When the post is scheduled, provider requirements (for example a network that requires media) are validated up front and reported as `422`.  **First comment and threads.** A version's `content` is an ordered array. Item 0 is the post. Add a second item to publish a first comment on Facebook Page, Instagram and LinkedIn, or to continue a thread on X, Threads, Bluesky, Mastodon and Pixelfed:  ```json {   \"accounts\": [12],   \"schedule_now\": true,   \"versions\": [{     \"account_id\": 0,     \"is_original\": true,     \"content\": [       { \"body\": \"Our API 1.8 is live.\", \"media\": [345] },       { \"body\": \"Full changelog: https://postboost.co/docs/changelog/\" }     ]   }] } ```  The comment is posted right after the post goes live. If the comment fails, the post stays published and the account's entry on the post reports the error. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_input** | [**PostInput**](PostInput.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::CreatePost201Response**](createPost_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_recycling_rule

> models::CreateRecyclingRule201Response create_recycling_rule(workspace_uuid, recycling_rule_input)
Create a recycling rule

Recycles one post (`post_uuid`) or a tag pool (`type: tag_pool` + `tag_uuid`) every `interval_days`. The first run is `start_at`, or one interval from now. Copies are never published immediately: `placement: queue` (default) takes each account's next free queue slot, `same_time` schedules at the source post's time of day, `draft` leaves a draft.  Copies pass the same guardrails as posts created through the API (duplicate guard, per-account daily caps, disconnected accounts, X monthly allowance). A refused copy is not created; the run is logged with the guard's code (see the runs endpoint). X accounts are left out of copies because X rejects repeated text. Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**recycling_rule_input** | [**RecyclingRuleInput**](RecyclingRuleInput.md) |  | [required] |

### Return type

[**models::CreateRecyclingRule201Response**](createRecyclingRule_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_rss_feed

> models::CreateRssFeed201Response create_rss_feed(workspace_uuid, rss_feed_input)
Add an RSS feed

Checks the feed every 30 minutes and turns each item published after the feed was added into a post for `account_ids`: a draft (`mode: draft`, default), a queued post (`mode: queue`), or a queued post awaiting approval (`mode: needs_approval`: it gets the next free queue slot and publishes only after someone approves it). The text comes from `template` with `{title}`, `{link}` and `{summary}` placeholders. Each item becomes at most one post, at most `max_items_per_run` per check and 20 per workspace per day. Posts pass the same guardrails as API-created posts. Only public http(s) URLs are accepted. Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**rss_feed_input** | [**RssFeedInput**](RssFeedInput.md) |  | [required] |

### Return type

[**models::CreateRssFeed201Response**](createRssFeed_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_post

> models::DeleteResult delete_post(workspace_uuid, post_uuid, delete_post_request)
Delete post

Deletes a post. Use `delete_mode` to control whether to also remove the published content from social platforms.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**delete_post_request** | Option<[**DeletePostRequest**](DeletePostRequest.md)> |  |  |

### Return type

[**models::DeleteResult**](DeleteResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_posts_bulk

> models::DeleteResult delete_posts_bulk(workspace_uuid, delete_posts_bulk_request)
Delete posts (bulk)

Delete multiple posts at once.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**delete_posts_bulk_request** | [**DeletePostsBulkRequest**](DeletePostsBulkRequest.md) |  | [required] |

### Return type

[**models::DeleteResult**](DeleteResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_recycling_rule

> serde_json::Value delete_recycling_rule(workspace_uuid, rule_uuid)
Delete a recycling rule

Deletes the rule and its run log. Copies it already created stay. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**rule_uuid** | **uuid::Uuid** | UUID of the recycling rule. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_rss_feed

> serde_json::Value delete_rss_feed(workspace_uuid, feed_uuid)
Delete an RSS feed

Stops the feed. Posts it already created stay. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**feed_uuid** | **uuid::Uuid** | UUID of the RSS feed. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_post

> models::Post get_post(workspace_uuid, post_uuid)
Get post

Returns a single post with all its versions and associated accounts.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |

### Return type

[**models::Post**](Post.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_post_analytics

> models::PostAnalytics get_post_analytics(workspace_uuid, post_uuid)
Get post analytics

Engagement metrics for a published post across its accounts (also works for trashed posts), with totals, trends and the best-performing account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |

### Return type

[**models::PostAnalytics**](PostAnalytics.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_recycling_rule

> models::CreateRecyclingRule201Response get_recycling_rule(workspace_uuid, rule_uuid)
Get a recycling rule

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**rule_uuid** | **uuid::Uuid** | UUID of the recycling rule. | [required] |

### Return type

[**models::CreateRecyclingRule201Response**](createRecyclingRule_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_rss_feed

> models::CreateRssFeed201Response get_rss_feed(workspace_uuid, feed_uuid)
Get an RSS feed

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**feed_uuid** | **uuid::Uuid** | UUID of the RSS feed. | [required] |

### Return type

[**models::CreateRssFeed201Response**](createRssFeed_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_posts

> models::ListPosts200Response list_posts(workspace_uuid, page)
List posts

Returns a paginated list of posts in the workspace.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**page** | Option<**i32**> |  |  |[default to 1]

### Return type

[**models::ListPosts200Response**](listPosts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_recycling_rules

> models::ListRecyclingRules200Response list_recycling_rules(workspace_uuid)
List recycling rules

Evergreen recycling rules of the workspace, newest first. A rule copies a post (or the least recently recycled published post with a tag) every `interval_days` and places the copy in the queue. Copies are ordinary posts: they show in the calendar and the queue. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListRecyclingRules200Response**](listRecyclingRules_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_recycling_runs

> models::ListRecyclingRuns200Response list_recycling_runs(workspace_uuid, rule_uuid)
List a recycling rule's runs

The latest 100 runs of the rule, newest first: the copy each run created, or why it skipped (`source_unavailable`, `no_eligible_post`, `no_accounts`, `queue_full`, `x_skipped_identical_text`, or a guardrail code such as `duplicate_post` or `account_daily_cap_reached`). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**rule_uuid** | **uuid::Uuid** | UUID of the recycling rule. | [required] |

### Return type

[**models::ListRecyclingRuns200Response**](listRecyclingRuns_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_rss_feeds

> models::ListRssFeeds200Response list_rss_feeds(workspace_uuid)
List RSS feeds

RSS and Atom feeds whose new items become posts, newest first.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListRssFeeds200Response**](listRssFeeds_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## poll_rss_feed

> models::PollRssFeed200Response poll_rss_feed(workspace_uuid, feed_uuid)
Check an RSS feed now

Reads the feed immediately instead of waiting for the next check. Limited to 6 calls per minute. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**feed_uuid** | **uuid::Uuid** | UUID of the RSS feed. | [required] |

### Return type

[**models::PollRssFeed200Response**](pollRssFeed_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## recycle_post

> models::CreateRecyclingRule201Response recycle_post(workspace_uuid, post_uuid, recycling_rule_settings)
Recycle a post on an interval

Shortcut for creating a `post` recycling rule for this post. Same body as `createRecyclingRule` without `type`, `post_uuid` and `tag_uuid`. Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**recycling_rule_settings** | [**RecyclingRuleSettings**](RecyclingRuleSettings.md) |  | [required] |

### Return type

[**models::CreateRecyclingRule201Response**](createRecyclingRule_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## retry_post_account

> models::RetryPostAccountResult retry_post_account(workspace_uuid, post_uuid, account_uuid, idempotency_key)
Retry publishing to one account

Re-publishes a post to a single account whose publishing failed. Returns `422` when the account is not on the post, the post is still publishing, or the account did not fail.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**account_uuid** | **uuid::Uuid** | UUID of the social media account. | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::RetryPostAccountResult**](RetryPostAccountResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## schedule_post

> models::ScheduleResult schedule_post(workspace_uuid, post_uuid, schedule_post_request, idempotency_key)
Schedule post

Schedule an existing post. Optionally move it with `date`/`time` (read in `timezone`) and give accounts their own times with `accounts_schedule`. Set `postNow: true` to publish immediately; publishing starts within the request and any per-account times are dropped. Provider requirements are validated and reported as `422`. The guardrails check the saved post at the time it would publish, as on create: `409` duplicate (override with `X-Allow-Duplicate: true`), `422` account cannot publish, `429` daily or X cap. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**schedule_post_request** | [**SchedulePostRequest**](SchedulePostRequest.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::ScheduleResult**](ScheduleResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_post

> models::UpdatePost200Response update_post(workspace_uuid, post_uuid, post_input)
Update post

Replaces a post's versions, accounts, tags, and scheduling options. The post must not be in a published state. `timezone` is honoured: `date`, `time` and `accounts_schedule` are read in it. When the post stays scheduled, provider requirements are validated and reported as `422`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_uuid** | **uuid::Uuid** | UUID of the post. | [required] |
**post_input** | [**PostInput**](PostInput.md) |  | [required] |

### Return type

[**models::UpdatePost200Response**](updatePost_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_recycling_rule

> models::CreateRecyclingRule201Response update_recycling_rule(workspace_uuid, rule_uuid, recycling_rule_update)
Update, pause or resume a recycling rule

Changes the interval, limit, placement or accounts, or pauses (`active: false`) and resumes the rule. Fields you leave out keep their value. A rule that reached `max_runs` resumes only with a higher `max_runs`. Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**rule_uuid** | **uuid::Uuid** | UUID of the recycling rule. | [required] |
**recycling_rule_update** | [**RecyclingRuleUpdate**](RecyclingRuleUpdate.md) |  | [required] |

### Return type

[**models::CreateRecyclingRule201Response**](createRecyclingRule_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_rss_feed

> models::CreateRssFeed201Response update_rss_feed(workspace_uuid, feed_uuid, rss_feed_update)
Update, pause or resume an RSS feed

Fields you leave out keep their value. Resuming (`active: true`) clears the error backoff. Admins and members only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**feed_uuid** | **uuid::Uuid** | UUID of the RSS feed. | [required] |
**rss_feed_update** | [**RssFeedUpdate**](RssFeedUpdate.md) |  | [required] |

### Return type

[**models::CreateRssFeed201Response**](createRssFeed_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## validate_post

> models::PreflightResult validate_post(workspace_uuid, post_input)
Validate post (dry run)

Runs everything create-post checks without creating anything: request validation, network requirements (text length, media count and type, links) for every given account, whether or not the post is scheduled, and the guardrails (duplicate content, daily caps, account health). Always answers `200`; read `valid`. Any workspace member, including viewers, may call it. Recommended agent loop: account health, validate, then create. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**post_input** | [**PostInput**](PostInput.md) |  | [required] |

### Return type

[**models::PreflightResult**](PreflightResult.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


# \InboxApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**approve_inbox_reply_draft**](InboxApi.md#approve_inbox_reply_draft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/approve | Approve and send a reply draft
[**create_inbox_reply_draft**](InboxApi.md#create_inbox_reply_draft) | **POST** /{workspaceUuid}/inbox/conversations/{conversationId}/drafts | Draft a reply
[**delete_inbox_reply_draft**](InboxApi.md#delete_inbox_reply_draft) | **DELETE** /{workspaceUuid}/inbox/drafts/{draftId} | Withdraw a reply draft
[**get_inbox_conversation**](InboxApi.md#get_inbox_conversation) | **GET** /{workspaceUuid}/inbox/conversations/{conversationId} | Get an inbox conversation
[**get_inbox_reply_draft**](InboxApi.md#get_inbox_reply_draft) | **GET** /{workspaceUuid}/inbox/drafts/{draftId} | Get a reply draft
[**list_inbox_conversations**](InboxApi.md#list_inbox_conversations) | **GET** /{workspaceUuid}/inbox/conversations | List inbox conversations
[**list_inbox_reply_drafts**](InboxApi.md#list_inbox_reply_drafts) | **GET** /{workspaceUuid}/inbox/drafts | List reply drafts
[**reject_inbox_reply_draft**](InboxApi.md#reject_inbox_reply_draft) | **POST** /{workspaceUuid}/inbox/drafts/{draftId}/reject | Reject a reply draft
[**update_inbox_conversation**](InboxApi.md#update_inbox_conversation) | **PATCH** /{workspaceUuid}/inbox/conversations/{conversationId} | Update an inbox conversation
[**update_inbox_reply_draft**](InboxApi.md#update_inbox_reply_draft) | **PUT** /{workspaceUuid}/inbox/drafts/{draftId} | Edit a reply draft



## approve_inbox_reply_draft

> models::CreateInboxReplyDraft201Response approve_inbox_reply_draft(workspace_uuid, draft_id, inbox_reply_draft_approve)
Approve and send a reply draft

Sends the draft to the network (optionally with an edited `body`). Ends as `sent`, or `failed` with `error`. Needs the `publish` ability; the API key that wrote the draft cannot approve it (`403`, `code: self_approval`). A draft is sent at most once: approving again returns `409`. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**draft_id** | **String** | The draft `id`. | [required] |
**inbox_reply_draft_approve** | Option<[**InboxReplyDraftApprove**](InboxReplyDraftApprove.md)> |  |  |

### Return type

[**models::CreateInboxReplyDraft201Response**](createInboxReplyDraft_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_inbox_reply_draft

> models::CreateInboxReplyDraft201Response create_inbox_reply_draft(workspace_uuid, conversation_id, inbox_reply_draft_input)
Draft a reply

Proposes a reply. Nothing is posted: a person approves the draft in the app (Reply drafts page) or another API key with the `publish` ability approves it. `in_reply_to` defaults to the latest incoming message. The body limit depends on the network (Bluesky 300, Mastodon 500, LinkedIn 1250, Google 4000). Needs the `write` ability. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**conversation_id** | **String** | The conversation `id`. | [required] |
**inbox_reply_draft_input** | [**InboxReplyDraftInput**](InboxReplyDraftInput.md) |  | [required] |

### Return type

[**models::CreateInboxReplyDraft201Response**](createInboxReplyDraft_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_inbox_reply_draft

> delete_inbox_reply_draft(workspace_uuid, draft_id)
Withdraw a reply draft

Deletes a pending draft. `409` once it was reviewed. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**draft_id** | **String** | The draft `id`. | [required] |

### Return type

 (empty response body)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_inbox_conversation

> models::GetInboxConversation200Response get_inbox_conversation(workspace_uuid, conversation_id)
Get an inbox conversation

The conversation with its 50 most recent messages, oldest first. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**conversation_id** | **String** | The conversation `id`. | [required] |

### Return type

[**models::GetInboxConversation200Response**](getInboxConversation_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_inbox_reply_draft

> models::CreateInboxReplyDraft201Response get_inbox_reply_draft(workspace_uuid, draft_id)
Get a reply draft

One draft. Poll it to see whether it was approved and sent. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**draft_id** | **String** | The draft `id`. | [required] |

### Return type

[**models::CreateInboxReplyDraft201Response**](createInboxReplyDraft_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_inbox_conversations

> models::ListInboxConversations200Response list_inbox_conversations(workspace_uuid, status, account_id, provider, unread, sentiment, ai_label, since, page)
List inbox conversations

Comments, mentions and reviews on your accounts, most recent activity first, 25 per page. Available for Bluesky, Mastodon, LinkedIn Pages and Google Business Profile. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**status** | Option<**String**> | Conversation status. |  |
**account_id** | Option<**i32**> | Account `id`. |  |
**provider** | Option<**String**> | Network, for example `bluesky`. |  |
**unread** | Option<**bool**> | Only unread (`true`) or read (`false`) conversations. |  |
**sentiment** | Option<**String**> | AI sentiment. |  |
**ai_label** | Option<**String**> | AI label. |  |
**since** | Option<**String**> | Only conversations with activity at or after this time. |  |
**page** | Option<**i32**> | Page number. |  |[default to 1]

### Return type

[**models::ListInboxConversations200Response**](listInboxConversations_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_inbox_reply_drafts

> models::ListInboxReplyDrafts200Response list_inbox_reply_drafts(workspace_uuid, status, conversation_id, page)
List reply drafts

Reply drafts, newest first, 25 per page. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**status** | Option<**String**> | Draft status. |  |
**conversation_id** | Option<**String**> | Only drafts for this conversation `id`. |  |
**page** | Option<**i32**> | Page number. |  |[default to 1]

### Return type

[**models::ListInboxReplyDrafts200Response**](listInboxReplyDrafts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## reject_inbox_reply_draft

> models::CreateInboxReplyDraft201Response reject_inbox_reply_draft(workspace_uuid, draft_id)
Reject a reply draft

Rejects a pending draft; nothing is sent. Needs the `publish` ability. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**draft_id** | **String** | The draft `id`. | [required] |

### Return type

[**models::CreateInboxReplyDraft201Response**](createInboxReplyDraft_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_inbox_conversation

> models::GetInboxConversation200Response update_inbox_conversation(workspace_uuid, conversation_id, inbox_conversation_update)
Update an inbox conversation

Marks the conversation open or resolved, read or unread. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**conversation_id** | **String** | The conversation `id`. | [required] |
**inbox_conversation_update** | [**InboxConversationUpdate**](InboxConversationUpdate.md) |  | [required] |

### Return type

[**models::GetInboxConversation200Response**](getInboxConversation_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_inbox_reply_draft

> models::CreateInboxReplyDraft201Response update_inbox_reply_draft(workspace_uuid, draft_id, inbox_reply_draft_edit)
Edit a reply draft

Changes the text of a pending draft. `409` once it was reviewed. Requires the inbox API to be enabled for the workspace (otherwise `404`). Admins and members only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**draft_id** | **String** | The draft `id`. | [required] |
**inbox_reply_draft_edit** | [**InboxReplyDraftEdit**](InboxReplyDraftEdit.md) |  | [required] |

### Return type

[**models::CreateInboxReplyDraft201Response**](createInboxReplyDraft_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


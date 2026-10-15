# \AccountsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**connect_channel**](AccountsApi.md#connect_channel) | **POST** /{workspaceUuid}/accounts/connect/{provider} | Connect a Telegram, Discord or Slack channel
[**create_connect_link**](AccountsApi.md#create_connect_link) | **POST** /{workspaceUuid}/accounts/connect-links | Create a connect link
[**create_reconnect_link**](AccountsApi.md#create_reconnect_link) | **POST** /{workspaceUuid}/accounts/{accountUuid}/reconnect-links | Create a reconnect link
[**get_account**](AccountsApi.md#get_account) | **GET** /{workspaceUuid}/accounts/{accountUuid} | Get account
[**get_account_health**](AccountsApi.md#get_account_health) | **GET** /{workspaceUuid}/account-health | Account health
[**list_accounts**](AccountsApi.md#list_accounts) | **GET** /{workspaceUuid}/accounts | List accounts



## connect_channel

> models::ChannelAccount connect_channel(workspace_uuid, provider, connect_channel_input)
Connect a Telegram, Discord or Slack channel

Connects a channel that uses a bot token or a webhook URL instead of a login. The credentials are checked against the network first, stored encrypted and never returned. Connecting the same channel again updates it (`200`) instead of adding a second account. Workspace admins only; counts toward the plan's social account limit.  - **telegram**: `bot_token` from @BotFather and `chat` (the channel's `@username`, or its   numeric id such as `-1001234567890` for a private channel). The bot must be an administrator   of the channel allowed to post messages. - **discord**: `webhook_url` from Channel settings → Integrations → Webhooks   (`https://discord.com/api/webhooks/…`). - **slack**: `webhook_url` of an incoming webhook (`https://hooks.slack.com/services/…`) and an   optional display `name`. Slack posts cannot be deleted from PostBoost, and images must be   publicly reachable.  Webhook URLs on any other host are refused (`422`) before any request is made. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**provider** | **String** |  | [required] |
**connect_channel_input** | [**ConnectChannelInput**](ConnectChannelInput.md) |  | [required] |

### Return type

[**models::ChannelAccount**](ChannelAccount.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_connect_link

> models::ConnectLink create_connect_link(workspace_uuid, create_connect_link_request)
Create a connect link

Creates a single-use link (valid 15 minutes) to connect a new account on an OAuth network to this workspace: ask the user to open it in their browser while logged in to PostBoost, wait until they confirm, then call `list-accounts` to get the new account id. The link signs no one in: only the user who created it, while a workspace admin, can use it. Telegram, Discord and Slack need no browser: connect them with `connectChannel`. Mastodon, Pixelfed and Bluesky ask for a server or handle first, so the user connects them in the app. Workspace admins only; at most 10 links per minute. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**create_connect_link_request** | [**CreateConnectLinkRequest**](CreateConnectLinkRequest.md) |  | [required] |

### Return type

[**models::ConnectLink**](ConnectLink.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_reconnect_link

> models::ReconnectLink create_reconnect_link(workspace_uuid, account_uuid)
Create a reconnect link

Creates a single-use link (valid 7 days) that lets someone without a PostBoost login, such as an agency's client, re-authorize this one account on its network. The link only refreshes the connection of this account; signing in as a different profile or page changes nothing. Workspace admins only. Available for Facebook Pages, Instagram, Threads, LinkedIn, TikTok, YouTube and Pinterest. Returns `404` while the feature is not enabled on this instance. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_uuid** | **uuid::Uuid** | UUID of the social media account. | [required] |

### Return type

[**models::ReconnectLink**](ReconnectLink.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_account

> models::Account get_account(workspace_uuid, account_uuid)
Get account

Returns a single social media account.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**account_uuid** | **uuid::Uuid** | UUID of the social media account. | [required] |

### Return type

[**models::Account**](Account.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_account_health

> models::GetAccountHealth200Response get_account_health(workspace_uuid)
Account health

Pre-flight health of every account in the workspace: whether it is authorized and holds an access token, how much of its daily post cap (per UTC day, scheduled, awaiting approval and published posts) is used today, and its connection health: predicted token expiry, latest publish outcome and where to reconnect it. The `account.token_expiring` and `account.disconnected` webhooks report changes as they happen. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::GetAccountHealth200Response**](getAccountHealth_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_accounts

> models::ListAccounts200Response list_accounts(workspace_uuid, keyword, group, providers_left_square_bracket_right_square_bracket, unauthorized)
List accounts

Returns all social media accounts connected to the workspace, newest first. Optional filters narrow the list.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**keyword** | Option<**String**> | Match the account name or username. |  |
**group** | Option<**String**> | Only accounts in this account group. |  |
**providers_left_square_bracket_right_square_bracket** | Option<[**Vec<String>**](String.md)> | Only accounts of these providers (for example `instagram`, `linkedin`). |  |
**unauthorized** | Option<**bool**> | When `true`, only accounts that need to be reconnected. |  |

### Return type

[**models::ListAccounts200Response**](listAccounts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


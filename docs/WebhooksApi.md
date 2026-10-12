# \WebhooksApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_webhook_subscription**](WebhooksApi.md#create_webhook_subscription) | **POST** /{workspaceUuid}/webhooks/subscriptions | Subscribe a webhook
[**delete_webhook_subscription**](WebhooksApi.md#delete_webhook_subscription) | **DELETE** /{workspaceUuid}/webhooks/subscriptions/{subscriptionUuid} | Unsubscribe a webhook
[**list_webhook_subscriptions**](WebhooksApi.md#list_webhook_subscriptions) | **GET** /{workspaceUuid}/webhooks/subscriptions | List webhook subscriptions



## create_webhook_subscription

> models::CreateWebhookSubscription201Response create_webhook_subscription(workspace_uuid, webhook_subscription_input)
Subscribe a webhook

Registers a callback URL for the given events, the way n8n, Zapier and Make instant triggers do. Deliveries are `POST` requests with a JSON body (see [Webhooks](/webhooks) for the payload), signed with the returned `secret` in `X-Signature` (HMAC-SHA256 of the raw body, hex encoded) and attempted up to 3 times. Only public `https://` URLs are accepted. The `secret` is in this response only. Workspace admins only. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**webhook_subscription_input** | [**WebhookSubscriptionInput**](WebhookSubscriptionInput.md) |  | [required] |

### Return type

[**models::CreateWebhookSubscription201Response**](createWebhookSubscription_201_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_webhook_subscription

> serde_json::Value delete_webhook_subscription(workspace_uuid, subscription_uuid)
Unsubscribe a webhook

Deletes the webhook and stops its deliveries. Workspace admins only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**subscription_uuid** | **uuid::Uuid** | UUID of the webhook subscription. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_webhook_subscriptions

> models::ListWebhookSubscriptions200Response list_webhook_subscriptions(workspace_uuid)
List webhook subscriptions

The workspace's webhooks, newest first: subscriptions created through this API and the ones added in **Settings → Webhooks**. Secrets are never returned here. Workspace admins only; needs the `webhooks` plan capability and, for scoped keys, the `webhooks` ability. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::ListWebhookSubscriptions200Response**](listWebhookSubscriptions_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


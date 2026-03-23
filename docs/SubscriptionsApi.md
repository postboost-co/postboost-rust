# \SubscriptionsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**add_generic_subscription**](SubscriptionsApi.md#add_generic_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/generic | Add generic subscription
[**cancel_subscription**](SubscriptionsApi.md#cancel_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/cancel | Cancel subscription
[**change_subscription_plan**](SubscriptionsApi.md#change_subscription_plan) | **PUT** /panel/workspaces/{workspaceUuid}/subscription/change-plan | Change subscription plan
[**checkout_subscription**](SubscriptionsApi.md#checkout_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/new | New subscription checkout
[**create_subscription**](SubscriptionsApi.md#create_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription | Create subscription
[**delete_subscription**](SubscriptionsApi.md#delete_subscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription | Delete subscription
[**get_subscription**](SubscriptionsApi.md#get_subscription) | **GET** /panel/workspaces/{workspaceUuid}/subscription | Get subscription
[**remove_generic_subscription**](SubscriptionsApi.md#remove_generic_subscription) | **DELETE** /panel/workspaces/{workspaceUuid}/subscription/generic | Remove generic subscription
[**resume_subscription**](SubscriptionsApi.md#resume_subscription) | **POST** /panel/workspaces/{workspaceUuid}/subscription/resume | Resume subscription
[**update_subscription**](SubscriptionsApi.md#update_subscription) | **PUT** /panel/workspaces/{workspaceUuid}/subscription | Update subscription



## add_generic_subscription

> serde_json::Value add_generic_subscription(workspace_uuid, add_generic_subscription_request)
Add generic subscription

Assigns a non-Stripe (generic) subscription plan to the workspace, optionally granting a trial period. Used for AppSumo-style lifetime deals. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**add_generic_subscription_request** | [**AddGenericSubscriptionRequest**](AddGenericSubscriptionRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## cancel_subscription

> serde_json::Value cancel_subscription(workspace_uuid)
Cancel subscription

Cancels the workspace's Stripe subscription at the end of the current billing period. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## change_subscription_plan

> serde_json::Value change_subscription_plan(workspace_uuid, change_subscription_plan_request)
Change subscription plan

Switches the workspace to a different Stripe plan. Optionally prorates the change and bills immediately. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**change_subscription_plan_request** | [**ChangeSubscriptionPlanRequest**](ChangeSubscriptionPlanRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## checkout_subscription

> models::CheckoutSubscription200Response checkout_subscription(workspace_uuid, checkout_subscription_request)
New subscription checkout

Returns a Stripe Checkout URL for a new subscription.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**checkout_subscription_request** | [**CheckoutSubscriptionRequest**](CheckoutSubscriptionRequest.md) |  | [required] |

### Return type

[**models::CheckoutSubscription200Response**](checkoutSubscription_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## create_subscription

> serde_json::Value create_subscription(workspace_uuid, subscription_input)
Create subscription

Manually creates a subscription record for the workspace (for external billing integrations). Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**subscription_input** | [**SubscriptionInput**](SubscriptionInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_subscription

> serde_json::Value delete_subscription(workspace_uuid)
Delete subscription

Removes the subscription record from the workspace. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_subscription

> models::Subscription get_subscription(workspace_uuid)
Get subscription

Returns the active subscription for the workspace, or `null` if none exists. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::Subscription**](Subscription.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## remove_generic_subscription

> serde_json::Value remove_generic_subscription(workspace_uuid)
Remove generic subscription

Removes the generic (non-Stripe) subscription from the workspace. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## resume_subscription

> serde_json::Value resume_subscription(workspace_uuid)
Resume subscription

Resumes a previously canceled subscription before it expires. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_subscription

> serde_json::Value update_subscription(workspace_uuid, subscription_update_input)
Update subscription

Updates the plan ID, status, or trial/pause dates of an existing subscription. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**subscription_update_input** | [**SubscriptionUpdateInput**](SubscriptionUpdateInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


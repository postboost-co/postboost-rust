# \ReceiptsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**create_receipt**](ReceiptsApi.md#create_receipt) | **POST** /panel/receipts | Create receipt
[**delete_receipt**](ReceiptsApi.md#delete_receipt) | **DELETE** /panel/receipts/{receiptUuid} | Delete receipt
[**delete_receipts_bulk**](ReceiptsApi.md#delete_receipts_bulk) | **DELETE** /panel/receipts | Delete receipts (bulk)
[**get_receipt**](ReceiptsApi.md#get_receipt) | **GET** /panel/receipts/{receiptUuid} | Get receipt
[**list_receipts**](ReceiptsApi.md#list_receipts) | **GET** /panel/receipts | List receipts
[**update_receipt**](ReceiptsApi.md#update_receipt) | **PUT** /panel/receipts/{receiptUuid} | Update receipt



## create_receipt

> models::Receipt create_receipt(receipt_input)
Create receipt

Creates a billing receipt record for a workspace. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**receipt_input** | [**ReceiptInput**](ReceiptInput.md) |  | [required] |

### Return type

[**models::Receipt**](Receipt.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_receipt

> serde_json::Value delete_receipt(receipt_uuid)
Delete receipt

Permanently deletes a single receipt. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**receipt_uuid** | **uuid::Uuid** | UUID of the receipt. | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## delete_receipts_bulk

> serde_json::Value delete_receipts_bulk(delete_receipts_bulk_request)
Delete receipts (bulk)

Permanently deletes one or more receipt records. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**delete_receipts_bulk_request** | [**DeleteReceiptsBulkRequest**](DeleteReceiptsBulkRequest.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_receipt

> models::Receipt get_receipt(receipt_uuid)
Get receipt

Returns a single receipt by UUID. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**receipt_uuid** | **uuid::Uuid** | UUID of the receipt. | [required] |

### Return type

[**models::Receipt**](Receipt.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_receipts

> models::ListReceipts200Response list_receipts(workspace_uuid, invoice_number, page)
List receipts

Returns a paginated list of billing receipts. Filter by workspace UUID or invoice number. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | Option<**uuid::Uuid**> |  |  |
**invoice_number** | Option<**String**> |  |  |
**page** | Option<**i32**> | Page number (15 items per page). |  |[default to 1]

### Return type

[**models::ListReceipts200Response**](listReceipts_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_receipt

> serde_json::Value update_receipt(receipt_uuid, receipt_update_input)
Update receipt

Updates a receipt's transaction details, amount, or payment date. Admin only.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**receipt_uuid** | **uuid::Uuid** | UUID of the receipt. | [required] |
**receipt_update_input** | [**ReceiptUpdateInput**](ReceiptUpdateInput.md) |  | [required] |

### Return type

[**serde_json::Value**](serde_json::Value.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


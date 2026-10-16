# \FreeToolsApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**build_utm_url**](FreeToolsApi.md#build_utm_url) | **POST** /tools/utm-builder | Build a UTM-tagged campaign URL
[**calculate_aspect_ratio**](FreeToolsApi.md#calculate_aspect_ratio) | **POST** /tools/aspect-ratio-calculator | Calculate an aspect ratio, or the missing side of an image at a given ratio
[**calculate_crop**](FreeToolsApi.md#calculate_crop) | **POST** /tools/social-media-image-sizes/crop | Calculate the crop box that fits an image to a social media size
[**calculate_engagement_rate**](FreeToolsApi.md#calculate_engagement_rate) | **POST** /tools/engagement-rate-calculator | Calculate an engagement rate
[**check_link_preview**](FreeToolsApi.md#check_link_preview) | **POST** /tools/link-preview-checker | Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags)
[**check_post**](FreeToolsApi.md#check_post) | **POST** /tools/social-media-post-checker | Check a post against each network's publishing rules
[**clean_text**](FreeToolsApi.md#clean_text) | **POST** /tools/ai-text-cleaner | Clean AI-written text: dashes, quotes, invisible characters, markdown
[**count_characters**](FreeToolsApi.md#count_characters) | **POST** /tools/social-media-character-counter | Count characters as each network counts them
[**format_linked_in_post**](FreeToolsApi.md#format_linked_in_post) | **POST** /tools/linkedin-post-formatter | Format a LinkedIn post with bold, italic and lists
[**generate_caption**](FreeToolsApi.md#generate_caption) | **POST** /tools/instagram-caption-generator | Write three post captions for a topic with AI (needs a token, spends AI credits)
[**generate_fancy_text**](FreeToolsApi.md#generate_fancy_text) | **POST** /tools/fancy-text-generator | Convert text to fancy Unicode styles
[**generate_hashtags**](FreeToolsApi.md#generate_hashtags) | **POST** /tools/instagram-hashtag-generator | Generate hashtags for a post topic with AI (needs a token, spends AI credits)
[**generate_hooks**](FreeToolsApi.md#generate_hooks) | **POST** /tools/hook-generator | Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits)
[**generate_qr_code**](FreeToolsApi.md#generate_qr_code) | **POST** /tools/qr-code-generator | Generate a QR code (SVG) for a link or text, with optional UTM tags
[**get_best_times_to_post**](FreeToolsApi.md#get_best_times_to_post) | **GET** /tools/best-time-to-post | Get the best times to post per network from published studies, with sources
[**get_hook_templates**](FreeToolsApi.md#get_hook_templates) | **GET** /tools/hook-generator/library | Get free hook templates for social media posts, filtered by style and network
[**get_image_sizes**](FreeToolsApi.md#get_image_sizes) | **GET** /tools/social-media-image-sizes | Get social media image sizes per network, each with its source
[**list_free_tools**](FreeToolsApi.md#list_free_tools) | **GET** /tools | List the free tools
[**preview_post**](FreeToolsApi.md#preview_post) | **POST** /tools/social-media-post-preview | Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook
[**split_thread**](FreeToolsApi.md#split_thread) | **POST** /tools/x-thread-maker | Split long text into a thread



## build_utm_url

> models::FreeToolBuildUtmUrlResponse build_utm_url(free_tool_build_utm_url_request)
Build a UTM-tagged campaign URL

Build a UTM-tagged campaign URL. The same logic as the free web tool at https://postboost.co/tools/utm-builder. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_build_utm_url_request** | [**FreeToolBuildUtmUrlRequest**](FreeToolBuildUtmUrlRequest.md) |  | [required] |

### Return type

[**models::FreeToolBuildUtmUrlResponse**](FreeToolBuildUtmUrlResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculate_aspect_ratio

> models::FreeToolCalculateAspectRatioResponse calculate_aspect_ratio(free_tool_calculate_aspect_ratio_request)
Calculate an aspect ratio, or the missing side of an image at a given ratio

Calculate an aspect ratio, or the missing side of an image at a given ratio. The same logic as the free web tool at https://postboost.co/tools/aspect-ratio-calculator. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_calculate_aspect_ratio_request** | [**FreeToolCalculateAspectRatioRequest**](FreeToolCalculateAspectRatioRequest.md) |  | [required] |

### Return type

[**models::FreeToolCalculateAspectRatioResponse**](FreeToolCalculateAspectRatioResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculate_crop

> models::FreeToolCalculateCropResponse calculate_crop(free_tool_calculate_crop_request)
Calculate the crop box that fits an image to a social media size

Calculate the crop box that fits an image to a social media size. The same logic as the free web tool at https://postboost.co/tools/social-media-image-sizes. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_calculate_crop_request** | [**FreeToolCalculateCropRequest**](FreeToolCalculateCropRequest.md) |  | [required] |

### Return type

[**models::FreeToolCalculateCropResponse**](FreeToolCalculateCropResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## calculate_engagement_rate

> models::FreeToolCalculateEngagementRateResponse calculate_engagement_rate(free_tool_calculate_engagement_rate_request)
Calculate an engagement rate

Calculate an engagement rate. The same logic as the free web tool at https://postboost.co/tools/engagement-rate-calculator. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_calculate_engagement_rate_request** | [**FreeToolCalculateEngagementRateRequest**](FreeToolCalculateEngagementRateRequest.md) |  | [required] |

### Return type

[**models::FreeToolCalculateEngagementRateResponse**](FreeToolCalculateEngagementRateResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## check_link_preview

> models::FreeToolCheckLinkPreviewResponse check_link_preview(free_tool_check_link_preview_request)
Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags)

Check how a link previews on X, LinkedIn, Facebook and chat apps (Open Graph and Twitter card tags). The same logic as the free web tool at https://postboost.co/tools/link-preview-checker. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_check_link_preview_request** | [**FreeToolCheckLinkPreviewRequest**](FreeToolCheckLinkPreviewRequest.md) |  | [required] |

### Return type

[**models::FreeToolCheckLinkPreviewResponse**](FreeToolCheckLinkPreviewResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## check_post

> models::FreeToolCheckPostResponse check_post(free_tool_check_post_request)
Check a post against each network's publishing rules

Check a post against each network's publishing rules. The same logic as the free web tool at https://postboost.co/tools/social-media-post-checker. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_check_post_request** | [**FreeToolCheckPostRequest**](FreeToolCheckPostRequest.md) |  | [required] |

### Return type

[**models::FreeToolCheckPostResponse**](FreeToolCheckPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## clean_text

> models::FreeToolCleanTextResponse clean_text(free_tool_clean_text_request)
Clean AI-written text: dashes, quotes, invisible characters, markdown

Clean AI-written text: dashes, quotes, invisible characters, markdown. The same logic as the free web tool at https://postboost.co/tools/ai-text-cleaner. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_clean_text_request** | [**FreeToolCleanTextRequest**](FreeToolCleanTextRequest.md) |  | [required] |

### Return type

[**models::FreeToolCleanTextResponse**](FreeToolCleanTextResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## count_characters

> models::FreeToolCountCharactersResponse count_characters(free_tool_count_characters_request)
Count characters as each network counts them

Count characters as each network counts them. The same logic as the free web tool at https://postboost.co/tools/social-media-character-counter. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_count_characters_request** | [**FreeToolCountCharactersRequest**](FreeToolCountCharactersRequest.md) |  | [required] |

### Return type

[**models::FreeToolCountCharactersResponse**](FreeToolCountCharactersResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## format_linked_in_post

> models::FreeToolFormatLinkedInPostResponse format_linked_in_post(free_tool_format_linked_in_post_request)
Format a LinkedIn post with bold, italic and lists

Format a LinkedIn post with bold, italic and lists. The same logic as the free web tool at https://postboost.co/tools/linkedin-post-formatter. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_format_linked_in_post_request** | [**FreeToolFormatLinkedInPostRequest**](FreeToolFormatLinkedInPostRequest.md) |  | [required] |

### Return type

[**models::FreeToolFormatLinkedInPostResponse**](FreeToolFormatLinkedInPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generate_caption

> models::FreeToolGenerateCaptionResponse generate_caption(free_tool_generate_caption_request)
Write three post captions for a topic with AI (needs a token, spends AI credits)

Write three post captions for a topic with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-caption-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_generate_caption_request** | [**FreeToolGenerateCaptionRequest**](FreeToolGenerateCaptionRequest.md) |  | [required] |

### Return type

[**models::FreeToolGenerateCaptionResponse**](FreeToolGenerateCaptionResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generate_fancy_text

> models::FreeToolGenerateFancyTextResponse generate_fancy_text(free_tool_generate_fancy_text_request)
Convert text to fancy Unicode styles

Convert text to fancy Unicode styles. The same logic as the free web tool at https://postboost.co/tools/fancy-text-generator. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_generate_fancy_text_request** | [**FreeToolGenerateFancyTextRequest**](FreeToolGenerateFancyTextRequest.md) |  | [required] |

### Return type

[**models::FreeToolGenerateFancyTextResponse**](FreeToolGenerateFancyTextResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generate_hashtags

> models::FreeToolGenerateHashtagsResponse generate_hashtags(free_tool_generate_hashtags_request)
Generate hashtags for a post topic with AI (needs a token, spends AI credits)

Generate hashtags for a post topic with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/instagram-hashtag-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_generate_hashtags_request** | [**FreeToolGenerateHashtagsRequest**](FreeToolGenerateHashtagsRequest.md) |  | [required] |

### Return type

[**models::FreeToolGenerateHashtagsResponse**](FreeToolGenerateHashtagsResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generate_hooks

> models::FreeToolGenerateHooksResponse generate_hooks(free_tool_generate_hooks_request)
Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits)

Generate hooks (opening lines) for a social media post with AI (needs a token, spends AI credits). The same logic as the free web tool at https://postboost.co/tools/hook-generator. Needs an API token (a scoped key needs the `ai` ability and pays with its own workspace). A new generation spends 1 AI credit of the workspace you name (or your active workspace); a repeated identical request is answered from the cache for free.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_generate_hooks_request** | [**FreeToolGenerateHooksRequest**](FreeToolGenerateHooksRequest.md) |  | [required] |

### Return type

[**models::FreeToolGenerateHooksResponse**](FreeToolGenerateHooksResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## generate_qr_code

> models::FreeToolGenerateQrCodeResponse generate_qr_code(free_tool_generate_qr_code_request)
Generate a QR code (SVG) for a link or text, with optional UTM tags

Generate a QR code (SVG) for a link or text, with optional UTM tags. The same logic as the free web tool at https://postboost.co/tools/qr-code-generator. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_generate_qr_code_request** | [**FreeToolGenerateQrCodeRequest**](FreeToolGenerateQrCodeRequest.md) |  | [required] |

### Return type

[**models::FreeToolGenerateQrCodeResponse**](FreeToolGenerateQrCodeResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_best_times_to_post

> models::FreeToolGetBestTimesToPostResponse get_best_times_to_post(network)
Get the best times to post per network from published studies, with sources

Get the best times to post per network from published studies, with sources. The same logic as the free web tool at https://postboost.co/tools/best-time-to-post. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**network** | Option<**String**> |  |  |

### Return type

[**models::FreeToolGetBestTimesToPostResponse**](FreeToolGetBestTimesToPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_hook_templates

> models::FreeToolGetHookTemplatesResponse get_hook_templates(topic, category, network, search)
Get free hook templates for social media posts, filtered by style and network

Get free hook templates for social media posts, filtered by style and network. The same logic as the free web tool at https://postboost.co/tools/hook-generator. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**topic** | Option<**String**> |  |  |
**category** | Option<**String**> |  |  |
**network** | Option<**String**> |  |  |
**search** | Option<**String**> |  |  |

### Return type

[**models::FreeToolGetHookTemplatesResponse**](FreeToolGetHookTemplatesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_image_sizes

> models::FreeToolGetImageSizesResponse get_image_sizes(network)
Get social media image sizes per network, each with its source

Get social media image sizes per network, each with its source. The same logic as the free web tool at https://postboost.co/tools/social-media-image-sizes. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**network** | Option<**String**> |  |  |

### Return type

[**models::FreeToolGetImageSizesResponse**](FreeToolGetImageSizesResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## list_free_tools

> models::FreeToolList list_free_tools()
List the free tools

Every free tool the API serves, with its operationId and web page. No token needed.

### Parameters

This endpoint does not need any parameter.

### Return type

[**models::FreeToolList**](FreeToolList.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## preview_post

> models::FreeToolPreviewPostResponse preview_post(free_tool_preview_post_request)
Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook

Preview where a post folds and when its image is cropped on Instagram, X, LinkedIn and Facebook. The same logic as the free web tool at https://postboost.co/tools/social-media-post-preview. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_preview_post_request** | [**FreeToolPreviewPostRequest**](FreeToolPreviewPostRequest.md) |  | [required] |

### Return type

[**models::FreeToolPreviewPostResponse**](FreeToolPreviewPostResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## split_thread

> models::FreeToolSplitThreadResponse split_thread(free_tool_split_thread_request)
Split long text into a thread

Split long text into a thread. The same logic as the free web tool at https://postboost.co/tools/x-thread-maker. No account needed: call it without a token, or with any API token.

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**free_tool_split_thread_request** | [**FreeToolSplitThreadRequest**](FreeToolSplitThreadRequest.md) |  | [required] |

### Return type

[**models::FreeToolSplitThreadResponse**](FreeToolSplitThreadResponse.md)

### Authorization

No authorization required

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


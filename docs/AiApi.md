# \AiApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**blog_to_social**](AiApi.md#blog_to_social) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
[**image_alt_text**](AiApi.md#image_alt_text) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
[**image_edit**](AiApi.md#image_edit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
[**image_generate**](AiApi.md#image_generate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
[**image_prompt**](AiApi.md#image_prompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
[**image_variations**](AiApi.md#image_variations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image



## blog_to_social

> models::BlogToSocial200Response blog_to_social(workspace_uuid, blog_to_social_input)
Generate social media captions from a blog post

Generates platform-specific social media captions from a blog post URL or directly provided title and excerpt. Each platform generates one caption, which consumes one AI credit from the workspace's monthly allowance.  **Input modes** (at least one required): - **URL mode**: provide `url` and the API scrapes the blog content automatically, including detecting the featured image via `og:image`. - **Direct mode**: provide `title` and `excerpt` directly (no scraping).  If both are provided, direct values take priority.  When `create_post` is `true`, a draft post is created in the workspace with per-account caption versions. If an image is available (from `image_url` or the scraped `og:image`), it is imported into the workspace media library and attached to the draft post. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**blog_to_social_input** | [**BlogToSocialInput**](BlogToSocialInput.md) |  | [required] |

### Return type

[**models::BlogToSocial200Response**](blogToSocial_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## image_alt_text

> models::ImageAltText200Response image_alt_text(workspace_uuid, image_alt_text_input)
Generate alt text for a media image using AI

Analyzes an existing workspace media item and generates accessible alt text. The alt text is saved back to the media record. Costs 1 AI credit per call. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**image_alt_text_input** | [**ImageAltTextInput**](ImageAltTextInput.md) |  | [required] |

### Return type

[**models::ImageAltText200Response**](imageAltText_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## image_edit

> models::ImageGenerate200Response image_edit(workspace_uuid, image_edit_input)
Edit an existing media image using AI

Edits an existing workspace media item using the source image and a text prompt. Optionally accepts a mask (transparent areas are replaced). Saves results to the media library. Credits: `count × credit_weight`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**image_edit_input** | [**ImageEditInput**](ImageEditInput.md) |  | [required] |

### Return type

[**models::ImageGenerate200Response**](imageGenerate_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## image_generate

> models::ImageGenerate200Response image_generate(workspace_uuid, image_generate_input)
Generate social media images from a caption

Generates one or more images and saves them immediately to the workspace media library.  **Standard mode** (recommended): provide `caption` + `platform`. PostBoost builds a professional image prompt internally using platform-specific templates. No prompt engineering required.  **Developer mode**: provide `prompt` directly to bypass prompt building. If both `caption` and `prompt` are sent, standard mode runs.  Credits: `count x credit_weight` (default: 5 per image). 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**image_generate_input** | [**ImageGenerateInput**](ImageGenerateInput.md) |  | [required] |

### Return type

[**models::ImageGenerate200Response**](imageGenerate_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## image_prompt

> models::ImagePrompt200Response image_prompt(workspace_uuid, image_prompt_input)
Build an optimized image prompt from a social media caption

Builds a professional image generation prompt from a caption and platform. No image is generated. Use this to preview the prompt before calling `image-generate`. Costs 1 AI credit per call.  When `image-generate` builds the prompt internally (standard mode), no credit is charged for the prompt step. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**image_prompt_input** | [**ImagePromptInput**](ImagePromptInput.md) |  | [required] |

### Return type

[**models::ImagePrompt200Response**](imagePrompt_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## image_variations

> models::ImageVariations200Response image_variations(workspace_uuid, image_variations_input)
Generate variations of an existing media image

Creates one or more variations of an existing workspace media item. Saves results to the media library. Credits: `count × credit_weight`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**image_variations_input** | [**ImageVariationsInput**](ImageVariationsInput.md) |  | [required] |

### Return type

[**models::ImageVariations200Response**](imageVariations_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


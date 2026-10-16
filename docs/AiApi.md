# \AiApi

All URIs are relative to *https://postboost.co/app/api*

Method | HTTP request | Description
------------- | ------------- | -------------
[**blog_to_social**](AiApi.md#blog_to_social) | **POST** /{workspaceUuid}/ai/blog-to-social | Generate social media captions from a blog post
[**delete_brand_voice**](AiApi.md#delete_brand_voice) | **DELETE** /{workspaceUuid}/brand-voice | Delete the brand voice
[**get_ai_usage**](AiApi.md#get_ai_usage) | **GET** /{workspaceUuid}/usage/ai | AI credit usage
[**get_brand_voice**](AiApi.md#get_brand_voice) | **GET** /{workspaceUuid}/brand-voice | Get the brand voice
[**get_repurpose_run**](AiApi.md#get_repurpose_run) | **GET** /{workspaceUuid}/ai/repurpose/runs/{runId} | Get a repurpose run
[**image_alt_text**](AiApi.md#image_alt_text) | **POST** /{workspaceUuid}/ai/image-alt-text | Generate alt text for a media image using AI
[**image_edit**](AiApi.md#image_edit) | **POST** /{workspaceUuid}/ai/image-edit | Edit an existing media image using AI
[**image_generate**](AiApi.md#image_generate) | **POST** /{workspaceUuid}/ai/image-generate | Generate social media images from a caption
[**image_prompt**](AiApi.md#image_prompt) | **POST** /{workspaceUuid}/ai/image-prompt | Build an optimized image prompt from a social media caption
[**image_variations**](AiApi.md#image_variations) | **POST** /{workspaceUuid}/ai/image-variations | Generate variations of an existing media image
[**learn_brand_voice**](AiApi.md#learn_brand_voice) | **POST** /{workspaceUuid}/brand-voice/learn | Learn a brand voice from past posts
[**repurpose_content**](AiApi.md#repurpose_content) | **POST** /{workspaceUuid}/ai/repurpose | Repurpose long-form content into a draft post set with a carousel
[**update_brand_voice**](AiApi.md#update_brand_voice) | **PUT** /{workspaceUuid}/brand-voice | Create or update the brand voice



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


## delete_brand_voice

> serde_json::Value delete_brand_voice(workspace_uuid)
Delete the brand voice

Removes the workspace's brand voice. AI endpoints then run without one. Admins and members only.

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


## get_ai_usage

> models::AiUsage get_ai_usage(workspace_uuid)
AI credit usage

The workspace's AI credits: text credits (captions, rewrites, outlines, alt text; counted per billing cycle) and image credits (one per generated, edited or varied image, and one per repurpose carousel; counted per calendar month, UTC). `limit` and `remaining` are `null` when the workspace has no limit. Readable when credits are used up; costs nothing.  When image credits run out, the image endpoints and carousels answer `429` with `code: image_credits_exhausted`; when text credits run out, the AI endpoints answer `429` with `code: ai_credits_exhausted`. Image endpoint responses also carry `image_credits_used` and `image_credits_remaining`; their `credits_used` counts text credits only. If the image pool is switched off (`image.enabled: false`), images cost text credits as before. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::AiUsage**](AIUsage.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_brand_voice

> models::GetBrandVoice200Response get_brand_voice(workspace_uuid)
Get the brand voice

The workspace's brand voice: identity, audience, tone sliders, style rules and example posts. It is the same profile as the Brand Voice page in the app (one per workspace). `data` is `null` when no voice is set. Any workspace member may read it; reading costs no AI credits.  The AI endpoints apply it automatically: `blog-to-social` adds it to the caption instructions, `image-prompt` and `image-generate` turn it into a short visual tone line, and `image-edit` applies it when you send `use_brand_voice: true`. `image-variations` and `image-alt-text` never use it (alt text must describe the image literally). Send `use_brand_voice: false` to skip it on a call; responses report `meta.brand_voice_applied`. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |

### Return type

[**models::GetBrandVoice200Response**](getBrandVoice_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## get_repurpose_run

> models::GetRepurposeRun200Response get_repurpose_run(workspace_uuid, run_id)
Get a repurpose run

Status of a run started by `repurposeContent`. `queued` and `running` mean it is still going; poll again in a few seconds. A run that has not finished after 10 minutes reports `failed`. `result` holds the same `data` body a `200` from `repurposeContent` returns, for one hour after the run ended with `ok` or `partial`; after that it is `null` (the draft post stays). Limited to 60 calls per minute. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**run_id** | **i32** | The `run_id` from `repurposeContent`. | [required] |

### Return type

[**models::GetRepurposeRun200Response**](getRepurposeRun_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: Not defined
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

Edits an existing workspace media item using the source image and a text prompt. Optionally accepts a mask (transparent areas are replaced). Saves results to the media library. Credits: 1 image credit per image (`429 image_credits_exhausted` when the monthly pool is empty). If the image pool is switched off, `count × credit_weight` text credits instead. 

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

Generates one or more images and saves them immediately to the workspace media library.  **Standard mode** (recommended): provide `caption` + `platform`. PostBoost builds a professional image prompt internally using platform-specific templates. No prompt engineering required.  **Developer mode**: provide `prompt` directly to bypass prompt building. If both `caption` and `prompt` are sent, standard mode runs.  Credits: 1 image credit per image (`429 image_credits_exhausted` when the monthly pool is empty). If the image pool is switched off, `count × credit_weight` text credits instead. 

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

Creates one or more variations of an existing workspace media item. Saves results to the media library. Credits: 1 image credit per image (`429 image_credits_exhausted` when the monthly pool is empty). If the image pool is switched off, `count × credit_weight` text credits instead. 

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


## learn_brand_voice

> models::LearnBrandVoiceResponse learn_brand_voice(workspace_uuid, learn_brand_voice_input)
Learn a brand voice from past posts

Reads the workspace's latest published posts (original text) and proposes a brand voice in the same shape as `GET /brand-voice`. Returns a draft and saves nothing unless `apply: true`.  Without `overwrite`, learned values only fill fields that are empty (tone sliders and styles still at their defaults count as empty); with `overwrite: true` they replace them. The first five sampled posts become `example_posts`. Needs at least 3 published posts (`422`, `code: not_enough_posts`). Costs one AI text credit per AI call (one retry when the reply is not usable). Admins and members only. A key limited to some accounts must send `account_ids`; only posts whose accounts are all among them are read. `apply` also needs the `write` ability. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**learn_brand_voice_input** | Option<[**LearnBrandVoiceInput**](LearnBrandVoiceInput.md)> |  |  |

### Return type

[**models::LearnBrandVoiceResponse**](LearnBrandVoiceResponse.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## repurpose_content

> models::RepurposeContent200Response repurpose_content(workspace_uuid, repurpose_input, idempotency_key)
Repurpose long-form content into a draft post set with a carousel

Turns an article URL, a YouTube video, a PDF or pasted text into one **draft** post with a caption for every target account, plus a carousel of rendered slide images (hook, 1 to 6 idea slides, call to action; 1080×1350 PNG). Nothing is published or scheduled.  **Sources** (`source_type`): - `url`: the article is fetched and its main text extracted. - `youtube`: title, description and chapters come from YouTube; send the transcript in   `transcript` for better results (required when the description is short). - `pdf`: `pdf_url` must be a public PDF of at most 20 MB; the first 30 pages are read. - `text`: send `title` and `text`.  **Carousel per network**: Instagram, Facebook, Threads up to 10 slides; LinkedIn up to 9; X and Bluesky up to 4; other networks get the cover slide; YouTube and TikTok get none (listed in `warnings`). Without a carousel, the source image (article image or video thumbnail) is attached when available.  **AI credits**: one per target account plus one for the carousel outline. Slides are drawn without AI and cost nothing. The workspace brand voice applies unless `use_brand_voice` is `false`. Send an `Idempotency-Key` so a retried call does not create a second draft. Limited to 10 calls per minute.  **Long runs**: the run is queued. The call waits up to 20 seconds and answers `200` with the result when the run finished by then. Otherwise it answers `202` with a `run_id`; poll `getRepurposeRun` (`status_url`) every few seconds until the status is `ok`, `partial` or `failed`. Send `async: true` to get the `202` right away. Validation, account and credit errors are answered before anything is queued. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**repurpose_input** | [**RepurposeInput**](RepurposeInput.md) |  | [required] |
**idempotency_key** | Option<**String**> | Unique key (for example a UUID) that makes the request safe to retry. A repeat with the same key and body within 24 hours returns the stored response with `Idempotent-Replayed: true` and has no further effect. Keys are scoped to your user, the workspace, the method and the path.  |  |

### Return type

[**models::RepurposeContent200Response**](repurposeContent_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


## update_brand_voice

> models::GetBrandVoice200Response update_brand_voice(workspace_uuid, brand_voice_input)
Create or update the brand voice

Creates the workspace's brand voice or updates it. Fields you leave out keep their current value. Admins and members only (not viewers); the workspace must have AI enabled. 

### Parameters


Name | Type | Description  | Required | Notes
------------- | ------------- | ------------- | ------------- | -------------
**workspace_uuid** | **uuid::Uuid** | UUID of the workspace. | [required] |
**brand_voice_input** | [**BrandVoiceInput**](BrandVoiceInput.md) |  | [required] |

### Return type

[**models::GetBrandVoice200Response**](getBrandVoice_200_response.md)

### Authorization

[bearerAuth](../README.md#bearerAuth)

### HTTP request headers

- **Content-Type**: application/json
- **Accept**: application/json

[[Back to top]](#) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to Model list]](../README.md#documentation-for-models) [[Back to README]](../README.md)


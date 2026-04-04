# BlogToSocialInput

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**url** | Option<**String**> | Blog post URL to scrape. Required if `title` and `excerpt` are not provided. | [optional]
**title** | Option<**String**> | Blog post title. Required if `url` is not provided. | [optional]
**excerpt** | Option<**String**> | Blog post summary or excerpt. Required if `url` is not provided. | [optional]
**image_url** | Option<**String**> | Featured image URL for the blog post. When `create_post` is `true`, the image is imported into the workspace media library and attached to the draft post. If omitted in URL mode, the scraper attempts to extract the `og:image` meta tag.  | [optional]
**platforms** | Option<**Vec<String>**> | Target social media platforms. Only connected accounts matching these platforms are used. If omitted, all connected accounts in the workspace are targeted.  | [optional]
**account_ids** | Option<**Vec<i32>**> | Specific account IDs to generate captions for. Takes precedence over `platforms` when both are provided.  | [optional]
**tone** | Option<**String**> | Writing tone for all generated captions. | [optional][default to Engaging]
**content_length** | Option<**String**> | Desired length of the generated captions. | [optional][default to Medium]
**hashtags** | Option<**String**> | Hashtag quantity: none (0), few (1-3), some (3-5), many (5+). | [optional][default to Few]
**cta** | Option<**String**> | Call-to-action type appended to each caption. | [optional][default to None]
**language** | Option<**String**> | Output language as an ISO 639-1 code (e.g. `en`, `de`, `fr`). Use `auto` to match the blog post's language automatically.  | [optional][default to auto]
**custom_instructions** | Option<**String**> | Additional instructions appended to the AI prompt (e.g. \"always mention our free tier\"). | [optional]
**create_post** | Option<**bool**> | When `true`, creates a draft post in the workspace with per-account caption versions. If an image is available, it is imported and attached to the post.  | [optional][default to false]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



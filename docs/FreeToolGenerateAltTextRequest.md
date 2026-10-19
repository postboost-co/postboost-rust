# FreeToolGenerateAltTextRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**image_base64** | Option<**String**> | The image itself, base64-encoded without a `data:` prefix: JPEG, PNG, WebP or GIF (first frame), up to 5 MB. On the API you can upload the file as `image` in a multipart/form-data body instead. A request to the MCP server at /mcp/tools may be at most 1.5 MB, so send larger images as `image_url` there. Send this or `image_url`. | [optional]
**image_url** | Option<**String**> | A public https URL of the image, up to 5 MB. Fetched once and never stored; each fetch also counts against the daily limit of the tools that load a URL. Send this or `image_base64`. | [optional]
**context** | Option<**String**> | Optional: what the post is about, so the text describes what matters for it. | [optional]
**length** | Option<**String**> | short (up to 125 characters) or detailed (up to 250). | [optional][default to Short]
**workspace** | Option<**String**> | UUID of the workspace whose AI credits pay for the call. Default: your active workspace (a scoped API key: its own workspace). | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



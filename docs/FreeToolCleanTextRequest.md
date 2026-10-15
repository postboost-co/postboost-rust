# FreeToolCleanTextRequest

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**text** | **String** |  | 
**dashes** | Option<**String**> | What replaces an em or en dash between words: \", \" (comma), \"-\" (hyphen), \" - \" (spaced) or nothing (keep). Number ranges like 2020–2024 always get a hyphen. | [optional][default to Comma]
**quotes** | Option<**bool**> | Curly quotes and apostrophes to straight ones. | [optional][default to true]
**invisible** | Option<**bool**> | Remove zero-width characters and soft hyphens; turn non-breaking and thin spaces into normal spaces. | [optional][default to true]
**spaces** | Option<**bool**> | Collapse double spaces between words and remove spaces at line ends. | [optional][default to true]
**ellipsis** | Option<**bool**> | The ellipsis character to three dots. | [optional][default to true]
**markdown** | Option<**bool**> | Strip **bold**, __bold__, *italic* and _italic_ markers, keeping the words. | [optional][default to true]
**flag_phrases** | Option<**bool**> | List common AI phrases (e.g. \"delve\") with their offsets. They are never changed. | [optional][default to true]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



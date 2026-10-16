# FreeToolCheckReadabilityResponse

## Properties

Name | Type | Description | Notes
------------ | ------------- | ------------- | -------------
**supported** | Option<**bool**> | False for a language other than English: no scores, hints or suggestions. | [optional]
**note** | Option<**String**> | Why the text was not scored, or null. | [optional]
**flesch_reading_ease** | Option<**f64**> | Flesch reading ease, one decimal: higher is easier, 60-70 is plain English. Null when not scored. | [optional]
**flesch_kincaid_grade** | Option<**f64**> | Flesch-Kincaid grade level, one decimal: the US school grade that can read the text. Null when not scored. | [optional]
**sentences** | Option<**i32**> | Sentences with at least one word. | [optional]
**words** | Option<**i32**> | Words, not counting hashtags, @mentions, links and emoji. | [optional]
**syllables** | Option<**i32**> | Syllables, by the heuristic described in the docs. | [optional]
**avg_words_per_sentence** | Option<**f64**> | Words per sentence, one decimal. | [optional]
**long_sentences** | Option<[**Vec<models::FreeToolCheckReadabilityResponseLongSentencesInner>**](FreeToolCheckReadabilityResponse_long_sentences_inner.md)> | Sentences of more than 25 words. | [optional]
**passive_hints** | Option<**i32**> | Possible passive phrases (\"was written\", \"is being reviewed\"). A hint, not a grammar check. | [optional]
**emoji_count** | Option<**i32**> | Emoji (Extended_Pictographic characters). | [optional]
**hashtag_count** | Option<**i32**> | Hashtags. | [optional]
**suggestions** | Option<**Vec<String>**> | Plain fixes, e.g. which sentence to split. Empty when the text reads easily. | [optional]

[[Back to Model list]](../README.md#documentation-for-models) [[Back to API list]](../README.md#documentation-for-api-endpoints) [[Back to README]](../README.md)



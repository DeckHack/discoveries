# ChirpBase

Base model for chirps (objects displayed in columns)

## Table of Contents

* [Properties](#properties)
* [Methods](#methods)
  * [belongsAbove](#belongsabove)
  * [belongsBelow](#belongsbelow)
  * [createdPretty](#createdpretty)
  * [createdPrettyFull](#createdprettyfull)
  * [createdPrettyTimeOrDate](#createdprettytimeordate)
  * [destroy](#destroy)
  * [email](#email)
  * [fromJSONObject](#fromjsonobject)
  * [fudgeCreatedTime](#fudgecreatedtime)
  * [getApiBounds](#getapibounds)
  * [getCardUrl](#getcardurl)
  * [getCardsForGallery](#getcardsforgallery)
  * [getChirpType](#getchirptype)
  * [getChirpURL](#getchirpurl)
  * [getDOMChirps](#getdomchirps)
  * [getFilterableText](#getfilterabletext)
  * [getMedia](#getmedia)
  * [getNotificationData](#getnotificationdata)
  * [getRelatedTweet](#getrelatedtweet)
  * [getScribeItemData](#getscribeitemdata)
  * [getSenders](#getsenders)
  * [getSinceId](#getsinceid)
  * [getSortIndex](#getsortindex)
  * [getUnreadChirps](#getunreadchirps)
  * [hasAnimatedGif](#hasanimatedgif)
  * [hasCard](#hascard)
  * [hasImage](#hasimage)
  * [hasLink](#haslink)
  * [hasMedia](#hasmedia)
  * [hasVideo](#hasvideo)
  * [hasVine](#hasvine)
  * [isFromVerifiedUser](#isfromverifieduser)
  * [isMediaGridContent](#ismediagridcontent)
  * [isOwnChirp](#isownchirp)
  * [isRetweetedStatus](#isretweetedstatus)
  * [isStreamed](#isstreamed)
  * [isTranslatable](#istranslatable)
  * [mediaLength](#medialength)
  * [passFilters](#passfilters)
  * [postComment](#postcomment)
  * [render](#render)
  * [scribeMediaImpression](#scribemediaimpression)
  * [setApiBounds](#setapibounds)
  * [translate](#translate)
  * [_generateHTMLText](#generatehtmltext)

## Properties

| Name | Description |
|------|-------------|
| `apiBounds` | API bounds of this chirp |
| `apiSource` | API source of this chirp |
| `chirpType` | Type of this chirp, usually defined by child classes |
| `created` | Creation date of this chirp |
| `creatorAccount` | ??? |
| `cursor` | ??? |
| `embeds` | ??? |
| `htmlText` | HTML formatted text of this chirp |
| `id` | ID of this chirp |
| `isListAction` | Boolean flag if this chirp is a list action |
| `isQuoteStatus` | Boolean flag if this chirp contains a quote |
| `sortIndex` | Object containing information on column sorting |
| `text` | Text of this chirp |
| `_hasAnimatedGif` | Boolean flag if this chirp has a animated GIF |
| `_hasImage` | Boolean flag if this chirp has an image |
| `_hasLink` | Boolean flag if this chirp has a link |
| `_hasVideo` | Boolean flag if this chirp has a video |
| `_hasVine` | Boolean flag if this chirp contains a Vine |

## Methods

### _belongsAbove_

**Parameters:**  
* `e` ChirpBase

**Description:**  
Returns if this chirp belongs above another chirp

### _belongsBelow_

**Parameters:**  
* `e` ChirpBase

**Description:**  
Returns if this chirp belongs below another chirp

### _createdPretty_

**Parameters:**  
None

**Description:**  
Returns prettified creation date of this chirp

### _createdPrettyFull_

**Parameters:**  
None

**Description:**  
Returns prettified full creation date of this chirp

### _createdPrettyTimeOrDate_

**Parameters:**  
None

**Description:**  
Returns prettified creation time or date of this chirp

### _destroy_

**Parameters:**  
None

**Description:**
Destroys this chirp

### _email_

### _fromJSONObject_

### _fudgeCreatedTime_

**Parameters:**  
* `e` ???

**Description:**  
Fudges the creation date of the current chirp

### _getApiBounds_

**Parameters:**  
* `e` API boundary _(optional)_

**Description:**  
Returns API bounds

### _getCardUrl_

**Parameters:**  
None

**Description:**  
Returns the card URL of the current tweet

### _getCardsForGallery_

### _getChirpType_

**Parameters:**  
None

**Description:**  
Returns the chirp type

### _getChirpURL_

### _getDOMChirps_

**Parameters:**  
None

**Description:**  
Returns DOM object of this chirp

### _getFilterableText_

**Parameters:**  
None

**Description:**  
Returns plain text of this chirp

### _getMedia_

**Parameters:**  
None

**Description:**  
Returns media of this chirp

### _getNotificationData_

### _getRelatedTweet_

### _getScribeItemData_

### _getSenders_

### _getSinceId_

**Parameters:**  
None

**Description:**  
Returns ID of this chirp

### _getSortIndex_

**Parameters:**  
None

**Description:**  
Returns sort index of this chirp

### _getUnreadChirps_

**Parameters:**  
* `e` ChirpBase

**Description:**  
Returns read status of chirp

### _hasAnimatedGif_

**Parameters:**  
None

**Description:**  
Returns if this chirp has a animated GIF

### _hasCard_

**Parameters:**  
None

**Description:**  
Returns if this chirp has a card

### _hasImage_

**Parameters:**  
None

**Description:**  
Returns if this chirp has a image

### _hasLink_

**Parameters:**  
None

**Description:**  
Returns if this chirp has a link

### _hasMedia_

**Parameters:**  
None

**Description:**  
Returns if this chirp has media attached

### _hasVideo_

**Parameters:**  
None

**Description:**  
Returns if this chirp has a video

### _hasVine_

**Parameters:**  
None

**Description:**  
Returns if this chirp has a Vine attached

### _isFromVerifiedUser_

### _isMediaGridContent_

**Parameters:**  
None

**Description:**  
Returns if this chirp has more than one piece of media

### _isOwnChirp_

### _isRetweetedStatus_

### _isStreamed_

**Parameters:**  
None

**Description:**  
Returns if this chirp was streamed in realtime

### _isTranslatable_

### _mediaLength_

**Parameters:**  
None

**Description:**  
Returns count of attached media

### _passFilters_

**Parameters:**  
* ??? (optional)

**Description:**  
Checks if this chirp passes all filters

### _postComment_

### _render_

### _scribeMediaImpression_

### _setApiBounds_

**Parameters:**  
* `e` API boundary
* `t` Boundary data

**Description:**  
Sets API bounds

### _translate_

### __generateHTMLText_

**Parameters:**  
None

**Description:**  
Generates HTML text for this chirp
# Settings

How TweetDeck is saving and getting your preferences!

## Table of Contents

* [Location](#location)
* [Methods](#methods)
  * [init](#init)
  * [addSafeguardedAccount](#addsafeguardedaccount)
  * [removeSafeguardedAccount](#removesafeguardedaccount)
  * [getAccountSelectorGridMode](#getaccountselectorgridmode)
  * [getBitlyAccount](#getbitlyaccount)
  * [getCheckForUpdates](#getcheckforupdates)
  * [getColumnWidth](#getcolumnwidth)
  * [getComposeStayOpen](#getcomposestayopen)
  * [getDataminrAuthToken](#getdataminrauthtoken)
  * [getDisplaySensitiveMedia](#getdisplaysensitivemedia)
  * [getFontSize](#getfontsize)
  * [getGlobalFilter](#getglobalfilter)
  * [getIdsForSeenMessages](#getidsforseenmessages)
  * [getLanguage](#getlanguage)
  * [getLinkShortener](#getlinkshortener)
  * [getNameCache](#getnamecache)
  * [getNavbarWidth](#getnavbarwidth)
  * [getPreviousSplashVersion](#getprevioussplashversion)
  * [getSafeguardedAccountList](#getsafeguardedaccountlist)
  * [getScheduledColAdded](#getscheduledcoladded)
  * [getShowSearchFilterCallout](#getshowsearchfiltercallout)
  * [getShowStartupNotifications](#getshowstartupnotifications)
  * [getTheme](#gettheme)
  * [getUseJmp](#getusejmp)
  * [getUseNotificationSound](#getusenotificationsound)
  * [getUseStream](#getusestream)
  * [setAccountSelectorGridMode](#setaccountselectorgridmode)
  * [setBitlyAccount](#setbitlyaccount)
  * [setCheckForUpdates](#setcheckforupdates)
  * [setColumnWidth](#setcolumnwidth)
  * [setComposeStayOpen](#setcomposestayopen)
  * [setDataminrAuthToken](#setdataminrauthtoken)
  * [setDisplaySensitiveMedia](#setdisplaysensitivemedia)
  * [setFontSize](#setfontsize)
  * [setGlobalFilter](#setglobalfilter)
  * [setIdsForSeenMessages](#setidsforseenmessages)
  * [setLanguage](#setlanguage)
  * [setLinkShortener](#setlinkshortener)
  * [setNameCache](#setnamecache)
  * [setNavbarWidth](#setnavbarwidth)
  * [setPreviousSplashVersion](#setprevioussplashversion)
  * [setSafeguardedAccountList](#setsafeguardedaccountlist)
  * [setScheduledColAdded](#setscheduledcoladded)
  * [setShowSearchFilterCallout](#setshowsearchfiltercallout)
  * [setShowStartupNotifications](#setshowstartupnotifications)
  * [setTheme](#settheme)
  * [setUseJmp](#setusejmp)
  * [setUseNotificationSound](#setusenotificationsound)
  * [setUseStream](#setusestream)
* [Usage](#usage)

## Location

You can all functions related to settings in `TD.settings`.  
Another bundled version of all settings can be found by executing

```js
TD.storage.clientsController.client.get('settings')
```

## Methods

### init

**Description:**  
Initializes the `settings` object

### addSafeguardedAccount

_TODO_

### removeSafeguardedAccount

_TODO_

### getAccountSelectorGridMode

**Description:**  
Returns the selected account select grid mode

### getBitlyAccount

**Description:**  
Returns details of the set Bitly account, if one exists

### getCheckForUpdates

**Description:**  
Returns if the client checks for updates automatically

### getColumnWidth

**Description:**  
Returns the set column width

### getComposeStayOpen

**Description:**  
Returns if the compose drawer is staying open after sending a tweet

### getDataminrAuthToken

**Description:**  
Returns the set Dataminr auth token

### getDisplaySensitiveMedia

**Description:**  
Returns if the user wants to see sensitive media on their timeline

### getFontSize

**Description:**  
Returns the font size of the interface

### getGlobalFilter

**Description:**  
Returns an object containing all your filters

### getIdsForSeenMessages

**Description:**  
Returns all IDs for flash messages you have seen in this session

### getLanguage

**Description:**  
Returns the currently set language for TweetDeck

### getLinkShortener

**Description:**  
Returns the currently selected link shortener

### getNameCache

**Description:**  
Returns the cache of custom timeline names, usernames and more

### getNavbarWidth

**Description:**  
Returns the width of the navbar

### getPreviousSplashVersion

**Description:**  
Returns the version in which the last feature splash-screen was shown

### getSafeguardedAccountList

**Description:**  
Returns a list of safeguarded accounts, _it's empty_

### getScheduledColAdded

**Description:**  
Returns if a column for your scheduled posts exists

### getShowSearchFilterCallout

**Description:**
Returns if the search filter callout will be shown

### getShowStartupNotifications

**Description:**  
Returns if all new incoming notifications should be shown at start

### getTheme

**Description:**  
Returns your currently set theme

### getUseJmp

**Description:**  
Whatever this is, it is never used anywhere

### getUseNotificationSound

**Description:**
Returns if a notification sound should be used

### getUseStream

**Description:**  
Returns if specific columns should stream their content

### set

**Parameters:**  
* `key`
* `value`

**Description:**  
Sets `key` to `value`

### setAccountSelectorGridMode

**Parameter:**  
* `value`, possible values:
  * `grid`
  * `minigrid`
  * `list`
  
**Description:**  
Set the account selector grid mode to `value`

### setBitlyAccount

**Parameter:**  
* `value`, object containing:
  * `login` your Bit.ly username
  * `apiKey` your Bit.ly api key
  
**Description:**  
Set your Bit.ly account details

### setCheckForUpdates

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if TweetDeck should automatically check for updates

### setColumnWidth

**Parameter:**  
* `value`, possible values:
  * `narrow`
  * `medium`
  * `wide`
  
**Description:**  
Set the column width

### setComposeStayOpen

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if the compose drawer should stay open after sending a tweet

### setDataminrAuthToken

**Parameter:**  
* `value`

**Description:**  
Sets your Dataminr auth token to `value`

### setDisplaySensitiveMedia

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if the user wants to see sensitive media on their timeline

### setFontSite

**Parameter:**  
* `value`, possible values:
  * `smallest`
  * `small`
  * `medium`
  * `large`
  * `largest`
  
**Description:**  
Set the font size of the interface

### setGlobalFilter

**Parameter:**  
* `value`, containing all your filters

**Description:**  
Set your global filters

### setIdsForSeenMessages

**Parameter:**  
* `value`, containing all IDs

**Description:**  
Set all IDs of flash messages the user has seen

### setLanguage

**Parameter:**  
* `value`

**Description:**  
Set the language of TweetDeck

### setLinkShortener

**Parameter:**  
* `value`

**Description:**  
Set the current active link shortener

### setNameCache

**Parameter:**  
* `value`, containing your name cache

**Description:**  
Set your name cache for custom timelines, users and more

### setNavbarWidth

**Parameter:**  
* `value`, possible values:
  * `condensed`
  * `full-size`
  
**Description:**  
Set the width of the navbar

### setPreviousSplashVersion

**Parameter:**  
* `value`

**Description:**  
Set the previous splash version to `value`

### setSafeguardedAccountList

**Parameter:**  
* `value`, containing all safeguarded accounts

**Description:**  
Set the list of safeguarded accounts

### setScheduledColAdded

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if a column for scheduled posts exists

### setShowSearchFilterCallout

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if the search filter callout should be shown

### setShowStartupNotifications

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if all notifications should be shown at startup

### setTheme

**Parameter:**  
* `value`, possible values:
  * `light`
  * `dark`
  
**Description:**  
Set the current active theme

### setUseJmp

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
This is not used anywhere, no idea what it does

### setUseNotificationSound

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if a notification sound should be used

### setUseStream

**Parameter:**  
* `value`, can be either `true` or `false`

**Description:**  
Set if specific columns should stream their content

## Usage

Just a small example how you can override settings using JS

```js
// We want to set our theme to "dark" and have it instantly update to the frontend as well

// Set our theme to "dark" in the settings backend (persistent)
TD.settings.setTheme("dark")

// Update the frontend to switch to the dark theme (session based, until reload)
$(document).trigger("dataSettings",
  {
    theme: "dark"
  }
)
```
```

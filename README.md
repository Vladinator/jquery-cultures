jquery-cultures
===============

Helps create a simple way to lookup information by LCID. More information can be found [at MSDN](http://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.lcid).

Usage
---------------

Calling
```javascript
$.culture(LCID)
```
returns the following object
```javascript
{
  id:           int,       // LCID
  name:         string],   // The culture name in the format languagecode2-country/regioncode2. languagecode2 is a lowercase two-letter code derived from ISO 639-1. country/regioncode2 is derived from ISO 3166 and usually consists of two uppercase letters.
  nativeName:   string],   // The culture name. consisting of the full name of the language, the full name of the country/region, and the optional script.
  displayName:  string],   // The full localized culture name in the format languagefull [country/regionfull], where languagefull is the full name of the language and country/regionfull is the full name of the country/region.
  englishName:  string],   // The culture name in the format languagefull [country/regionfull] in English, where languagefull is the full name of the language and country/regionfull is the full name of the country/region.
  isNeutral:    boolean],  // Read more at http://msdn.microsoft.com/en-us/library/system.globalization.cultureinfo.isneutralculture
  keyboard:     string],   // Keyboard locale identifier.
  ietf:         string],   // RFC-4646 language identifier.
  iso6391:      string],   // ISO-639-1 two-letter language code.
  iso6392:      string],   // ISO-639-2 three-letter language code.
  windows:      string],   // The three-letter code for the language as defined in the Windows API.
  currency:     string]    // The currency symbol.
}
```

Examples
---------------
```javascript
// lookup several values about a culture
var info = $.culture(1033);
console.log('Name', info.name); // "en-US"
console.log('DisplayName', info.displayName); // "English (United States)"
console.log('Currency', info.currency); // "$"
```
```javascript
// when you simply care about one value
console.log($.culture(1033).displayName); // "English (United States)"
```

Skip to content

[ Digital Fortress ](https://digitalfortress.tech/)

Menu

Menu

  * [About](https://digitalfortress.tech/about/)
  * [Contact](https://digitalfortress.tech/contact/)
  * [Write for Us!](https://digitalfortress.tech/technical-writers-volunteers-needed/)

# Top 15 Commonly Used Regex

July 5, 2018May 30, 2018 / Niket Pathak / 3 min read

Tags [Regex](https://digitalfortress.tech/tag/regex/)

Regular Expressions aka Regex are expressions that define a search pattern.
They are widely used for validation purposes, like email validation, url
validation, phone number validation and so on.

**Forming Regex:**  
A regex is written between two **forward slashes** (`/`) delimiters. These
delimiters are essential only for certain Regex engines (JS,PHP..). It is then
followed by 2 flags:

  * `i` : **Ignore case** Flag, ignores the case(uppercase/lowercase) of the input string
  * `g` : **Global** Flag, searches for multiple matches instead of stopping at the first match

    
    
     /* Regex Example */
     /hello/ig 
     /* will match the word "hello" irrespective of its case and 
        will return all found matches. */
    

A quick cheat sheet for those of you who do not remember all the rules of
Regex


### Cheat Sheet – Regex Rules

Character classes |  | Quantifiers & Alternation |  
---|---|---|---  
. | any character except newline | a* a+ a? | 0 or more, 1 or more, 0 or 1  
\w \d \s | word, digit, whitespace | a{5} a{2,} | exactly five, two or more  
\W \D \S | not word, digit, whitespace | a{1,3} | between one & three  
[abc] | any of a, b, or c | a+? a{2,}?  | match as few as possible  
[^abc] | not a, b, or c | ab|cd | match ab or cd  
[a-g] | character between a & g |  |  
Anchors |  | Groups & Lookaround |  
^abc$ | start / end of the string | (abc) | capture group  
\b | word boundary | \1 | backreference to group #1  
Escaped characters |  | (?:abc) | non-capturing group  
\\. \\* \\\ | \ is used to escape special chars. \\* matches * | (?=abc) |
positive lookahead  
\t \n \r | tab, linefeed, carriage return | (?!abc) | negative lookahead  
  
### Commonly used Regex

#### 1\. Digits

  * [Whole Numbers](https://www.regexpal.com/?fam=104020) – `/^\d+$/`
  * [Decimal Numbers](https://www.regexpal.com/?fam=104021) – `/^\d*\.\d+$/`
  * [Whole + Decimal Numbers](https://www.regexpal.com/?fam=104022) – `/^\d*(\.\d+)?$/`
  * [Negative, Positive Whole + Decimal Numbers](https://www.regexpal.com/?fam=104023) – `/^-?\d*(\.\d+)?$/`
  * [Whole + Decimal + Fractions](https://www.regexpal.com/94462) – `/[-]?[0-9]+[,.]?[0-9]*([\/][0-9]+[,.]?[0-9]*)*/`

#### 2\. Alphanumeric Characters

  * [Alphanumeric without space](https://www.regexpal.com/?fam=104024) – `/^[a-zA-Z0-9]*$/`
  * [Alphanumeric with space](https://www.regexpal.com/?fam=104025) – `/^[a-zA-Z0-9 ]*$/`

#### 3\. Email

  * [Common email Ids](https://www.regexpal.com/?fam=104026) – `/^([a-zA-Z0-9._%-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,6})*$/`
  * [Uncommon email ids](https://www.regexpal.com/?fam=104027) – `/^([a-z0-9_\.\+-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$/`

#### 4\. Password Strength

  * [Complex](https://www.regexpal.com/?fam=104028): Should have 1 lowercase letter, 1 uppercase letter, 1 number, 1 special character and be at least 8 characters long 
    
        /(?=(.*[0-9]))(?=.*[\!@#$%^&*()\\[\]{}\-_+=~`|:;"'<>,./?])(?=.*[a-z])(?=(.*[A-Z]))(?=(.*)).{8,}/ 
    

  * [Moderate](https://www.regexpal.com/?fam=104029): Should have 1 lowercase letter, 1 uppercase letter, 1 number, and be at least 8 characters long 
    
        /(?=(.*[0-9]))((?=.*[A-Za-z0-9])(?=.*[A-Z])(?=.*[a-z]))^.{8,}$/
    

#### 5\. Username

  * [Alphanumeric string](https://www.regexpal.com/?fam=104030) that may include _ and – having a length of 3 to 16 characters –  
`/^[a-z0-9_-]{3,16}$/`

#### 6\. URL

  * Include [http(s) Protocol](https://www.regexpal.com/?fam=104034)
    
        /https?:\/\/(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#()?&//=]*)/ 
    

  * [Protocol Optional](https://www.regexpal.com/?fam=104035)
    
        /(https?:\/\/)?(www\.)?[-a-zA-Z0-9@:%._\+~#=]{2,256}\.[a-z]{2,6}\b([-a-zA-Z0-9@:%_\+.~#?&//=]*)/ 
    

#### 7\. IP Address

  * [IPv4 address](https://www.regexpal.com/?fam=104036)
  * [IPv6 address](https://www.regexpal.com/?fam=104037)
  * Both [IPv4, IPv6 addresses](https://www.regexpal.com/?fam=104038)

    
    
    /* Match IPv4 address */
    /^(([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])$/ 
    /* Match IPv6 address */
    /(([0-9a-fA-F]{1,4}:){7,7}[0-9a-fA-F]{1,4}|([0-9a-fA-F]{1,4}:){1,7}:|([0-9a-fA-F]{1,4}:){1,6}:[0-9a-fA-F]{1,4}|([0-9a-fA-F]{1,4}:){1,5}(:[0-9a-fA-F]{1,4}){1,2}|([0-9a-fA-F]{1,4}:){1,4}(:[0-9a-fA-F]{1,4}){1,3}|([0-9a-fA-F]{1,4}:){1,3}(:[0-9a-fA-F]{1,4}){1,4}|([0-9a-fA-F]{1,4}:){1,2}(:[0-9a-fA-F]{1,4}){1,5}|[0-9a-fA-F]{1,4}:((:[0-9a-fA-F]{1,4}){1,6})|:((:[0-9a-fA-F]{1,4}){1,7}|:)|fe80:(:[0-9a-fA-F]{0,4}){0,4}%[0-9a-zA-Z]{1,}|::(ffff(:0{1,4}){0,1}:){0,1}((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.){3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])|([0-9a-fA-F]{1,4}:){1,4}:((25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9])\.){3,3}(25[0-5]|(2[0-4]|1{0,1}[0-9]){0,1}[0-9]))/
    /* Match both IPv4, IPv6 addresses */
    /((^\s*((([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5])\.){3}([0-9]|[1-9][0-9]|1[0-9]{2}|2[0-4][0-9]|25[0-5]))\s*$)|(^\s*((([0-9A-Fa-f]{1,4}:){7}([0-9A-Fa-f]{1,4}|:))|(([0-9A-Fa-f]{1,4}:){6}(:[0-9A-Fa-f]{1,4}|((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3})|:))|(([0-9A-Fa-f]{1,4}:){5}(((:[0-9A-Fa-f]{1,4}){1,2})|:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3})|:))|(([0-9A-Fa-f]{1,4}:){4}(((:[0-9A-Fa-f]{1,4}){1,3})|((:[0-9A-Fa-f]{1,4})?:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){3}(((:[0-9A-Fa-f]{1,4}){1,4})|((:[0-9A-Fa-f]{1,4}){0,2}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){2}(((:[0-9A-Fa-f]{1,4}){1,5})|((:[0-9A-Fa-f]{1,4}){0,3}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(([0-9A-Fa-f]{1,4}:){1}(((:[0-9A-Fa-f]{1,4}){1,6})|((:[0-9A-Fa-f]{1,4}){0,4}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:))|(:(((:[0-9A-Fa-f]{1,4}){1,7})|((:[0-9A-Fa-f]{1,4}){0,5}:((25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)(\.(25[0-5]|2[0-4]\d|1\d\d|[1-9]?\d)){3}))|:)))(%.+)?\s*$))/
    

#### 8\. Dates

  * Date Format [YYYY-MM-dd](https://www.regexpal.com/?fam=104039) using separator `-`
  * Date Format [dd-MM-YYYY](https://regexr.com/?346hf) using separators `-` or `.` or `/`
  * Date Format [dd-mmm-YYYY](https://regexr.com/39tr1) using separators `-` or `.` or `/`

    
    
    /* Date Format YYYY-MM-dd */ 
    /([12]\d{3}-(0[1-9]|1[0-2])-(0[1-9]|[12]\d|3[01]))/
    
    /* Date Format dd-MM-YYYY or 
                   dd.MM.YYYY or
                   dd/MM/YYYY
       with check for leap year */ 
    /^(?:(?:31(\/|-|\.)(?:0?[13578]|1[02]))\1|(?:(?:29|30)(\/|-|\.)(?:0?[1,3-9]|1[0-2])\2))(?:(?:1[6-9]|[2-9]\d)?\d{2})$|^(?:29(\/|-|\.)0?2\3(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00))))$|^(?:0?[1-9]|1\d|2[0-8])(\/|-|\.)(?:(?:0?[1-9])|(?:1[0-2]))\4(?:(?:1[6-9]|[2-9]\d)?\d{2})$/
    
    /* Date Format dd-mmm-YYYY or
                   dd/mmm/YYYY or
                   dd.mmm.YYYY */ 
    /^(?:(?:31(\/|-|\.)(?:0?[13578]|1[02]|(?:Jan|Mar|May|Jul|Aug|Oct|Dec)))\1|(?:(?:29|30)(\/|-|\.)(?:0?[1,3-9]|1[0-2]|(?:Jan|Mar|Apr|May|Jun|Jul|Aug|Sep|Oct|Nov|Dec))\2))(?:(?:1[6-9]|[2-9]\d)?\d{2})$|^(?:29(\/|-|\.)(?:0?2|(?:Feb))\3(?:(?:(?:1[6-9]|[2-9]\d)?(?:0[48]|[2468][048]|[13579][26])|(?:(?:16|[2468][048]|[3579][26])00))))$|^(?:0?[1-9]|1\d|2[0-8])(\/|-|\.)(?:(?:0?[1-9]|(?:Jan|Feb|Mar|Apr|May|Jun|Jul|Aug|Sep))|(?:1[0-2]|(?:Oct|Nov|Dec)))\4(?:(?:1[6-9]|[2-9]\d)?\d{2})$/
    

#### 9\. Time

  * Time Format [HH:MM 12-hour](https://www.regexpal.com/?fam=104040), optional leading 0  
`/^(0?[1-9]|1[0-2]):[0-5][0-9]$/`

  * Time Format HH:MM 12-hour, optional leading 0, **[Meridiems (AM/PM)](https://www.regexpal.com/?fam=104041)**  
`/((1[0-2]|0?[1-9]):([0-5][0-9]) ?([AaPp][Mm]))/`

  * Time Format [HH:MM 24-hour](https://www.regexpal.com/?fam=104042) with leading 0  
`/^(0[0-9]|1[0-9]|2[0-3]):[0-5][0-9]$/`

  * Time Format [HH:MM 24-hour, optional leading 0](https://www.regexpal.com/?fam=104043)  
`/^([0-9]|0[0-9]|1[0-9]|2[0-3]):[0-5][0-9]$/`

  * Time Format [HH:MM:SS 24-hour](https://www.regexpal.com/?fam=104044)  
`/(?:[01]\d|2[0123]):(?:[012345]\d):(?:[012345]\d)/`

#### 10\. HTML Tags

  * [Elements with Attributes](https://www.regexpal.com/95941) `/<\/?[\w\s]*>|<.+[\W]>/`

#### 11\. Javascript Handlers

  * [Inline JS handler](https://www.regexpal.com/?fam=104055) `/\bon\w+=\S+(?=.*>)/`
  * [Inline JS handler with element](https://www.regexpal.com/94641) `/(?:<[^>]+\s)(on\S+)=["']?((?:.(?!["']?\s+(?:\S+)=|[>"']))+.)["']?/`

#### 12\. Slug

  * [Slug](https://www.regexpal.com/?fam=104056) `/^[a-z0-9]+(?:-[a-z0-9]+)*$/`

#### 13\. Match Duplicates in a String

  * [Search Duplicates](https://www.regexpal.com/?fam=104060) `/(\b\w+\b)(?=.*\b\1\b)/`

#### 14\. Phone Numbers

  * [International Phone Numbers](https://www.regexpal.com/?fam=99127) – with optional country code/extension

    
    
    /* International Phone Numbers */
    /^(?:(?:\(?(?:00|\+)([1-4]\d\d|[1-9]\d?)\)?)?[\-\.\ \\\/]?)?((?:\(?\d{1,}\)?[\-\.\ \\\/]?){0,})(?:[\-\.\ \\\/]?(?:#|ext\.?|extension|x)[\-\.\ \\\/]?(\d+))?$/
    

_Note:_ Use regex for validating phone numbers **only** if you don’t have the
choice to use a library. There are [several
libraries](https://stackoverflow.com/a/15644461/4717533) that handle phone
numbers more accurately and should be used instead.

#### 15\. File Path

  * [File Path with Filename and extension](https://www.regexpal.com/?fam=104047)
    
        /((\/|\\|\/\/|https?:\\\\|https?:\/\/)[a-z0-9 _@\-^!#$%&+={}.\/\\\[\]]+)+\.[a-z]+$/
    

  * File Path with optional Filename, extension
    
        /^(.+)/([^/]+)$/
    

  * [File Name with extension](https://www.regexpal.com/?fam=104048) having 3 chars
    
        /^[\w,\s-]+\.[A-Za-z]{3}$/
    

### Additional Regexes

#### 1\. Zip codes

There is **NO** single Regex that can handle all zip codes given that zip
codes around the world do not follow a common pattern. Here is a
[list](https://stackoverflow.com/a/7185241/4717533) that contains Regex
specific to each country.

#### 2\. Payment Validation

Here is a [link](https://www.regular-expressions.info/creditcard.html) that
contains regex for validating leading Credit cards like Visa, Mastercard and
so on.

#### 3\. Identity Documents

  * Social Security Number – [Ref](https://www.codeproject.com/Articles/651609/Validating-Social-Security-Numbers-through-Regular)
    
        /* can use either hypen(-) or space( ) character as separator */
    /^((?!219-09-9999|078-05-1120)(?!666|000|9\d{2})\d{3}-(?!00)\d{2}-(?!0{4})\d{4})|((?!219 09 9999|078 05 1120)(?!666|000|9\d{2})\d{3} (?!00)\d{2} (?!0{4})\d{4})|((?!219099999|078051120)(?!666|000|9\d{2})\d{3}(?!00)\d{2}(?!0{4})\d{4})$/
    

  * Passport – `/^[A-PR-WY][1-9]\d\s?\d{4}[1-9]$/`

* * *

#### References

  * [https://www.codeproject.com/validate-passport-number](https://www.codeproject.com/Questions/1046445/How-to-validate-passport-number-using-javascript)
  * [https://gist.github.com/](https://gist.github.com/nerdsrescueme/1237767)
  * [https://code.tutsplus.com/regular-expressions](https://code.tutsplus.com/tutorials/8-regular-expressions-you-should-know--net-6149)
  * <https://www.regular-expressions.info>
  * <http://www.regexlib.com/>
  * <https://projects.lukehaas.me/regexhub/>
  * <http://wiki.zoolz.com/commonly-used-regular-expressions/>
  * [https://www.smashingmagazine.com/advanced-regular-expressions/](https://www.smashingmagazine.com/2009/05/introduction-to-advanced-regular-expressions/)

**P.s.** Need a **graphical explanation** of any of the above Regex ? Try
[Regular Expression Visualization](https://www.debuggex.com/) and copy-paste
any Regex in the input box to get a graphical representation of it. Hope that
helps!

### Share this:

  * [Click to share on Facebook (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=facebook "Click to share on Facebook")
  * [Click to share on Twitter (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=twitter "Click to share on Twitter")
  * [Click to share on WhatsApp (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=jetpack-whatsapp "Click to share on WhatsApp")
  * [Click to share on LinkedIn (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=linkedin "Click to share on LinkedIn")
  * [Click to email a link to a friend (Opens in new window)](mailto:?subject=%5BShared%20Post%5D%20Top%2015%20Commonly%20Used%20Regex&body=https%3A%2F%2Fdigitalfortress.tech%2Ftips%2Ftop-15-commonly-used-regex%2F&share=email "Click to email a link to a friend")
  * More
  * 

  * [Click to share on Tumblr (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=tumblr "Click to share on Tumblr")
  * [Click to share on Pocket (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=pocket "Click to share on Pocket")
  *   * [Click to share on Telegram (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=telegram "Click to share on Telegram")
  * [Click to share on Pinterest (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=pinterest "Click to share on Pinterest")
  *   * [Click to share on Reddit (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=reddit "Click to share on Reddit")
  * [Click to share on Skype (Opens in new window)](https://digitalfortress.tech/tips/top-15-commonly-used-regex/?share=skype "Click to share on Skype")
  *   * 

### _Related Articles_

Categories [Javascript](https://digitalfortress.tech/category/js/), [Tips &
Tricks](https://digitalfortress.tech/category/tips/) Post navigation

[Smart search using Twitter Typeahead and
Bloodhound](https://digitalfortress.tech/tutorial/smart-search-using-twitter-
typeahead-bloodhound/)

[Create Global gitconfig and Setup git
alias](https://digitalfortress.tech/tutorial/create-global-gitconfig-git-
alias/)

Search for:

  * [Compress images with Javascript](https://digitalfortress.tech/js/compress-images-with-javascript/)
  * [Whats a double Arrow function in javascript ?](https://digitalfortress.tech/js/whats-a-double-arrow-function-in-javascript/)
  * [Rotate Ads in Javascript with Ad-rotator](https://digitalfortress.tech/tutorial/rotate-ads-in-javascript-with-ad-rotator/)
  * [File Upload with API Platform and Symfony](https://digitalfortress.tech/php/file-upload-with-api-platform-and-symfony/)
  * [How to Encrypt LocalStorage data?](https://digitalfortress.tech/js/encrypt-localstorage-data/)

## Tags

[Android](https://digitalfortress.tech/tag/android/)
[apache2](https://digitalfortress.tech/tag/apache2/)
[API](https://digitalfortress.tech/tag/api/)
[automation](https://digitalfortress.tech/tag/automation/)
[Babel](https://digitalfortress.tech/tag/babel/)
[BASH](https://digitalfortress.tech/tag/bash/)
[bloodhound](https://digitalfortress.tech/tag/bloodhound/)
[Doctrine](https://digitalfortress.tech/tag/doctrine/)
[Dropzone](https://digitalfortress.tech/tag/dropzone/)
[ES2015](https://digitalfortress.tech/tag/es2015/)
[ES2016](https://digitalfortress.tech/tag/es2016/)
[ES2017](https://digitalfortress.tech/tag/es2017/)
[ES2018](https://digitalfortress.tech/tag/es2018/)
[ffmpeg](https://digitalfortress.tech/tag/ffmpeg/) [File
System](https://digitalfortress.tech/tag/file-system/)
[GIT](https://digitalfortress.tech/tag/git/)
[htaccess](https://digitalfortress.tech/tag/htaccess/)
[IDE](https://digitalfortress.tech/tag/ide/)
[Jquery](https://digitalfortress.tech/tag/jquery/)
[JWT](https://digitalfortress.tech/tag/jwt/)
[Linux](https://digitalfortress.tech/tag/linux/)
[MacOS](https://digitalfortress.tech/tag/macos/)
[MySQL](https://digitalfortress.tech/tag/mysql/)
[PhpStorm](https://digitalfortress.tech/tag/phpstorm/)
[Regex](https://digitalfortress.tech/tag/regex/)
[REST](https://digitalfortress.tech/tag/rest/)
[SEO](https://digitalfortress.tech/tag/seo/)
[Symfony](https://digitalfortress.tech/tag/symfony/)
[Symfony3](https://digitalfortress.tech/tag/symfony3/)
[Symfony4](https://digitalfortress.tech/tag/symfony4/)
[Symfony5](https://digitalfortress.tech/tag/symfony5/)
[Twig](https://digitalfortress.tech/tag/twig/)
[typeahead](https://digitalfortress.tech/tag/typeahead/)
[Ubuntu](https://digitalfortress.tech/tag/ubuntu/)
[UI](https://digitalfortress.tech/tag/ui/) [Vanilla
JS](https://digitalfortress.tech/tag/vanillajs/) [VS
Code](https://digitalfortress.tech/tag/vs-code/)
[Vue](https://digitalfortress.tech/tag/vue/)
[Vue.js](https://digitalfortress.tech/tag/vue-js/)
[VueJS](https://digitalfortress.tech/tag/vuejs/) [Vue
Router](https://digitalfortress.tech/tag/vue-router/)
[Vuex](https://digitalfortress.tech/tag/vuex/)
[Webpack](https://digitalfortress.tech/tag/webpack/) [Webpack
Encore](https://digitalfortress.tech/tag/webpack-encore/)
[WebStorm](https://digitalfortress.tech/tag/webstorm/)

Privacy & Cookies: This site uses cookies. By continuing to use this website,
you agree to their use.  
To find out more, including how to control cookies, see here: [ Cookie Policy
](https://automattic.com/cookies/)

#### Pages

  * [About](https://digitalfortress.tech/about/)
  * [Contact](https://digitalfortress.tech/contact/)
  * [Technical Writers / Volunteers Needed](https://digitalfortress.tech/technical-writers-volunteers-needed/)

#### Recent Posts

  * [Compress images with Javascript](https://digitalfortress.tech/js/compress-images-with-javascript/)
  * [Whats a double Arrow function in javascript ?](https://digitalfortress.tech/js/whats-a-double-arrow-function-in-javascript/)
  * [Rotate Ads in Javascript with Ad-rotator](https://digitalfortress.tech/tutorial/rotate-ads-in-javascript-with-ad-rotator/)
  * [File Upload with API Platform and Symfony](https://digitalfortress.tech/php/file-upload-with-api-platform-and-symfony/)
  * [How to Encrypt LocalStorage data?](https://digitalfortress.tech/js/encrypt-localstorage-data/)

#### Categories

  * [Bugfix](https://digitalfortress.tech/category/bugfix/)
  * [CSS](https://digitalfortress.tech/category/css/)
  * [Debug](https://digitalfortress.tech/category/debug/)
  * [Javascript](https://digitalfortress.tech/category/js/)
  * [Miscellaneous](https://digitalfortress.tech/category/misc/)
  * [PHP](https://digitalfortress.tech/category/php/)
  * [SQL](https://digitalfortress.tech/category/sql/)
  * [Tips & Tricks](https://digitalfortress.tech/category/tips/)
  * [Tutorial](https://digitalfortress.tech/category/tutorial/)

## Meta

  * [Log in](https://digitalfortress.tech/wp-login.php)
  * [Entries feed](https://digitalfortress.tech/feed/)
  * [Comments feed](https://digitalfortress.tech/comments/feed/)
  * [WordPress.org](https://wordpress.org/)

© 2022 Digital Fortress


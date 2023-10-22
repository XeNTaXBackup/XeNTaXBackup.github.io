## Post #1
- Username: piotruspan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 19, 2015 7:57 am
- Post datetime: 2015-09-22T14:19:06+00:00
- Post Title: Any tool to extract stringtables from Warframe?

I extracted "Languages.bin" and "Packages.bin" from "H.Misc.cache" using [Evolution Engine Cache Extractor](http://forum.xentax.com/viewtopic.php?f=32&t=10782), but don't know how to extract any strings from it. I found this: [https://github.com/Deathmax/WFPackageParser](https://github.com/Deathmax/WFPackageParser) but can't get it to work. "Languages.bin" for other languages are in "H.Misc_<lang code>.cache"
## Post #2
- Username: piotruspan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Sep 19, 2015 7:57 am
- Post datetime: 2015-09-24T11:05:24+00:00
- Post Title: Any tool to extract stringtables from Warframe?

I wrote [Python script](http://pastebin.com/92Vwfcth) that takes path to 'Languages.bin' and prints grouped data. I still can't read anything, but I hope it will help.

Here is what I get from /Lotus/Language/Factions/ group and what it should be:
[English](http://pastebin.com/ehUYDxJb), [Polish](http://pastebin.com/A4wJT8ih)
This is one of the smallest groups, so it may be good to begin with.
## Post #3
- Username: hadesy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 24, 2015 2:25 am
- Post datetime: 2015-11-19T21:32:46+00:00
- Post Title: Any tool to extract stringtables from Warframe?

> Reply from piotruspan
>
> I wrote Python script that takes path to 'Languages.bin' and prints grouped data. I still can't read anything, but I hope it will help.

Here is what I get from /Lotus/Language/Factions/ group and what it should be:
English, Polish
This is one of the smallest groups, so it may be good to begin with.
Hi, Are you making any progress?I have the same question.
## Post #4
- Username: Deathmax
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 22, 2013 11:42 am
- Post datetime: 2015-11-29T22:39:21+00:00
- Post Title: Any tool to extract stringtables from Warframe?

I've updated my code to not crash and burn when it encounters encrypted blocks.

I've also added below the format used before they started encrypting Languages.bin. The last time I used this, only the English Languages.bin was encrypted, the other languages should be plaintext.

```
 * -------------------
 * START OF FILE
 * ------+-------------------------------
 * 31    | Unknown
 * Int32 | Number of language suffixes
 * ------+-------------------------------
 * Int32 | Length of string to read
 * Size  | Language suffix
 * ------+-------------------------------
 * Int32 | Unknown
 * 
 * REPEAT BLOCK UNTIL END
 * ------+------------------------------
 * Int32 | Size of header string
 * Size  | Header string
 * Int32 | Unknown
 * Int32 | Number of null-delimited strings
 * Int32 | Total length of null-delimited strings (including last /0)
 * Size  | Strings, delimited with /0
 * ------+------------------------------
 * Int32 | Size of string title
 * Size  | String title
 * 11    | Unknown
 * ------+------------------------------
 */

```
## Post #5
- Username: uraabk
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 20, 2015 5:44 pm
- Post datetime: 2015-12-15T08:23:17+00:00
- Post Title: Any tool to extract stringtables from Warframe?

Hello.
I received [PackagesLexer.dll](https://yadi.sk/d/2-aiwOuTmEZGq) from [https://github.com/Deathmax/WFPackageParser](https://github.com/Deathmax/WFPackageParser), but how to work with it?

## Post #1
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-01T19:52:51+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

Please, help me with unpacking and repacking these .ztd and .zti archives.
Please.

```
http://www.multiupload.com/QG8B9L0KEU
```
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-11T00:00:17+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

your ZTD and ZTI files are the same except ZTI is big endian, ZTD is little. this does mean whoever writes this up can have it spit out 2 files, and either file can be used to edit!

the strings are grouped, and easy to parse. someone like bacter could write something up with this - and writing a BMS is sorta pointless as you want to repack etc etc

```
byte NULL[ 12 ]
short GROUPS
short UNKNOWN (only 1 in samples, but could be number of 'groups' in the file)
byte NULL[ 4 ]

-- 12 byte group headers

for i = 0 < GROUPS
{
  int STRINGS
  int HASH (similar base number between samples, probally using size&|groups, but unknown)
  int POS

  -- to get to POS
  goto 20 + POS + (i * 12)

  for j = 0 < STRINGS
  {
    long STRPOS (same calc to get to POS as with STRPOS, but can be ignored)
  }

  for j = 0 < STRINGS
  {
    unicode STR (null-terminated)
  }

}


```
## Post #3
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-11T15:42:46+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

Thanks, can someone create pack/unpack aplication ?
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-12T18:52:46+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

i downloaded the wrc2010 demo from the official site, but there aren't zti/ztd files in the client? what am i missing here!
## Post #5
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-12T19:29:11+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

> Reply from WRS
>
> i downloaded the wrc2010 demo from the official site, but there aren't zti/ztd files in the client? what am i missing here!
I have those files in archive menu.mix
## Post #6
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-12T19:51:17+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

so extracting menu.mix and comparing USENGLISH with the other languages shows me that the unknown 'checksum' value i gave the second header value is just a resource id! - it doesn't change with string length or with different characters. bah.
## Post #7
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-12T20:09:07+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

I can change characters in zti and ztd files but i don´t know how to add any characters.
I uploaded some .zti and .ztd files in different languages and pack/unpack tools for .mix archives and guide for this tool

```
http://www.multiupload.com/C6V41NJH9Y
```
## Post #8
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-03-13T19:03:56+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

the characters are unicode but you're waiting for something which can adjust the string position headers
## Post #9
- Username: Jurko
- Rank: veteran
- Number of posts: 86
- Joined date: Fri Jan 22, 2010 9:35 pm
- Post datetime: 2011-03-13T19:58:11+00:00
- Post Title: WRC FIA World Rally Championship .ztd and .zti text archives

Yes

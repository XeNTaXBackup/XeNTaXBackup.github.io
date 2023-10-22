## Post #1
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T13:55:34+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

Hello friends,

I was watching the game MONOPOLY Streets, he works with the. BIG, I managed to extract these file with the BMS script below.

```
IDString 0 BIGF ;
Get D Long 0 ;
Get FC Long 0 ;
ReverseLong FC ;
Get D Long 0 ;
SavePos FS 0 ;
For T = 1 To FC ;
GoTo FS 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
ReverseLong FO ;
SavePos FSO 0 ;
Get FSI Long 0 ;
ReverseLong FSI ;
Get FN String 0 ;
SavePos FS 0 ;
Log FN FO FSI FOO FSO ;
Next T ;
```


Inside it will be several. Rpk, rpk have attached 2 files containing the texts I believe.

does anyone manages to extract the texts?
[monopoly streets.rar](https://xentaxbackup.github.io/file/5991_monopoly streets.rar)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-11-14T15:23:59+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

Well i found game only for Xbox and here script for unpack. I think for PS3 it's work too. RPK files seems compressed.

```
# 
# Written by Ekey (h4x0r)
# http://www.progamercity.net
# 
# script for QuickBMS http://quickbms.aluigi.org

idstring "BIGF"
get PAKSIZE long
endian big
get FILES long

get SIZE long
get OFFSET long
get DUMMY long
get NAME string
log NAME OFFSET SIZE

for i = 1 < FILES
    get OFFSET long
    get SIZE long
    get NAME string
    log NAME OFFSET SIZE
next i
```
## Post #3
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-14T16:16:25+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

Thanks for the script.

well if anyone knows anything about the prk.
## Post #4
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-04-18T14:01:43+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

Friends, anyone can extract the text of this file?
[en-gb.rar](https://xentaxbackup.github.io/file/6336_en-gb.rar)
## Post #5
- Username: wesllem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 30, 2010 8:13 am
- Post datetime: 2013-11-18T00:31:56+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

> Reply from timartinelli
>
> Friends, anyone can extract the text of this file?

I am also in the same doubt. Get anything friend?
## Post #6
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2013-11-18T12:17:46+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

> Reply from wesllem
>
> timartinelli wrote:Friends, anyone can extract the text of this file?

I am also in the same doubt. Get anything friend?

no friend, but to no avail unfortunately.
## Post #7
- Username: wesllem
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 30, 2010 8:13 am
- Post datetime: 2013-11-19T19:19:09+00:00
- Post Title: [PS3] MONOPOLY Streets - .BIG - .RPK

> Reply from timartinelli
>
> wesllem wrote:timartinelli wrote:Friends, anyone can extract the text of this file?

I am also in the same doubt. Get anything friend?

no friend, but to no avail unfortunately.

really wanted to translate this game, but without a tool that can open this file, it is difficult

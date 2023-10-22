## Post #1
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2013-11-03T00:10:40+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

Hi! I need help to open .pkg files of new xbox360 game Blood Knights. Inside must be english.bin and maybe font.bin. I hope on your advice   . 
[http://rghost.ru/49897724](http://rghost.ru/49897724)

Info: [http://en.wikipedia.org/wiki/Deck13_Interactive](http://en.wikipedia.org/wiki/Deck13_Interactive)
[http://www.ign.com/games/blood-knights/xbox-360-136948](http://www.ign.com/games/blood-knights/xbox-360-136948)
## Post #2
- Username: TimonS
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-11-03T01:10:42+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

its xmem compressed.
decompress it with xbdecompress from xbox sdk.
## Post #3
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2013-11-03T10:07:12+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

Thanks!!! I am ultra-n00b
## Post #4
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2013-11-03T11:45:31+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

I decompressed my file with xbdecompress from xbox sdk. But now can't find any script to open decompressed .pkg    

Pls help!

[http://rghost.ru/49904594](http://rghost.ru/49904594)
## Post #5
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2013-11-03T13:17:27+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

This quickbms script can unpack the files

```
goto 12
get files long
xmath base "16 + files * 16"
for i = 0 < files
get null long
get offset long
math offset += base
get size long
get hash? long
log "" offset size
next i
```


But all files has some kind of hash at 0x4 position, and you cant edit them if you dont know how to change that value.
## Post #6
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2013-11-03T13:30:44+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

Thanks, man!
## Post #7
- Username: TimonS
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Nov 03, 2013 5:49 am
- Post datetime: 2013-11-03T15:21:44+00:00
- Post Title: Blood Knights - Xbox360 (2013) [.pkg]

Sorry guys! It's me again) 

I found english.bin & font.bin, try to convert and extract, got some results. But may be somebody have practice with it ? 
Because need start to translate)))

[http://rghost.ru/49909566](http://rghost.ru/49909566)

Sorry for my english

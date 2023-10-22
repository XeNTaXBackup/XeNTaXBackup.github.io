## Post #1
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-05-27T19:24:39+00:00
- Post Title: could I add multiple ID flags to my bms script?

Im wondering if I am able to add multiple ID flags to my script
example 
```
if FLAG = 0x##78
```


I have a bunch of bms scripts that are similar but only have an offset of the second hex code and I want to merge them all into one.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-28T10:12:06+00:00
- Post Title: could I add multiple ID flags to my bms script?

in that case you could use something like:

```
math TMP &= 0xff # or math TMP %= 0x100
if TMP == 0x78
...
```
## Post #3
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-05-28T14:26:32+00:00
- Post Title: could I add multiple ID flags to my bms script?

This works like a charm thanks.

IDK if its because you didn't get to see the whole code but 
```
TMP == 0x78
```
 was making the script not work. Instead of using it I put 

```
math TMP &= 0xDA78 # or math TMP %= 0x9C78 or math TMP %= 0x5E78
```
 and it works on all those zlib files even at the same time. =]
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-28T15:17:32+00:00
- Post Title: could I add multiple ID flags to my bms script?

you must never use a similar check for zlib data.
in that case if you don't know if a file is compressed is better to use "comtype unzip_dynamic" that will do the check correctly and unpack or copy the data automatically
## Post #5
- Username: Troopermanaic
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Jul 01, 2011 11:29 pm
- Post datetime: 2012-05-29T05:52:41+00:00
- Post Title: could I add multiple ID flags to my bms script?

the script with this line of code seems to be working 100% fine with absolutely no errors, even can re import with bms. Is there something I should be aware of?

I checked the coding of the decompressed files and they look right. Everything seems to be working this way.
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2012-05-29T08:24:33+00:00
- Post Title: could I add multiple ID flags to my bms script?

I forgot about reimporting (unzip_dynamic would zip everything, even the uncompressed files).

anyway the file format must have for sure a field in which it says if the file is compressed and what's its size, that will avoid the 0x78 work-around
## Post #7
- Username: Atwaetere
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 30, 2012 2:23 am
- Post datetime: 2012-06-04T20:06:11+00:00
- Post Title: could I add multiple ID flags to my bms script?

I have the same issue but it wasnt solved with all the hints. Becuase the problem is that i am a bit of a newbie and do not have any experience of what you guys are talking about. it would be very helpful, if someone could post the entire code. It would be a huge learning curve for me and it would be thankful.

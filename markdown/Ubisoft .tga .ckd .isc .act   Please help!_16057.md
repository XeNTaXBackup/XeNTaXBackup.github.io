## Post #1
- Username: ThEReZoX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 28, 2016 4:41 am
- Post datetime: 2017-03-26T12:08:05+00:00
- Post Title: Ubisoft *.tga *.ckd *.isc *.act   *Please help!*

*DELETED*
## Post #2
- Username: Acewell
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-26T13:58:33+00:00
- Post Title: Ubisoft *.tga *.ckd *.isc *.act   *Please help!*

Both of the attached files are DDS images.  Remove the first 44 bytes, save as .DDS, open in your favorite image viewer.
## Post #3
- Username: ThEReZoX
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Oct 28, 2016 4:41 am
- Post datetime: 2017-03-26T14:06:09+00:00
- Post Title: Ubisoft *.tga *.ckd *.isc *.act   *Please help!*

> Reply from MichaelDarkAngel
>
> Both of the attached files are DDS images.  Remove the first 44 bytes, save as .DDS, open in your favorite image viewer.

How Do I remove the first 44 bytes?
## Post #4
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2017-03-26T14:49:11+00:00
- Post Title: Ubisoft *.tga *.ckd *.isc *.act   *Please help!*

Open the file in a hex editor.  There are plenty of free ones available.



The area I have highlighted is the 44 bytes that need to be deleted.

Save the file with a "DDS" extension.  They should now open in an image viewer that can handle DDS images.
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-03-26T16:31:30+00:00
- Post Title: Ubisoft *.tga *.ckd *.isc *.act   *Please help!*

here is a bms script to automate that task  

```
get SIZE asize
math OFFSET = 0x2c
math SIZE - OFFSET
get NAME basename
string NAME + ".dds"
log NAME OFFSET SIZE
```

## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-01-01T17:21:00+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

The textures in this game all use .rtf, but of course looking up the format just gets me Rich Text Documents. Can someone help me convert them? Thanks.
[https://dl.dropboxusercontent.com/u/107 ... rdrobe.zip](https://dl.dropboxusercontent.com/u/107081038/sbtos_wardrobe.zip)
## Post #2
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-01-07T20:39:02+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

no one?
## Post #3
- Username: Chipicao
- Rank: ultra-veteran
- Number of posts: 476
- Joined date: Thu Feb 03, 2011 6:18 pm
- Post datetime: 2014-01-10T06:58:05+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

You're not gonna get any help if you post a bunch of pkg files.
WTF do you expect us to do, google our asses off until we find a working extractor?

I tried Multi PKG tool and PSNPKGDecryptor&Extractor but neither one worked.
## Post #4
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-01-12T19:57:03+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

oh whoops, that's the wrong thing, sorry.
[https://dl.dropboxusercontent.com/u/107 ... rdrobe.zip](https://dl.dropboxusercontent.com/u/107081038/sbtos_wardrobe.zip)
here it is
## Post #5
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-01-20T15:35:43+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

no one again? I gave the right files.
## Post #6
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-20T16:43:31+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

By looking at the samples in a hex editor it seems there's an 80 byte header followed by a 32-bit palette. I can't make heads or tails of the textures though, perhaps they are swizzled? (It is likely the case since it's a PSP game).
## Post #7
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-20T17:43:18+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

Alright, I figured it out!



Here's a Noesis script I wrote for the game:
[http://www21.zippyshare.com/v/7097821/file.html](http://www21.zippyshare.com/v/7097821/file.html)

Some of Mr. Krabs' textures are blank for some reason.
## Post #8
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2014-01-23T03:03:00+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

It works! ... mostly. There's a bunch of textures that are just scrambled, but that's probably because I didn't give enough samples. Here's a folder with a lot that don't exactly work right.
[https://dl.dropboxusercontent.com/u/107 ... st_tr3.zip](https://dl.dropboxusercontent.com/u/107081038/sbtos_test_tr3.zip)
## Post #9
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-01-23T17:50:18+00:00
- Post Title: SpongeBob's Truth or Square .rtf (PSP)

I've updated the script, loads all samples now. Unfortunately some textures look a bit blurry and I can't pinpoint the problem.
Here's the new link: [http://www47.zippyshare.com/v/86780469/file.html](http://www47.zippyshare.com/v/86780469/file.html)

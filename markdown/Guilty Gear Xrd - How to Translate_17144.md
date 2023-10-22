## Post #1
- Username: Ignatyus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 16, 2017 8:47 am
- Post datetime: 2017-10-16T01:23:09+00:00
- Post Title: Guilty Gear Xrd - How to Translate?

Yes I'm newbie in this forum. I signed up here recently because I'm almost going MAD trying to translate two Guilty Gear games to my language: Xrd SIGN and Xrd REV 2 for PC. GG Xrd games are made using Unreal Engine 3.

I was able to unpack and extract the upk files needed for translation using UPK Decompressor and UPK Extractor. I edited some text files of the game using UE Explorer and Hex Editor. The problem is, when I use decompressor the upk file it can be used by Hex Editor for editing, but it is not possible to compress an upk file again and the game does not recognize the decompressed and edited file.

So I've figured out that you're able to make the XCOM game recognize changes to the UPK files by directly modifying the XCOM.exe so that it recognizes the new files. But I did not see any such program for other games (like Guilty Gear Xrd).

I spent a few days researching and trying to perform some basic steps to try to translate the game and as far as I can tell it seems impossible. What made me not get discouraged is that I saw a project of localization to RU and they seem to have achieved what I'm not getting.

[https://i.imgur.com/aNUHc1l.jpg](https://i.imgur.com/aNUHc1l.jpg)
[https://i.imgur.com/QgnKPtd.jpg](https://i.imgur.com/QgnKPtd.jpg)

Exactly. They were able to put modified files to be recognized in the game. The question I have is how?

I really need to translate this game. It's a matter of honor now. Can someone help me?
## Post #2
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2017-10-16T20:56:23+00:00
- Post Title: Guilty Gear Xrd - How to Translate?

Upload some UPK files for analysis.
## Post #3
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-10-16T23:59:43+00:00
- Post Title: Guilty Gear Xrd - How to Translate?

Edit file REDGame\PCConsoleTOC.txt
Example:
## Post #4
- Username: Ignatyus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 16, 2017 8:47 am
- Post datetime: 2017-10-17T02:00:44+00:00
- Post Title: Guilty Gear Xrd - How to Translate?

It worked! Thank you very much for your help. Really.

What about the Fonts of the game? Is there any way I can edit by myself to add more characters?

Startup_LOC_INT.upk [http://www.mediafire.com/file/evobnffc6 ... OC_INT.upk](http://www.mediafire.com/file/evobnffc6fsy31a/Startup_LOC_INT.upk)
HaikuFont_SF_LOC_INT.upk [http://www.mediafire.com/file/fy75r7t3c ... OC_INT.upk](http://www.mediafire.com/file/fy75r7t3cb6ifcv/HaikuFont_SF_LOC_INT.upk)
StoryFont_SF_LOC_INT.upk [http://www.mediafire.com/file/kwowwr585 ... OC_INT.upk](http://www.mediafire.com/file/kwowwr585qbvked/StoryFont_SF_LOC_INT.upk)
## Post #5
- Username: makcar
- Rank: veteran
- Number of posts: 154
- Joined date: Tue May 13, 2014 5:41 am
- Post datetime: 2017-10-17T11:17:30+00:00
- Post Title: Guilty Gear Xrd - How to Translate?

I used:
Startup_LOC_INT.upk\StaticFont\REDFont\


StoryFont_SF_LOC_INT.upk\storyfont\

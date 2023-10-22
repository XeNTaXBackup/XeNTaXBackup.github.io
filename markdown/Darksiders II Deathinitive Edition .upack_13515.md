## Post #1
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2015-11-09T01:46:14+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

Hi I was wondering if anyone intended to take a whack at the new .upacks for Darksiders II Deathinitive Edition. Looks like the textures are improved.

I tried to use DS2Extract from the following thread:

[viewtopic.php?f=16&t=9483&p=79039&hilit ... act#p79039](http://forum.xentax.com/viewtopic.php?f=16&t=9483&p=79039&hilit=DS2Extract#p79039)

I found that if I renamed manifest.bin to pc.mnfst (which DS2Extract looks for), then the extraction process starts and around 30 files are extracted, with readable .dds files, so the archive structure must not be drastically different from Darksiders II.

Ping me if anything is needed,

thanks
## Post #2
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-11-14T14:16:51+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

hop someone update this extractor, I think there model files are same, just repaint tetures.
## Post #3
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2015-11-16T02:40:57+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

I got a response back from Sir Kane:

"The only thing that changed is the offset values in the manifest. They changed that into 64 bit values to support upak sizes over 4 GB."

Sadly, this is too far above my skill level in programming (Shaved Ape level) to resolve. To any who are interested, the source code can still be found here:

[http://sktest.aruarose.com/DS2Extract.rar](http://sktest.aruarose.com/DS2Extract.rar)
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2015-11-16T11:38:55+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

I fixed it but not tested
[DS2DEExtract.zip](https://xentaxbackup.github.io/file/10024_DS2DEExtract.zip)
## Post #5
- Username: zardalu
- Rank: veteran
- Number of posts: 134
- Joined date: Sat Sep 13, 2008 10:13 pm
- Post datetime: 2015-11-18T02:07:07+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

> Reply from Ekey
>
> I fixed it but not tested

Awesome, I tested it, it's extracting the first 5 GB without issues, then stops, saying it's 100% complete. I am sure about half is missing. Still, the first half is great, lots of improved textures... thanks Ekey!
## Post #6
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2015-12-03T03:57:18+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

this is so awsome!!!!
## Post #7
- Username: dibe91
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Tue Jul 29, 2014 4:06 pm
- Post datetime: 2015-12-09T06:54:34+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

I take advantage of this discussion to talk about the models and the skin. if you try to import the models of golem on 3dstudio max no 'is the skeleton and are dismembered using this script: [viewtopic.php?f=16&t=11574](http://forum.xentax.com/viewtopic.php?f=16&t=11574)
## Post #8
- Username: agaron20
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Dec 13, 2015 10:41 pm
- Post datetime: 2015-12-17T09:26:33+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

Hi guys!

I tire this tool and it's good. I and my friend want to translate the game to another language. We find the .loc files with the dialogues, etc... but maybe have you got idea how can we edit it? 

Thanks for your help!
## Post #9
- Username: Keeperv85
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Aug 06, 2010 8:41 am
- Post datetime: 2016-11-21T07:52:50+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

Hi guys!

After a long time I found this topic, i worry quite late... or may not.

I have an idea, how can i translate this game, but after a long time still don't know what is the right steps...

First:

I found BMS script > unpack/repack media.upack 

Second: 

obp > offzip > bod > 

bod > packzip > obp

Okay. but I have no idea for this:

bod > loc, or loc to bod....

...but i saw the DS2Extractor.... It did not help for this.

The "loc" files very interesting....

- 4 byte file signature, 4c 4f 43 02, it's called "loc ".
- 4 byte: count of language 0x000b > 11
- 11 x 8 byte line. The first 4 byte: language ID, second: length language file for details. Example English  0x000005f5 > 1525.


Content of all language:

- 56 byte, 7x8 byte data structure. I have no idea what is this...
- x 40 byte metadata. some fix numbers, string id, string lenght (?), string counter, simple incremental.
- x 16 byte, strings length again (?).
- strings, zero closed, x pieces, of course 

Okay, its not to hard... but... the line of 639...

x 40 > zero? Zero length? What is this? Why?

I found this: [http://turkceoyunmerkezi.com/darksiders ... -yama.html](http://turkceoyunmerkezi.com/darksiders-2-100-turkce-yama.html)

Woho.. these guys have a working tool! But... unfortunately, they did not reply to me...
## Post #10
- Username: amzerof6
- Rank: advanced
- Number of posts: 57
- Joined date: Sat Oct 23, 2010 10:50 pm
- Post datetime: 2018-01-11T08:57:39+00:00
- Post Title: Darksiders II Deathinitive Edition .upack

> Reply from Ekey
>
> I fixed it but not tested

first, so thank U made this awsome tool, very!

I try this tool to export game files. and I think so many files losted, just like this
[img.png](https://xentaxbackup.github.io/file/13779_img.png)

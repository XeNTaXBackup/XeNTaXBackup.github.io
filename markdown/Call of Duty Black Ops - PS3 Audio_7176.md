## Post #1
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-13T20:27:35+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

Have a jail broken PS3 and love playing against the bots in Black Ops but there's just one thing that bothers me...the sounds. Treyarch did some very poor work on weapon sounds, they all sound too much alike and I don't think they actually sound like their real life counterparts.

Strolling through the game files, the only files I see that look like they could contain the sound files are packed in .pak files and I cannot for the life of me figure out how to extract them. People have said winzip, winrar, pakscape...the list goes on. Nothing I have tried so far has worked. But I run into another problem even if there was a way to extract them, how do I repack them? If anybody can help, please do.

Any help would be greatly appreciated.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-13T22:03:32+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

Can you post a sample?
## Post #3
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-13T23:46:58+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

I'm getting the message...

"The extension pak is not allowed."

So here is the files uploaded elsewhere.

Smaller File
[http://www.mediafire.com/?d9s3ocmzlc6zdb4](http://www.mediafire.com/?d9s3ocmzlc6zdb4)

Bigger File
[http://www.megaupload.com/?d=77RJL21S](http://www.megaupload.com/?d=77RJL21S)
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-14T01:41:10+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

This is not a Usual PAK file that winrar handles, has a custom filetable and the data is mp3.
## Post #5
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-14T02:26:48+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

> Reply from OrangeC
>
> This is not a Usual PAK file that winrar handles, has a custom filetable and the data is mp3.

How did you extract it?
## Post #6
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-14T18:07:42+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

I am very sorry for being impatient, but could anybody help with this?

Sorry again.
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-08-14T22:30:57+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

Since there are no filenames use an mp3 scanner like nova extractor.
## Post #8
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-14T22:37:51+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

Oh I see. Very nice, I'm going to try to replace the files and see if I can rebuild with the changes. Wish me luck.
## Post #9
- Username: vadim
- Rank: advanced
- Number of posts: 41
- Joined date: Fri Apr 09, 2010 11:15 pm
- Post datetime: 2011-08-15T10:09:31+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

snd.all.pak looked inside the lie mp3 tracks can extract and insert hex editor

and to extract all the tracks you can use Dragon UnPACKer \ HyperRipper
## Post #10
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-17T02:21:48+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

Ran into a bit of a problem here, not sure if anyone can help me out. When extracted, none of the files have anything to do with weapon sounds. Some random sound effects and voices but nothing weapons wise. Anybody have any ideas? Ran through all of the files which looked like they would hold some weapon sounds, but nothing seems to pull up anything so I'm at a bit of a stand still now.

Would appreciate any ideas anyone may have.
## Post #11
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-08-18T13:30:59+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

weapon sounds are stored in the common_mp ff file. I don't know what format or what compression they use on ps3.

On xbox360, i've managed to decode them as xma after using cpmonkey's tool to decrypt and decompress the ff file. (with a good bit of help from hcs)

pretty much the pak files are like the IWDs of the pc blops, they only have certain sounds that are streamed mainly, not played over and over commonly.
## Post #12
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-18T22:53:47+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

> Reply from Pepper
>
> weapon sounds are stored in the common_mp ff file. I don't know what format or what compression they use on ps3.

On xbox360, i've managed to decode them as xma after using cpmonkey's tool to decrypt and decompress the ff file. (with a good bit of help from hcs)

pretty much the pak files are like the IWDs of the pc blops, they only have certain sounds that are streamed mainly, not played over and over commonly.

What tool did you use to extract the data? Do they extract as an audio file or another type?
## Post #13
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-08-19T13:58:41+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

the thing about ff files is they have some kind of compression on each platform. i used cpmonkey's tool to decompress to a zone file, then i scan through the large zone file looking for paths to sounds, which are usually .xm4 (xma in leet) and then i cut them out with a hex editor, one at a time.

and yes, on the xbox version i have gotten the gunshot and foley sounds out of the ff files.

the tool i have is xbox only.
## Post #14
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-19T16:03:37+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

So basically, your saying that because I'm on the PS3, I'm screwed.
## Post #15
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-08-19T22:50:15+00:00
- Post Title: Call of Duty: Black Ops - PS3 Audio

well, the ff format isnt very repack or mod friendly to begin with, even on pc versions
## Post #16
- Username: residualdamage
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sun Aug 14, 2011 3:48 am
- Post datetime: 2011-08-20T01:31:49+00:00
- Post Title: Re: Call of Duty: Black Ops - PS3 Audio

I just cannot believe that people haven't managed to crack the .FF format yet. I mean, haven't these files been in use for over 4 years? Call of Duty is a very popular game too, I would think there would be some sure-fire way to mod by now. Not trying to provoke or criticize anyone, I'm just a bit shocked is all.

I guess I have my answer though, there doesn't appear to be a way to do what I want to do. Mod's can close this if they want to.
## Post #17
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2011-08-20T16:39:12+00:00
- Post Title: Re: Call of Duty: Black Ops - PS3 Audio

well there are several issues, one being lack of mod tools for ps3 version, lack of modding happening in general since cod2, since the ff files are basically not mod friendly without modtools. (talking doing stuff besides texture and lang mods) and hell, the latest cod blops mod tools doesnt even give a way to make custom maps, since they still want to sell more dlc first. anys, games like cod2 were completely open for modding, they used zip files renamed to iwd, non of this compressed data stream fast file nonsense. I dont care if it makes loading faster. it kills the pc community. hence why we see far more hl2 mods everyday, they are much more open. they give full transparency in their tools, and when they don't, they even assist the mod community via the SDK wiki's heaps and heaps of information, allowing anyone to code a tool to decompile any part of their formats. FF files arent really cracked on mw2 and blops, since ps3 doesnt have as large a mod community as pc or even xbox, and they started adding anti-mod protections.

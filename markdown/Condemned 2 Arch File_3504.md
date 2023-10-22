## Post #1
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-05-22T22:57:17+00:00
- Post Title: Condemned 2 Arch File

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-23T00:24:49+00:00
- Post Title: Condemned 2 Arch File

*update* check the following post
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-25T00:58:51+00:00
- Post Title: Condemned 2 Arch File

and that's the magic script:
[http://aluigi.org/papers/bms/condemned2.bms](http://aluigi.org/papers/bms/condemned2.bms)
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-25T20:10:40+00:00
- Post Title: Condemned 2 Arch File

thanks luigi.
## Post #5
- Username: pixellegolas
- Rank: ultra-veteran
- Number of posts: 423
- Joined date: Tue Aug 12, 2008 6:30 am
- Post datetime: 2010-01-25T21:38:58+00:00
- Post Title: Condemned 2 Arch File

could you enlighten me with what model format this game is?
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-30T22:43:26+00:00
- Post Title: Condemned 2 Arch File

I have updated the script to version 0.2 because there was a bug and a needed compatibility fix (for some formats) so you MUST download the new version.
and please remember ever to test the extracted files because errors can be anywhere
## Post #7
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T01:07:20+00:00
- Post Title: Condemned 2 Arch File

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-08T07:52:46+00:00
- Post Title: Condemned 2 Arch File

here it works perfectly (tested with quickbms 0.4.5)
## Post #9
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T12:04:26+00:00
- Post Title: Condemned 2 Arch File

> Reply from aluigi
>
> here it works perfectly (tested with quickbms 0.4.5)
I just checked and strangely enough it works with the cut file, but not with the complete archive (2.517.228.532 Bytes) - maybe it's too big? Error message is always the predefined one from the script. As you can see, the offset is always negative: 
[](http://img704.imageshack.us/i/cond.png/)
What's wrong here?
## Post #10
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-08T12:09:48+00:00
- Post Title: Condemned 2 Arch File

yeah it's for sure the size, because it's major than 0x7fffffff
as fix you should try to add a 'u' before the comparison signs at the following lines like the examples:

```
line 66:        if OFFSET u> RATL_FULLSIZE
line 91:     for OFFSET = OFFSET u< LIMIT
```
let me know if this fixes the problem so I will modify the online script
## Post #11
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T12:16:51+00:00
- Post Title: Condemned 2 Arch File

HA! Works now - thanks a lot! 
Should I open a new topic for those *.bndl files inside the archives or could I also post here?
## Post #12
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-08T12:28:20+00:00
- Post Title: Condemned 2 Arch File

I hope the following answers your question :)

```
idstring LDNB   # from QuickBMS 0.4.5 idstring is auto-endian... cool :)
get VER long
get OFFSET long
goto 0x14
get FILES long
log MEMORY_FILE 0x18 OFFSET
math OFFSET += 0x18
for i = 0 < FILES
    goto OFFSET
    get NAME_OFF long
    get SIZE long
    savepos OFFSET
    goto NAME_OFF MEMORY_FILE
    get NAME string MEMORY_FILE
    log NAME OFFSET SIZE
    math OFFSET += SIZE
next i
```
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-06-08T12:30:14+00:00
- Post Title: Condemned 2 Arch File

A hint alpha for newer monolith games such as fear2/condemned 2 the filenames are stored in another data bank while the rest of the audio is in .snd files, this is basing off of fear 2 on pc so not sure if  monolith games on 360 is different, but just to know ahead
## Post #14
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T13:28:16+00:00
- Post Title: Condemned 2 Arch File

The contents of this post was deleted because of possible forum rules violation.
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-06-08T19:21:46+00:00
- Post Title: Condemned 2 Arch File

A little more info about the sounds/music in monolith games, mind you im basing this off fear 2 but both games coneemned and fear 2 uses the same engine anyway.

Seems that all .snds banks have a linker and there appropirate filenames can be found in here!

[http://www.filefront.com/16688871/SoundDB.gamedb](http://www.filefront.com/16688871/SoundDB.gamedb)

I am sure alpha must have the same file for condemned 2, but this is interesting nonetheless. This data bank file links to all the .snds in the snd folders in the bndls archives of the levels and the Mission banks include filenames as well, perhaps another script is in order here
## Post #16
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-08T21:44:02+00:00
- Post Title: Re: Condemned 2 Arch File

Ok, this took me all day:

```
pt02: http://www.megaupload.com/?d=20PAQRZF
pt03: http://www.megaupload.com/?d=PX1BXJ1Z
pt04: http://www.megaupload.com/?d=YQWPELGO
pt05: http://www.megaupload.com/?d=YP80ITBP
pt06: http://www.megaupload.com/?d=MJBJWA6L
pt07: http://www.megaupload.com/?d=EW8SEYQX
pt08: http://www.megaupload.com/?d=N9FDY7J0
pt09: http://www.megaupload.com/?d=A3BWJRPZ
pt10: http://www.megaupload.com/?d=G98JBKTZ
pt11: http://www.megaupload.com/?d=5ZKHNAM0
pt12: http://www.megaupload.com/?d=LF5OAAXI
pt13: http://www.megaupload.com/?d=I3125WIB
```
## Post #17
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-11T11:09:53+00:00
- Post Title: Re: Condemned 2 Arch File

Uhm, maybe it's a bit much to ask for, but could anyone with decent BMS skills please download the file and see what's wrong? I guess one of the "<" shouldn't be changed to "u<".
## Post #18
- Username: jukko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jun 13, 2010 8:33 pm
- Post datetime: 2010-06-13T18:20:28+00:00
- Post Title: Re: Condemned 2 Arch File

Will it work with Condemned: Criminal Origins Arch00 files?
Can't unpack DDS textures or even all archive with Dragon Unpacker. I mean they can be unpacked, but no editor can open them, cause they're somehow encrypted.
## Post #19
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-23T12:20:07+00:00
- Post Title: Re: Condemned 2 Arch File

Has anyone downloaded the arch file and tested the script? It always stops at a certain file because of a negative size. I don't know how to skip that file because the next ones depend on its file size!
## Post #20
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-24T20:31:01+00:00
- Post Title: Re: Condemned 2 Arch File

Please, can anyone tell me how to skip the files that throw an exception? Just as a work-around.
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-06-24T20:41:22+00:00
- Post Title: Re: Condemned 2 Arch File

I don't think aluigi hasn't been on in a while. If he comes on msn i will give him a heads up.
## Post #22
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-06-24T20:55:14+00:00
- Post Title: Re: Condemned 2 Arch File

k thanks
## Post #23
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-06-27T21:19:01+00:00
- Post Title: Re: Condemned 2 Arch File

script fixed (was a bug in quickbms in the Padding function), redownload it:
[http://aluigi.org/papers/bms/condemned2.bms](http://aluigi.org/papers/bms/condemned2.bms)
## Post #24
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2010-09-30T15:01:41+00:00
- Post Title: Re: Condemned 2 Arch File

Sorry, just saw that you updated the script a long time ago. I tried it on the layer *.arch files and now it doesn't work with either of the two files! Always throws a "canno write x bytes" exception.
Can you check again please?
EDIT: That's the exception I get
[](http://img4.imageshack.us/i/condemned2.png/)
I don't know if the extraction is over, more than 4GB were extracted from the bigger 2GB archive.
## Post #25
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-10-01T15:05:47+00:00
- Post Title: Re: Condemned 2 Arch File

> Reply from AlphaTwentyThree
>
> Sorry, just saw that you updated the script a long time ago. I tried it on the layer *.arch files and now it doesn't work with either of the two files! Always throws a "canno write x bytes" exception.
Can you check again please?
EDIT: That's the exception I get

I don't know if the extraction is over, more than 4GB were extracted from the bigger 2GB archive.

Alpha, I get the same message, but the extracted files (at least for me) are in fact, there. "it's possible bms has been written to exit this way...blah blah blah" I just assumed that was normal and looked in my output location and it was all there.

Now..I finally figured out that code bit he posted (on extracting the .bndl files) needed to be saved in notepad as a .bms file (yes, I am a total noob) and I have successfully extracted EVERYTHING in the bundle files.

However..the Fear2 Tools posted HERE: [viewtopic.php?f=10&t=3382&hilit=fear+2+tools](http://forum.xentax.com/viewtopic.php?f=10&t=3382&hilit=fear+2+tools) dont seem to work on these (like TEXconverter) and I'm also not sure how to get the mesh files into 3dsmax either..

So I've got them extracted..but cant do squat with them
## Post #26
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-10-08T14:46:24+00:00
- Post Title: Re: Condemned 2 Arch File

Ok, back on this again. I am now tending to agree with alpha that there is a POSSIBILITY that all files are NOT being extracted. 

My problem is this: I cannot find any of the models. NOTE: I am not talking about characters (ai) Those seem to be there (and I have someone working on getting the .mesh files that are there "usable") what I am talking about is the objects, the "Static" models if you will. Sure the model and prefab folders extract nicely and the .tex files for these assets are all there..but not the meshes themselves.

I know from reading some of the posts above that the folder/asset structure in this game is really wierd and things are linked and split up all over the place, but for the LIFE OF ME I cant find the model (meshes) that are supposed to correspond to the textures that go on them. 

so close..but yet so far.

Anyone?

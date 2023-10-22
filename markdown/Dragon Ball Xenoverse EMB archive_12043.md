## Post #1
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-03T11:56:07+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

After unpacking the CPKs I found out that the files inside are also packed in some kind of EMB format!
There's a fair ammount of types variaty in these archives, but what I'm looking at now is at the pictures (.dds to be precise)

I made a quickbms script to extract all the content of the images 

```
idstring "#EMB"
get UNK1 long
get UNK2 long
get FILES long
goto 0x20
get HEADER_OFFSET_TEMP long
set x 0x20
XMath HEADER_OFFSET "x + HEADER_OFFSET_TEMP"
goto HEADER_OFFSET
get UNK3 long
get SIZE long
get UNK4 long
get UNK5 long
get HEADER_SIZE long
XMath OFFSET "HEADER_OFFSET + HEADER_SIZE"
set NAME = "KLL.dds"
log NAME OFFSET SIZE
For i = 1 < FILES
	XMath NEXT_HEADER_OFFSET_TEMP = "HEADER_OFFSET + HEADER_SIZE"
	XMath HEADER_OFFSET = "NEXT_HEADER_OFFSET_TEMP + SIZE"
	goto HEADER_OFFSET
	get UNK3 long
	get SIZE long
	get UNK4 long
	get UNK5 long
	get HEADER_SIZE long
	XMath OFFSET "HEADER_OFFSET + HEADER_SIZE"
	log NAME OFFSET SIZE
next i
```
 

I know it's a bit rough but I'm working on it 
This extracts the content information of KLL.dds from KLL.emb but my problem is that I cannot seem to understand where is the information about the DDS header! So it's kinda pointless for me to get the content out!

Can anybody look at it and give me a hand? Thanks!
[KLL.rar](https://xentaxbackup.github.io/file/7876_KLL.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-03T15:48:20+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

give it a DDS header, change the params 'til you get a pic that makes sense (more or less):



emb_DDS_test.JPG (41.61 KiB) Viewed 372 times


Then compare the params to the emb data. That's how I would do it.

(To load fake DDS I use DXTbmp because it doesn't complain as DirectX texture tool does
when some header bytes are a little bit weird.)
## Post #3
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-03T15:59:06+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from shakotay2
>
> give it a DDS header, change the params 'til you get a (more or less) sensefull pic:
emb_DDS_test.JPG
Then compare the params to the emb data. That's how I would do it.

(To load fake DDS I use DXTbmp because it doesn't complain as DirectX texture tool does
when some header bytes are a little bit weird.)
Hmm, randomly changing the DDS Header is like picking a nail out of a haystack! 
I even understand the header format since there's this 
[http://msdn.microsoft.com/en-us/library ... s.85).aspx](http://msdn.microsoft.com/en-us/library/windows/desktop/bb943982%28v=vs.85%29.aspx)

but the problem is that I don't really have the slightest idea what are the parameters :S
I did use textureFinder and it kinda works, I don't know if anything (like width and height) from it is reliable for the parameters!

Do you think it's possible for the DDS header to be in another file somewhere? I mean, how does the PS3 know how to read the DDS if there is no header information anywhere?

Anyways, thanks, at least that DXTbmp might help me testing! I don't think noesis lets me do a proper test :S
## Post #4
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-03T16:04:05+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

EMB?? Is it by anymeans similar to SFIV emb container where is packed the textures??
## Post #5
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-03T16:09:51+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Dakilla
>
> After unpacking the CPKs I found out that the files inside are also packed in some kind of EMB format!
There's a fair ammount of types variaty in these archives, but what I'm looking at now is at the pictures (.dds to be precise)

I made a quickbms script to extract all the content of the images 
Code: Select allEndian big
idstring "#EMB"
get UNK1 long
get UNK2 long
get FILES long
goto 0x20
get HEADER_OFFSET_TEMP long
set x 0x20
XMath HEADER_OFFSET "x + HEADER_OFFSET_TEMP"
goto HEADER_OFFSET
get UNK3 long
get SIZE long
get UNK4 long
get UNK5 long
get HEADER_SIZE long
XMath OFFSET "HEADER_OFFSET + HEADER_SIZE"
set NAME = "KLL.dds"
log NAME OFFSET SIZE
For i = 1 < FILES
	XMath NEXT_HEADER_OFFSET_TEMP = "HEADER_OFFSET + HEADER_SIZE"
	XMath HEADER_OFFSET = "NEXT_HEADER_OFFSET_TEMP + SIZE"
	goto HEADER_OFFSET
	get UNK3 long
	get SIZE long
	get UNK4 long
	get UNK5 long
	get HEADER_SIZE long
	XMath OFFSET "HEADER_OFFSET + HEADER_SIZE"
	log NAME OFFSET SIZE
next i 

I know it's a bit rough but I'm working on it 
This extracts the content information of KLL.dds from KLL.emb but my problem is that I cannot seem to understand where is the information about the DDS header! So it's kinda pointless for me to get the content out!

Can anybody look at it and give me a hand? Thanks!

Use piecemontee SIV assets explorer to extract the file. ¿the models are emo or emz? If it's using crapcom SFIV engine then modding is possible. Also you can use texture finder to find texture compression.
## Post #6
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-03T16:12:14+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Darko
>
> EMB?? Is it by anymeans similar to SFIV emb container where is packed the textures??

Hmm..I've tried everything related to Street Fighter but nothing seems to work

The header seems a bit different then SF
But it's the same container yes! 

Just download the file and compare  I couldnt really get my hands on a proper SF emb to be absolutely sure

EDIT : 

The models seem to be in EMO , but I'm not sure how to check this!
But there's also an EMB which is the largest file in this character's folder!
I can't really put my finger on this
## Post #7
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-03T16:30:46+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Dakilla
>
> Darko wrote:EMB?? Is it by anymeans similar to SFIV emb container where is packed the textures??

Hmm..I've tried everything related to Street Fighter but nothing seems to work

The header seems a bit different then SF
But it's the same container yes! 

Just download the file and compare  I couldnt really get my hands on a proper SF emb to be absolutely sure

EDIT : 

The models seem to be in EMO , but I'm not sure how to check this!
But there's also an EMB which is the largest file in this character's folder!
I can't really put my finger on this

Can you upload some files pls?? let me check them 

Anyways, this seems PS3 related. That image is a 256x128 dtx5 modified image for PS3. I just changed the complete header and saved as tga with irfanview. In the pack there is the modified dds and the new tga. Compare the original with the one I modified to se what I did.

Edit:

Ouch ok, this seems to come from a beta, then don't worry, It's just matter to wait for the release of the game.
[KLL.7z](https://xentaxbackup.github.io/file/7880_KLL.7z)
## Post #8
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-03T16:50:29+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Darko
>
> Dakilla wrote:Darko wrote:EMB?? Is it by anymeans similar to SFIV emb container where is packed the textures??

Hmm..I've tried everything related to Street Fighter but nothing seems to work

The header seems a bit different then SF
But it's the same container yes! 

Just download the file and compare  I couldnt really get my hands on a proper SF emb to be absolutely sure

EDIT : 

The models seem to be in EMO , but I'm not sure how to check this!
But there's also an EMB which is the largest file in this character's folder!
I can't really put my finger on this 

Can you upload some files pls?? let me check them 

Anyways, this seems PS3 related. That image is a 256x128 dtx5 modified image for PS3. I just changed the complete header and saved as tga with irfanview. In the pack there is the modified dds and the new tga. Compare the original with the one I modified to se what I did.

Edit:

Ouch ok, this seems to come from a beta, then don't worry, It's just matter to wait for the release of the game.

Of course 

[https://www.mediafire.com/?2r6w3ur4523863v](https://www.mediafire.com/?2r6w3ur4523863v)

Please make sure to tell me what you find out 

hmm, now how the heck did you figured that thing out? I mean the 256x128 dtx5 was this information on the emb? I hope so, cause if it is I want to make a quickbms to extract that correctly(unless you have a better suggestion to extract that is)

And how did you get it into tga exactly? With Noesis? Cause I tried with noesis and it said the dds had a corrupt header! 
I mean, I didn't input any parameters to the extraction, should I?

thanks dude 


OH! And about this being a beta  I don't want to wait aha
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-03T17:42:41+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Dakilla
>
> I mean the 256x128 dtx5 was this information on the emb?

```
000040   02 02 00 FF 00 00 80 00  00 00 00 01 00 00 00 00
```


height 80 00 00 00 = 128
width 00 01 00 00 = 256
## Post #10
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-03T18:03:04+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from shakotay2
>
> Dakilla wrote:I mean the 256x128 dtx5 was this information on the emb?
Code: Select allOffset    0  1  2  3  4  5  6  7   8  9  A  B  C  D  E  F
000040   02 02 00 FF 00 00 80 00  00 00 00 01 00 00 00 00

height 80 00 00 00 = 128
width 00 01 00 00 = 256

of course, how could I be so blind lol
thanks
## Post #11
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2014-10-04T16:20:12+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

How do I decrypt the EDAT archive for this game?
## Post #12
- Username: Dakilla
- Rank: n00b
- Number of posts: 15
- Joined date: Mon Aug 11, 2014 8:37 pm
- Post datetime: 2014-10-06T10:04:46+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Darko
>
> Dakilla wrote:Darko wrote:EMB?? Is it by anymeans similar to SFIV emb container where is packed the textures??

Hmm..I've tried everything related to Street Fighter but nothing seems to work

The header seems a bit different then SF
But it's the same container yes! 

Just download the file and compare  I couldnt really get my hands on a proper SF emb to be absolutely sure

EDIT : 

The models seem to be in EMO , but I'm not sure how to check this!
But there's also an EMB which is the largest file in this character's folder!
I can't really put my finger on this 

Can you upload some files pls?? let me check them 

Anyways, this seems PS3 related. That image is a 256x128 dtx5 modified image for PS3. I just changed the complete header and saved as tga with irfanview. In the pack there is the modified dds and the new tga. Compare the original with the one I modified to se what I did.

Edit:

Ouch ok, this seems to come from a beta, then don't worry, It's just matter to wait for the release of the game.

So Darko, did you find anything on the files I sent you?
## Post #13
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2014-10-06T14:17:40+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

Nope, about the texture I found out because I used texture finder so it's easy to tell that with the program (I used it with Saint Seiya Senki). Models seems to be the emd files, and it's the same with you, I couldn't open it >_<.
## Post #14
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2014-10-07T11:13:13+00:00
- Post Title: Dragon Ball Xenoverse EMB archive

> Reply from Gh0stBlade
>
> How do I decrypt the EDAT archive for this game?

You'll need the EDAT, [BruteForce EDAT Tool and NPDTool](http://www66.zippyshare.com/v/28403228/file.html)

1. Extract the EDAT from the PKG or ISO.
2. Run the BruteForce EDAT tool and select the EDAT
3. Run BruteForce EDAT
4. Copy the EBOOT.ELF and EBOOT.BIN files to NPDTool folder
5. Once BruteForce has found the key, open up a hex editor and type it in. It should be exactly 16 bytes long / 0x0F.
6. Save that as <filename>.klic inside the NPDTool folder.
7. Run the command line and navigate to the NPDTool folder
8. Put the following arguments in
   
```
npdtool dk data.edat data.dat <filename>.klic
```

9. Let it decrypt the file

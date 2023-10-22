## Post #1
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-14T16:34:36+00:00
- Post Title: Twin Snake [GC MGS]

This game is for the Gamcube for anyone who isnt sure, the disk Will Not work in a PC or a Laptop or ANYTHING that it isnt made for.
TO obtain this game onto your PC i suggest you use google as Iam not sure if the way to get this game, albiet a perfectly legal way, would be condoned by Mr Mouse & Co(Yes & Co just sounded cool).

I obtained this game this morning and within about 20 minutes I was makigns oem Progress with the games Audio files,
I was at 1st confused by the File format (well actually the format was only called FILE so i had a reason to be a bit "???").

But after searching around the internet for a few short moments I found a HUGE GC guide, it covers all the aspects of the machine and its many file formats, Of course new ones may have ome out since its release.

I found a Plugin for Winamp that enables it to play gamecube ADCPM files (Audio only), so i simply added an extension to a file ad walla it worked in Winamp, I have the Source code to this Plugin aswell if anyone wants to know how it all works.

So the only thing left to look at NOW is DEMO.DAT and Stage.DAT, I looked at Stage.dat with Strobe and we were unable to figure out a way to extract the files as eventhough the DAT file itself wasnt encrypted all the files inside were packed and we are Currently unable to figure out their File Formats or even the format they were packed with.

So thats currently where Im at, Im making a ADP to WAV converter after studying the Winamp ADP player Plugin so I shud be abelt o release that sometime soon,though at the moment EVENTHOUGH i have change the hertz to the correct one the files are STILL sounding rather CHOPPY and unrecognisable.
I have uploaded the Gamecube File Guide in a RAR file along with the a 2meg piece of STAGE.DAT.
i hope someone can shed some light on this, Im still carefully staring at the File formats and hex viewers myself.The uploaded fiel can be found[http://www.megaupload.com/?d=Z5YLYLKF](http://www.megaupload.com/?d=Z5YLYLKF) (is there a way to make it so that the link is INSIDE  word? Ie: here)
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-14T18:20:59+00:00
- Post Title: Twin Snake [GC MGS]

I'm not sure whether this is what you wanted to know, but after a quick and dirty look:

The DAT file you uploaded is structured in blocks (or "sectors"), each 2048 bytes in size. The first 16 bytes of the first sector compose the header:

- 8 bytes that are currently unknown to me
- a word (i. e. 2 bytes) for the number of files within the DAT archive
- 6 bytes whose purpose I also don't know yet

After this header, there are descriptive entries for the files within the archive:

- 8 bytes for the file name
- (probably) a doubleword (i. e. 4 bytes) for the start sector

All values are stored as big endians, which makes sense, since the GameCube is based on PowerPC hardware.


But you probably have found that all out already ... what do exactly do you mean by "packed"? Do you suspect some sort of compression at work?

Concering your URL question: Try [ url=[http://example.com/](http://example.com/)]here[ /url]
(Remove the spaces after the opening brackets to make this work.)
## Post #3
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-14T19:12:16+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from Deniz Oezmen
>
> But you probably have found that all out already ... what do exactly do you mean by "packed"? Do you suspect some sort of compression at work?

Concering your URL question: Try [ url=http://example.com/]here[ /url]
(Remove the spaces after the opening brackets to make this work.)
Thanks for the Url help lol, i wondered that for the longest time now.
Well I never noticed they were Packed actually STROBE noticed and told me.
But he ses u can tell because u cant see the FIle extension of them files, they are just STRINGS and nothing more, so i GUESS thinking about it we could SOMEHOW make an archieve viewer for THAT EXACT DAT file, adn THEN wed be able to see the extension of them ohter files right? ie: Sna_def.archive type
Yes thats a pretty VIVID explanation of what i mean.
But would that even WORK, or wud be jsut see the files the correct way but just without their extension, so itd just be a gloryfied fiew of what we already have right?
if you like ad me to your msn IF oyu have it afrohollic@hotmail.com
## Post #4
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-14T23:35:00+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from lionheartuk
>
> Thanks for the Url help lol, i wondered that for the longest time now.
The post entry form tells you this when you hover the mouse cursor over the "URL" button ... 

> Reply from lionheartuk
>
> Well I never noticed they were Packed actually STROBE noticed and told me.
But he ses u can tell because u cant see the FIle extension of them files, they are just STRINGS and nothing more
Well, I guess if he found that out it'll be correct. I'm no expert for the GameCube; however, the absence of file name extensions in general does not necessarily indicate a compression. The developers might have created their own file formats that do not rely on file naming conventions.

> Reply from lionheartuk
>
> But would that even WORK, or wud be jsut see the files the correct way but just without their extension, so itd just be a gloryfied fiew of what we already have right?
Hard to tell from my point of view, since I don't even know what I should be looking for (i. e. what kind of data I should be able to extract from these archives). Currently, I don't see any way to get a file name extension from the archive.

Personally, I'd suggest you extract the single files (even without extension, just with the name given in the archive entries) and then look at them one by one. You might be able to find out more about the formats this way.

> Reply from lionheartuk
>
> if you like ad me to your msn IF oyu have it afrohollic@hotmail.com
Sorry, I'm not really into IM of any kind.
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-15T11:37:10+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from Deniz Oezmen
>
> 
lionheartuk wrote:But would that even WORK, or wud be jsut see the files the correct way but just without their extension, so itd just be a gloryfied fiew of what we already have right?
Hard to tell from my point of view, since I don't even know what I should be looking for (i. e. what kind of data I should be able to extract from these archives). Currently, I don't see any way to get a file name extension from the archive.

Personally, I'd suggest you extract the single files (even without extension, just with the name given in the archive entries) and then look at them one by one. You might be able to find out more about the formats this way.

Same here lol.
Though I should have some free time today so il look into the Stage.dat once again.
But thinking about it LOGICALLY if i simply extract the file names then all Il have will be something like  a 1KB file called "Snake_def" or whatever.
At least i THINK thats how itl work.
Hm.. I might try this way, I might need STROBES help on how to do it consideringt hey have no header or file size or anythig of the sort.
## Post #6
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-15T11:48:03+00:00
- Post Title: Twin Snake [GC MGS]

Yeah i think that it MIGHT work, because seing as the AUDIO files didnt have a file extension it MAY mean that the  MODEL and TEXTURE files within the DAT might not have extensions either.

All i know other then THIS is that the models were made in 3D Studio MAX, yes i read it on the site somewhere, il post a link when i find the site again ok.
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-15T15:22:14+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from lionheartuk
>
> But thinking about it LOGICALLY if i simply extract the file names then all Il have will be something like  a 1KB file called "Snake_def" or whatever.
At least i THINK thats how itl work.

Correct. You might need to look into the files themselves to determine of which type they are.

I have attached the sample program I used to analyze the cut files you posted. Maybe you can use it to look at the single files. No guarantee that it works, however, since I could not test it with a complete archive file.

[Edit: The file got somehow lost ... reattached.]
[Edit2: Next try to attach this file.]
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-15T15:58:22+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from Deniz Oezmen
>
> lionheartuk wrote:But thinking about it LOGICALLY if i simply extract the file names then all Il have will be something like  a 1KB file called "Snake_def" or whatever.
At least i THINK thats how itl work.

Correct. You might need to look into the files themselves to determine of which type they are.

I have attached the sample program I used to analyze the cut files you posted. Maybe you can use it to look at the single files. No guarantee that it works, however, since I could not test it with a complete archive file.

[Edit: The file got somehow lost ... reattached.]
The file still isnt in the post dude.
And yeah il need to lok into this a LOT i tihnk, I need the help of someone really good at this, like Mr Mouse or Turfster even (he ses he is more of a Grahics man).
My post worked?
wHEN I TRIED OT POST ERLIER the forum gave me this WHACKED error i couldnt even understand, wonder waht it was
## Post #9
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-15T17:44:47+00:00
- Post Title: Twin Snake [GC MGS]

Well eventhough the forum seemed ot have gone INSANE me and Deniz Oezmen continued ot work on the DAT.
Well the DAT HAS been extracted and its thrown out a bunch of files I am currently  abit confuseed by.
NOne the less im gonna TIRELESSLY run though the Gamecube Documentation PDF i have and see if i can dig up ANYTHING(why do i know im STILL gonna be a dead end after this).
well itsthrown out a bunch of files.
They dont ahve extensions so its hard to tell what they even do.
I cant tell if there IMAGES, models or even Archives.
Its damn hard to understand this lot.
Once the forum attachments are working again il upload a smaller file and se if anyone else wants to have a go
## Post #10
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-16T15:08:30+00:00
- Post Title: Twin Snake [GC MGS]

Just as a follow-up to summarize the current results:

As noted earlier, the file offsets are addressed in units of sectors, each 2048 bytes in size. When seeking to such a start sector, it will actually not yet contain file data (which starts one sector later), but yet another descriptor. Most values in this additional header are unknown, but bytes 14 and 15 specify how many bytes of the last (!) sector are occupied by file data. Thus, the file can finally be extracted with the correct size.

The file data itself might be (ZLib-?) compressed, since it usually starts with an "x".

So ... whoever has a working infrastructure to test this, please volunteer. I won't have enough time over the course of the next week.
## Post #11
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-16T15:23:28+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from Deniz Oezmen
>
> 
The file data itself might be (ZLib-?) compressed, since it usually starts with an "x".
So ... whoever has a working infrastructure to test this, please volunteer. I won't have enough time over the course of the next week.

Ahhh, so we HAVE extracted the files at the EXACT correct size then as I wasnt to sure really.
It SEEM like their MAY be some archieves within that DAT file aswell.
Ie most of the stages dont compress very well and I cant find any information inside them.
Oh well [HERE](http://www.megaupload.com/?d=OC7943NF/)is a file from the game.
I ahve uploaded several into 1 RAR file so u can compare then
im not sure what it contains, tho it SEEMS to be Either MODEL data or Texture Data.
## Post #12
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-09-17T16:11:31+00:00
- Post Title: Twin Snake [GC MGS]

From a (very) quick peek at one of the files, I'd say you first have a 2048 byte header which contains at least some of the following : 
number of objects in the file (first 4 bytes)
endedness indicator? (next 2 bytes)
? (next 2 bytes)
unpacked size (next 4 bytes)
package identifier (my guess is offset 20)
object identifiers (numobject count)

Your real data starts at 2048, and yeah, it's compressed - when I threw it at STUNS, I got some pretty coherent results for the deflate algorithm. Haven't really got the time to take a closer look at the moment, and I'm still in the middle of the MGS2 work, so I dunno when/if I'll have time.
## Post #13
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-17T17:46:07+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from Turfster
>
> From a (very) quick peek at one of the files, I'd say you first have a 2048 byte header which contains at least some of the following : 
number of objects in the file (first 4 bytes)
endedness indicator? (next 2 bytes)
package identifier (my guess is offset 20)
object identifiers (numobject count)

Your real data starts at 2048, and yeah, it's compressed - when I threw it at STUNS, I got some pretty coherent results for the deflate algorithm. Haven't really got the time to take a closer look at the moment, and I'm still in the middle of the MGS2 work, so I dunno when/if I'll have time.
ahhhhhhhh.
Well seems this is getting SOMEWHERE.
STUNS? whats STUNS?
Il try get it if i can, this STUNS program i mean.
Deflate algorithm?(im guessing by deflate u mean = dissasemble or take aprt)
There MORE to do on MGS2?
oh no wait, yeah them EVX files + animations, but thats it as far as i know right?
## Post #14
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-09-17T17:58:02+00:00
- Post Title: Twin Snake [GC MGS]

I've attached a copy of STUNS (stupid uncompressor) to this post.
Deflate is a generic compression algorithm.
As for the MGS2 work, there's quite a lot left, really.
[Stupid uncompressor.rar](https://xentaxbackup.github.io/file/861_Stupid uncompressor.rar)
## Post #15
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-17T19:01:57+00:00
- Post Title: Twin Snake [GC MGS]

> Reply from Turfster
>
> I've attached a copy of STUNS (stupid uncompressor) to this post.
Deflate is a generic compression algorithm.
As for the MGS2 work, there's quite a lot left, really.
Thanks dude.
Im gonna see what I can get up to now, though im not expecting MUCH, as i am yet to find a feild im good at, tho IMAGES arnt as hard as others i have found.
Maybe there is a lot of work.
Do you plan on attempting to complete her ENTIRE list of requests, some are cool but others, well I dont think they are really possible for a LONG time at least (Namely the Engine edits to make ur own snake tales).
Well animations are a cool next if you can crack them i guess.
## Post #16
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-17T22:15:21+00:00
- Post Title: 

Well thnaks to STUNS me and strobe managed ot get SOMETHING fromt he files.
Image data,  .
But.....
We actually cant get ANYWHERE after this.
We spent at least a hour replacing Bytes, renaming fie extensions, and even COnverting With Solidus.
But.
the best thing we were actually ABLE to get was this.
Its a texture of SOEM SORT.
But its HUGE, so im guessing that TTS must hold texture data in a similar way to MGS2 PC.

There have also been a good few Similarities to Konami XTI textures, noted by Strobe not me,a s I have LITTLE exp in the XTI area.
But weve come to the conclusion that there are more then likely a form or DDS, though maybe compressed once AGAIN (why so many times?).

Note: this IS the size ofthe DDS texture itself I have just converted it to a JPEG Image for the forum.
If anyone else can get anything from the file i have posted cimbined with STUNS then please post your results here.
Il be workin on this with Storbe for a while lol.
## Post #17
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-09-17T23:42:19+00:00
- Post Title: 

Hm... Have you tried unswizzling the image?
## Post #18
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-18T07:50:42+00:00
- Post Title: 

> Reply from Turfster
>
> Hm... Have you tried unswizzling the image?
Unswizzling?
TO help explain what happened here im gonna attach the file that i got THIS from.
Il email it to you in a little while.
As its too big to Attach (1MEG rar), adn Its too early in the morning for me to do megaupload lol.
## Post #19
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-09-18T20:21:58+00:00
- Post Title: 

Im gonna tell you exactly what i did.
I loaded one of the compressed files into STUNS and let it bruteforce thru the
file. the largest output i assumed was the real decompressed file. and it was.

When i looked at it thru a Hex editor i noticed there where many similarities to a format ive seen before. XTI files. but soliduz didnt want to read it.

So, after loading another XTI file and comparing those i saw that the main difference was 2 bytes in the beginning of the file.

So, i removed those, and saved. and Bang, soliduz read the file as
a normal XTI , and even exported it as a DDS file.
(however the dimensions where set to 0x0, so i changed those to
read 256x256 instead) and Photoshop read it.

And that is the image you see there which lionheartuk posted.
(with some bytes chewed to correct the image further, because there is
an offset skew when exporting these with soliduz, so i manually adjusted
this with hex)

However, the exports are not really legit, as Soliduz doesnt support this
"new" XTI format . but yes, there are data that looks like DDS (using DXT1 format) in there. but no matter how you puzzle with the bytes it cannot be unscrambled.

BUT. notice how the scrambleblocks seems to be 4x4 pixels wide. that made me think of S3TC compression which stores information in 4x4 blocks and
interpolate between colors. could this be something?

I have not tried unswizzling, mainly because i didnt think of it until now,
but swizzle is XBOX specific?, maybe not in a GC game.
but the possibility is still open.
## Post #20
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-18T20:29:34+00:00
- Post Title: 

> Reply from Strobe
>
> However, the exports are not really legit, as Soliduz doesnt support this
"new" XTI format . but yes, there are data that looks like DDS (using DXT1 format) in there. but no matter how you puzzle with the bytes it cannot be unscrambled.

BUT. notice how the scrambleblocks seems to be 4x4 pixels wide. that made me think of S3TC compression which stores information in 4x4 blocks and
interpolate between colors. could this be something?

I have not tried unswizzling, mainly because i didnt think of it until now,
but swizzle is XBOX specific?, maybe not in a GC game.
but the possibility is still open.
So unswizzling MEANS somehting then lol, I thought maybe he ment like "have you tried playing about with it"(I at 1st thought it was sarasm lol).
Well the GC uses a LOT of things actually lol.
In the guide that i sent you Storobe there  is  section saying about  Texture files being 2x2 or something, meaning that u cant touch one pixel without affecting the other.

Yes I played a bout with it for a good HOUR and all i manged to change was Dimensions, Resolution and maybe one or two other things i wasnt sure of.
But if this Swizzle thing can work then SOMEONE please try it as I have never heard of it so il be unable to try it unless I get some INFO on it,(for all i know its a program lol)
## Post #21
- Username: Turfster
- Rank: veteran
- Number of posts: 92
- Joined date: Fri Dec 16, 2005 9:12 am
- Post datetime: 2006-09-19T00:48:48+00:00
- Post Title: 

> Reply from Strobe
>
> but soliduz didnt want to read it.
That's because they're really almost nothing like the PC XTI files 

Here's what I *think* the files look like (this should get you started, anyway) : 
Note : This is basically guesswork, based on 2 files (mrl_def and mrl_dis). Values are *big*-endian, not little-endian.

First, there's some sort of header, which is probably 32 bytes big, 
with the identifier offset (see further) at 26-27, and the number of files at 16-20. Note that I've seen at least 1 file ("area" that lionheartuk sent me) that doesn't follow this pattern, but that's for you to figure out 

After that, you get your file information blocks, 128 bytes each.
Bytes 48-52 here are probably your file identifiers.

Your format identifier is a $20AF30, and is at the indentifier offset mentioned earlier. The next bytes after your identifier are :
00 : number of files, again
04 : fileinfo (8 bytes) * numfiles

So yeah, basically, nothing like the PC XTI files. Hope this is enough to get you started.
## Post #22
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-09-19T10:14:41+00:00
- Post Title: 

> Reply from Turfster
>
> Strobe wrote:
First, there's some sort of header, which is probably 32 bytes big, 
with the identifier offset (see further) at 26-27, and the number of files at 16-20. Note that I've seen at least 1 file ("area" that lionheartuk sent me) that doesn't follow this pattern, but that's for you to figure out
Thanks dude.
Yeah il take a look at the files with your info, Should be enough to get us started I think.

Yes Area doesnt seem anything like the other files either, well it has a lot in common with the OTHER 100 area files   .
I believe that Meryl Def and such contain textures (I originally believed models aswell, unless the models are MEGA compresse like in MGS2, then they could be like 4 KB or even below), Wheras it makes sense for Area to contain MODELS and textures, So maybe its only models Im not sure.

I looked into S3TC texture compression, andYES it IS used by the Gamecube aswell, I collected a loa dof info on it and I have a few ideas, but imgoignt o try and run them by Strobe and see what he thinks.
## Post #23
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-05T15:16:07+00:00
- Post Title: 

The NEWEST release of Soidus by the one and only TURFSTER has provided FULL SUPPORT to the GAMECUBE mgs TEXTURES.
So everyone thank him for that.
The only things left on THIS GAME that I hope are one dayt supported By ANY program are 
- VOX.DAT extraction(this holds the voice data)
- Texture REPLACEMENT into the.texture file then replacing the STAGE.DAT original texture file with the NEW MODIFIED texture file.

- Model Support for the .KMY files in this game.

- Information regarded WHAT the TYPE04 and stuff fiels are, because i cant understand ANYTHING about these.
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-13T21:03:00+00:00
- Post Title: 

Like said before in this thread, the files in the stage.dat are Zlib compressed. Easy.  

Furthermore, there's a little more to the archive format then meets the eye. I see shining stars, but they are somewhat occluded by misalligned logic circuits in my brain that are dying for some more info. 

It is a shame I do not have more of that stage.dat file. Lionheart, do you think it possible to cut off and zip say 16 mb from the front and upload that somewhere?
## Post #25
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-13T21:45:58+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> Like said before in this thread, the files in the stage.dat are Zlib compressed. Easy.  

Furthermore, there's a little more to the archive format then meets the eye. I see shining stars, but they are somewhat occluded by misalligned logic circuits in my brain that are dying for some more info. 

It is a shame I do not have more of that stage.dat file. Lionheart, do you think it possible to cut off and zip say 16 mb from the front and upload that somewhere?
huh.
Erm yeah sure I can give you more if you like, Il upload a 3 meg piece ok, 2meg middle start and End.(6meg overall)
But Solidus has already gotten support for this, as It seems Turfster is making an all Purpose MGS tool and not jsut one for MGS2PC.
But if you want to add support for MultiEx then that would be cool aswell, Maybe then IL understand the files as I still dont really understand HOW turfster did what he did with them lol.
If you stillw antt he files anyways then say And il upload a larger Piece for you.

HOW do i take 16MEG from the Font? Or is there a tool u have that will do this for me?
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2006-10-13T23:15:29+00:00
- Post Title: 

> Reply from lionheartuk
>
> 
HOW do i take 16MEG from the Font? Or is there a tool u have that will do this for me?

Yep, I want to support it in MexCom. 


Take Hex Workshop and select 16 MB of the file. Copy it to a new file and then zip it. 16MB = 16777216 bytes. It's like selecting a piece of text. When you select you can see bottom right how many bytes you've selected.
## Post #27
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2006-10-14T10:24:51+00:00
- Post Title: 

> Reply from Mr.Mouse
>
> lionheartuk wrote:
HOW do i take 16MEG from the Font? Or is there a tool u have that will do this for me?

Yep, I want to support it in MexCom. 


Take Hex Workshop and select 16 MB of the file. Copy it to a new file and then zip it. 16MB = 16777216 bytes. It's like selecting a piece of text. When you select you can see bottom right how many bytes you've selected.
I thought of that but then i though "Nah thats a silly way, there must be another way" But it seems not lol, Oh well.
Il upload it sometime soon then.
Btw: Gamecube Disks cannot Be read by the PC i just happen to have an ISO of the disk that I made(perfectly legal considering i OWN the original game).
But yes Maybe il be able to learn semething from the Mex Script, As i learned very little in Turfsters Conversion as He did it all himself and I only Provided some files lol.

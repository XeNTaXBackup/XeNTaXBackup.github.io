## Post #1
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-05T19:43:15+00:00
- Post Title: Splinter Cell 2 .SS0 Music

I have done some investigating into the format of music in Splinter Cell Pandora Tomorrow, and I figured out the format (the key is that it uses a variant of IMA-ADPCM for compression). I wrote a program to extract it. The music is in pieces, just like the in other Splinter Cell games. It seems that no one else has found a way to extract the music from the .SS0 files. Is this something that is still of interest?
## Post #2
- Username: Bioscope
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Mar 26, 2007 9:43 pm
- Post datetime: 2008-05-07T10:25:16+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Well, to quote Star Trek: Put it on screen....

There are many who would like to get their hands on this program.
## Post #3
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-09T19:53:32+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Well... here it is. The source code is included (C++). It is a command line program. It is important to note that all of the music is in chunks, and my program cannot yet thread those chunks together, nor does it attempt to figure out at what offset in the file it's at or how long it is. This information comes from MAPS.SM0. I am still not sure of the format of the header, so my program just assumes a constant size of it, but this is probably not the case.

Now, for actually using my program:
You must tell it the filename (*.SS0), the name of the file to write to (-o Filename), the offset (-i Offset), the size (-s Size), and whether it is stereo (--stereo) or mono (--mono). You can write to a standard wave file (option -w or --wave), or just output raw audio (option -r or --raw). I included some batch files for examples.

Example of How to Use It:

```
DecUbiSnd "C:\Program Files\UBISOFT\Splinter Cell Pandora Tomorrow\offline\data\sounds\Music_Emb.SS0" -i 9015072 -s 3238562 -w -o EmbassySearch.wav --stereo
```

I installed the demo of Splinter Cell Double Agent, and I found that this uses the same audio compression method. So my program is able to decode this audio (with a little workaround). The header is different though, and I will probably add official support for this later.
[DecUbiSnd-0.1.zip](https://xentaxbackup.github.io/file/1512_DecUbiSnd-0.1.zip)
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-15T16:39:05+00:00
- Post Title: Splinter Cell 2 .SS0 Music

So will this work for all ubifsoft games that use the SS0 files?
## Post #5
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-15T19:47:37+00:00
- Post Title: Splinter Cell 2 .SS0 Music

I don't know, but it seems like this could be the case most of the time. Sounds in UbiSoft .SS0 files have a 1-byte version number, so that is probably what we should go by.

SC Pandora Tomorrow: Version 3
SC Double Agent (Demo?): Version 5

Another UbiSoft game I checked had version 5 also, but I don't own very many UbiSoft games. Perhaps I could find demos? I have not yet added support for type 5, but it can decode the files anyway (see one of the batch files I included in the zip file). It is very similar to type 3, so it shouldn't be difficult. I also want to give it the ability to scan for audio pieces (the only lookup table for offsets and lengths is in MAPS.SM0, but that file is pretty complicated). I have not yet figured out the audio decompression method for the original Splinter Cell, but it seems to be older and has a simpler stream.
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-15T20:50:39+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Ubisoft also use other formats like SS5 and SS4, any support in the future for those, or are they the same?
## Post #7
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-05-16T10:39:58+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Formats like SS5 and SS4 are not the problems if he his tool scan/convert direct the stream.
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-16T13:00:55+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Ahh okay, because when i input a ss5 or 4 file it doesn't support it.
## Post #9
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-16T18:10:53+00:00
- Post Title: Splinter Cell 2 .SS0 Music

It doesn't matter what the file extention is, but if the first byte of it is a 3 or a 5, it can decode it.

By the way, does anyone have any questions about how to use my program? Even though I made it, I think it's difficult to use.
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-16T18:59:06+00:00
- Post Title: Splinter Cell 2 .SS0 Music

yes it is kinda tricky to use, I hope it can decode beowulf if its a 3 or 5, but thats the problem, ubisoft always make changes to there audio system and you have to constantly keep on tweaking the program, correct me if im wrong on this.
## Post #11
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-05-17T19:48:59+00:00
- Post Title: Splinter Cell 2 .SS0 Music

I haven't had the chance to go diving into the files.  Most of the ones for Pandora Tomorrow (the ambient SS0 files) are accompanied by .UAX files that are much much smaller, perhaps a file table?  My question is how are you finding the offset and sizes of each audio file within the package?

Also, I stumbled upon a page talking about the similar file formats for Myst from Ubisoft.  
[http://simonwoodside.com/weblog/2004/11/10](http://simonwoodside.com/weblog/2004/11/10)

According to this page, at least for Myst, the LS0 files are straight ogg files that can just be renamed with the extension .ogg.  I attempted this on the LS0 files in the english folder for all splinter cell games and failed every time.  However, on that very page mentioned above, the author mentioned a program called Revelator
[http://homepage.mac.com/rshayter/Revelator.html](http://homepage.mac.com/rshayter/Revelator.html)

It is available for Windows and Mac.  The program is a .jar and it didn't convert any files but maybe this may help in finding out more about all the different file types associated with audio for Ubisoft games.  And perhaps someone would be kind enough to add this link to the Game Specific Tools page for anyone wishing to extract files from Myst as it seems perfectly capable of at least working with that game!  I'd do it myself but I'm not used to the wiki formatting.
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-18T01:32:33+00:00
- Post Title: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> ... ubisoft always make changes to there audio system and you have to constantly keep on tweaking the program, correct me if im wrong on this.
This is partially right. UbiSoft changes the format of the MAPS.SM0 file for almost every game. This file contains the list of offsets and sizes, and some sound effects I think. But the format of the chunks in .SS* files does not change often. I thought that the .UAX files might contain offsets and sizes, but they don't. I think they contain IDs that match up with the ones in MAPS.SM0, but I'm not sure. It is also possible to scan through the data looking for these chunks, and I am extending my program to do that.

Well, here is the latest version of it. I added a new feature which will string the segments of music together, so that you don't have to do it manually afterwords. There are seperate files (you have to create yourself) which hold each offset and size. See the batch files for examples.
[DecUbiSnd-0.2.zip](https://xentaxbackup.github.io/file/1513_DecUbiSnd-0.2.zip)
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-18T18:31:46+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Ive tried to test ss files from other games like rainbow six vegas for psp which uses ss5 but it decoded into a bunch of static, it needs to be a type 3 or 5 but thats the thing, im not sure how to even in a hex editor. I would really like to test other games on this.
## Post #14
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-18T21:40:34+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Post some of the files and I'll have a look at them.
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-18T22:00:02+00:00
- Post Title: Splinter Cell 2 .SS0 Music

Don't have the rainbow six vegas anymore but here is a BAO file from beowulf, now this behaves the same way as an ss file, its just when i loaded into goldwave it sounds all distorted, it manages to play fine, all other files are like this, except some play clearly while others are just plain static.

anyway here it is.
[http://www.megaupload.com/?d=QCXU5P9B](http://www.megaupload.com/?d=QCXU5P9B)
## Post #16
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-05-19T22:27:26+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Wow thanks for the post on the new compiled version of your program.  Will give it a test run asap!  I've been having a lot of trouble trying to even play Double Agent as my Alienware laptop has an NEC dvd drive which really sucks.  Can't read half of the discs I put in it.
## Post #17
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-20T19:05:41+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I looked at that file from Beowulf. My program cannot decode it yet. It looks like it uses an interleaved format, but different from that in SC DA.
## Post #18
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-20T19:24:49+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

okay thanks.
## Post #19
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-25T21:15:55+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I now have added support for SC DA-type interleaved streams. Also, Beowulf uses a similar format. I did not upload the latest version of my program, but it can decode that file from Beowulf that you posted, OrangeC. I don't want to overrun the topic with versions. Support for Ogg Vorbis streams is coming.
## Post #20
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-05-26T05:51:07+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Great news!  I think the folks here at xentax are patient to begin with so I for one don't mind but if you want someone else to help test you know there will be people here that will be happy to!
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-26T15:48:19+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Yes, cant wait to try it out!!
## Post #22
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-27T22:55:08+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I have also tested your second version of the progam on red steels ss7 files and it seems to decode the streams, but the audio plays a bit choppy and seems rather loud, i guess some testings of later versions might seem to touch up on these, but it seems like a simple stream.
## Post #23
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-27T23:34:46+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well, here it is. I also added support for SC1/SC2 ambient streams.

I decoded some interleaved audio from SC DA and mixed the layers together, and this is what I came up with:
[http://files.openomy.com/public/Zench/SCDALayers.mp3](http://files.openomy.com/public/Zench/SCDALayers.mp3)

Also, I decoded that Beowulf file that was posted (it had 2 layers), and I think I have the wrong sample rate (it would sound speeded up or slowed down), but here is the result:
[http://files.openomy.com/public/Zench/BeowulfLayers.mp3](http://files.openomy.com/public/Zench/BeowulfLayers.mp3)

Enjoy!
[DecUbiSnd-0.26.zip](https://xentaxbackup.github.io/file/1526_DecUbiSnd-0.26.zip)
## Post #24
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-28T00:47:17+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

A few more things...

I should explain that my program doesn't even attempt to mix together the layers in an interleaved stream. It outputs the layer, and then you can mix them together (easily) with an audio editor. I added the command line switch -l or --layer {Layer Number} to specify which layer you want to decode. A great thing about the interleaved streams is you don't need to specify the size, it's included in a header in the file. (If you didn't specify the size and it was a simple stream it would just decode until the end of the file.)

About the .SS7 files from Red Steels: post a little of them. I think I might know what's wrong -- it's happened to me many, many times when I was debugging my program. It could be that my program doesn't start decoding at the right position, or that it messed up when it read the header, or a few other things.
## Post #25
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-28T01:28:05+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well i think i figured out red steels ss7 files, inside the ss7 files there are segments that have to be extracted then decoded with your program, problem is there are alot of segments and that can take a long time.

But here is one.
[http://www.megaupload.com/?d=9KF83UV4](http://www.megaupload.com/?d=9KF83UV4)
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-28T20:13:09+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Hmm when i try to decode the beowulf layers it gives me an error: unknown sub-type 2, and ive tried forcing it to use decoder 3,5 and 8 and i even did the layer input and it doesn't decode, it also lets me know that i failed to initialize the header.
## Post #27
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-05-30T20:54:22+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well, it wasn't you who did anything wrong when it says "failed to initialize header". It just couldn't do it. Did you know that the audio (that my program can decode) in the file you posted and probably the rest of Beowulf doesn't start at offset 0? I forgot exactly where it begins in the file you posted, but you can use the scan feature to find it. It may not decode every single file in Beowulf even at the correct offset, because I made some false assumptions and haven't gotten around to fixing it yet.

I'm not sure if I explained the scan feature; it looks in the file you specify for UbiSoft audio chunks and outputs the offsets and sizes of where they are. This command line (with the new version of my program below) will extract all those chunks from the Red Steels .SS7 file and output a single wave file containing the one after another:

```
DecUbiSnd zikstore814jpopfpp.ss7 -g Segments.seg --stereo -w -o zikstore814jpopfpp.wav

```


I'm sorry for the message saying this feature is experimental. I forgot to remove it; it should work just fine, but I still want many people to test it and tell me if it works or not.

Ogg Vorbis and better layers support are coming.
[DecUbiSnd-0.27.zip](https://xentaxbackup.github.io/file/1531_DecUbiSnd-0.27.zip)
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-30T21:02:03+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Thanks

Will check it out.

EDIT: okay tried it on a red steel file and so far seems to work. I looked at the other beowulf files more and some have the type with layers, the type with segments i believe and the raw type which needs no decoding.

I will send you all three types later for further analyses if you want.
## Post #29
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-05-31T00:48:19+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Okay a little more on beowulf

This seems to use three types of files

The files that have RAW unencrypted codecs> program not needed, just convert them to wav with an audio editor

The files that have segments just like in red steel> some don't want to convert though, like when i scan them it displays as zero segments and it doesn't want to convert to wav.

Then there are layer files> i tried to decode them but it only does 1 layer, and it ignores the second one and it ignores the -l command and still gives me this sub-type 2 thing.

is it possible to add a layer scan?
## Post #30
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-01T22:17:33+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> The files that have segments just like in red steel> some don't want to convert though, like when i scan them it displays as zero segments and it doesn't want to convert to wav.You were using an old version of my program. I know because it happened to me.   

> Reply from OrangeC
>
> Then there are layer files> i tried to decode them but it only does 1 layer, and it ignores the second one and it ignores the -l command and still gives me this sub-type 2 thing.Layers decoding is a bit messed up still, so let's just wait until I can get it to work properly before we worry about that. It probably won't decode many files. 

> Reply from OrangeC
>
> is it possible to add a layer scan?Do you mean something that scans for all of the layers together, or scan for each of the layers seperately? It can already (I think) scan for all of the layers together i.e. the stream. I like to call it an 'interleaved stream'. I should probably add something that tells you how many layers there are in the file.
## Post #31
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-01T23:17:46+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Yeah i shall wait for the next version because i can decode some beowulf files but others don't want to convert. But i finally finished red steel.
## Post #32
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-03T18:28:30+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Cool  

I think I'll make one or two more small releases and then do a version 0.5 release. It should have complete support for everything I've seen so far. For this bigger release I think I'll start a new topic because the title of this one is getting a little irrelevant. I will also probably write a good, formal description of UbiSoft streams. If anyone wants to write documentation on UbiSoft streams or my program I would be happy to include them.

I have been thinking that maybe it would also be neat to create a UbiSoft stream encoder. It probably wouldn't be really difficult. I like how the XeNTaX community stresses not only file decoding, but also game modding abilities as well.
## Post #33
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-03T18:42:19+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

yes that'd be cool cant wait.
## Post #34
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-04T19:22:01+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Here is the next version. Besides Ogg Vorbis support, I am also working to make the error messages more meaningful. Actually this version can decode Ogg Vorbis.

Edit: Attachment removed. I found a bug in my program. I posted a fixed version below.
## Post #35
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-04T19:46:53+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Does this version have better beuwulf support?
## Post #36
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-04T21:03:16+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

It should. If you still have problems try the scan feature as well. If that doesn't do it then you should probably just post the file.
## Post #37
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-04T22:17:54+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well its the same interleaved layer file that you posted and this is the command i usually try to put in but it gives me an error.

decubisnd --input-type 8 (Filename).bao -l 0 --stereo -w -o track.wav

I even force the codec to 8.

It either gives me an error or i can only extract one layer from the multilayer file.

EDIT: okay well i figured out the commands, error on my part. now the only thing is some short files they show 0 segments.

Like this one
[http://www.megaupload.com/?d=TPI07U9L](http://www.megaupload.com/?d=TPI07U9L)
## Post #38
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-05T19:19:05+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

It must be an ending segment. Kataah said he encountered some of these in Ogg Vorbis. I don't know the right way to decode them, except perhaps sticking them onto the end of the correct file and trying to decode the whole thing. I don't have any games that use these ending segments unfortunately.
## Post #39
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-05T20:16:58+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Weird, i have about 170MB left of these files. and i want to make sure i have the complete beowulf rip.

Some of the files are 9MB to 11MB so those are too long to be ending segments.
## Post #40
- Username: MurraySkull
- Rank: advanced
- Number of posts: 48
- Joined date: Sun Nov 26, 2006 10:48 am
- Post datetime: 2008-06-05T23:50:49+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

How about you forget this topic and look at MINE instead:
[viewtopic.php?f=17&t=3052](http://forum.xentax.com/viewtopic.php?f=17&t=3052)
## Post #41
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-05T23:55:11+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

How about you be patient.
## Post #42
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-06T18:42:26+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Weird, i have about 170MB left of these files. and i want to make sure i have the complete beowulf rip.

Some of the files are 9MB to 11MB so those are too long to be ending segments.I could be wrong. If they are like the file you posted, there is not enough data in the file to correctly decode it. Maybe you could figure out if these files match up somehow.

I'm just going to ignore that "interruption" in the topic.
## Post #43
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-06T19:28:08+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

[http://www.megaupload.com/?d=PXZYGTWY](http://www.megaupload.com/?d=PXZYGTWY)

Well here is all the files that i cannot decode, most of them have the begiining header with a $ symbol, but i stil cant get anything out of that.
## Post #44
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-06T21:49:21+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Wow... thanks! I'll be sure to have a look at them. Hopefully there are some headers in there that I can use to try to decode them.
## Post #45
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-07T00:38:32+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I've had quite a bit of success with your tool.  It's very stable!  Great work!  Thank you very much for all your hard work.

On an older note that was brought up earlier in the topic: I think people would benefit from being able to encode to these files as well.  I for one have been composing music and designing sounds with the intent of implementing them in free mods for various game formats.  I've done so for various game engines like Quake series and Doom series, even Half-life series.  However, when it comes to unreal Tournament 3/ Splinter Cell series, Gears of War, etc...  that use the Unreal Engine 3 technology I haven't had much luck learning the all-in-one editing suite that comes with UT3.  Splinter Cell Chaos Theory has been my biggest troubles as I've wanted to simply re-write some of my music elements and implement that into the single player game to showcase my interactive music-composition abilities. 

Anyway, this tool has been invaluable for learning the layer systems they use in the games.
## Post #46
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-08T19:12:13+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

First, I am sorry to report that version 0.3 posted above has a bug in it. The bug only affects the decoding of interleaved streams. It is that some of the samples in the middle of the we getting dropped, so you would hear an occational pop or click. Here is the fixed version:


 DecUbiSnd-0.31.zip
Decode UBISOFT Audio, version 0.31 (229.08 KiB) Downloaded 111 times


OrangeC, I had a good look at those files from Beowulf you posted. I looked at every single one of them, and created a report of what I found. There were many different types of files in there. One of them was just information and contained no audio data. Four of them were files that could already be decoded by my program. Another two of them were just PCM. Now, for the ones that are not so easy to decode. Thirty-seven of them are pieces of interleaved streams, and 45 of them are pieces of simple streams. You can decode these in my program by adding the appropriate header to them, but that is a lot of hex editing. This is the time when I should be directing you to a format specification of these headers, but as far I know, there are none written. As I probably already wrote, I would like to add these formats to the wiki.

These pieces must go onto the end of other files. I looked at some files Kataah sent me, and these files indicate this even more. They were Ogg Vorbis, and these types of streams have some little tricks to them that are cool. Each page begins with 'OggS'. The first trick is each stream has a serial number that is stored in each page. Yep, it does exactly what is says. Second, each page also has a number indicating what page index it is. I looked at one file, and it had an page index of 7. That means that there must be seven packes before it (the first one is 0). This surely says that there must be more data (the beginning part) in another file. Unfortunately, I did not find any streams that matched up. It would help if I wrote a tool that searched for Ogg pages in every file in a directory and reported their serial numbers and page indices.

Mirrodin, thank you for your compliments. It was my pleasure. I would definitely be very happy to help you, and to make an encoder. Many games that UbiSoft publish don't even use Unreal Engine formats for audio, so you couldn't even edit the audio with its editing suite. You probably already know that Chaos Theory uses Ogg Vorbis for audio, which is pretty easy to encode with any modern audio editor. (If it isn't in yours try [Audacity](http://audacity.sourceforge.net/), free) Now the problem is fitting it into the data files. You would need to be able to modify the .SM0 file. I haven't focused my efforts on finding the format of the different .SM0 files, but I know the format used in SC1 and SC2. This format changes for almost every game. I was planning to writing a program to look inside the .SM0 files, and because you suggested, I'll probably add the ability to edit them as well.

Man that was a long post!
## Post #47
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-08T19:14:33+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Here is the full report on those Beowulf files.
[BeowulfReport.zip](https://xentaxbackup.github.io/file/1536_BeowulfReport.zip)
## Post #48
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-08T19:28:14+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Thank you very much, now about the ones that says: add a header what do i have to add?
## Post #49
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-08T19:52:36+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

That's the difficult part. For the simple streams there is a header, 48 bytes for mono or 68 bytes for stereo, which you tack on to the front, which basically works for every file. You can find this header at the beginning of the files that I said my program can decode. The interleaved streams are more difficult. That's why I say I would like to create some format specifications. I hope you can wait to decode these files, there is no easy way to explain it without some docs. I think I'll upload some templates of these headers sometime, to make things easier. Or, better yet, I'll make a tool that adds these headers automatically. I think I'm adding a feature to version 0.5 that would allow you to decode the simple pieces.

I hope that I have stressed enough that you first have to get rid of the usually 36-byte Beowulf header before any of the above is applicable.
## Post #50
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-08T19:59:08+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Ahh yep, know that.

anyway cant wait for the solutions, but i can be patient though.
## Post #51
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-08T20:29:19+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Zench
>
> 
Mirrodin, thank you for your compliments. It was my pleasure. I would definitely be very happy to help you, and to make an encoder. Many games that UbiSoft publish don't even use Unreal Engine formats for audio, so you couldn't even edit the audio with its editing suite. You probably already know that Chaos Theory uses Ogg Vorbis for audio, which is pretty easy to encode with any modern audio editor. (If it isn't in yours try Audacity, free) Now the problem is fitting it into the data files. You would need to be able to modify the .SM0 file. I haven't focused my efforts on finding the format of the different .SM0 files, but I know the format used in SC1 and SC2. This format changes for almost every game. I was planning to writing a program to look inside the .SM0 files, and because you suggested, I'll probably add the ability to edit them as well.

Yea I just meant implementing the audio in the games they can open the packages to place the sounds in a level etc...  But to be able to create my own audio packages and import them into the game so I don't have to overwrite the original data would make it a lot easier to create a music mod for a single player experience.  New sounds and new music = alternate experience.
## Post #52
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-09T00:15:52+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Mirrodin
>
> Yea I just meant implementing the audio in the games they can open the packages to place the sounds in a level etc...  But to be able to create my own audio packages and import them into the game so I don't have to overwrite the original data would make it a lot easier to create a music mod for a single player experience.  New sounds and new music = alternate experience.That would be really cool, but it would take a long time to make a program to do that. There is a lot of data to be manipultated, and far too many unknowns at this point (regarding the .SM0 files). Oh well.

> Reply from OrangeC
>
> anyway cant wait for the solutions, but i can be patient though.Maybe you don't have to wait... I finished it rather quickly. Here it is. I didn't spend much time testing it, though. This is how to use it:

```
AddUbiHeader InputFile OutputFile Channels [Offset]
```

Offset is optional, if you don't specify it it assumes 36 (should work for you OrangeC).

Edit: Attachment removed. I found a bug. Fixed version posted below.
## Post #53
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-09T01:57:10+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Its taking quite a bit just to write the header. is it suppose to do that?
## Post #54
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-09T06:57:10+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Okay i got how to add the headers to the layers files, but it won't add headers to the simple streams, the program gets stuck.

And i did what you said by adding 68 bytes at the beginning but that doesn't work, i even deleted the original header and added the byttes but it still won't decode.
## Post #55
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-09T15:28:27+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Okay i got how to add the headers to the layers files, but it won't add headers to the simple streams, the program gets stuck.Oops... just wait a little while, I'll fix it.

> Reply from OrangeC
>
> And i did what you said by adding 68 bytes at the beginning but that doesn't work, i even deleted the original header and added the byttes but it still won't decode.The first byte of the header needs to be 05 and the byte at offset 14 needs to be 0A. The rest of the bytes should be zero. It should be easier with my tool, though.
## Post #56
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-09T15:30:34+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

ahh okay, i shall wait for your tool.
## Post #57
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-09T18:08:35+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Okay, here's the fixed version. This time I did test it.
[AddUbiHeaderTool.zip](https://xentaxbackup.github.io/file/1539_AddUbiHeaderTool.zip)
## Post #58
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-09T20:26:07+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

It works!!

Thanks.

I also have assassins creed and that uses ubisoft with oggvorbis. i decoded the file with your program but it leaves the songs stuttering.

I will send you the file after im done with beowulf but hopefullly your 0.5 can do ac.
## Post #59
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-09T21:14:08+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Ubisoft uses FMOD.  I know how to use the designer and everything to create the banks but the games won't read the original FMOD format.  Crysis has proven way easier as they use FMOD's original format without any alterations.  This add-header tool is really useful though thank you!
## Post #60
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-09T22:37:56+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

To everyone who has had success with my tool: could you post a list which games you got to work, and some other information about it? We would like to add these formats to the wiki. Here are mine:
Splinter Cell - *.SS0; PC (except Music_*.SS0)
Splinter Cell: Pandora Tomorrow - *.SS0, *.LS0; PC
Splinter Cell: Chaos Theory - *.SS0, *.LS0; PC
Splinter Cell: Double Agent - *.SS0, *.LS0; PC

Those who posted files that I looked at: I'll let you specify exactly what you found.

Also, we need to come up with some names for the formats. This is what I have thought of:
UbiSoft Old Simple Stream (version 3)
UbiSoft Simple Stream (version 5)
UbiSoft Old Interleaved Stream (version 2)
UbiSoft Interleaved Stream (version 8 )
## Post #61
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-10T01:22:31+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Same, I've mostly been trying to mod sounds and music for the Splinter Cell series.
I've been successful in extracting from Splinter Cell, Pandora Tomorrow, Chaos Theory, and Double Agent.
## Post #62
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2008-06-10T16:08:42+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I'm also going to need the actual formats for these files, if any of you could write them up for me...
## Post #63
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-10T16:14:02+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Ive gotten Red steel and beowulf to work.
## Post #64
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-10T19:29:55+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Here is the format of the simple streams, together, but you might want to separate them:

```

Header:
byte {1} - Version number (3 or 5)
byte {3} - Unknown
byte {4} - Unknown
uint32 {4} - Unknown
uint16 {2} - Unknown
uint16 {2} - Number of extra uncompressed samples before the data (always 10)
int16 {2} - First left sample for decompression
byte {1} - First left index for decompression
byte {1} - Unknown
int16 {2} - First right sample for decompression
byte {1} - First right index for decompression
byte {1} - Unknown
byte {4} - Unknown

Extra Uncompressed Samples:
if the sound is mono:
int16 {Number of extra uncompressed samples * 2} - Uncompressed samples

if the sound is stereo:
int16 {Number of extra uncompressed samples * 4} - Uncompressed samples

Data:
 byte {?} - Compressed data

```
## Post #65
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-10T22:26:47+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

And here is the format of the old interleaved streams:

```

uint32 {4} - Signature (2)
uint32 {4} - Number of Layers (always 3)
uint32 {4} - Total File Size
uint32 {4} - Unknown (always 20)
uint32 {4} - Unknown (always 1104)
uint32 {4} - Average Block Size (always 361)

For Each Block: {
	uint32 {4} - Block Index (begins at 1)
	uint32 {4} - Unknown (always 20)
	
	For Each Layer (Chunk): {
		uint32 {4} - Layer Chunk Size
	}
	
	For Each Layer (Chunk): {
		uint32 {Layer Chunk Size} - Chunk of an Encapsulated UbiSoft Old Simple Stream
	}
}
```

And the new interleaved streams:

```

uint16 {2} - Signature (8)
uint16 {2} - Unknown
uint32 {4} - Unknown
uint32 {4} - Number of Layers
uint32 {4} - Number of Blocks
uint32 {4} - Number of Bytes after This to the Headers
uint32 {4} - The Sum of (Number of Layers * 4) Plus the Header Lengths
uint32 {4} - Average Sum of Chunk Data Lengths

For Each Layer: {
	uint32 {4} - Layer Header Size
}

For Each Layer: {
	uint32 {Layer Header Size} - Header of an Encapsulated Stream (PCM, UbiSoft Simple Stream, Ogg Vorbis)
}

For Each Block: {
	uint32 {4} - Signature (3)
	uint32 {4} - Number of bytes from the start of this block to the next block, 0 if no more blocks
	
	For Each Layer (Chunk): {
		uint32 {4} - Layer Chunk Size
	}
	
	For Each Layer (Chunk): {
		uint32 {Layer Chunk Size} - Chunk of an Encapsulated Stream (PCM, UbiSoft Simple Stream, Ogg Vorbis)
	}
}
```

I realize that these formats are quite complicated, and I did not explain them very well, so here are some examples: (just the first few blocks)
[Examples.zip](https://xentaxbackup.github.io/file/1541_Examples.zip)
## Post #66
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-12T16:17:08+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Hey zerich have you looked into assassins creed yet?
## Post #67
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-15T01:04:24+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Yes, Kataah sent me some files.
## Post #68
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-15T01:13:17+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Ahh cool, yes he told me its not easy to extract.
## Post #69
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-17T02:17:55+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Update on what's coming for version 0.5:
There will be some fixes, and a few new features. Nothing phenomenal, though. Most notably are: automatic mono/stereo detection (I always hated having to specify that), and decompression of raw stream of UbiSoft compressed audio (useful for tinkering). I could add the ability to mix the layers together, if anyone would find that useful. Although not all layers in interleaved streams are meant to be mixed.
## Post #70
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-17T10:48:14+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Yes cant wait.
## Post #71
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-17T23:49:48+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I think for most of us it would be best not to auto-mix the layers.
## Post #72
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-20T15:47:46+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

It would work the same as before, but you could specify multiple layers, separated by commas (-l 2,3) and it would mix them. You could also specify all (-l all) to decode all the layers (up to 16). Important note about layers: in version 0.5 the layer numbers will start with 1, not 0 like before.

While I was experimenting with Pandora Tomorrow (modifying the sound files to see what would happen in game), I actually found the flag that indicates whether the sound is mono or stereo. I should have noticed this before. This means that the format specification above should be changed. I also found out that the value of the unknowns doesn't really matter; the sound still plays as it's supposed to. I have not tried any interleaved streams.
## Post #73
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-20T18:06:25+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I see.  Have you worked at all with FMOD?  I've been looking at the similarities between your posts with this tool to decode and FMOD's standard bank files and how things are allocated.  I do know that Ubisoft does use FMOD tool but modifies the code perhaps?  I've only used the designer and not the API because i'm not a programmer .
## Post #74
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-20T18:50:33+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Mirrodin
>
> I see.  Have you worked at all with FMOD?  I've been looking at the similarities between your posts with this tool to decode and FMOD's standard bank files and how things are allocated.  I do know that Ubisoft does use FMOD tool but modifies the code perhaps?  I've only used the designer and not the API because i'm not a programmer .I downloaded the designer and looked at it, but the things that I have been working with are more low-level than it (I didn't see anything about interleaved streams, though). In the Splinter Cell series UbiSoft doesn't use the FMOD library, but instead Dare Audio. There are some UbiSoft games that use the FMOD library, though. Whether they use the FMOD designer and then convert it to Dare Audio or not I don't know. I could look at the API too.
## Post #75
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-20T19:12:43+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

My guess would have been that Ubisoft has been using the API tools to program, I know with Crysis they did absolutely no modification to Fmod's core and use it to it's fullest extent.  Ubisoft games have been compiling proprietary format files but use FMOD somewhere in the pipeline.  Since Fmod supports the design of "3d" playback it would have been the API that they were using to develop the audio engine.
## Post #76
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-20T20:19:35+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

So when can we expect ver. 0.5?
## Post #77
- Username: xkLOJ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 21, 2008 5:52 pm
- Post datetime: 2008-06-21T15:02:43+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Hi, do you know how extracting "Infiltration" themes (SCDA) and where they are?
## Post #78
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-21T18:20:03+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> So when can we expect ver. 0.5?Right now! I uploaded it [here](http://files.openomy.com/public/Zench/DecUbiSnd-0.5.zip), but I just didn't find the time to write up something good.

> Reply from xkLOJ
>
> Hi, do you know how extracting "Infiltration" themes (SCDA) and where they are?I haven't done a lot of extracting SCDA, but aren't the infiltration themes in the interleaved streams? Please correct me if I'm wrong.

I'm working on a GUI version of DecUbiSnd that I think you're all going to like. I'm also still thinking about that encoder.
## Post #79
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-21T20:23:25+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

A GUI would be sweet.

Three files i came across with red steel's SS7 varaint that i cannot decode, i tried all different decoding versions used your header utility, and downloaded the latest 0.5 version of your program and i still get scrambled output. maybe im doing something wrong with the offsets or something, and im not sure but it could be interleaved layer?

[http://www.megaupload.com/?d=M0UPZ78C](http://www.megaupload.com/?d=M0UPZ78C)
## Post #80
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-21T23:53:44+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Sounds great! A gui will definitely help very much, I will even try to write some tutorials based on the GUI asap for other users to get the most from the app.
## Post #81
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-23T18:07:16+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from xkLOJ
>
> Hi, do you know how extracting "Infiltration" themes (SCDA) and where they are?The GUI version will make it easy to extract; it will show you all the sounds/music from a directory.

Here is a screen shot of the GUI version. Sorry for the red buttons, it is just a reminder to me that I haven't completely implemented that functionality yet. There will be no red buttons in the final release. Please post any feature requests or things you would like changed. Also ask about things that aren't self explanatory.



Screen Shot of DecUbiSndGui DecUbiSndGui_ScreenShot.png (33.27 KiB) Viewed 781 times

There is one thing that I must explain. The layers column (on the right list) is not the number of layers, but which layer will be decoded if that item is selected. This is so that you can decode the layers separately. About the two output options: 'Concatenated' strings all the selected items together and saves it in one wave file, but 'Separate' saves them all in separate wave files, one for each selected item.
## Post #82
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-23T18:16:40+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Sorry to be a nag but haver you looked at the files that i posted?

SWEET GUI BTW.
## Post #83
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-23T18:27:52+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Sorry to be a nag but haver you looked at the files that i posted?Oh, I'm sorry. I didn't get around to it, and I might not for a while.
## Post #84
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-23T18:31:59+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Thats okay i might look at them with the GUI.
## Post #85
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-23T21:52:46+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Very nice!  I especially love the preview feature you've implemented it looks like.  Being able to play a stream without having to extract it is very useful!
## Post #86
- Username: xkLOJ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 21, 2008 5:52 pm
- Post datetime: 2008-06-24T07:04:51+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

to Zench
Excellent work, the GUI look`s very usable. 

P.S. How about old Ubi game "XIII", I can upload some file, probably with music.
P.P.S. Sorry for my english.
## Post #87
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-26T02:31:14+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Three files i came across with red steel's SS7 varaint that i cannot decode, i tried all different decoding versions used your header utility, and downloaded the latest 0.5 version of your program and i still get scrambled output. maybe im doing something wrong with the offsets or something, and im not sure but it could be interleaved layer?

http://www.megaupload.com/?d=M0UPZ78CIt's a good thing I looked at those files. Indeed, they are interleaved streams, just a little bit different. These files are big-endian, and the others are little-endian. That is the only difference. Below is a new version of DecUbiSnd that can decode them.

Also included in the new version is a fixed memory leak (just a small one), and a layer extract feature by request of Kataah. The layer extract feature (-L, --layer-extract) works on interleaved streams; it extracts a layer without decoding it. This is particularly useful in streams that use Ogg Vorbis, so that you can just play the Ogg Vorbis file and don't need to re-encode the wave file.

About when I will be done with the GUI version: I am almost finished, it will probably be June 26 or 27.

> Reply from Mirrodin
>
> Sounds great! A gui will definitely help very much, I will even try to write some tutorials based on the GUI asap for other users to get the most from the app.If you would write some tutorials, I would like to include them in the program, if that's okay.

> Reply from xkLOJ
>
> P.S. How about old Ubi game "XIII", I can upload some file, probably with music.Sure, go ahead.

One more thing: Has anyone been able to decode sounds/music from Prince of Persia with DecUbiSnd?
[DecUbiSnd-0.51.zip](https://xentaxbackup.github.io/file/1560_DecUbiSnd-0.51.zip)
## Post #88
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-06-26T06:55:10+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Not a problem with me, it's your program anyway   After I play around with the gui for a bit and try out various packed files I may write a series that's either game specific, or just function specific of the GUI.  The idea of the tutorials will be to learn the easiest way to get audio from the packaged files without having to do too much research.  The extract layer function you were talking about also sounds very useful as you said: for extracting ogg without having to go through the process of rendering a wave file from it.
## Post #89
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-26T11:33:04+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Once again you saved the day!!

Its interesting how many ubisoft formats there are in one game, its obvious they don't want anybody ripping there music, but then again they never put out a soundtrack to there games.
## Post #90
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-26T18:40:10+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Here is the first alpha GUI version. It has some bugs, I think. They are mostly in the areas of scanning and playback. I tested it with SC1, PT, and CT and it worked fine, though. The executable was a bit large so I packed it with [UPX](http://upx.sourceforge.net/). I didn't include the source code with this one (it uses [wxWidgets](http://www.wxwidgets.org/)), but I can upload a separate package if anyone wants. I await your comments.
DecUbiSndGui alpha 1

One other note: I'm going on a trip from June 30 to July 8 so I won't be able to help you then.
## Post #91
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-27T01:00:34+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Im testing it on Double agent and so far its working pretty good.
## Post #92
- Username: xkLOJ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 21, 2008 5:52 pm
- Post datetime: 2008-06-27T07:45:28+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

The contents of this post was deleted because of possible forum rules violation.
## Post #93
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-06-28T22:15:52+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

The contents of this post was deleted because of possible forum rules violation.
## Post #94
- Username: xkLOJ
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Jun 21, 2008 5:52 pm
- Post datetime: 2008-06-29T08:43:40+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Zench
>
> One more thing: Has anyone been able to decode sounds/music from Prince of Persia with DecUbiSnd? I testing DecUbiSndGui alpha 1 on Prince of Persia: Warrior Within & The Two Thrones -> it seems everything is all right, sounds\music is unpacked without problems. The unique difficulty - program not correctly determines sample rate, in game - 22050, in program - 48000.
## Post #95
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-30T00:53:52+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Hmm im having also a bit of trouble decoding sounds from the original graw for 360. some are raw but i think some might be interleaved audio.
## Post #96
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-09T03:09:35+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from xkLOJ
>
> The unique difficulty - program not correctly determines sample rate, in game - 22050, in program - 48000.Yes -- unfortunately the sample rate cannot be determined automatically. That is why there is the Set Info button where you can change it. You can find the sample rate in the .SB0 or .SM0 files, but my program doesn't support them because they change for every game and I wanted to support as many games as possible. I am thinking about making something for these, but in the far future.

> Reply from OrangeC
>
> Hmm im having also a bit of trouble decoding sounds from the original graw for 360. some are raw but i think some might be interleaved audio.As always, post some pieces and I'll have a look at them.
## Post #97
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-07-09T14:45:30+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

[http://www.megaupload.com/?d=G4VDFWJD](http://www.megaupload.com/?d=G4VDFWJD)
## Post #98
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-11T16:12:06+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> http://www.megaupload.com/?d=G4VDFWJDIt is another variant of the interleaved format, in big-endian. Here's an updated version of DecUbiSnd:
[DecUbiSnd-0.52.zip](https://xentaxbackup.github.io/file/1582_DecUbiSnd-0.52.zip)
## Post #99
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-07-11T16:23:04+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Thanks

Was wondering if you were gonna update the GUI with the updated format.
## Post #100
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-11T17:36:12+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Was wondering if you were gonna update the GUI with the updated format.[Here](http://files.openomy.com/public/Zench/DecUbiSndGui-alpha1.zip) is the updated GUI. Notice that the URL is the same as before.
## Post #101
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-07-15T01:05:07+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I have discovered a bug when extracting from SC double agent. it says: unhandled exception has occured and it cant complete the extraction, scanning and playing is fine though.
## Post #102
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-15T21:52:40+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> I have discovered a bug when extracting from SC double agent. it says: unhandled exception has occured and it cant complete the extraction, scanning and playing is fine though.Does it do that every time?
## Post #103
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-07-15T23:26:52+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

yes.
## Post #104
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-18T20:35:08+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Can you give me more information about the problem? It would help me if I knew exactly what you clicked on which made be problem occur.
## Post #105
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-07-18T21:15:53+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well when i scanned the streams inside the ss0 file it showed a set of interleaved streams and simple streams, when i tried to extract a first set of streams mixed or unmixed i cliked on: seperate, then tried to output the file, it then gives me this an unhandled exception has occured, it teels me to ignore, retry or cancle, i retry and the program just closes.

When i extract other sets of streams simpel or interleaved then i get no error, its just for specific streams inside the file.
## Post #106
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-22T16:13:45+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

The contents of this post was deleted because of possible forum rules violation.
## Post #107
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-07-26T22:26:50+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well the SS0 is 1gb for double agent PC so its too big to post here.

But i had to extract all tracks inside of it, it only happens when i extract tracks in a batch or one by one in the file, And it does only on some files, not all.

So if i want to extract files i have to select everything and it will extract them with no errors, weird.
## Post #108
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-07-27T23:04:36+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Well the SS0 is 1gb for double agent PC so its too big to post here.

But i had to extract all tracks inside of it, it only happens when i extract tracks in a batch or one by one in the file, And it does only on some files, not all.

So if i want to extract files i have to select everything and it will extract them with no errors, weird.Well, thanks for the infomation. I'll try harder this time.
## Post #109
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-03T04:18:54+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Thanks very much, Zench, for your work decoding UbiSoft's sound formats. I've been looking at Myst III for PlayStation 2, another UbiSoft game, and your info has been invaluable.

Unlike the Mac/PC version of Myst III, where all sounds and music are in individual WAV and MP3 files, the PS2 version appears to have everything in a pair of files: MAPS.SM1 (14 MB) and STRM.SM1 (433 MB).

Your DecUbiSndGui application figured out that STRM.SM1 contains 38 simple streams of the version 3 variety, all of the music in the game. I know that part of MAPS.SM1 is directory information. In particular, I've figured out how MAPS.SM1 describes the 38 streams in STRM.SM1. However, MAPS.SM1 is much too big to be only directory info. I'm sure that it must also contain audio data for the game's non-musical sounds. If so, it's in a format not recognized by me or by DecUbiSndGui.

If anyone is interested in looking at an example of a piece of MAPS.SM1 that I believe is audio data, here's the 8 KB chunk between a couple of the dozen or so directories scattered throughout MAPS.SM1:

[http://homepage.mac.com/rshayter/MAPS-000bc800.bin.zip](http://homepage.mac.com/rshayter/MAPS-000bc800.bin.zip)

Any suggestions on how to make sense of this data would be much appreciated!

Ron
## Post #110
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-03T21:41:29+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from RonHayter
>
> Thanks very much, Zench, for your work decoding UbiSoft's sound formats. I've been looking at Myst III for PlayStation 2, another UbiSoft game, and your info has been invaluable.I am always glad to help other people. Thank you for your feedback.

> Reply from RonHayter
>
> Your DecUbiSndGui application figured out that STRM.SM1 contains 38 simple streams of the version 3 variety, all of the music in the game. I know that part of MAPS.SM1 is directory information. In particular, I've figured out how MAPS.SM1 describes the 38 streams in STRM.SM1. However, MAPS.SM1 is much too big to be only directory info. I'm sure that it must also contain audio data for the game's non-musical sounds. If so, it's in a format not recognized by me or by DecUbiSndGui.

If anyone is interested in looking at an example of a piece of MAPS.SM1 that I believe is audio data, here's the 8 KB chunk between a couple of the dozen or so directories scattered throughout MAPS.SM1:

http://homepage.mac.com/rshayter/MAPS-000bc800.bin.zipYes, *.SM? files do contain audio (typically sound effects) as well as directory information. I should write a program that actually parses the directory information, but it varies from game to game. The segment you posted is not any UbiSoft audio format which I've seen. Keep in mind UbiSoft uses raw audio and platform specific codecs in their audio files (for example [XMA](http://en.wikipedia.org/wiki/XMA_%28audio_format%29) on the Xbox platform). I am not very familiar with Playstation audio, though. Ahh... yes! I just tried this file in PSound (I can't remember where I found it) and it worked.

If you are able post the entire MAPS.SM1 file, I would very much like to examine it.
## Post #111
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-04T05:59:22+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Zench
>
> Keep in mind UbiSoft uses raw audio and platform specific codecs in their audio files (for example XMA on the Xbox platform). I am not very familiar with Playstation audio, though. Ahh... yes! I just tried this file in PSound (I can't remember where I found it) and it worked.
Brilliant! You're absolutely right -- PSound found 280 sounds in MAPS.SM1. Thanks for the help! Next step: google for a description of the PS2 sound format.   

Here is the complete [MAPS.SM1](http://homepage.mac.com/rshayter/MAPS.SM1.zip). My understanding of the directory structures is incomplete but I can tell you what I know, if you like. I don't have time to do so right now, though. Maybe tomorrow...

Ron
## Post #112
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-04T22:35:18+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Here's my interpretation of the directory information inside MAPS.SM1. All values are little-endian.

```
uint32 {4} - Unknown
uint32 {4} - Offset to root directory
uint32 {4} - Number of root directory entries, each 48 bytes long

Root directory entries:
{
	uint32 {4} - Unknown (always 0)
	uint32 {4} - Unknown (always 0)
	uint32 {4} - Offset to subdirectory
	uint32 {4} - Length of subdirectory
	char {32} - Subdirectory name, zero-padded
}

Subdirectory:
uint32 {4} - Unknown (always 0)
uint32 {4} - Offset to unknown table X (always 0x0024)
uint32 {4} - Number of X entries, each 52 bytes long
uint32 {4} - Offset to streamed sound table
uint32 {4} - Number of streamed sound entries, each 112 bytes long
uint32 {4} - Offset to unknown table Y
uint32 {4} - Number of Y entries? (usually 1)
uint32 {4} - Offset to unknown table Z
uint32 {4} - Number of Z entries

Streamed sound entries (apparently valid only if the length field at offset 0x0038 is non-zero):
{
	uint16 {2} - Sound ID, minor component?
	uint16 {2} - Sound ID, major component?
	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown

	uint32 {4} - Unknown
	uint32 {4} - Offset of version 3 simple stream in STRM.SM1, only if length > 0
	uint32 {4} - Unknown
	uint32 {4} - Unknown

	uint32 {4} - Unknown
	uint32 {4} - Number of channels (always 2 when length > 0)
	uint32 {4} - Sample rate (always 44,100 when length > 0)
	uint32 {4} - Unknown

	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Length of version 3 simple stream in STRM.SM1
	uint32 {4} - Unknown

	uint32 {4} - Unknown
	char {8} - File containing streamed sound (always "STRM.SM1" when length > 0)
	uint32 {4} - Unknown

	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown

	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown
}

Following almost every subdirectory and its tables are PS2-native sequenced sounds.

```


Unknowns:

Purpose and structure of tables X, Y, and Z.
Purpose of many of the fields in a streamed sound entry.
Purpose of the many streamed sound entries where length == 0.
How sequenced sounds are described in a subdirectory.


I hope this is of use to someone.   

Ron
## Post #113
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-08-05T04:14:47+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Arg! finally able to log back into xentax!  (changed emails took forever to get reactivated).
## Post #114
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-05T16:41:32+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from RonHayter
>
> Here's my interpretation of the directory information inside MAPS.SM1. All values are little-endian.Nice work! The general structure is very similar to the other *.SM? files I've seen, except that this one has lots of padding an the other ones don't. That's probably just a Playstation thing, though. I should post the format of the Splinter Cell 1 PC .SM0 file so you can see how similar they are. I should also add a bunch of UbiSoft audio formats to the wiki. I already started adding a few but I didn't finish. If you want to add this format and know how, go ahead; otherwise I can do it.

> Reply from Mirrodin
>
> Arg! finally able to log back into xentax!  (changed emails took forever to get reactivated).We're glad to have you back!
## Post #115
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-06T06:00:53+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Zench
>
> I should post the format of the Splinter Cell 1 PC .SM0 file so you can see how similar they are.Please do. There's no hurry, though. I'm curious but I don't have that game.

> Reply from Zench
>
> If you want to add this format and know how, go ahead; otherwise I can do it.If you're sure you don't mind, I'd appreciate that.

Ron
## Post #116
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-09T20:50:45+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Here is the .SM0 format from Splinter Cell 1 and 2:

```
uint16 {2} - Unknown
uint32 {4} - Root directory offset
uint32 {4} - Directory count

For each directory {
	uint32 {4} - Unknown (mostly null)
	uint32 {4} - Unknown (mostly null)
	uint32 {4} - Directory offset
	uint32 {4} - Directory size
	char {32} - Directory name
}

At the directory offset {
	uint32 {4} - Unknown (always null)
	uint32 {4} - Offset to directory 1
	uint32 {4} - Number of directory 1 entries
	uint32 {4} - Offset to directory 2
	uint32 {4} - Number of directory 2 entries
	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown
	uint32 {4} - Unknown

	For each entry in directory 1 {
		uint32 {4} - Resource ID
		byte {84} - Unknown
	}
	
	For each entry in directory 2 (each entry is 128 bytes){
		uint32 {4} - Resource ID
		uint32 {4} - Type (1 - 15)
		uint32 {4} - Unknown (always 1)
		
		If Type is 1 {
			uint32 {4} - Size
			uint32 {4} - Unknown (always 0)
			uint32 {4} - External Offset (0 if the data is in MAPS.SM0)
			uint32 {4} - Unknown
			uint32 {4} - Unknown (always 1)
			uint32 {4} - Unknown (0 or 1)
			uint32 {4} - Unknown (always 1)
			uint32 {4} - Location (0 for internal, 1 for external)
			uint32 {4} - Wierd Flag
			uint32 {4} - Size
			uint32 {4} - Size/2
			If Wierd Flag is 1 {
				uint32 {4} - Size
				uint32 {4} - Size/2
			} Else {
				uint32 {4} - null
				uint32 {4} - null
			}
			uint32 {4} - Bitrate
			uint32 {4} - Sample rate
			uint16 {2} - Bits
			uint16 {2} - Channels
			uint32 {4} - Type (1 is raw PCM, 2 is SC1-type audio, 3?, 4 is Old Simple Stream)
			char {40} - Filename (external if location is 1)
			uint32 {4} - Unknown (1)
			uint32 {4} - Unknown (padding?)
		}
		If type is 13 {
			uint32 {4} - Size
			uint32 {4} - Unknown
			uint32 {4} - External Offset
			uint32 {4} - null
			uint32 {4} - null
			uint32 {4} - Unknown
			uint32 {4} - Unknown (3)
			uint32 {4} - null
			uint32 {4} - null
			uint32 {4} - Unknown (1)
			char {40} - External Filename
			uint32 {4} - Unknown
			uint32 {4} - null
			uint32 {4} - Size
			uint32 {4} - null
			uint32 {4} - null
			uint32 {4} - Unknown (0)
			uint32 {4} - Unknown (0)
			uint32 {4} - Unknown (1)
			uint32 {4} - Unknown (padding?)
		}
		If type is anything else {
			byte {116} - Unknown
		}
	}
}

```
## Post #117
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-08-10T16:26:50+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Hey zerichs will we see another version of the GUI?
## Post #118
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-10T19:17:49+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Hey zerichs will we see another version of the GUI?It's likely. I've been thinking about adding a few new features (like layer extract). I was also thinking about how I can get it to read .SM? files, if possible. I'm not sure if I fixed the bug you mentioned yet. It isn't high priority, though.
## Post #119
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-08-10T22:05:38+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Sweet!  I am still promising tutorials of the program.  I'm still breaking down the tutorial structure so it may be a while before I post anything,  But i'll be sure to link and give credit to all who are involved.  If anyone has any suggestions on whether they'd like to see a game-specific tutorial series, or a general tutorial covering specific functions of the program (regardless of game), please feel free to comment!  I haven't actually started writing them yet. but I will asap when I get some feedback from you guys!
## Post #120
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-08-11T20:13:47+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Zench
>
> Here is the .SM0 format from Splinter Cell 1 and 2:
You're right, there are many similarities with the format of MAPS.SM1 from Myst III for PS2. Thanks.

Do you have any idea how the offsets to the sounds that are inside MAPS.SM0 are determined? I still haven't figured that out for Myst III.

Ron
## Post #121
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-14T20:29:25+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from RonHayter
>
> Do you have any idea how the offsets to the sounds that are inside MAPS.SM0 are determined? I still haven't figured that out for Myst III.No, I haven't yet. But I tried this and it works some of the time: take the offset of the end of the directory, which is where the audio data is supposed to start, and add the size of each internal sound (there is a flag to indicate whether or not the sound is here) in progression taking into account the padding (4 in my case). I wrote a small Lua script to parse the file. This worked with the sound effects (MAPS.SM0), but did not work with the voices (ENGLISH\MAPS.LM0), or at least there was some problem which I still need to figure out. I will do more experimentation with this.

About the GUI: I'm adding a feature that displays the currently playing segment in bold. If you have any feature requests I would like to hear them.

> Reply from Mirrodin
>
> Sweet! I am still promising tutorials of the program. I'm still breaking down the tutorial structure so it may be a while before I post anything, But i'll be sure to link and give credit to all who are involved. If anyone has any suggestions on whether they'd like to see a game-specific tutorial series, or a general tutorial covering specific functions of the program (regardless of game), please feel free to comment! I haven't actually started writing them yet. but I will asap when I get some feedback from you guys!I would at least like to see a tutorial that describes the general use of my program, because it is a little bit complicated. And series- or game-specific tutorials would be awesome too!
## Post #122
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-08-14T21:20:29+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Nice to hear from you zerich.

As for feature requests, could there be a feature for us to mix arrange layers but in our own way, not just mix them, because in Double agent each infiltration track has a bunch of layers and thats for every instrument segment of the track, and we have to build the track ourselves, i was wondering if a feature like that could be implemented.
## Post #123
- Username: Mirrodin
- Rank: advanced
- Number of posts: 71
- Joined date: Wed Jun 01, 2005 2:36 am
- Post datetime: 2008-08-14T21:39:18+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Well for the sake of simplicity i'd rather keep each individual layer as a separate file if it's packaged that way.  Most people who want to mix would use an external program anyway like Acid, Sonar, Reaper, Pro Tools etc...
## Post #124
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-08-16T20:51:25+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

I probably would rather keep it simple, unless information on how to mix it was found in the file. Thanks for the suggestion anyway.
## Post #125
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-11T18:18:21+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Can SCDA for PS2 be researched? it had a bit different music than in the PC version and i remember kataah ripped it but it had bad quality, im wondering if you zerich can add support for it.

Here is a stream sample that i extracted.

[http://www.megaupload.com/?d=ZLVY4HJX](http://www.megaupload.com/?d=ZLVY4HJX)
## Post #126
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-11T21:50:18+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from OrangeC
>
> Can SCDA for PS2 be researched? it had a bit different music than in the PC version and i remember kataah ripped it but it had bad quality, im wondering if you zerich can add support for it.

Here is a stream sample that i extracted.

http://www.megaupload.com/?d=ZLVY4HJXNikson was wondering about that in a PM, but I ran out of time... I'll have a look at your sample (and probably Nikson's again).

Sorry about the long wait for the next version of the GUI; I have been especially busy in the past few weeks, so I'll get to it when I can.
## Post #127
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-11T22:54:10+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

That is okay zerich. take your time.
## Post #128
- Username: Kataah
- Rank: beginner
- Number of posts: 39
- Joined date: Fri May 25, 2007 2:21 am
- Post datetime: 2008-09-13T14:58:51+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

The GUI works with the Wii version of SC 4, OrangeC 
Yeah quality is bad, the problem is the sample rate which is 28000hz or 29000hz. I hoped the Wii version would use a better quality but no, it is the same. Take a look 

The ps2 version has two different codecs. For the music voxware and for the sound fx maybe for a few other tracks too ps2 adpcm.
## Post #129
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-13T15:11:17+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Thanks kataah will check the wii version.
## Post #130
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2008-09-13T19:18:22+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

> Reply from Kataah
>
> The ps2 version has two different codecs. For the music voxware and for the sound fx maybe for a few other tracks too ps2 adpcm.About the PS2 version: the file you sent, OrangeC, was missing a bit of the header (maybe 50 bytes). So I looked in Nikson's files and found the same thing. It is another variant. I'm sorry Nikson for not noticing this sooner. I got some things done on DecUbiSndGui, so I think I'll release another version now.
## Post #131
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-13T20:09:21+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

The wii version i already ripped. its the same music anyway.  

And cant wait for your gui rls.
## Post #132
- Username: wuixntx
- Rank: beginner
- Number of posts: 28
- Joined date: Sat Nov 14, 2009 10:25 am
- Post datetime: 2010-11-28T09:21:30+00:00
- Post Title: Re: Splinter Cell 2 .SS0 Music

Splinter Cell 1, 2, 3.

I've googled many times how can to rip the sound files from these games.
And the method maybe not yet. Can any?

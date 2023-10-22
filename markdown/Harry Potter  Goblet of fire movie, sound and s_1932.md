## Post #1
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-01T19:37:49+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-01T21:04:15+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

Okay i downloaded the 2 files:

The "HP-GOF, extracted from SPEECH.BIG.zip" it's Electronicsa Arts sound, look the header  
"SCHl$   PT eÃ½â‚¬â€¦{xâ€š Å’Ã¿  SCCl   o   SCDlL  "

Can be reconverted

The "HP-GOF, extractedfrom MOVIES.BIG.zip" it's 3 files, okay
"SCHl0   GSTR    
this it's trhe header of the file.asf, note, the exa, asf, mus, etc etc are a electronic arts sound format

You need a reconversor, to easound to wav and viceversa

The file .mpc i dont' know but it's really compressable

okay the resume:

The files: cutscene_TW2.sdt  and AVea.asf are the same codec of electronic arts sound
## Post #3
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-01T21:16:27+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

wow, that's great, thnx! that was fast 
but how can i find that converter? is there such a program? 

and does the *.mpc got anything to do with *.mpg files?
## Post #4
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-01T21:30:54+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

Sorry i forgott the attachment
yeps here the converter:
[http://rapidshare.de/files/21975849/sx.rar.html](http://rapidshare.de/files/21975849/sx.rar.html)
Enjoy 

> and does the *.mpc got anything to do with *.mpg files
the example dont' looks this, maybe i'm wrong
## Post #5
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-01T22:00:09+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

thanks an, this is great !!!

but which option should i be using? -pcstream ? or do i have to figure it out from the files header?
## Post #6
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-01T22:22:55+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

Okay:
look the file: cutscene_TW2.sdt it's pcstream

```
SCHl$   PT
```
 

the file AVea.asf it's Gstream:

```
SCHl0   GSTR
```
 You see the GSTR header?
## Post #7
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-01T22:30:47+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

yeah man! I sure do see it! cool, thnx, i'll give it a try now, if i still had probs, i'll leave a message for further help requests.

and thanx very much for sparing your time, to you and the forum.
## Post #8
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-02T10:36:28+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

I dunno why i cant play the asf files, both the files i extracted from the .BIG files, and the files which i convert from a wav to asf with the sx.exe !!! I have already downloaded the WMA v9.0 runtime SDK, and already have the Windows Media Player v10. 

What am i doing wrong? Are you able to read the ASF files?

BTW, when i try to play it with Awave Studio v9.5 (unregistered) it gimes me the message that says: "The file is 'DRM protected' and you are not allowed to convert it!"
## Post #9
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-02T13:07:26+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

there's something else, I used sx.exe to convert wav->asf and to achieve the header which we found in the extracted files, I tried severeal options. For the file cutscene_TW2.sdt it's ps2stream with the following header:

```
SCHl$   PT
```

But for the AVea.asf, i didn't find any header matching this one.
The options I used and the headers resulting them are as follows:
-sndstream :

```
SCHl$   GSTR
```

-gcstream :

```
SCHl    PT eÂ²
```

-macstream:

```
SCHl    PT eÂ²
```

-pcstream:

```
SCHl$   PT eÂ²
```

-ps2stream:

```
SCHl$   PT eÂ²
```

-pspstream:

```
SCHl    PT eÂ²
```

-xboxstream:

```
SCHl    PT eÂ²
```

-xenonstream:

```
SCHl    PT eÂ²
```


There are some characters that can't be pasted here, but some of these headers have slight differences from eachother. Still as you can see, none of them is the header for the AVea.asf file which is:

```
SCHl0   GSTR
```


Now what should i do?
## Post #10
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-02T13:55:41+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

Easy 

To wav

```
sx -wave sound.asf -=test.wav
```


To asf (gstream)

```
sx -sndstream test.wav -=test.asf
```


For pcstream: 

```
sx -pcstream test.wav -=test.asf
```


Note: you can play with the values of every parameter, to compress more the audio, don't worry sure the game play the audio.

Enjoy!
## Post #11
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-02T14:09:36+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

good, so i need to burn back the game and try it on the consule. well, till then if i had any problem, i'll drop a message 

Thanx alot for all the information
## Post #12
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-02T16:52:36+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

another problem:

there are some files with multi elements, and when i use sx.exe, it says that it can't export all the elements, because wave files can only contain the element 0.

what do i have to do with these files? how can i convert all the elements in seperate wave files?

and there are some files that for example are 10MB of size, but when i try to convert them to wave, it only results a small 100KB file (with no error like the one i mentioned above). I checked the header of this file, after maybe 100 bytes, i found the easound header which was repeated several times in the file, maybe hundered times. what i asume is that this big file consists of several asf files which are appended together and the first 100 bytes are pointers too these asf files in the bigger file.

how can i extract these files? and even worse, how can i encode all the extracted wave files back to this packed file?
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-02T17:41:12+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

I know this problem  easy to do 
[http://www.volny.cz/nova-software/](http://www.volny.cz/nova-software/) try this
## Post #14
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-02T19:45:27+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

this is such a great program ! i'm going for the registration 

but only one problem, it's got a error with one of it's groupfiles, APAK : Archangle pack. it sayz "error while reading groupfile" , do you have the same error?
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-02T23:49:41+00:00
- Post Title: "Harry Potter : Goblet of fire" movie, sound and s

I dont'k now this error   i don't have the game of harry
## Post #16
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-03T08:51:29+00:00
- Post Title: 

another thing... (problems keep coming!):( 

when i convert wav files using -ps2stream which fits the best with the audio in speech.big (after extracting the elements) the size is a little bit bigger than the original one, so when i want to import them in Extractor 2.4 to replace the original file, it says that it can only import a portion of the file which destructs the header of that element. 

how can i deal with this problem?

i tried several options of the sx.exe, but it didn't help. how can i import these files without destructing them? or how can i convert them to the exact filesize of the original file?

thnx for being there and helping
## Post #17
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-03T09:57:19+00:00
- Post Title: 

look:

The switches of ps2stream are:
(s16l_blk)
(eaxa_blk)
(mt_blk)
(mt5_blk) =>This it the best compression, you can choose the last, the file it's more small anc sure can fit

Of course you "destruct" it's lossy compressor, i don't have experience in ps2 files

I tried the reconversion in pc sound files (EA) without any problem

Good luck
## Post #18
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-03T11:24:53+00:00
- Post Title: 

good idea with compressing the files...

but is there a program known as the "sdt packer"? so that i can just give the files and it packs them into an SDT file, like the original one? i'm searching the net for it, but thought to drop a message, maybe you might have some info about it.
## Post #19
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-03T16:32:37+00:00
- Post Title: 

we did it ! i finally packed the file and burnt the game and it had no problem. i changed some of the audios and the console play them arrrrright !

even the loss cause by the compression doesn't show itself during the gameplay.

but i only inserted some few changed files, which took quite a long time, because i have to import them one by one by hand and replacing them with the original files in the SDT file using the Extractor, now that i need to import more than 5000 files, that's a nightmare, it'll take ages ! dunno what to do with this.

but thanx to you for all the guide
## Post #20
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-03T19:16:40+00:00
- Post Title: 

SDT it's a BIGF file? you know if the header it's "BIGF" ?
## Post #21
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-04T01:46:56+00:00
- Post Title: 

Okay it's group of audios, you can do 2 things, extract the audios , reconvert it and later do copy /b audio + audio +audio 3 (etc) finalname, i don't know if
 this really works

Other options it's a called "injection technique", you need a extractor with the offset and later reinject the data, like filestripper or nadub, this two are great file strippers but don't support the header of this audio, you can mail to the autors (i did it, but not answer)

So actually you can try the worst option of "copy /b", but i'm sure the game looks the offset of the audio, but...
## Post #22
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-04T10:46:26+00:00
- Post Title: 

i just downloaded the filestripper, and the nadub, i didnt find.

so, let's give it a try
## Post #23
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-04T10:52:13+00:00
- Post Title: 

> file strippers but don't support the header of this audio
## Post #24
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-04T16:03:13+00:00
- Post Title: 

I see... still no reply from the author?
## Post #25
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-05T13:28:02+00:00
- Post Title: 

yep
## Post #26
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-06T16:33:58+00:00
- Post Title: 

This type of Audio format has been on my todo-list for
over a year. the reason it isnt detected and ripped yet
is because i wanted an automatic converter for it to
save as WAVE/RIFF when ripped. i could make a detection
for it and make it rippable, the question is though, is
that for any use?
## Post #27
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-06T17:32:05+00:00
- Post Title: 

Another thing with those files, do they start with "SCHl" or are they
as you post them? (they have 127 bytes first of strange data, and then
after that an SCHl header)

i just wanna be sure so the offset is correct.
(started adding EA Games support for Jaeder now :// )
## Post #28
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-06T18:02:30+00:00
- Post Title: 

That's exactly how it is, as you 127 byte strange data and after that starts the audio data whith the SCHl header. I actualy could extracts the audios, and where able to convet them back to WAV, but i like to put them back into the SDT file, that's what seems to be hard and time consuming.

I can send you even more of these files if you like.
## Post #29
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-06T18:28:36+00:00
- Post Title: 

Now for the tricky part.

Ive tried extracting and examinating some of the posted files here,
and some of them contains several SCHl marks, isnt it
one SCHl header per audio file? or can several audiostreams
have multiple headers?

and, only the first file (in the sdt files) has 127 bytes 
of the file actually contains something.
if I extract lets say 3 files , only the first file with SCHl header
has the 127 bytes of data. the rest have just Zeros in the 127 junk section,
and then followed by an SCHl header.

*this is confusing*

i dont blame you if you dont get my explanation.
## Post #30
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-07T05:11:51+00:00
- Post Title: 

you mean comparing between SDT files or the files which are encapsulated in the STD file? something else, since the STD file consists of several files, doesnt it need any pointer to the parts of its files? isnt that 127 kb something to do with this?
## Post #31
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-07T07:58:07+00:00
- Post Title: Well....

YEs. The STD files seems to contain several chunks....
atleast i found 3 SCHl headers in some of them, are these individual
sample files, or do they contain to the same sound? =o

Ive found an EA Games ADPCM Decompression scheme, so
it is possible to make a converter for them aswell, however
i dont know how to make bit operations in a smooth
way using VB code :/
## Post #32
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-07T09:03:53+00:00
- Post Title: Well....

@Strobe some games with Ea sound are with 4-6 channels, like fifa '06
## Post #33
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-07T09:47:23+00:00
- Post Title: Well....

pulposo:
That would make more sense actually.

However, im not fully convinced about this format.
some sites states that SCHl is the beginning of an EA Sound file,
and you say they start with 127 junk data and then SCHl header?

im not sure of what i should be going after here. =(
## Post #34
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-07T16:07:31+00:00
- Post Title: Well....

OK, I dunno if i have understood you well enough, but here's the story I faced while dealing with these STD files :

First of all there was a game called Harry Potter : Goblet of Fire. The game had several big files including MOVIES.BIG and SPEECH.BIG .

I extracted these BIG files using Watto's Game Extractor.

So, now i have some .SDT files which come from the SPEECH.BIG and some .ASF and .MPC files which come from the MOVIES.BIG. The ASF files i could handle easily, but i noticed that the SDT files are something like gropfiles which were containing several (at some cases upto 500+) EA Sound files with the header SCHl. So what pulposo suggested and it realy helped was using a program called Extractor. By using this software I was able to extract the EA Sound files (Extractor used MUS as their extension) and succesfully converted them to WAV using the good and helpful sx.exe which also pulposo suggested. Now i have bunch of working WAV files and so i changed them I wished and by using the sx.exe again, i converted them to ASF (same as MUS; the same header atleast). Till here, I had no problem. The hard part starts when i want to put these ASF files back into the SDT file, which using the extractor again, i had to import the ASF files one by one (after reducing it's size) in to the original ST file and replacing the original MUS part of the file.

What I realy would appretiate is how to make an SDT file without importing the files one by one inside it (and without the need to reduce the filesize). I couldnt just merge the ASF files and rename it to SDT, just because of the 127 byte header of the SDT file, so I had to import and replace the MUS files without touching the skeleton stucture of the SDT file.

wow! i hope this story made any sense to you folks. I would appretiate any help. thnx
## Post #35
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-09T10:12:59+00:00
- Post Title: Well....

hehehe, thanks for the story! now i have bit better understanding of what
you need here. Ive started on EA Game file implementations in my ripper,
however at the moment only extraction. no conversion, or easy injection.

but atleast it seems to work terrific in extracting the data for now.

I may redesign my injector tool to be able to inject files
easier. (especially multiple files, people seems to need this),
but it will be done when i have time =X   (or feel like it!)

are there anymore references too anyother EA game files?
(the MUS files seems to work as intended now).
## Post #36
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-09T10:22:52+00:00
- Post Title: Well....

further analyzing of the SDT format.
its very easy to recreate a header by the way. i think i can write a program
for it. (or make an implementation in jaeder).

if i have understood everything correctly, you need something
that can take your reconverted EA games (mus files) and recompile
them to a SDT archive?
## Post #37
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2006-06-09T10:46:33+00:00
- Post Title: Well....

I understood this:

-Extraction of the audio with offsett info
-Reconversion with the reconverter
-Inject the reconverted file to the big file (tnx to the info of the offsett) dont main if the file it's more small
## Post #38
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-09T11:08:11+00:00
- Post Title: Well....

Forgot that the SDT files actually comes from a bigger archive =o
funny to have archived archives.......well well...

i think ill just go order a pizza and have a nap for a few hours.
*poor brain is overheating*

Another irritating thing ive now found is that if im having a MUS ripper,
it will meen it will rip the MUS files out of the archived archive files (SDT)
from a BIGFile instead of actually saving the SDT file. (which would
be neccessary because of the 127 byte header)

the problem here is too determine if the file is really an sdt-archive
or if it is a stand-alone MUS file? =///
(the SDT table contains information of where files are stored
in the sdt files, and offset, and how many of them there is, it can contain up to 14 files per SDT archive at maximum), this makes it 
difficult too determine what-is-what. because there is NOTHING in the header
that says "Hey im an SDT file!! please rip me!" 

but this is maybe off topic.....=X


EDIT: you say that a SDT file can contain over 500 files? =o
that meens i have to analyze some more. for me, it looks locked at 14 files, as the table is always 128 bytes, (atleast on all SDT files ive seen).
## Post #39
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-06-09T18:36:48+00:00
- Post Title: Well....

Could anyone help me with an editor I can decompress/compress the .str files? These file contain the speeches.
[example.zip](https://xentaxbackup.github.io/file/760_example.zip)
## Post #40
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-09T19:12:17+00:00
- Post Title: Well....

> Reply from Strobe
>
> you say that a SDT file can contain over 500 files? =o
that meens i have to analyze some more. for me, it looks locked at 14 files, as the table is always 128 bytes, (atleast on all SDT files ive seen).

yes, I've found some SDT files 10 Megabytes large and containing 500+ files in it. As soon as i get back to my own PC, i'll check the header to see if it has 128 byte or more, or maybe i could send it, but i know it'll take ages via 56kb dial up connections.
## Post #41
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-09T19:14:23+00:00
- Post Title: Well....

> Reply from SilentHill
>
> Could anyone help me with an editor I can decompress/compress the .str files? These file contain the speeches.

I think these files have something to do with subtitles. Can i ask in which game did you find them?
## Post #42
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-09T19:20:27+00:00
- Post Title: Well....

> Reply from Strobe
>
> if i have understood everything correctly, you need something
that can take your reconverted EA games (mus files) and recompile
them to a SDT archive?

that's so true, specially by selecting multiple files at a time, like if a SDT file is going to contain 20 files, i could select the 20 files and click on "convert" or "pack" button and does all the work for me  that sound's cool doesn't it?
## Post #43
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-06-09T20:27:54+00:00
- Post Title: Well....

> I think these files have something to do with subtitles. Can i ask in which game did you find them?

I found them in the Harry Potter: Goblet of fire. They are in the .big file.
## Post #44
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2006-06-09T21:13:16+00:00
- Post Title: Well....

Prince_of_peace: An SDT archive creator wouldnt be so difficult too create.
however i must ask, how can you reinject the SDT file later into the BIG file
if making it larger ?  (or maybe mexcom supports this archive type :X)

because right now when looking at the SDT files, they look kinda easy to
recompile.
## Post #45
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-09T23:18:39+00:00
- Post Title: Well....

> Reply from SilentHill
>
> I think these files have something to do with subtitles. Can i ask in which game did you find them?

I found them in the Harry Potter: Goblet of fire. They are in the .big file.

yeah, i suppose they've got something to do with subtitles
## Post #46
- Username: Prince_of_Peace
- Rank: beginner
- Number of posts: 29
- Joined date: Fri May 26, 2006 1:41 pm
- Post datetime: 2006-06-09T23:24:37+00:00
- Post Title: Re: Well again....

> Reply from Strobe
>
> Prince_of_peace: An SDT archive creator wouldnt be so difficult too create.
however i must ask, how can you reinject the SDT file later into the BIG file
if making it larger ?  (or maybe mexcom supports this archive type :X)

because right now when looking at the SDT files, they look kinda easy to
recompile.

the last time i tried it, i didnt resize the SDT files, and put it back in the BIG, and burn it and it worked alright... so i must say i'm not sure yet, maybe i should give it a try! i used "game extractor". I don't have the program here on this PC, so maybe that'll be the day after tomorrow
## Post #47
- Username: SilentHill
- Rank: VIP member
- Number of posts: 16
- Joined date: Sun Feb 05, 2006 6:18 pm
- Post datetime: 2006-06-10T11:43:55+00:00
- Post Title: Re: Well again....

> yeah, i suppose they've got something to do with subtitles

Ok, and should it mean anything to me? 

I'd need an editor ar something I could translate the text with.
## Post #48
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-07-03T18:57:00+00:00
- Post Title: Re: Well again....

> Reply from Savage
>
> Sorry i forgott the attachment
yeps here the converter:
http://rapidshare.de/files/21975849/sx.rar.html
Enjoy 

and does the *.mpc got anything to do with *.mpg files
the example dont' looks this, maybe i'm wrong

Can you repost this converter?  The link is stale.
## Post #49
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-12-31T13:09:53+00:00
- Post Title: Re: Well again....

I Attach the converter
[sx.part1.rar](https://xentaxbackup.github.io/file/1416_sx.part1.rar)
## Post #50
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-12-31T13:10:42+00:00
- Post Title: Re: Well again....

Part 2/2
[sx.part2.rar](https://xentaxbackup.github.io/file/1417_sx.part2.rar)
## Post #51
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2007-12-31T13:49:20+00:00
- Post Title: Re: Well again....

> Reply from Savage
>
> I Attach the converter

Thanks. I'll give this a look this week.
## Post #52
- Username: Dandapani
- Rank: advanced
- Number of posts: 55
- Joined date: Tue Jul 03, 2007 12:11 am
- Post datetime: 2008-01-03T20:41:53+00:00
- Post Title: Re: Well again....

> Reply from Savage
>
> I Attach the converter

Savage, I looked at each RAR archive, part 1 and part2 and both contain the same byte by byte file called sx.exe. Was there something expected different in each?

$: unrar l sx.part1.rar 

UNRAR 3.70 freeware      Copyright (c) 1993-2007 Alexander Roshal

Volume sx.part1.rar

 Name             Size   Packed Ratio  Date   Time     Attr      CRC   Meth Ver
-------------------------------------------------------------------------------
 sx.exe         247808   124922  --> 04-03-06 15:52  .....A.   86FAA9D1 m5c 2.9
-------------------------------------------------------------------------------
    1           247808   124922  50%       volume 1

$: unrar l sx.part2.rar

UNRAR 3.70 freeware      Copyright (c) 1993-2007 Alexander Roshal

Volume sx.part2.rar

 Name             Size   Packed Ratio  Date   Time     Attr      CRC   Meth Ver
-------------------------------------------------------------------------------
 sx.exe         247808   112037  <-- 04-03-06 15:52  .....A.   224A905F m5c 2.9
-------------------------------------------------------------------------------
    0                0   112037   0%       volume 2

$: unrar e sx.part1.rar

UNRAR 3.70 freeware      Copyright (c) 1993-2007 Alexander Roshal


Extracting from sx.part1.rar

Extracting  sx.exe                                                       

Extracting from sx.part2.rar

...         sx.exe                                                    OK 
All OK
$: mv sx.exe sx.part1.exe
$: unrar e sx.part2.rar  

UNRAR 3.70 freeware      Copyright (c) 1993-2007 Alexander Roshal


Extracting from sx.part2.rar


Extracting from sx.part1.rar

Extracting  sx.exe                                                       

Extracting from sx.part2.rar

...         sx.exe                                                    OK 
All OK
$: mv sx.exe sx.part2.exe
$: cmp sx.part?.exe
$: ls -l sx*exe
-rw-r--r-- 1 dandapani dandapani 247808 2006-03-04 15:52 sx.part1.exe
-rw-r--r-- 1 dandapani dandapani 247808 2006-03-04 15:52 sx.part2.exe
## Post #53
- Username: primevalrex
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 14, 2009 7:25 pm
- Post datetime: 2009-06-26T11:26:22+00:00
- Post Title: Re: Well again....

hi,
i want to have the mesh and the textures of that game aswell.
and i extracted the big file.
but all the things i got where str files.
and i already tried some converters but none worked of them.
when i extracted the big file those str files had textures in it but i could get them.
can someone help me please?
i really want that dragon model. :/

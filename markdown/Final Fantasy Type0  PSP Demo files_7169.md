## Post #1
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-08-12T21:38:57+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

Hey Team,  I'm not sure if I should have posted this here or in the NOESIS area...

  I'm new and still learning, so please bear with me.  I've come across various .RAW files from Type-0, and wasn't sure how to look into them using NOESIS or any other viewer.  A couple years ago, I was using Mr. Adults mesh2rdm to look at the .raw files from ff7crisis core, and thought that this would be similar.  To my chagrin it was not the same.
The folder with all the .RAWs was rather large, but I've posted a couple of the files of different sizes.

 I used NOESIS to open the "yellow.pkg" which extracted the files into the following folders.

audio (contains 294 .sscf files)
other (contains 890 .raw files)
video (contains 7 .psmf files)




Any help would be greatly appreciated.
 Thanks for your time - LUBDAR
## Post #2
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2011-08-12T22:51:00+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

could you link me some tool to unpack the PSAR file you obtain after the extraction of the PBP please?
## Post #3
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-08-13T00:15:50+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

Here is what I used

[http://pspslimhacks.com/eboot-2-iso-1-1-converter/](http://pspslimhacks.com/eboot-2-iso-1-1-converter/)

however I don't think it works consistently.
## Post #4
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-14T08:27:16+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

I wonder how the models are encrypted in it
## Post #5
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-08-15T10:44:44+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

I'm also interested in text files, some people seem to have been able to extract some text from the game but I don't know how since the game doesn't seem to use any regular encoding such as Shift-jis or UTF-8/16.
## Post #6
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-08-15T18:51:20+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

> Reply from DOTAPRINCE
>
> I wonder how the models are encrypted in it
All files are unencrypted, don't know how model files work, textures are custom gim files with external palette.

> Reply from Truthkey
>
> I'm also interested in text files, some people seem to have been able to extract some text from the game but I don't know how since the game doesn't seem to use any regular encoding such as Shift-jis or UTF-8/16.

The Game uses SHIFT-JIS tables for Debug messages, UTF-8 for system messages, some other files also uses UTF-8 but i think the ingame text is a custom font inside the map files
[fft0_samples_text.7z](https://xentaxbackup.github.io/file/4631_fft0_samples_text.7z)
## Post #7
- Username: Truthkey
- Rank: beginner
- Number of posts: 20
- Joined date: Sat Jul 24, 2010 5:39 am
- Post datetime: 2011-08-15T20:02:23+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

> Reply from Falo
>
> DOTAPRINCE wrote:I wonder how the models are encrypted in it  
All files are unencrypted, don't know how model files work, textures are custom gim files with external palette.
Truthkey wrote:I'm also interested in text files, some people seem to have been able to extract some text from the game but I don't know how since the game doesn't seem to use any regular encoding such as Shift-jis or UTF-8/16.

The Game uses SHIFT-JIS tables for Debug messages, UTF-8 for system messages, some other files also uses UTF-8 but i think the ingame text is a custom font inside the map files

What? But I have searched for text myself using all those encoding and I didn't find even a single word.

EDIT: Nevermind...
Still, if in-game text is not translatable it ruins all the fun for me xD
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-08-16T00:40:37+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

[](http://imageshack.us/photo/my-images/11/fft0.png/)
Same format as T3B. Noesis already supports it if you just make up a t3b .pack header, but next release will support it natively.

Also Noesis already supports extracting the archives from the game as-is.
## Post #9
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-16T01:37:06+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

> Reply from MrAdults
>
> 
Same format as T3B. Noesis already supports it if you just make up a t3b .pack header, but next release will support it natively.

Also Noesis already supports extracting the archives from the game as-is.
Wow this is awesome :O
So to view those models, we need to change some of the files contents?
Anyway what is the exact file format for them?
And Noesis will be able to support the model format in its next release? Then that's good news 
Thanks Mr.Adults
## Post #10
- Username: Aurangzeb56
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 30, 2010 2:38 pm
- Post datetime: 2011-08-16T04:48:13+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

> Reply from MrAdults
>
> 
Same format as T3B. Noesis already supports it if you just make up a t3b .pack header, but next release will support it natively.

Also Noesis already supports extracting the archives from the game as-is.

Can you tell me how to make the t3b .pack header?Since when i ripped the files from USRDIR and renamed to 3rd,pkg and .fsd and used Noesis to extract it's contents,i go tvideo,audio and other folder.Didn't got any folder with models in it. :/
## Post #11
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-16T09:21:34+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

Just wait a little bit he will release it soon.
He has a very bug surprise in store for everyone in noesis.
## Post #12
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-16T12:29:45+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

Ok I see, can't wait for the next version 
I wonder when will it be XD
## Post #13
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-08-16T16:30:09+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

works ^^
[http://www.imagebanana.com/view/8zvvd5sj/King.jpg](http://www.imagebanana.com/view/8zvvd5sj/King.jpg)

pack header is a 128 Byte header:

4 Byte = "pack"
4 Byte = 0xC // Headersize ?
4 Byte = Model Size
4 Byte = Modelstart (0x80)
112 Byte = 00

//edit
some model files are inside the mot and map files, 

a quick written bms script:

```
get unk1 long
get unk2 long
GetDString Name 12

for x = 1 to numFiles
GetDString ext 4
get Offset long
get unk3 byte
get Size THREEBYTE

if Size > 0
set FileName Name
string FileName += "."
string FileName += ext

log FileName Offset Size
endif

next x
```


*.mdls files are the models + a 48 Byte header, 
just delete the header, add a pack header and noesis can open them

to identify a mot or map file, open a raw file in hex editor and you should see something like this:
"mot_s_siva_" or "map_mto05_0"

//edit2:

i think i identified the text files, they have the "ATELY" header (*.lang extension), but don't know the encoding, some custom UTF16 stuff.
[sample_pack.7z](https://xentaxbackup.github.io/file/4636_sample_pack.7z)
## Post #14
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-08-16T20:45:15+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

From what I've seen, it uses ATEL and GT formats that Crisis core use, just with an extra header. If you delete that, you can view them in Koral's old viewer.
## Post #15
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-17T10:48:13+00:00
- Post Title: Final Fantasy Type0  PSP Demo files

> Reply from Falo
>
> works ^^
http://www.imagebanana.com/view/8zvvd5sj/King.jpg

pack header is a 128 Byte header:

4 Byte = "pack"
4 Byte = 0xC // Headersize ?
4 Byte = Model Size
4 Byte = Modelstart (0x80)
112 Byte = 00

//edit
some model files are inside the mot and map files, 

a quick written bms script:
Code: Select allget numFiles long
get unk1 long
get unk2 long
GetDString Name 12

for x = 1 to numFiles
GetDString ext 4
get Offset long
get unk3 byte
get Size THREEBYTE

if Size > 0
set FileName Name
string FileName += "."
string FileName += ext

log FileName Offset Size
endif

next x

*.mdls files are the models + a 48 Byte header, 
just delete the header, add a pack header and noesis can open them

to identify a mot or map file, open a raw file in hex editor and you should see something like this:
"mot_s_siva_" or "map_mto05_0"

//edit2:

i think i identified the text files, they have the "ATELY" header (*.lang extension), but don't know the encoding, some custom UTF16 stuff.
How do you do this actually? I want to know how to get the model files 
Or can you send them to me?
## Post #16
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-08-17T13:18:38+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

The contents of this post was deleted because of possible forum rules violation.
## Post #17
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-17T15:08:17+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

Wow I wish I can be like you since I wanted to learn hex editing too 

Anyway thanks falo ^^

When the game comes out on October, all characters will have their models there and the characters will be complete XD
## Post #18
- Username: 80T
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jul 23, 2011 9:45 am
- Post datetime: 2011-08-18T15:49:08+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

Sory if I'm hijacking the thread but I don't think it's necessary to open a new one for my question.
I didn't quite understood if Noesis can extract animations from PE: T3B I mean I can extract the models with bones and all but I wasn't able to extract any kind of animations...
I've tried to export extra animations but no animations were exported...
I've tried also to extract animations from "file0652.pack" but with the same luck...
Is there any way that Noesis would extract animations from this game or is not supported ?
## Post #19
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-08-18T19:59:32+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

> Reply from 80T
>
> Sory if I'm hijacking the thread but I don't think it's necessary to open a new one for my question.
I didn't quite understood if Noesis can extract animations from PE: T3B I mean I can extract the models with bones and all but I wasn't able to extract any kind of animations...
I've tried to export extra animations but no animations were exported...
I've tried also to extract animations from "file0652.pack" but with the same luck...
Is there any way that Noesis would extract animations from this game or is not supported ?

noesis extracts all files, you have to search for "mot_???" files with a Hex Editor.

all files from 960 to 1105 should be the .mot files (example: File1091 -> mot_s_siva_ -> Shiva), 
then use my bms script to extract them and you get:

*.snde -> (sscf) sound effects
*.fimg -> picture
*.fclt -> picture palette
*.lang -> text
*.moti -> ???
*.mdls -> 3D model
*.mots -> animation ?
*.efft -> (FEP header) some 3d data and pictures

but i don't think noesis supports .mots files.
## Post #20
- Username: Cloud452
- Rank: veteran
- Number of posts: 91
- Joined date: Sat Oct 23, 2010 9:50 pm
- Post datetime: 2011-08-21T20:29:50+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

> Reply from Falo
>
> 80T wrote:but i don't think noesis supports .mots files.

Nope, at present it doesn't. I've been trying to [garner interest in a plugin](http://forum.xentax.com/viewtopic.php?f=32&t=6801) that would allow it to utilize those .mot files.

Looks like they reused the Guard Scorpion model from Crisis Core: [http://i.imgur.com/HiYWt.png](http://i.imgur.com/HiYWt.png)
## Post #21
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-08-22T05:21:01+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

HUGE thanks to everyone's help with this game!!!

For the most part all of the .t0mdl files can be viewed with the exception of
file0598
file0670
file0709
file0710
and file0715,
for these files Noesis gives me an error message


Output extension has set output file type to:
.obj - WaveFront OBJ
Detected file type: FF Type-0 Model/Texture
WARNING: Bad mesh offset.
Cleaned 8.00MB (in 2 pools).
## Post #22
- Username: MAXumYM
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 01, 2011 10:24 pm
- Post datetime: 2011-11-01T14:30:44+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

Hi, can I ask you a question? How did you extract everything from that .PKG file?
## Post #23
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-11-02T01:43:09+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

> Reply from MAXumYM
>
> Hi, can I ask you a question? How did you extract everything from that .PKG file?
Use Noesis. The most recent version has additional fixes for better-identifying files for this game and sorting them into the right places. I've tested that all files are working as expected/intended from each disc of the Japanese version.

Not all files will actually load in Noesis though. Some are animation-only and animations are not currently supported. (though I'd be happy to support them if anyone else wants to spend the time reversing them, they're on my list of shit to figure out the next time I'm on vacation and/or jobless)
## Post #24
- Username: thegtsolo
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Jul 12, 2011 3:18 am
- Post datetime: 2011-11-12T13:52:49+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

it posible for load animation
## Post #25
- Username: Feit
- Rank: n00b
- Number of posts: 14
- Joined date: Sun Nov 27, 2011 10:14 am
- Post datetime: 2011-11-27T02:57:19+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

can i ask sir?,

I've already extracted all files(i think) that the yellow.pkg file has to offer but no luck on finding the txt files or th
".lang" files, i am hoping to translate the game. oh i forgot its the Disk 1 actually.
## Post #26
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-11-27T08:17:14+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

> Reply from Feit
>
> can i ask sir?,

I've already extracted all files(i think) that the yellow.pkg file has to offer but no luck on finding the txt files or th
".lang" files, i am hoping to translate the game. oh i forgot its the Disk 1 actually.

Noesis extracts the model files, I think you'll have to look in another thread to get more info on how to get these ".lang" files you speak of.
## Post #27
- Username: LUBDAR
- Rank: veteran
- Number of posts: 95
- Joined date: Wed Jun 08, 2011 2:14 pm
- Post datetime: 2011-11-29T00:16:11+00:00
- Post Title: Re: Final Fantasy Type0  PSP Demo files

> Reply from LUBDAR
>
> Feit wrote:can i ask sir?,

I've already extracted all files(i think) that the yellow.pkg file has to offer but no luck on finding the txt files or th
".lang" files, i am hoping to translate the game. oh i forgot its the Disk 1 actually. 

Noesis extracts the model files, I think you'll have to look in another thread to get more info on how to get these ".lang" files you speak of.

Just in case you were wondering Type-0 is being localized so your efforts of translation can be relaxed..

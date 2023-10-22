## Post #1
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2022-11-12T07:22:44+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

I actually posted something related to this at somewhere else (not here) several years back but I didn't get a response. I thought I should give it a go again since it's been quite a long time... I'm going to share the whole image file that I converted from the chd file, and it has several file formats that may or may not be known such as .FC (used for models and textures). What I'm most keen about is the "osm_3_eng_v1002.bin" file (most of the assets are in there), though it is encrypted sadly.

Is anyone able to look into this and help? If possible, models/textures in a file format that can be easily imported or opened with software would be great.

Thanks!

I've included a separate .bin file if you're just looking into that.

mda-c0042.img (converted from .chd)
[https://drive.google.com/file/d/1fEbouH ... X4hyC/view](https://drive.google.com/file/d/1fEbouH7r-IKelnFm3R4Ywil3pIFX4hyC/view)

osm_3_eng_v1002.bin
[https://drive.google.com/file/d/1rd3Lak ... share_link](https://drive.google.com/file/d/1rd3Lako4vblvNZFL_Kj89PSR3LUq44Pp/view?usp=share_link)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-12T20:08:37+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> but I didn't get a response
So you're in luck. This time I will share a file format research results with you.   


Here is the wiki article about FC format [http://wiki.xentax.com/index.php/Love_a ... _Dance!_FC](http://wiki.xentax.com/index.php/Love_and_Berry:_Dress_Up_and_Dance!_FC)
This is just a container for PVR and NJ files. You can extract files with this script
[https://github.com/bartlomiejduda/Tools ... script.bms](https://github.com/bartlomiejduda/Tools/blob/master/NEW%20Tools/Love%20and%20Berry%20Dress%20Up%20and%20Dance/Love_and_Berry_FC_script.bms)

You can use it with quickbms [http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)

Here are also articles for PVR images and NJ models:
[http://wiki.xentax.com/index.php/PVR_Image](http://wiki.xentax.com/index.php/PVR_Image)
[http://wiki.xentax.com/index.php/Ninja_Model_NJ](http://wiki.xentax.com/index.php/Ninja_Model_NJ)

Both formats are natively supported by Noesis. [https://richwhitehouse.com/index.php?co ... project=91](https://richwhitehouse.com/index.php?content=inc_projects.php&showproject=91)
So you can use it to view models and textures:
[https://i.imgur.com/ONpQh6G.png](https://i.imgur.com/ONpQh6G.png)
[https://i.imgur.com/Utlexbz.png](https://i.imgur.com/Utlexbz.png)

As for ADX files, they are CRI ADX 4-bit ADPCM audio. You can use foobar2000 with vgmstream plugin to play them.
## Post #3
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2022-11-15T03:14:47+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

Thank you! What about the .bin file? Would it be possible to decrypt or extract the contents?
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-15T19:35:54+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> Reply from diszxchat ↑Tue Nov 15, 2022 11:14 am at Tue Nov 15, 2022 11:14 am
>
> 
Thank you! What about the .bin file? Would it be possible to decrypt or extract the contents?

No, sorry, it seems to be too complicated to figure out without debugging the game.
This BIN file is still a mystery to me.
## Post #5
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2022-11-16T03:00:31+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> Reply from ikskoks ↑Wed Nov 16, 2022 3:35 am at Wed Nov 16, 2022 3:35 am
>
> 
diszxchat wrote: ↑Tue Nov 15, 2022 11:14 am
Thank you! What about the .bin file? Would it be possible to decrypt or extract the contents?


No, sorry, it seems to be too complicated to figure out without debugging the game.
This BIN file is still a mystery to me.

That's alright. Thank you for your help. I couldn't find any strings that suggests a folder or file name in HxD so it's likely heavily encrypted. All I know about the .bin file is it contains models, graphics, and sounds (possibly scripts too but who knows) when I open the game in DEMUL with Cheat Engine on. It doesn't reveal the entire list of contents since it looks like it only displayed the important assets in the memory editor. The other sound files are listed in order of AXXXXX.adx. 

The previous versions of the game (1st-2nd Collection), stored as IC files, displayed almost an entire list of the files as shown in the C.E memory editor. Common extensions are .pvr and .adx. These files haven't been cracked yet and I don't think anyone can extract it out from IC for the time being?
## Post #6
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2022-11-26T14:23:31+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> Reply from ikskoks ↑Wed Nov 16, 2022 3:35 am at Wed Nov 16, 2022 3:35 am
>
> 
diszxchat wrote: ↑Tue Nov 15, 2022 11:14 am
Thank you! What about the .bin file? Would it be possible to decrypt or extract the contents?


No, sorry, it seems to be too complicated to figure out without debugging the game.
This BIN file is still a mystery to me.

I was wondering if it's possible to extract the contents of the earlier versions (1st-2nd collection). They're IC files (nameless extension). They have some readable strings like file names when I open it up with HxD editor.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-26T17:45:25+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> Reply from diszxchat ↑Sat Nov 26, 2022 10:23 pm at Sat Nov 26, 2022 10:23 pm
>
> 
I was wondering if it's possible to extract the contents of the earlier versions (1st-2nd collection). They're IC files (nameless extension). They have some readable strings like file names when I open it up with HxD editor.

Can you upload a few samples of the IC files to some hosting site like mega.nz, google drive etc. and then share a public link here?
## Post #8
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2022-11-27T14:04:41+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> Reply from ikskoks ↑Sun Nov 27, 2022 1:45 am at Sun Nov 27, 2022 1:45 am
>
> 
Can you upload a few samples of the IC files to some hosting site like mega.nz, google drive etc. and then share a public link here?

There's two versions of it but there isn't any major difference when played with DEMUL Emulator except the build version is different. I believe one of the other files have several ICs (I assume that version has contents split into parts).

[https://drive.google.com/drive/folders/ ... 74fdUAMJBa](https://drive.google.com/drive/folders/1UrSwceN5yoItkOjWyFi92x74fdUAMJBa)
## Post #9
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2022-12-17T15:19:29+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

A user messaged me that the enceypted bin might be possible to decrypt with the help of dump file (though task manager) but I'm not sure what to do with the file since I don't understand how it may help?
## Post #10
- Username: BrittanyRowe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 09, 2023 9:27 pm
- Post datetime: 2023-01-14T10:50:43+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

> Reply from ikskoks ↑Sun Nov 13, 2022 4:08 am at Sun Nov 13, 2022 4:08 am
>
> 
but I didn't get a response
So you're in luck. This time I will share a file format research results with you.   


Here is the wiki article about FC format http://wiki.xentax.com/index.php/Love_a ... _Dance!_FC
This is just a container for PVR and NJ files. You can extract files with this script
https://github.com/bartlomiejduda/Tools ... script.bms

You can use it with quickbms http://aluigi.altervista.org/quickbms.htm

Here are also articles for PVR images and NJ models:
http://wiki.xentax.com/index.php/PVR_Image
http://wiki.xentax.com/index.php/Ninja_Model_NJ

Both formats are natively supported by Noesis. https://richwhitehouse.com/index.php?co ... project=91
So you can use it to view models and textures:
https://i.imgur.com/ONpQh6G.png
https://i.imgur.com/Utlexbz.png

As for ADX files, they are CRI ADX 4-bit ADPCM audio. You can use foobar2000 with vgmstream plugin to play them.
Thank you, you made my day. I will surely save your post so that I won't miss it. I was searching for reviews online for https://writinguniverse.com/free-essay- ... imination/ website because I want to take help from that website regarding my essay assignments. I am not so good at writing essay assignments and that is why I always prefer to take help from online.

Thank you, you made my day.
## Post #11
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2023-03-23T16:32:19+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

Thanks to memory dumping, I've only ripped a bit of data that were inside of the encrypted and unsolved BIN file. Other file formats with signatures like NJCM (.njm) and NCAM (.???) are present but there is one file that may hold the game script data? It has a signature of SAN 8 and has mentions of "DATA" string.

Here are a few samples of the unknown file format in both compressed (FC) and uncompressed state (set as BIN):

[https://drive.google.com/file/d/1evc0vt ... K-dWL/view](https://drive.google.com/file/d/1evc0vtUcE86ULLavx6qlCHgdgOcK-dWL/view)

I wonder if these unknown files are actually the strings and it would be cool to fish out unused strings or CODE39 barcodes.
## Post #12
- Username: diszxchat
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Oct 20, 2016 6:10 pm
- Post datetime: 2023-03-29T17:07:07+00:00
- Post Title: Love and Berry: Dress Up and Dance! NAOMI2 File Formats

The "SAN 8" signature file could possibly be a file archive or a custom graphic file format since all fourteen of the SAN files are stored in the TEX_2D folder. They're in .SAN. DATA could probably be graphic information?

And it seems that there's no way to get the BIN files of the arcade games based on NAOMI open with any CD mounting software as far as I've surfed through the Internet. I have to manually extract the file data by creating file or make a script to dump the files.

[https://drive.google.com/file/d/1SJkald ... share_link](https://drive.google.com/file/d/1SJkald9NYLRB3gjqYcv7L4OBx2v73m5P/view?usp=share_link)

## Post #1
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2014-09-24T16:43:44+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Hey there everyone!

Arrowhead has made lots of great games, and it seems that they are all using the very same engine, which I don't know if it's custom made or not. They are found mostly in the Content folder (maybe it's made with XDK?), and all file names are 16 char long with random characters in them (like e7729a796e71cb7e, d7bd9aca006835ae, c9ecdfc7f0c89432...etc), and they don't have a file extension, just that random name. There are also some random files which have another file like them, but it has an extension, which is .stream (so like there's an ec181385e7000cf1 file and an ec181385e7000cf1.stream file). These files vary from sizes, some can be 50 or 64 kbyte, and some can be 75 megs or more.

If anyone can help me research these (how to extract them, how to repack them...etc) then please let me know, and I'll get back to you when I can.


EDIT:
Here you can download the Showdown Effect demo from free on Steam, it's around 4-500 megabytes, has the same filesystem -> [http://store.steampowered.com/app/204080/](http://store.steampowered.com/app/204080/)

And also here's a screenshot of a 1 kbyte file from the game that's opened in a HEX Editor:
## Post #2
- Username: kilik
- Rank: mega-veteran
- Number of posts: 195
- Joined date: Sat Dec 08, 2012 6:14 pm
- Post datetime: 2014-10-03T19:04:30+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

same here check wav scan bms and dragon packer nothing work 
if someone can help please thank's
## Post #3
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-20T12:53:17+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

*bump*

Today is my birthday, yay! Can anyone look at the files for me as a gift?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-23T15:42:18+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

The latest version of all tools. Tested on Showdown Effect demo, Gauntlet, Wizard Wars, Helldivers. May also work with other Bitsquid games and also the new Autodesk Stingray Engine games like Warhammer: End Times.

bitsquid_unp [package file name]

It will unpack the contents into the same folder. Files will be named as hash, with proper extensions.

Multi-language files have the same name inside the package. So I decide to unpack them adding "version" flag at the end. This will not correspond to languages, just some special flag. Some files have multiple flags set. I don't know what it means. 

bitsquid_txt [strings file name]

Strings exporter/importer. If the parameter is txt file, it will do import. If it is ".strings", it will do export.
Text file must be in UTF-8 encoding. Some lines contain "next line" characters and when converted to txt it will be impossible to leave them. I just replaced 0xD to 0xF0 and 0xA to 0xF1. If the source file will contain either of these bytes, it will not work.

bitsquid_str [strings file name]

Repack ONE strings file into the new package. "data.bin" file made by extractor must be in the same folder. It contains some unknown info that we need to put back into the package.

It will make "out.packet" file, rename it to whatever it was originally and put into the game.

bitsquid_timpani [bank file name]

Audio bank unpacker for Showdown. It will unpack all sounds to OGG and WAV files, with no filenames, just hash. I'm working on this.

bitsquid_timpani [bank file name] [stream file name]

Audio bank unpacker for other games. It requires stream name too. If there's no stream for some particular bank, just type anything you want for second parameter. If you run it with 1 parameter, the result is unpredictable. If the stream will not be present, it will work, but files may be cut, having only some first seconds of sound.

About the .stream files

Streams are just an "addition" to the bank, you can't extract it without the bank. Bank files have extension "timpani_bank" and they are extracted from the packages with all the other files. During this process, the main stream file is also been cut into parts (small stream files) that are corresponding to each bank contained within a package.
[bitsquid.rar](https://xentaxbackup.github.io/file/10262_bitsquid.rar)
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-24T09:20:20+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

No filenames, they are hashed. I already found this engine (bitsquid) use murmur64 hash with seed=0. I found hash for all the filetypes:

```
0D972BAB10B40FD3	strings
18DEAD01056B72E9	bones
27862FE24795319C	render_config
2A690FD348FE9AC5	level
2BBCABE5074ADE9E	input
3B1FA9E8F6BAC374	network_config
786F65C00A816B19	wav
7FFDB779B04E4ED1	baked_lighting
82645835E6B73232	config
8FD0D44D20650B68	data
92D3EE038EEB610D	flow
931E336D7646CC26	animation
99736BE1FFF739A4	timpani_bank
9E5C3CC74575AEB5	shader_library_group
9EFE0A916AAE7880	font
A14E8DFA2CD117E2	lua
A486D4045106165C	state_machine
A8193123526FAD64	particles
AD9C6D9ED1E5E77A	package
AD2D3FA30D9AB394	surface_properties
B277B11FE4A61D37	mouse_cursor
BF21403A3AB0BBB1	physics_properties
CD4238C6A0C69E32	texture
D8B27864A97FFDD7	sound_environmenta
DCFB9E18FFF13984	animation_curves
E0A48D0BE9A7453F	unit
E3F0BAA17D620321	static_pvs
E5EE32A477239A93	shader_library
EAC0B497876ADEDF	material
F7505933166D6755	vector_field
F97AF9983C05B950	spu_job
FA4A8E091A91201E	ivf
FE73C7DCFF8A7CA5	shading_environment

```


Now only need to find filenames and it will be possible to make packer/unpacker.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-24T14:24:15+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

The "no filenames" unpacker is ready, I can now get all the resourses, with no names.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-24T17:18:47+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Bitsquid package unpacker. Tested on Showdown Effect, Gauntlet. May also work with other Bitsquid games.

Use: bitsquid_unp.exe [filename]

It will unpack the contents into the same folder. Files will be named as hash, with proper extensions.
Textures are DDS, all sounds packed into one huge bank.

Multi-language files have the same name inside the package. So I decide to unpack them adding "version" flag at the end. This will not correspond to languages, just some special flag. Some files have multiple flags set. I don't know what it means.
[bitsquid_unp.rar](https://xentaxbackup.github.io/file/9229_bitsquid_unp.rar)
## Post #8
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-24T17:35:22+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> First unpacker version. May also work with other Bitsquid games.

Use: bitsquid_unp.exe [filename]

It will unpack the contents into the same folder. Files will be named as hash, with proper extensions.
Textures are DDS, all sounds packed into one huge bank.

Now I will proceed with collecting the filenames, but obviously I can't find names from the full version, only demo.

Wow, you are awesome!

Does this work with other games as well? Like Magicka - Wizard Wars, I tried to unpack some files, but couldn't get the localisations out of them :\
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-24T17:56:02+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> Does this work with other games as well? Like Magicka - Wizard Wars

I don't know. If it has the same filesystem, it will work i think. If not - give me some files from it.

The only thing it doesn't support now is multiple chunk files (probably for different languages). You didn't say anything about localization, so I assumed you need sounds, textures e.t.c. If you tell, what do you plan to do, I can choose the best way to unpack these multi-files.
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-24T19:32:04+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Package names (so you know where to search for particular resources):

```
0D42C15E8F2B473F	base_game_resources 
171E8B0D2241EB79	script_files_game 
406C3644BD95237A	units 
71EEC7A172194FE5	language 
9E13B2414B41B842	boot
B5AF853949550001	backup_font 
D636772C67EB4760	cursors 
DD14D1E54AA54D93	particles 
EC181385E7000CF1	menu 
EDE759915C406BB6	fonts

```
## Post #11
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-24T20:05:15+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Sorry for not saying my plans. Well I plan to translate some of these games, and I may need some pictures/textures in case they need to be edited, some language files and maybe font files in case I have to edit in some unicode characters.

Will try it out with Showdown Effect, as I couldn't find any language files within Wizard Wars' files, and report back.

EDIT:
Sorry for not replying earlier, but I just realised that you've said I can't extract the files
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-25T16:43:51+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

New version. (old post updated)

Multi-language files have the same name inside the package. So I decide to unpack them adding "version" flag at the end. This will not correspond to languages, just some special flag. Some files have multiple flags set. I don't know what it means.

Look at the files inside "language" and "fonts" packages. You can now decide, how can you change them.

I see no need in filenames now. If anyone needs filenames for any bitsquid games, let me know then.
## Post #13
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-25T19:17:19+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> New version. (old post updated)

Multi-language files have the same name inside the package. So I decide to unpack them adding "version" flag at the end. This will not correspond to languages, just some special flag. Some files have multiple flags set. I don't know what it means.

Look at the files inside "language" and "fonts" packages. You can now decide, how can you change them.

I see no need in filenames now. If anyone needs filenames for any bitsquid games, let me know then.

Nice! I could extract the files from the full version of The Showdown Effect, and I've located the strings. I know it's an unpacker, but how can I pack the files back in?
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-26T15:49:40+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

If you think you can change these files for your purposes, I can try and pack it back.
## Post #15
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-26T16:52:38+00:00
- Post Title: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> If you think you can change these files for your purposes, I can try and pack it back.

Well I can edit the text in these files with a HEX Editor or something like that, and I'd like to translate these games. It would be awesome if you could help me out with it.

Although I might need to put up another request for the text files, maybe they need some unpacking too, but will see after packing them back in in the way they are now.

EDIT:
Just found Magicka 2's String files, and I think I can easily edit them. Will have to try once I can pack them back in
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-26T17:24:47+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> will see after packing them back in in the way they are now.

So you think you can edit text to the language you need using 1-byte encoding in one of the languages they have here and fonts they use in game?
## Post #17
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-26T17:45:23+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> TheReaperCooL wrote:will see after packing them back in in the way they are now.

So you think you can edit text to the language you need using 1-byte encoding in one of the languages they have here and fonts they use in game?

Well I see that the string files contains random stuff in the beginning (don't know what all that means), and then the strings come, separated with NUL or double FF HEX bytes.

If I change it and pack it back in then I can see if it changes, if it works, will see if I could write longer or smaller strings in it, then I go and use unicode characters (lots of them are supported, there are separate files for German, Swedish and such languages, I could use those if I'm correct).
## Post #18
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-26T18:27:38+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> I go and use unicode characters (lots of them are supported, there are separate files for German, Swedish and such languages, I could use those if I'm correct).

That's what I was asking about. So these unicode characters will be enough for your language?
## Post #19
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-26T18:42:25+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> TheReaperCooL wrote:I go and use unicode characters (lots of them are supported, there are separate files for German, Swedish and such languages, I could use those if I'm correct).

That's what I was asking about. So these unicode characters will be enough for your language?

I don't know yet, but I assume they are included in the game, seeing how cyrillic characters are already in it, and it supports many languages. I'll only know for sure once I've tested it.
## Post #20
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-26T19:35:53+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Ok. Well, at least I can say you can't write longer or smaller strings in it, because that "random stuff in the beginning" are all string offsets, and they need to be changed for that.
## Post #21
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-26T20:15:04+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> Ok. Well, at least I can say you can't write longer or smaller strings in it, because that "random stuff in the beginning" are all string offsets, and they need to be changed for that.

Damn... thought they are something like that. I translate other games too, and I have a hard time adjusting the pointers in Clock Tower (SNES).
## Post #22
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2015-05-26T22:53:22+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> daemon1 wrote:If you think you can change these files for your purposes, I can try and pack it back.

Well I can edit the text in these files with a HEX Editor or something like that, and I'd like to translate these games. It would be awesome if you could help me out with it.

Although I might need to put up another request for the text files, maybe they need some unpacking too, but will see after packing them back in in the way they are now.

EDIT:
Just found Magicka 2's String files, and I think I can easily edit them. Will have to try once I can pack them back in

Hey, we are working on translation too, which file exactly?
## Post #23
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-27T06:53:39+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from Taner038
>
> TheReaperCooL wrote:daemon1 wrote:If you think you can change these files for your purposes, I can try and pack it back.

Well I can edit the text in these files with a HEX Editor or something like that, and I'd like to translate these games. It would be awesome if you could help me out with it.

Although I might need to put up another request for the text files, maybe they need some unpacking too, but will see after packing them back in in the way they are now.

EDIT:
Just found Magicka 2's String files, and I think I can easily edit them. Will have to try once I can pack them back in 

Hey, we are working on translation too, which file exactly?

dd5d5b00fde9b0fb

And there are lots of files in it, and you need to edit the very first, which is B64470F86611DB9A.strings

Can't pack it back in yet, but you could edit this file and then when we can pack it back in you could translate the game. Also I'm translating it into Hungarian, as I've translated the first game and Wizard of the Square Tablet, too
## Post #24
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-27T15:08:17+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> dd5d5b00fde9b0fb

And there are lots of files in it

What are these files? All strings or something else?
## Post #25
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-27T15:31:27+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> TheReaperCooL wrote:dd5d5b00fde9b0fb

And there are lots of files in it

What are these files? All strings or something else?

All strings, and here's the list:

B64470F86611DB9A.strings (English)
B64470F86611DB9A_2.strings (Italian)
B64470F86611DB9A_4.strings (Portuguese-Brazil)
B64470F86611DB9A_8.strings (Russian
B64470F86611DB9A_10.strings (German)
B64470F86611DB9A_20.strings (Polish)
B64470F86611DB9A_40.strings (French)
B64470F86611DB9A_80.strings (Spanish)
## Post #26
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-27T15:44:59+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

ok, i will now try some tests. Packing only one file - english, will be easier, and maybe this is all we need.

update: interesting, it worked. Now I'm gonna make a tool that will pack one "english strings" file into package and you try it.
## Post #27
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-27T19:04:23+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Very first and temporary solution for repacking.

Unpack the strings again, and the tool will additionally make a file "data.bin" that contains some unknown info that we need to put back into the package.

Then change english strings (don't change its size yet!) and pack back with bitsquid_str [strings file name]
That file "data.bin" must be in the same folder.

It will make out.packet file, rename it to whatever it was originally and put into the game.
[bitsquid_unp.rar](https://xentaxbackup.github.io/file/9235_bitsquid_unp.rar)
## Post #28
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-27T20:17:40+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> Very first and temporary solution for repacking.

Unpack the strings again, and the tool will additionally make a file "data.bin" that contains some unknown info that we need to put back into the package.

Then change english strings (don't change its size yet!) and pack back with bitsquid_str [strings file name]
That file "data.bin" must be in the same folder.

It will make out.packet file, rename it to whatever it was originally and put into the game.

Tried it out, and yes, I could translate the game. I was curious and tried to input longer text, and the game started, but anything after said string was like [LOC:NOT_TRANSLATED] and such.

[Link to picture](http://kepfeltoltes.hu/150527/2004790782015-05-27_00001_www.kepfeltoltes.hu_.jpg)

EDIT:
Also I've just noticed, but this file only contains item, spell and such descriptions, but not actual dialogue. They are stored in a different file
## Post #29
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-27T20:27:16+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

To make longer texts, we have these options:

- you edit it in hex, and I make a tool that recalculate and update the offsets.
- make a tool to fully export texts (to what format?) and import them back
## Post #30
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-27T20:34:45+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> To make longer texts, we have these options:

- you edit it in hex, and I make a tool that recalculate and update the offsets.
- make a tool to fully export texts (to what format?) and import them back

Well the export sounds good (.txt or .xls is good, or whatever way you can extract it). This is because if I translate something and then I make a typo or something, then you'd have to recalculate every single text that's been inserted
## Post #31
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-27T20:40:33+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> you'd have to recalculate every single text that's been inserted

The tool will do it automatically for all text lines.
## Post #32
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-27T21:05:45+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> TheReaperCooL wrote:you'd have to recalculate every single text that's been inserted

The tool will do it automatically for all text lines.

Exporting it into a file might be better, but you should do what works and what's easier (I'd prefer exporting as I've said before).

EDIT:
I've looked around, and I see that there are no other files that contain strings, at least not under 10 megabytes (which means that's the only text in the game, but I need to look deeper in the files).

Also I've found almost all unicode characters, but couldn't test them. They should be the same as they were for Magicka 1. Once I get home I'll test them out.
## Post #33
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-28T15:53:49+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Ok, I will try export/import thought I doubt about this utf-8 encoding and how it may work.

Also I can see no files with "double FF". Can you send me those?

Did you find dialogue text? Because if you didn't, there's no use in this repacker.

p.s. another strange thing, different language files have different number of strings.
## Post #34
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-28T16:44:51+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> Ok, I will try export/import thought I doubt about this utf-8 encoding and how it may work.

Also I can see no files with "double FF". Can you send me those?

Did you find dialogue text? Because if you didn't, there's no use in this repacker.

p.s. another strange thing, different language files have different number of strings.

Sorry, not double FF, double 00. I'm translating many games and I wrote a bad value.

Also there's only one string file, but it's all messed up and didn't see the dialogue, but I think it's all there.
## Post #35
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-28T17:05:46+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from TheReaperCooL
>
> it's all messed up and didn't see the dialogue, but I think it's all there.

The list is sorted by hash value.
## Post #36
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-28T18:23:47+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Tried out the unicode characters, and I'm happy that the game can use all unicode characters, no need for tricky letters and such (by this I mean that some games require ő, but there's no such character, so I use ô or maybe õ instead, but here it's not needed thankfully).

[Link to the image](http://kepfeltoltes.hu/150528/2015-05-28_00001_www.kepfeltoltes.hu_.jpg)
## Post #37
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-28T18:28:29+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

We have a problem with special characters. Some lines contain "next line" characters and when converted to txt or xls it will be impossible to leave them. I need to replace them with something.
## Post #38
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-28T19:38:44+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> We have a problem with special characters. Some lines contain "next line" characters and when converted to txt or xls it will be impossible to leave them. I need to replace them with something.

Exporter ready.

In this cases I always use × or ¤, because those can't be found normally in files. Here you can find this, but if you'd define this "next line" character with both chars next to each other (like ×¤), then it wouldn't be a problem I guess.

Thanks for the exporter, will look through the text and see how I can translate it.
## Post #39
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-28T19:52:50+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

I have no time or experience to parse utf-8 strings, so i just replaced 0xD to 0xF0 and 0xA to 0xF1. If the source file will contain either of these bytes, it will not work.

This is exporter/importer. If the parameter is txt file, it will do import. If it is ".strings", it will do export.
[bitsquid_txt.rar](https://xentaxbackup.github.io/file/9239_bitsquid_txt.rar)
## Post #40
- Username: TheReaperCooL
- Rank: advanced
- Number of posts: 60
- Joined date: Sun Apr 18, 2010 3:18 am
- Post datetime: 2015-05-28T20:28:54+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> I have no time or experience to parse utf-8 strings, so i just replaced 0xD to 0xF0 and 0xA to 0xF1. If the source file will contain either of these bytes, it will not work.

This is exporter/importer. If the parameter is txt file, it will do import. If it is ".strings", it will do export.

Thanks dude, you rock!

Some examples of trying out the program:

[Some main menu text](http://kepfeltoltes.hu/150528/13189002082015-05-28_00003_www.kepfeltoltes.hu_.jpg)

[Testing weapon descriptions](http://kepfeltoltes.hu/150528/2015-05-28_00002_www.kepfeltoltes.hu_.jpg)

[Testing tutorial descriptions](http://kepfeltoltes.hu/150528/2015-05-28_00004_www.kepfeltoltes.hu_.jpg)
## Post #41
- Username: mystvilla
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 21, 2010 1:31 pm
- Post datetime: 2015-05-29T08:01:02+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

hey,
nice work daemon1!
btw you said the audio files are packed into one bank file... how do you extract these?

thanks
## Post #42
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-29T16:43:49+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from mystvilla
>
> the audio files are packed into one bank file... how do you extract these?

You need to write a tool to extract them. The format is simple: filename hash, offset, size - for every sound.
## Post #43
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-05-30T07:32:16+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

I can't find where they store filenames yet. Also there are at least 2 types of banks in different games: those with .stream files, and without them.
## Post #44
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-01T17:31:03+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

It seems there are no sound filenames left in this engine, because it doesn't need them. It works with audio events and sound file hashes. Some events may use many sounds in random, or many different events may use the same sound. Like this:

audio event "ring_activate" ---> sound file 45A40FC9
audio event "relic_activate" ---> sound file 45A40FC9

So i think we can only extact them with no filenames.
## Post #45
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-06-02T17:36:37+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Is there a way to make a compiled list of audio events and group them by sound file ID?
## Post #46
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-03T16:21:01+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from brendan19
>
> Is there a way to make a compiled list of audio events and group them by sound file ID?

Yes I think it's possible.
## Post #47
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-03T20:45:39+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Yet it will be tricky. Here's the master ID list for gauntlet: [http://pastebin.com/bJ5Q1wzt](http://pastebin.com/bJ5Q1wzt)
## Post #48
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-04T17:08:45+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Alright, here's what we have for gauntlet:

1939 audio events.
They use links to 2965 sounds (some of these are groups, and some duplicates)
These 2965 sounds use links to 2151 sound files.

I've unpacked all sounds from all sound banks, total of 2139 files (876 wav, 1263 ogg)

Then I checked their IDs, and all of them are used in events.
Also we have 12 events that have links to missing files (probably not used in game?)
## Post #49
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-06T10:22:59+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

New version of all tools, audio bank unpacker included, no filenames yet.

[viewtopic.php?p=106336#p106336](http://forum.xentax.com/viewtopic.php?p=106336#p106336)
## Post #50
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-06T19:57:23+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

If anyone's interested, here's the list of 844 voice audio events for Gauntlet that I was able to find today.

[http://pastebin.com/saYVGsfX](http://pastebin.com/saYVGsfX)
## Post #51
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-06-07T17:01:40+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Tools updated:

- There was an error with stream unpacking.
- Batch file added to rename all 1187 known audio files to proper filenames. As they are not the real original filenames, but just guessed from events names, I decide not to put this in unpacking process.

I think that's enough for this engine. If anyone needs anything else, or more resource file names, let me know.
## Post #52
- Username: portify
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 05, 2015 4:44 am
- Post datetime: 2015-07-04T21:01:36+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Has anybody had any success with unpacking Magicka 2 sounds?
## Post #53
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-05T06:13:15+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Sure I unpacked them.
## Post #54
- Username: portify
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 05, 2015 4:44 am
- Post datetime: 2015-07-05T07:50:46+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

How did you go about doing that? I don't know which file to use _unp on if any (but I did successfully extract all the dds textures for particles in the process). I tried _timpani on all the file pairs that had a .stream and got an ArithmeticException on all of them. Not sure which file to use that on either. None of the hashes related to sounds seem to have a file in the Magicka 2 assets.
## Post #55
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-05T10:05:48+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

There are many packages with timpani banks here. The total size is not that big, just unpack all of them with a batch.

for %%a in (*.) do bitsquid_unp "%%a"

Then use _timpani extractor on banks extracted. Don't forget the second parameter. In this game streams are not used for sounds, only for videos, but you must type something anyway, for example:

bitsquid_timpani 238476234.timpani_bank 0
## Post #56
- Username: bolvan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 30, 2015 6:38 pm
- Post datetime: 2015-08-30T12:51:42+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Can you pls help with finding music in Magicka 2.
I extracted oggs and wavs from timpani files.
Found very few music files. Found just one wav of "Dunka, Dunka"  29 seconds long. Obviously not full.
## Post #57
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-30T14:25:52+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

As I remember, music in magicka2 was not in timpany banks, but in separate files. Those must be big, you can't miss them.
## Post #58
- Username: bolvan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 30, 2015 6:38 pm
- Post datetime: 2015-08-31T05:32:45+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

"Magicka 1 Orchestral soundtrack" folder is just a bonus not used by the game.
All game data is in the 'data' folder. Aside from files without extensions I see some *.stream files. May be there but format is unknown.
## Post #59
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-31T15:13:46+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from bolvan
>
> files without extensions

Unpack all those, music must be there.
## Post #60
- Username: bolvan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 30, 2015 6:38 pm
- Post datetime: 2015-08-31T17:05:01+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from bolvan
>
> "Magicka 1 Orchestral soundtrack" folder is just a bonus not used by the game.
All game data is in the 'data' folder. Aside from files without extensions I see some *.stream files. May be there but format is unknown.

I suspect E4206F5415A996E6.timpani_bank.stream.
But it does not contain regular ogg files.  It does contain some OggS frames, none of them have "first page" flag but some have "last page" flag.
I written my own ogg extraction utility in C and it does well against non-"stream" timpani banks.
## Post #61
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-31T17:39:21+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from bolvan
>
> I written my own ogg extraction utility in C and it does well against non-"stream" timpani banks.

Why making your own utilities when my utility extracts ALL banks, including stream, and non-stream?
## Post #62
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-08-31T17:41:50+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> bitsquid_timpani [bank file name] [stream file name]

Audio bank unpacker for other games. It requires stream name too. If there's no stream for some particular bank, just type anything you want for second parameter. If you run it with 1 parameter, the result is unpredictable. If the stream will not be present, it will work, but files may be cut, having only some first seconds of sound.
## Post #63
- Username: bolvan
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 30, 2015 6:38 pm
- Post datetime: 2015-08-31T18:53:11+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

OK, i've got the idea. Seems like first 9 OggS chunks in extension-less file, rest is in stream.
I successfully extracted the music, thanx !
Your utilities work well if run correctly but miss help text and crash if anything is wrong.
So i didnt realize everything first and did some own job. It took not too long, no problem.
My prog is able to search any binary, find music files there and extract them. May be if I find some unknown container it will be helpful.
## Post #64
- Username: qwerty0ytrewq
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 01, 2014 1:41 pm
- Post datetime: 2015-11-07T19:05:55+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Any ideas on the model files format? Textures are plain [DDS](https://en.wikipedia.org/wiki/DirectDraw_Surface), but what's about models? I'd like to use these as placeholder models in Unity3D.
## Post #65
- Username: Kathie
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Aug 24, 2016 4:30 pm
- Post datetime: 2016-08-24T12:09:12+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from bolvan
>
> OK, i've got the idea. Seems like first 9 OggS chunks in extension-less file, rest is in stream.
I successfully extracted the music, thanx !
Your utilities work well if run correctly but miss help text and crash if anything is wrong.
So i didnt realize everything first and did some own job. It took not too long, no problem.
My prog is able to search any binary, find music files there and extract them. May be if I find some unknown container it will be helpful.
Is there any chance you can share your prog? Cause i seems to not get how to use that "bitsquid", all i get after some hours is a bit of chunks like choped 11 oggs (some of them didn't even open), and 2 wavs. And that's it. Damn i wish there were atleast one good help post on how to manage it.
## Post #66
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-24T15:13:33+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from Kathie
>
> all i get after some hours is a bit of chunks like choped 11 oggs (some of them didn't even open), and 2 wavs. And that's it.

What game you extracting?
## Post #67
- Username: Fyren
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 10, 2007 2:59 pm
- Post datetime: 2017-02-04T21:03:52+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from daemon1
>
> The latest version of all tools. Tested on Showdown Effect demo, Gauntlet, Wizard Wars, Helldivers. May also work with other Bitsquid games and also the new Autodesk Stingray Engine games like Warhammer: End Times.

daemon1, thanks for making this tool.  Is there any chance of a Linux version or possibly providing the source so I can try porting it myself?
## Post #68
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-02-06T15:52:09+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

> Reply from Fyren
>
> daemon1 wrote:The latest version of all tools. Tested on Showdown Effect demo, Gauntlet, Wizard Wars, Helldivers. May also work with other Bitsquid games and also the new Autodesk Stingray Engine games like Warhammer: End Times.

daemon1, thanks for making this tool.  Is there any chance of a Linux version or possibly providing the source so I can try porting it myself?

check your PM
## Post #69
- Username: MatiasGray
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 09, 2017 9:25 am
- Post datetime: 2017-02-09T12:17:15+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Daemon1, thank you for unpacker, great work!
I managed to extract some files:

Anyone knows how to open they? I tried Autodesk Stingray and don't succeed. I want to get 3d models from Helldivers for printing.
## Post #70
- Username: Luriam
- Rank: advanced
- Number of posts: 46
- Joined date: Mon Jun 25, 2012 3:44 pm
- Post datetime: 2018-09-29T14:46:02+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

I'm sorry for necroing this thread, but I was wondering if anyone here can extract the sounds from [this](https://puu.sh/BCU8t/08602c938d.zip) particular .stream file.

And just like some other people pointed it out here on the forum, there's also a file with no extension, and a "patch_001" file - all with the same name. So I attached those too, just in case.

Thank you very much! And just in case anyone's wondering these come from a game called Vermintide 2.
## Post #71
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-07-22T13:59:14+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Yeah, I'm looking to get the files out of Vermintide 2 as well. I have here some examples. They don't seem to work with the current version of the tools. Although the Steam version does grant you a 'modding tools' pack, there's nothing that seems to be able to extract them included, and most of the readme is just scripting mumbo-jumbo that is more about just writing scenarios rather than actual asset modding.
## Post #72
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2020-07-29T19:49:08+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

Sorry, I did 'a dumb' and completely forgot to link the example files for Vermintide 2. Here they are!
[https://www.dropbox.com/s/3qw9wqauglt2p ... 9.zip?dl=0](https://www.dropbox.com/s/3qw9wqauglt2pkd/00f1a958e7d2dad9.zip?dl=0)
## Post #73
- Username: hoovytaurus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 03, 2020 6:08 pm
- Post datetime: 2020-08-06T05:44:59+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

hey chums, was looking to extract Helldivers sound files and while i realize this is THE tool to do it with i'm not 100% on the process:

1. extract "File"s, inside are timpani_bank files
2. timpani_bank files basically point to the sound in the loose .stream files

there's a few steps missing, obviously.

1. how do i know which timpani_bank "points" to what .stream file? i got lucky and managed to get some random file just to test out but this obviously isn't sustainable
2. the result is a .wav with no name, just a random string. how do i get a usable filename, what's the process for that?

some misc questions:

1. is there a way to automate this for example with a .bat file? im too dumb to know how to say "file with no extension" for example
## Post #74
- Username: ZEFIR0011
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Nov 17, 2020 5:29 am
- Post datetime: 2020-11-16T22:02:29+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

the script doesnt working. Im put it in game files (content) Renamed to bitsquid_unp [038bbacc4ce89296] - start and nothing appears.
Can someone help me?
## Post #75
- Username: Zekfad
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 16, 2018 10:45 pm
- Post datetime: 2023-07-16T19:38:41+00:00
- Post Title: Re: Magicka 2/Wizard Wars, Showdown Effect, Gauntlet files

I've reversing Helldivers package and save file formats, save had some ambiguous paddings, but I was able to successfully dump and pack back modded save.
Package is modifiable as well, but I've found some interesting parts:
There are some "variants" of the textures, where there are multiple files in a single resource (meaning they have same path), I've not figured what flags in these variants mean.
Scripts are modifiable as well, but I haven't found good decompiler for LuaJIT that would produce more info, some slots are not decoded well.

I'm looking for someone to help me with remaining pieces.

I've published formats I was able to reverse for ImHex editor on my GH: [save.hexpad](https://github.com/Zekfad/helldivers/blob/master/formats/save.hexpat), [exploded_package.hexpat](https://github.com/Zekfad/helldivers/blob/master/formats/exploded_package.hexpat).

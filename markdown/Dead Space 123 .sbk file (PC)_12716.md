## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-03-25T16:34:31+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

Dead Space stores big audio files as separate .exa.snu files in first two .DAT archives. These can be converted with towav or "ealayer3 -i 32", depending on the format.

But thousands of small sound are stored in many .sbk files across all other .DAT archives. These are all generic sounds: Isaac's steps, gunshots, interface, costume, necromorphs, etc. There are hundreds of .sbk files in the game, one for each kind of enemy, npc, weapon, level and sublevel. So many sounds duplicate.

Here's a simple tool written on c# that will extract all sounds from .sbk. Enjoy.
Extracted sounds can be converted to mp3 with ealayer3.

This one works with DS1 & DS2.

To extract all sounds from the game you need to follow the steps:
step 1 - unpack .dat files
step 2 - unpack .str files that have sfx in them
step 3 - unpack .sbk files with this tool
step 4 - use ealayer3 or Xas_decode to decode them
[ds2_sbk.zip](https://xentaxbackup.github.io/file/8885_ds2_sbk.zip)
## Post #2
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-04-01T17:53:56+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

Here's the version for DS3.

The files extracted can only be converted with my new version of Ealayer3 that you can find here: [viewtopic.php?p=104766#p104766](http://forum.xentax.com/viewtopic.php?p=104766#p104766)

This is because they are version 7 with header B, which was not supported before.

It will not work correctly with DS2. I will try to make universal version later, but for now, please use corresponding versions.
[ds3_sbk.rar](https://xentaxbackup.github.io/file/8920_ds3_sbk.rar)
## Post #3
- Username: Predatory Lootboxes
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Nov 06, 2008 7:51 am
- Post datetime: 2015-07-19T10:36:05+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

What are the extra actions needed for DS1/DS3 using EAlayer3?
## Post #4
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2015-07-20T13:47:39+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

For DS1 you need Xas_decode (latest version here [viewtopic.php?p=107650#p107650](http://forum.xentax.com/viewtopic.php?p=107650#p107650))

For DS3 you need new version Ealayer3 as said above.
## Post #5
- Username: kodznak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 02, 2017 4:58 pm
- Post datetime: 2017-07-02T09:48:50+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

Ok, guys, im think i doin it wrong or... i dont know.
I hawe all those tools and all big .DAT files.
I use Gibbed.Visceral.BigViewer.exe to extract all .str files
Next im trying to use xas_decode.exe and it crashes leawing me with 0bite *.wav file
I need simple necromorph sounds and some beautiful screams from apartments. 

Anyone can help me?
(please)
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-02T09:52:46+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

> Reply from kodznak
>
> Next im trying to use xas_decode.exe

On which file you're trying it?
## Post #7
- Username: kodznak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 02, 2017 4:58 pm
- Post datetime: 2017-07-02T22:00:10+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

> Reply from daemon1
>
> kodznak wrote:Next im trying to use xas_decode.exe

On which file you're trying it?

Many of *.str, *.toc, from *.DAT
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-03T06:08:01+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

you missed step 2 - unpack .str files that have sfx in them
## Post #9
- Username: kodznak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 02, 2017 4:58 pm
- Post datetime: 2017-07-03T11:34:18+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

> Reply from daemon1
>
> you missed step 2 - unpack .str files that have sfx in them

Can you tell me how i can do it?
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-04T07:48:55+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

Gibbed tools
## Post #11
- Username: kodznak
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Jul 02, 2017 4:58 pm
- Post datetime: 2017-07-04T16:41:30+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

> Reply from daemon1
>
> Gibbed tools

Thanks a lot! It worked perfectly. 
I have around 10 000 sounds now! O_o
## Post #12
- Username: Laenthor
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 06, 2018 11:50 am
- Post datetime: 2018-03-06T04:17:38+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

I want to extract the sfx out of the str files but I can't find Gibbed tools anywhere. Someone wants to send me a link?
## Post #13
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-03-06T06:29:41+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

> Reply from Laenthor
>
> I want to extract the sfx out of the str files but I can't find Gibbed tools anywhere. Someone wants to send me a link?
not sure if its last version, or what you need: [https://www.saintsrowmods.com/forum/att ... 6-7z.9683/](https://www.saintsrowmods.com/forum/attachments/gibbed-tools-rev-96-7z.9683/)
## Post #14
- Username: TheObserver
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 14, 2018 4:46 am
- Post datetime: 2019-10-04T16:33:02+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

I hate to be the guy that necro's a post, and I apologize. I have spent hours trying to piece together everything from getting Gibbed.Visceral tools to work, all the way up to extracting files and converting them. I have exhausted my searches to the point that I'm necroing this post. Again, I apologize, but I have some questions. 

I've been able to convert most of the .exa.snu files from .DAT0 and .DAT1 from Dead Space 2. My entire reason for wanting to rip these sounds is because I want to sample Nicole's audio. When I extracted her Dementia .snu files, I am completely unable to convert them. TOWav cannot convert them. It's as if they don't exist or are readable, and EALayer3 says they are not a readable format, too. I am at a loss as to what I should do next. I don't know if her dialogue for what I'm looking for is even in these files, and aren't sure where I'd find her final boss dialogue, but I'm learning and I'm hoping someone could help me with this. I'm mostly looking for her "MAKE US WHOLE" line, but getting everything from the game files would be fantastic as well. 

Also, is there a genuine tutorial for all of this stuff? There needs to be a megathread where it covers compiling Rick's tools, all the way up to extracting everything, because some of this is super confusing to people who want the sounds, but don't understand the technical stuff to obtain binaries and everything else. 

Thanks in advance if anyone can help.

Edit: I'm tired and forgot a couple details. Namely mentioning TOWav didn't work and that I'm trying to extract DS2 sounds.
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2019-10-04T17:47:03+00:00
- Post Title: Dead Space 1/2/3 .sbk file (PC)

try

ealayer3 -i 32 sample.snu
## Post #16
- Username: TheObserver
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 14, 2018 4:46 am
- Post datetime: 2019-10-04T18:22:18+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

> Reply from daemon1 ↑Sat Oct 05, 2019 1:47 am at Sat Oct 05, 2019 1:47 am
>
> 
try

ealayer3 -i 32 sample.snu

Which way should I do this? ealayer3 flickers on screen for about 3-5 frames before disappearing. I've gone so far as to run this through the CMD Prompt in admin mode, attempting to call the parameters everyone's mentioned. I get an error that a file "libmpg123.dll" isn't present, so I add that, which allows it to run for half a second. I've even tried to use a batch file calling for the program and using every file with the .snu file type. The only way I've been able to get anything to convert is one file at a time by dragging it on top of the ealayer3 executable.
## Post #17
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-04T18:44:32+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

> Reply from TheObserver ↑Sat Oct 05, 2019 2:22 am at Sat Oct 05, 2019 2:22 am
>
> The only way I've been able to get anything to convert is one file at a time by dragging it on top of the ealayer3 executable.
How about do the following.
for batch of files located in same folder, inside a text file using notepad copy/paste code below and change extension to bat or cmd instead of txt:

```
FOR %%a IN (*.extension) do ealayer3.exe -i 32 "%%a"
```

or to run recursively in all folders/subfolders do:

```
FOR /r %%G IN (*.extension) do ealayer3.exe -i 32 "%%G"
```

also make sure the libmpg123.dll is at root folder where ealayer3.exe is.
Obviously change extension to what ever your files have.
## Post #18
- Username: South Village
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 20, 2019 2:25 am
- Post datetime: 2019-11-19T18:54:48+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

> Reply from daemon1 ↑Sat Oct 05, 2019 1:47 am at Sat Oct 05, 2019 1:47 am
>
> 
try

ealayer3 -i 32 sample.snu

Hi! Please tell me how to extract sfx from str files in Dead Space 3. Str files I have already extracted. Please! Help!
## Post #19
- Username: OpticalFox
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 29, 2020 1:36 am
- Post datetime: 2020-02-28T19:35:15+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

Gibbed's extracting tools don't work.  There's no exe to run them.  Is there any other way?
## Post #20
- Username: marcoxD95
- Rank: n00b
- Number of posts: 10
- Joined date: Mon May 27, 2019 5:14 am
- Post datetime: 2020-10-26T23:32:00+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

Weirdly enough this WAV snu decoder and ealayer3 dont work on the file I have. When I run the bat files absolutely nothing happens. My file is named mx_chase_01.exa.snu. I am actually trying to rip Soundtrack files from the game since I wasnt able to get a music rip from Dead Space 3 anywhere. Joshw also doesnt have one. I am not sure if music files are not convertable or if I do something wrong. Is there any other way to get these snu and exa files to play? VGMStream cant handle them it seems.

All I get when I try to decode this snu file is "'wav.exe' is not recognized as an internal or external command" in CMD. Is this tool not working on Windows 10?
## Post #21
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-11-13T17:19:48+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

> Reply from marcoxD95 ↑Tue Oct 27, 2020 7:32 am at Tue Oct 27, 2020 7:32 am
>
> 
Weirdly enough this WAV snu decoder and ealayer3 dont work on the file I have. When I run the bat files absolutely nothing happens. My file is named mx_chase_01.exa.snu. I am actually trying to rip Soundtrack files from the game since I wasnt able to get a music rip from Dead Space 3 anywhere. Joshw also doesnt have one. I am not sure if music files are not convertable or if I do something wrong. Is there any other way to get these snu and exa files to play? VGMStream cant handle them it seems.

All I get when I try to decode this snu file is "'wav.exe' is not recognized as an internal or external command" in CMD. Is this tool not working on Windows 10?

Chances are why it doesn't work is because that song is from Dead Space 1 and probably under DS1 file format.
## Post #22
- Username: JohnFont49
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Nov 13, 2020 9:23 am
- Post datetime: 2020-11-14T05:10:46+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

> Reply from marcoxD95 ↑Tue Oct 27, 2020 7:32 am at Tue Oct 27, 2020 7:32 am
>
> 
Weirdly enough this WAV snu decoder and ealayer3 dont work on the file I have. When I run the bat files absolutely nothing happens. My file is named mx_chase_01.exa.snu. I am actually trying to rip Soundtrack files from the game since I wasnt able to get a music rip from Dead Space 3 anywhere. Joshw also doesnt have one. I am not sure if music files are not convertable or if I do something wrong. Is there any other way to get these snu and exa files to play? VGMStream cant handle them it seems.

All I get when I try to decode this snu file is "'wav.exe' is not recognized as an internal or external command" in CMD. Is this tool not working on Windows 10?

I can't even get ealayer3 working on Dead Space 1, and I'm on Windows 7... tried all sorts of formats with the batch file (that i -12 and -32 stuff) and every version of ealayer3 and the sbk.exe I can find (in case it's corrupting the files) but all I get are many errors :/

Kinda sucks when all of the feedback sounds I need are presumably in these global assets, they weren't in audiostreams. Is there no way to open file formats from the original despite all audio apparently being exportable??
## Post #23
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2020-11-15T16:50:25+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

Don't use ealayer on DS1, use xas_decode

[http://www.mediafire.com/file/tnisaj3el ... v.rar/file](http://www.mediafire.com/file/tnisaj3elv77ajy/ds1_.snu_to_wav.rar/file)

I don't know if you can even find most of the extraction tools for the Dead Space franchise anymore, so I have stored all known ones to my mediafire archive and my HDD.
## Post #24
- Username: glanbalf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 12, 2021 4:04 pm
- Post datetime: 2021-02-13T13:37:30+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

Hi @MaZTeR , I just wanted to thank you for your files, it just worked perfectly! I simply copy-pasted all the .snu files in another folder, executed your file, and it was all done.

I was looking for a way to gather good sounds in order to master a space horror RPG with my friends, now thanks to you I'm able to use the Dead Space ones, which left me a strong impression back in the days.
## Post #25
- Username: TyapLyap
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 01, 2019 4:37 am
- Post datetime: 2022-01-27T19:33:44+00:00
- Post Title: Re: Dead Space 1/2/3 .sbk file (PC)

Someone know how deconvert .exa.snu files from Dead Space 2?
(Not all .snu files deconverts)
I can deconvert DS1 .snu files,DS3,but not DS2 .exa.snu files.

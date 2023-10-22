## Post #1
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-26T11:05:47+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-26T11:50:05+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

I look at it, and it starts off by giving a nametable, and then what seems to be another table after that.

So far from what I can make out is that the files are compressed/encrypted (zlib? LZ?)
## Post #3
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-27T01:25:57+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Seems to be easy... filenametable followed directly by the zlibbed data, offzip works but i don't know if the filetable is in correct order... hard to say with only one archive   

i think chrrox will write a qbms script in a minute
## Post #4
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-27T05:16:04+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-27T07:56:34+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

It is zlib compressed, wait for chrrox quickbms script... if you keep the folder structure intact the game SHOULD load modified files 

NIF's are Models
## Post #6
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-07-27T12:31:13+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

i took a look at patch's files and at a closer look they're not so simple as it seems. 
First of all, not all files are compressed and the pointer table is not very ordered (it's not a real POINTER table, it's a FILELENGTH table, we just have the offset of the first zlibbed file) and it seems that in the archives there's more shit after the files. It needs a a longer study
## Post #7
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-28T05:59:56+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

ah damn...

i just took a quick peek and thought... LOL easy   

gonna check it out some more when im back from work
## Post #8
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-28T06:22:12+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

So it's a bit more complicated than what it first appeared to be, interesting nontheless though I also thought it would be a rather quick affair to work out how the file was packed or encrypted but I'm not exactly good at these things and it was just what I thought after a quick view of some of the archives in a simple hex editor. (Based on that all files appeared as readable albeit I guess that's the "header" and the actual info is that compressed and perhaps even encrypted data further into the file or how to say.)

Still I hope it can be sorted out eventually even though it might take some time. 
(As to not be misunderstood and to be clear I'm not in a hurry or anything and I'm happy of any progress made with this and now since it seems proven to be more difficult than I first believed it's obvious it might take more time to work out the format and eventually be able to extract it in some way so once again thanks for looking into it.)
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2009-07-28T13:31:00+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

So we've established that it IS zlib. And we have a file name table followed by a file length table. Then we can also assume that the data runs in that order, otherwise the game itself would probably get confused. Afterall, it does need to have some logic.
## Post #10
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-28T13:42:24+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Well if any other files are required I can provide those as well, can't think of much else though aside from the actual EXE if that would somehow provide some insight. (Perhaps in how the game reads the archives?)

In terms of files it's actually pretty light (Outside of what might be in those .dv2 archives.), aside from the EXE it only uses a NxCharacter.dll and PhysXCore.dll file for the NVIDIA PhysX accelerated functions and then it's followed by the .dv2 files in the "\Data\Win32\Packed" folder and a bunch of pre-rendered movies in the "\Data\Win32\Video\" folder (WMV format.)

Unsure if this helps in ayway though I'll try to provide if anything else is required though the current .DV2 files are probably OK. 
(Once one of them is extractable the others should work using the same method as I see it.)
## Post #11
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2009-07-28T13:55:41+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Bad news    . Archives are more difficult than I thought. For example I extracted manually a couple of zlibbed files which should have been 1 nif and 2 xmls but they were 3 nif so it means that not all files are listed. Plus, GUI.dv2 has some dds compressed (and tabled) and some aren't. 

> And we have a file name table followed by a file length table

nope...the filelength table is not right, look at this, it's a dump i made from MainDataPlatform.dv2 that should be [FILENAME][POINTER]:

```
Win32\CompiledAssets\AssetDataDescriptors.xml  -  16609
Win32\Effects\ItemDescriptors.xml  -  22d5d
Win32\Items\Sizes.xml  -  6e73b
Win32\Effects\Sizes.xml  -  97eaa
Win32\FlyingFortresses\flyingfortressanimationdata.xml  -  9991b
Win32\Characters\TemplateStats.xml  -  b4683
Win32\Characters\Sizes.xml  -  e2137
Win32\Scenery\ItemDescriptors.xml  -  e60b7
Win32\Textures\_NormalMap.nif  -  f6b32
Win32\FlyingFortresses\Sizes.xml  -  1336b5
Win32\World\WorldSizes.xml  -  135a9e
Win32\Effects\effectanimationdata.xml  -  14694c
Win32\Textures\_White.nif  -  178380
Win32\DungeonBlocks\dungeonblocks.xml  -  1796ac
Win32\Textures\Checkers.nif  -  18057e
Win32\Scenery\Sizes.xml  -  1b32de
Win32\Items\ItemDescriptors.xml  -  1b35cc
Win32\Textures\Textures.bin  -  1b434d
Win32\Items\itemanimationdata.xml  -  1da958
Win32\Characters\ItemDescriptors.xml  -  1ddabc
Win32\Textures\_Gray.nif  -  20810c
Win32\Textures\_Black.nif  -  22cae2
Win32\FlyingFortresses\ItemDescriptors.xml  -  22e717
Win32\Characters\CharacterAnimationData.xml  -  23be08

```


> Well if any other files are required I can provide those as well, can't think of much else though aside from the actual EXE if that would somehow provide some insight.

Latest Securom >_<
## Post #12
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-28T14:22:04+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Ah, you're right about that, the protection does things to the EXE so I guess it's not as usable as I thought it was.
(It wraps it or what it's called, probably some encryption as well plus other stuff.)

Interesting progress though, will be fun to see what this will lead to, hopefully the compression/encryption doesn't become too difficult to handle but I'm not really good at these things so I can't really say much about it.
(Initially I had simply planned to extract the "Dialogs.dv2" file - Not uploaded as it's 700MB - and change the layout of what seems to be - \German\ to \English\ to make the localized data in "MainDataStreaming.dv2" usable without going trough every XML file manually but as it seems to be normal LUA and XML files more editing might be possible such as LOD levels and perhaps even NIF models eventually, textures seem to be normal .DDS - Most of which are in a separate .dv2 file at 1500 MB - but TexMod has worked great for that already.)

I guess that should the files become extractable others can also utilize it to further mod the game and alter data. 
(Albeit once again I don't know much about this so unfortuantely I don't have any ideas or suggestions that would help, might just be a matter of time though, someone is bound to figure out the file format eventually but this is already showing good progress as I see it with various data and info such as it using zlib plus part of the file header and such.)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-28T21:30:35+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Those anti-piracy implementations do nothing to stop piracy. What they do, however, is annoy the end-user extremely. A useless effort and a waste of money for the producers. It's about time they see that (yet again, as history seems to repeat every 3 to 4 years, already for decades....). Sorry for the off-topic message, but I had to get my anger out
## Post #14
- Username: madpaddy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 28, 2009 11:48 pm
- Post datetime: 2009-07-29T13:29:31+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Anybody made any headway into getting this game into english .
## Post #15
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-29T14:04:36+00:00
- Post Title: Divine Divinity 2 ".DV2" file.

Well from what I've read on this and other forums the file format is some standard zlib compressed format but the actual files aren't proper but instead some game engine specific format for streaming so even if it says .nif or .dds it'll not work like a standard .dds or .nif file (Some gamebryo technical thing or something perhaps?)

Still what I would have expected to work was to change the \Data\Win32\Character\Dialogues\German into *\English and hope the scripts and everything worked as intended however this seems more complicated now as there's a Filename.dialouge file for scripts during conversations and a FilenameGerman.dialogue for lipsynch data or something from what I've been told so all those might need to be renamed as well.

Even so the person who mentioned this said the game didn't really like unpacked files and had problems reading them so it sounds like it would be a bit of a problem though I do have a few ideas albeit they would require all of those .dv2 files to be unpacked in order to be tested. (There's a -data launch parameter which might be used for when not everything is packed in archives, causes crashes at the moment though and perhaps it won't be required when everything is unpacked even though it's a bit cumbersome workaround.)

Easiest solution as I see it would have been to play in the English language, switch to German just before when the game goes into one of those infinite loading screen loops and then switch back to English afterwards, bit of work but would have functioned aside from the savegame teating English and German saves as incompatible due to using different languages. 

Still something has to work though first the files must get extracted in some way.
(Supposedly Offzip worked but the resolution hex location named .dat files aren't really optimal.)
## Post #16
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-29T14:27:37+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Hello guys!
I`ve got an extractor utility for these .dv2 files.
There it is: [http://www.sendspace.com/file/942i5p](http://www.sendspace.com/file/942i5p)

This utility succesfully extracts all the files in specified archive.
## Post #17
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-29T14:30:30+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Nicely done and thanks. 

EDIT: Very useful, albeit the "Textures.dv2" file isn't unpacked correctly as each file is 0 kb, completely blank that is, other than that it works great. 

EDIT: Seems to be correct that the game only loads some files once unpacked, it's never quite as easy as expected, perhaps reversing the unpacking process to pack files would work to force the game to load the new data?
## Post #18
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-29T15:11:39+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

.dv2 archive structure:

[04 00 00 00].........id tag?
[xx]....................0 - packed data aligned to 0x8000 (32768) bytes boundary; 1 - not aligned, continuous stream
[01]....................don`t know
[xx xx xx xx].........offset to start of packed data 
[xx xx xx xx].........length of filename array
[...]....................array of null terminated filename strings
[xx xx xx xx].........number of files

[xx xx xx xx].........offset to packed data...\
[xx xx xx xx].........packed data length........} repeat for each file
[xx xx xx xx].........unpacked data length.../

[...]....................packed data stream, aligned or continuous (depends on data align byte)

Many thanks to camrade IvanAls for writing the program and getting this information
## Post #19
- Username: madpaddy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 28, 2009 11:48 pm
- Post datetime: 2009-07-29T15:54:33+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Nice to see some progress,just wish i was able to help but most of this is above my knowledge level .Keep up the good work guys  for your hard work lol
## Post #20
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2009-07-29T17:08:14+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

good job
## Post #21
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-29T18:17:31+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

I did exactly what you said, but the game does not see unpacked folders/files.
Even with the original value - "German" - in the system registry key HKLM\SOFTWARE\Larian Studios\Divinity2\Language, and Dialogs.dv2 file deleted\renamed the game runs without voices\lipsync...
It works only with it`s original packed archives, but won`t read unpacked data in these directories: 
Divinity II - Ego Draconis\Data\Sound\Soundbanks\Win32\English\
Divinity II - Ego Draconis\Data\Win32\Characters\Dialogs\

But why? Maybe, you did some other modifications to the original game? Registry keys? Command line options?
## Post #22
- Username: madpaddy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 28, 2009 11:48 pm
- Post datetime: 2009-07-29T18:43:36+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Yeh it doesnt seem to work the way you say m8,if you can please post a step by step fools guide that would be great cheers.
## Post #23
- Username: madpaddy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 28, 2009 11:48 pm
- Post datetime: 2009-07-29T19:07:17+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Ok this is how i got it working"""i think lol"" follow those instructions  from before but i removed the diologs.DV2 file from the win32/ packed /foulder ,i allso copy these foulders,from the sound soundbanks win32 foulder copy the english foulder then paste it too data/win32,and also paste it to data/win32/packed.I also copyed this foulder from the download link its the edited dialogs with the english extention,i copyed it to data/win32/characters/dialogs,and also copied it to data/win32/packed,so in the packed foulder you have a characters foulder with the dialogs foulder inside it.Hope this helps i cant be sure this will work ,i have files and foulders all over from messing with it lol,but it was after doing this that it started working.Dont forget to alter the reg with regedit search for divinity and alter any de to en and any German to English.

..Ps  I also have the german 1.01 patch installed not sure if that makes a difference or not.
## Post #24
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-29T19:33:53+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

What I did was that I unpacked the Dialog.dv2 archive, moved both resulting folders back to the game folder\Data\

Then I went into the "\Data\Sound\Soundbanks\Win32\" folder and renamed the "German" folder to "English" to add access to the "sound bank" files (Compressed files with sounds in them, .bnk) as the original English localization won't be available until it's release in September sometime.

After that I went back and then into the "\Win32\Characters\Dialogs" folder where I renamed all the types of "FileGerman.dialog" to "FileEnglish.dialog" (The archive I uploaded here as renaming all files takes a bit of time.)

Then I altered the Larian key in the registry or rather the string value "Language" from German to English, game will start with English text and when switching voice types in the character menu they'll play a German voice audio preview.

Other than that nothing is done or altered with the game or game files (Dialog.dv2 is present as well.) though I also use the 1.01 patch.

If the above folder rename won't work from "German" to "English" try with "English(US)" instead.
## Post #25
- Username: madpaddy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 28, 2009 11:48 pm
- Post datetime: 2009-07-29T19:40:16+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

> Reply from jbeckman
>
> What I did was that I unpacked the Dialog.dv2 archive, moved both resulting folders back to the game folder\Data\

Then I went into the "\Data\Sound\Soundbanks\Win32\" folder and renamed the "German" folder to "English" to add access to the "sound bank" files (Compressed files with sounds in them, .bnk) as the original English localization won't be available until it's release in September sometime.

After that I went back and then into the "\Win32\Characters\Dialogs" folder where I renamed all the types of "FileGerman.dialog" to "FileEnglish.dialog" (The archive I uploaded here as renaming all files takes a bit of time.)

Then I altered the Larian key in the registry or rather the string value "Language" from German to English, game will start with English text and when switching voice types in the character menu they'll play a German voice audio preview.

Other than that nothing is done or altered with the game or game files (Dialog.dv2 is present as well.) though I also use the 1.01 patch.

If the above folder rename won't work from "German" to "English" try with "English(US)" instead.

Mmm strange thats what i did at first m8 even though i have it working with english text i get no dialog sounds altall ,ill try a reinstall tomorrow and see if i can get it going the way you say cheers.
## Post #26
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-29T19:46:17+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Strange, in the "\Divinity2\Data\Sound\Soundbanks\Win32" I have three folders (English, English(US) and German) but only the one named English should be required and it contains the extracted .bnk files. (It takes a bit of space though I guess you could try to have both English and German folders.)

Then in the "\Divinity2\Data\Win32\Characters\Dialogs" there's the files named for example "AL_AD_Br_Ch.dialog" and "AL_AD_Br_ChEnglish.dialog" (Previously named "AL_AD_Br_ChGerman.dialog") albeit only the latter should be needed.

Aside from that it's just the registry alteration, all files are present and nothing else is modified or altered.
(There's a dialogdata.xml file in the "\Data\Win32\Characters" folder but it shouldn't do anything, just from when extracting the archive.)

Extracting was done by simply dropping the .dv2 file over the dv2_u.exe file.

EDIT: Seems to be "English(US)" and not "English", seems I made a mistake somewhere but at least it was easily corrected.
## Post #27
- Username: madpaddy
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 28, 2009 11:48 pm
- Post datetime: 2009-07-29T19:56:54+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

> Reply from jbeckman
>
> Strange, in the "\Divinity2\Data\Sound\Soundbanks\Win32" I have three folders (English, English(US) and German) but only the one named English should be required and it contains the extracted .bnk files. (It takes a bit of space though I guess you could try to have both English and German folders.)

Then in the "\Divinity2\Data\Win32\Characters\Dialogs" there's the files named for example "AL_AD_Br_Ch.dialog" and "AL_AD_Br_ChEnglish.dialog" (Previously named "AL_AD_Br_ChGerman.dialog") albeit only the latter should be needed.

Aside from that it's just the registry alteration, all files are present and nothing else is modified or altered.
(There's a dialogdata.xml file in the "\Data\Win32\Characters" folder but it shouldn't do anything, just from when extracting the archive.)

Extracting was done by simply dropping the .dv2 file over the dv2_u.exe file.

EDIT: Seems to be "English(US)" and not "English", seems I made a mistake somewhere but at least it was easily corrected.

Ok will change the English foulder to English(US) and try that other than that its working with english text so well done m8  

PPs yes changing the English to English(us) did it works great ,English text for everything including chat ,and speach spoken in german.
## Post #28
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-29T20:02:09+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Yes, "English(US)" instead of just "English" did the job!
It works for me!
English text with german voices - just what I want!

Thanks for your help, finally we "did" this game
## Post #29
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-29T20:03:26+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Congrats to all ! You've made excellent progress.
## Post #30
- Username: kimono
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 01, 2009 6:10 am
- Post datetime: 2009-07-29T20:41:53+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Awesome work gentlemen, great community here :>

E: Next thing would be cracking open these .NIF files so I can start getting some of my work in there
## Post #31
- Username: Maltus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 30, 2009 4:41 am
- Post datetime: 2009-07-29T20:58:07+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Hello Everyone,

I originally created an account because I wanted to know if anyone tried to switch the game to French.
I though English would be fine but for me the English syntax used is difficult to understand and I had to read each sentence twice.

By the time my account was activated I found it.

It was a bit tricky, you have to rename the "German" folder to "French(France)".

Hope it helps some people!
## Post #32
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-30T00:56:17+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

It seems that the lipsync did not work after switching to english...
Other dialog animation is ok, but the lips stands still all the time...
## Post #33
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-30T04:50:27+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

So there's something that still doesn't trigger correctly, will see if I can find out what causes it but I'm a bit limited due to how the files work, I have a idea however.

EDIT: Found the problem but a solution might prove difficult.

Basically the only thing that makes the translation work is the "English(US)" renaming of the folder containing the .bnk sound bank files, the animation data is already present and renaming the *German.dialog files won't give results as the game loads this from the Dialog.dv2 files only, however I'll keep looking for some sort of solution for the lip sync data to play properly.
## Post #34
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-30T13:24:50+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Well, finally I`ve got the lips sync working with english language.

This has been done by:
1. Unpacking Dialogs.dv2 file with the unpacker.
2. Adding a copy for each ...German.dialog file with English(US) instead of German in Win32\Characters\Dialogs\ folder, so the Dialogs folder contents will be:
A_AD_Deodatus.dialog
A_AD_DeodatusEnglish(US).dialog
A_AD_DeodatusGerman.dialog
and so on.
3. Making a copy of Sound\Soundbanks\Win32\German\ folder and changing its name to English(US), thus having two different folders with the same contents.
4. Packing all the files back to Dialogs.dv2 with the [packer utility](http://www.sendspace.com/file/x8uyez) (thanks again to IvanAls).

This is it!
PS: game version is 1.01 (patched).
## Post #35
- Username: jbeckman
- Rank: advanced
- Number of posts: 43
- Joined date: Wed May 16, 2007 12:13 pm
- Post datetime: 2009-07-30T17:02:41+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Nicely done, had a feeling that repacking could work once the files were renamed but didn't know such a utility existed, great!
## Post #36
- Username: Maltus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 30, 2009 4:41 am
- Post datetime: 2009-07-30T17:15:54+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Thanks for the tip sonycman but i can't seem to repack the right way.

How do you tell the dv2_pak utility to pack the 2 folders ?
If I drag and drop them both, only one is packed.
(Selecting both my win32 folder (with characters folder in it) and my sound folder).

Thank you
## Post #37
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-30T17:50:14+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

> Reply from Maltus
>
> Thanks for the tip sonycman but i can't seem to repack the right way.
Just create empty folder and copy Win32 and Sound folders to it.
Then drag and drop this resulting folder or type its name in the console...
## Post #38
- Username: Maltus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 30, 2009 4:41 am
- Post datetime: 2009-07-30T18:26:53+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Hummm, i must be doing something wrong, got an application error while launching the game.

Got my folders :

sound/soundbanks/win32/ -> French(France), German, English(US)
Win32/Characters/Dialogs -> x.dialog xgerman.dialog xenglish.dialog xenglish(us).dialog xfrench.dialog xfrench(france).dialog

with this in data folder, it's ok, the game launch (either in french or english depending on registery key) but no lip sync.


So i move them out in a new folder named for exemple "empty". Gives me something like : 

c:/empty/sound/soundbanks/win32/French(France)
c:/empty/sound/soundbanks/win32/German
c:/empty/sound/soundbanks/win32/English(US)
c:/empty/Win32/Characters/Dialogs

(they are no more in the data folder at this step)

Then I drop the "empty" folder on the dv2_pak utility and got an out.dv2 file.

I rename the original dialogs.dv2 to dialogsxxx.xxx
Move the out.dv2 to the packed folder and rename it dialogs.dv2

Launch the game -> application error

I must be missing something.
## Post #39
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-30T18:32:28+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

> Reply from Maltus
>
> 
I must be missing something.
Try packer`s -a command line option. This option activates data alignment.

Like this: dv2_pak -a source_dir
## Post #40
- Username: Maltus
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 30, 2009 4:41 am
- Post datetime: 2009-07-30T18:39:23+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Thank you sir   

the command line option -a did the trick !
## Post #41
- Username: sonycman
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 29, 2009 9:04 pm
- Post datetime: 2009-07-30T18:52:06+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

> Reply from Maltus
>
> Thank you sir   
the command line option -a did the trick !
You`re welcome!

It seems that this -a option is absolutely required when compressing Dialogs.dv2.
Its absence forces the game to crash before menu screen.
## Post #42
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-30T19:10:35+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

any news on unpacking the Textures.dv2 properly?

the unpacker seems to work but you only get 0 byte files
## Post #43
- Username: Itze
- Rank: veteran
- Number of posts: 81
- Joined date: Sat Mar 15, 2008 11:43 pm
- Post datetime: 2009-07-31T06:09:33+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

thanks, gonna test it when im back from work
## Post #44
- Username: kimono
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Jul 01, 2009 6:10 am
- Post datetime: 2009-08-01T14:32:24+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Perhaps this would be better suited to a different section of the forums but seeing as this utilises the pretty common Gamebryo engine is anyone managing to make any headway decompiling these NIF's into a format readable by 3d App's? I would try myself but I'm only a lowly artist and have no experience with coding past the language hack detailed on the last few pages   I modelled a sword recently that I would certainly love to get into the game and usable, I have my fingers crossed that eventually it will be as easy as TES:O 

[](http://img36.imageshack.us/i/splashz.jpg/)
## Post #45
- Username: xrysha
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 13, 2009 11:07 pm
- Post datetime: 2009-08-13T15:25:28+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Hello! can someone please help me, I read a little of what you wrote here and the way I understood so far is that you have found a way to get the game to English-speaking! but can someone explain how to do and what you need to do it?
## Post #46
- Username: bonzay
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 20, 2009 3:25 pm
- Post datetime: 2009-08-20T07:32:01+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Hi,
I need a little help.
It seems that most of you guys succeded in making
game work in english lang without the second screen to get stuck.
well I tried to follow some of the steps u guys did but I lost you
guys in what to change to what...
if any one can post a full guide what to change and what to put in what
so I can play the game in english it would be awsome.

Thank you.
## Post #47
- Username: Lozz
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 25, 2009 3:34 pm
- Post datetime: 2009-09-25T07:59:25+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Edited: 15:53. changed it abit since i have the same problem as the guy above,
now iv tried for two days to get it working =/

this is what i do, 
1- Extract the dialogs.dv2 file,  change the "German" in soundbanks to "English(US)"
2- Change the Dialog file in the win32 folder that gets exstracted from "xxx.German.dialog -> xxx.English(US).dialog
3- opens CMD   and packs it all up again, 
4- moves the modified  "dialogs.dv2" file back to it original position.
5- goes into the Larian studio folder in the registry and changes it to "English(US)"

but still. char creation goes smooth, the first area goes smooth, but when leaving that town area, the "intro cinematic " starts and when finished it goes into loadingmode for the next zone, witch it just wont finish loading,

where or what am i doing wrong?..

ps,  when im in the first area, i do not have sound from npc's i talk to, just the English Text.
## Post #48
- Username: axel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 27, 2009 11:38 am
- Post datetime: 2009-09-27T13:08:37+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

if anyone can  help, greatly appreciated,
so i got the dialogs to work, all txt is now in english
but when i repack soundbanks even with -a, my game loses all sound, any ideas
## Post #49
- Username: Farflame
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Nov 11, 2009 12:11 am
- Post datetime: 2009-12-17T13:30:02+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Interesting discussion here. I have problem with packing utility mentioned in this topic. Please could you help me? 

I explained my problem in this topic:
forum.xentax.com/viewtopic.php?f=10&t=3942
## Post #50
- Username: topagae
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 03, 2010 10:48 pm
- Post datetime: 2010-01-03T23:51:36+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Can someone please repost the .dv files? They're off megaupload now
## Post #51
- Username: drysler
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Sep 26, 2010 8:21 am
- Post datetime: 2010-09-26T00:30:46+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

Hi guys,

i am just looking at the dv2 files that came with Divinity 2: Flames of Vengeance, 
and the dv2_u unpack tool does not seem to work anymore.

The developers of that dv2 files must be complete nutty or wizards  ( ... I believe in the first....)
## Post #52
- Username: ShadowRoze
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 24, 2008 1:50 am
- Post datetime: 2013-04-07T18:59:26+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

the dv2_u.exe utility does not seem to work on the DV2-files in the developers cut version, too bad, I really wanted the music.
Anyone got a updated utility?
## Post #53
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-04-07T20:53:04+00:00
- Post Title: Re: Divine Divinity 2 ".DV2" file.

> Reply from ShadowRoze
>
> the dv2_u.exe utility does not seem to work on the DV2-files in the developers cut version, too bad, I really wanted the music.
Anyone got a updated utility?
The music can be downloaded legally from Kirill Pokrovsky, the composer's homepage: [http://pokrovsky.hosthazard.com/divinity2.zip](http://pokrovsky.hosthazard.com/divinity2.zip)

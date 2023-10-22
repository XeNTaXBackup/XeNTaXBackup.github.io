## Post #1
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-02-10T23:48:44+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

Well, as the title saids, i looking for a way to get sound from Fate/Unlimited Codes (PSP or PS2).
Because i already exported models and textures from PSP version i tried to export sound from PSP version too. 
I can export from game sound in .vag format (Voices of characters, like xxx_entry_yyy, xxx_win). 
"Big" voices like dialogues of characters or character "super moves" i can found by path "Fate UC PSP data\fpack\voice\" and there are many folder for each hero with .fpk inside and after extracting i get .vag audio files.

But i looking for way to export from game small sounds like sounds of hits, voices of characters when they get hit, etc.

I went here "Fate UC PSP data\fpack\snd\se\" and found many .fpk files like "se_sys_drm.fpk", "chr_sbr00.fpk", "mgsht.fpk", "se_system.fpk". After using FPK extractor i went "unpacked_folder_name\snd\se\" and there are located three files with different formats: .pbd, .pef, .phd. 

.pef - always 44 bytes.
The remaining two is always different but it seems .pbd biggest, .phd middle-sized, .pef - lowest.

I can only guess what that file doing, but i thinking that there are files with voices that i need (because of their paths).

Somebody know something about those formats or just how to get sound from Fate/Unlimited Codes?

upd:
EXAMPLE: Here u can get 5 .fpk files and folders with files inside them:
[https://yadi.sk/d/BF3tPCmsecAWD](https://yadi.sk/d/BF3tPCmsecAWD)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-02-11T10:35:29+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

So what you are looking for is the sound effects.

Post some samples of the .pbd, .pef, .phd files
## Post #3
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-02-11T15:50:43+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

Here u can get 5 .fpk files and folders with files inside them:

[https://yadi.sk/d/BF3tPCmsecAWD](https://yadi.sk/d/BF3tPCmsecAWD)
## Post #4
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-03-14T16:31:28+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

i'l up theme, still need sound effects and have no idea to how export them =(
## Post #5
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-10-17T15:49:14+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

up
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-26T09:46:39+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

```
mgsht.pbd
system.pbd
```


These three are ADPCM. Not sure what the other two are sorry 

You can use VGM Toolbox's GENH to make these .PBD files playable though 

Change the extension of the files to .MIB and open it up in Winamp. Look at the stream info (Alt+3) and it should tell you the interleave, so take a note of that.
EDIT: You will need vgmstream to see this information.

Then open VGM Toolbox and go to the GENH creator, select the .PBD file and use the following settings:

Input File Format: PlayStation 4-bit ADPCM
Header Skip: 0
Interleave: <whatever vgmstream told you the interleave was>
Channels: 1
Frequency: 22050 or 44100
No Loops

Then select the create GENH
## Post #7
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-10-27T16:10:56+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

> Reply from brendan19
>
> 
You can use VGM Toolbox's GENH to make these .PBD files playable though
Thanks for reply. I tried to do what you have writen, but no result.
Let me show you steps which i did:

1) Rename .pbd to .MIB
2) Open that .MIB file in Winamp
3) In Winamp select that .MIB file and press Alt+3 in order to get file "Interleave"

So i think for now i stop at that step - because it shows me only "Payload size", no other thing like "Interleave"



Well, i tried to take that digit and insert it into VGM Toolbox. 
So i run VGMToolbox => GEHN => here i select .pbd file, make settings like u wrote, then put that didit into "interleave" field. Press "Create GENHs".
It showed me:
...\...se\chr_sk200.genh Created.



But.. uhm... well... EVEN if that file created CORRECTLY (very doubt) -  i dont know what to do with that file. 
I tried play it in Winamp, tried extract him using VGMToolbox in that programm, but in the end i get nothing.

Did i miss something? 

P.S. Did you tried to do that procedure with at least one of those files from archive? Maybe they just different from other files which you talking about
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-10-27T16:30:16+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

Yes I did try it 

You'll need vgmstream to get the interleave and you'll need it to be able to playback the GENH files as well.

Download [vgmstream](http://hcs64.com/files/vgmstream/vgmstream-r1040-test.zip)

and these [external DLLs for vgmstream](http://hcs64.com/files/vgmstream_external_dlls.zip)


Place the in_vgmstream.dll in Winamp's 'plugins' folder.

Put everything else including the external DLLs in the winamp directory.
## Post #9
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-10-27T17:28:21+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

> Reply from brendan19
>
> Yes I did try it 

You'll need vgmstream to get the interleave and you'll need it to be able to playback the GENH files as well.
Download vgmstream
and these external DLLs for vgmstream

Place the in_vgmstream.dll in Winamp's 'plugins' folder.

Put everything else including the external DLLs in the winamp directory.
OH. MY. GOD. Its working! Thanks a lot! Half year of waiting worth it =D

P.S. Actually i tried setup "Interleave" from 0x10 to 0x8000 and at first sight i dont see any differences. Well, maybe i will see those in future.

Anyway, thanks a lot again. I can start adding to my mods more sounds from game!
## Post #10
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-10-30T13:59:11+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

> Reply from sanyabane
>
> brendan19 wrote:Yes I did try it 

You'll need vgmstream to get the interleave and you'll need it to be able to playback the GENH files as well.
Download vgmstream
and these external DLLs for vgmstream

Place the in_vgmstream.dll in Winamp's 'plugins' folder.

Put everything else including the external DLLs in the winamp directory.
OH. MY. GOD. Its working! Thanks a lot! Half year of waiting worth it =D

P.S. Actually i tried setup "Interleave" from 0x10 to 0x8000 and at first sight i dont see any differences. Well, maybe i will see those in future.

Anyway, thanks a lot again. I can start adding to my mods more sounds from game!

You could also scan those three files with [Psound](http://snailrush.online.fr/). it's much faster and auto detects each individual stream.

Looking at the other files, Psound can't find anything, and they seem to have almost no structure compared to the others. Looking at an analysis of the rate certain values appear shows it as a near match to the others which are adpcm, a ton of 00 (used for silence or padding typically) and then going from 00 to FF, a sort of inverse bell curve spikes pattern.  It seems like it's most certainly some form of adpcm, but while mgsht.pdb is clearly structured in aligned blocks, battle.pdb is hard to find clear points of interest in, it's like all the right bits are there, just jumbled.

Weirder still, if you drag the whole fpks that held the bad pdbs into psound, you DO find the audio, and you can see the structure clearly inside the fpk with a hex editor (where the others were scrambled, but with the same ratio of characters)

it seems like those pdbs where you didnt find anything were in fpks that not XOR'd or encrypted, and the fpk unpacker did the same thing it does normally. it gave you the files from the container, but it also moved the characters around with a pattern, because it expected this is solve to logical data. in the instances where logical data already existed (se_battle and se_sys_ber) this just messed it up.
## Post #11
- Username: sanyabane
- Rank: n00b
- Number of posts: 14
- Joined date: Fri Oct 31, 2014 3:37 am
- Post datetime: 2015-11-01T14:47:50+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

> Reply from Pepper
>
> 
You could also scan those three files with Psound. it's much faster and auto detects each individual stream.

Wow thank you very much too! 

Before your post i used above method and it forced me to "cut" all sound files by myself. But PSound do it automatically. You save me a lot of time, thanks =)
## Post #12
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-11-05T02:32:35+00:00
- Post Title: Exporting Fate/Unlimited Codes sounds (not music or voice)

> Reply from sanyabane
>
> Pepper wrote:
You could also scan those three files with Psound. it's much faster and auto detects each individual stream.


Wow thank you very much too! 

Before your post i used above method and it forced me to "cut" all sound files by myself. But PSound do it automatically. You save me a lot of time, thanks =)

no problem, also for the ones that dont detect with a pdb, drop the whole fpk into it.

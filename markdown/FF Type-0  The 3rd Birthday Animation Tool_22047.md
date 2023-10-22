## Post #1
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-21T14:11:04+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

I have decided to reverse engineering an old PSP format. Good thing is that it works with multiple games  I will be posting the Type-0 tool first, will release the 3rd birthday one after some more tests.

Final Fantasy Type-0 (PC)

The tool will work with the PC version. Supports battle animations, as well as cutscenes. You need to load matching bin (model) and mot (animation) files. It should be easy to find based on names.

Tool overview and example animation



How to use
- Select the model file (.bin) you want to load.
- Select the animation file (.mot) you want to load.
- If everything is correct, you will see the model being animated in the preview.

- Export NEXF :  Exports the model in a custom format to be loaded in Noesis. Supports animations. Noesis import script : [Nexf Script](https://www.mediafire.com/file/6cq3izfhidig01d/fmt_Nexf.py/file)
- Export Textures :  Exports the textures used by the model.

Download :  [https://www.mediafire.com/file/btkpvsxv ... 1.rar/file](https://www.mediafire.com/file/btkpvsxvxd4fzp0/FFT0Anim_U1.rar/file)

The 3rd Birthday (PSP) - Soon

Filesystem is a bit painful since it is PSP. I am also making some tools for filtering the animation files. The process will probably be more complex and require Noesis often.

Test preview
## Post #2
- Username: Allanoon
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Apr 15, 2012 4:00 am
- Post datetime: 2020-04-21T22:47:48+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

Thanks for the awesome tool akderebur~
I checked various models/animations and noticed that the script seems to works perfectly with "p_" files (players one) and, generally "soldiers" one like "m_bhei".
All the others gets more or less stretched once animated, example: the s_ifrit down here



Is it a problem of mine or you're also experiencing this?
I Also had a problem at first when exporting the files as .nexf the animation completely broke on Noesis... but it's misteriously working now so that's good   "
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-21T22:56:29+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

> Reply from Allanoon ↑Wed Apr 22, 2020 6:47 am at Wed Apr 22, 2020 6:47 am
>
> 
All the others gets more or less stretched once animated
I will admit that I haven't tested much other than player/npc animations 

There is a good chance it is related to scale. I will check it out tomorrow. Hopefully it won't be too hard to fix. Thanks for reporting.

EDIT : 

Upon investigating, the issue seems to be related to position keys. Unfortunately I couldn't find a perfect solution for it. So I basically added the option to "Disable Position". The root motion (position) will still work. This is mostly related to weapon/prop positioning which doesn't seem to effect monsters/summons too much anyway. Maybe I can do a proper fix for this later.

Also did some improvements to root motion itself. You can get the new download link from the first post.
## Post #4
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-04-23T06:49:22+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

Thank you for sharing this wonderful achievement!
and Parasite Eve is a very memorable game. Looking forward to the release!


by the way, I heard of * .mot files in the PSP game files, and I remembered "Eighting" from the game company.
But unfortunately, this *.mot file is from "HEXA DRIVE", so it has nothing to do with them.

Do you have any plans to start reversing PSP game mot files with Eighting?
Used in many games such as Bleach, Fate and Naruto.
Since the model format is gmo, it can be load with Noesis.
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-04-23T17:49:58+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

> Reply from einherjar007 ↑Thu Apr 23, 2020 2:49 pm at Thu Apr 23, 2020 2:49 pm
>
> 
Do you have any plans to start reversing PSP game mot files with Eighting?
Sorry, but no plans for that atm. I did this one because it also had a pc port (type-0), so it was bit easier to debug. Using the psp emulator for reversing seems like too much effort for me
## Post #6
- Username: darkluap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2010 8:04 am
- Post datetime: 2020-04-28T03:55:25+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

I thought I would never see the animations of 3rd birthday, incredible
## Post #7
- Username: banz99
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 09, 2022 6:11 pm
- Post datetime: 2022-05-09T10:17:39+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

I know this is 2 years old at this point, but is there any chance of you open sourcing the .mot format? I'm working on an high framerate patch for the game, but some animations weren't properly closed (the spinning save relic for example (chr\bin\x_relic2.bin with chr\bin\motion\x_relic2\f_stand.mot)) and I'd like to fix them if possible.
## Post #8
- Username: Lune
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 06, 2023 6:21 pm
- Post datetime: 2023-02-06T10:45:19+00:00
- Post Title: FF Type-0 / The 3rd Birthday Animation Tool

Hi, now it's the 3rd year of this topic (ironic). Did you manage to get anims from The 3rd Birthday with models together? Because Noesis can extract animations and models separatly. And it's too hard to make them whole in editor.

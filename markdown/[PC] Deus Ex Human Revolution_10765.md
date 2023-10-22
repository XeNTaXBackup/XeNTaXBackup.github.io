## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-09T09:33:05+00:00
- Post Title: [PC] Deus Ex: Human Revolution

Version 2 fixes a problem with skeleton not loading for Adam.
Version 3 adds secondary UV maps.



Ripping Instructions:

 Create a new folder somewhere called "DEHR" (you can call it anything you want though).
 Copy bigfile.000, bigfile.001, bigfile.002, bigfile.003, patch0.000, patch0.001, and patch0.002 from main game into a new subfolder (i.e. "DEHR\main").
 Screw bigfile_English.000 as it contains nothing important.
 Copy bigfile.000 from the Missing Link DLC into a new subfolder as well (i.e. "DEHR\missing_link").
 Screw bigfile_English.000 as it contains nothing important.
 Place ripper.exe and zlib DLL into the "DEHR" folder (or whatever you called it) and run it.
 Say "YES" when it asks if it can delete unimportant files (unless you want a million files on your hard drive).
 Say "YES" when it asks if to process "000" files.
 Say "YES" when it asks if to process "DEX" files.
 Say "YES" when it asks if to process "PCD" files.
 Say "YES" when it asks if to process "MOD" files.
 Come back maybe one to two hours later depending on the strength of you computer. The program touches everything so it takes a while. This is amazing because if you spend 6 to 8 hours playing a game, at least one hour is spent watching some kind of loading screen .
Model Instructions:

 OBJ: For quick previewing in Noesis or other editor.
 SMC: Model + skeleton. This file can be loaded into Blender 2.49b using the provided plugin.
 BONECOUNT.TXT: A text file generated in the same folder where you put the EXE. This lists all model files and the number of bones in each model file. From this, you should be able to tell which models are main characters and which ones are not.
Other Instructions:

 Eventually, you will find some textures are in other directories and may have trouble finding them.
 In these cases, look at the bottom of the material MTL_A files in a hex editor.
 You will see data like the below example.
 In the example below, look for textures 00000ADA.dds, 0000002B.dds, 00000035.dds, and 0000003D.dds.
 If they aren't in the same directory as the model file, search elsewhere.
 Or you can also wait till I implement auto-texture.

```
2B 00 00 00 - 00 00 00 00 00 00 00 00 20 01 01 00 
35 00 00 00 - 00 00 00 00 00 00 00 00 60 04 01 00 
3D 00 00 00 - 00 00 00 00 03 00 00 00 8B 02 01 00 
3D 00 00 00 - 00 00 00 00 00 00 00 00 2C 03 02 00 
2B 00 00 00 - 00 00 00 00 00 00 00 00 20 00 01 00 
DA 0A 00 00 - 00 00 00 00 00 00 00 00 20 01 01 00 
35 00 00 00 - 00 00 00 00 00 00 00 00 60 02 01 00 
3D 00 00 00 - 00 00 00 00 00 00 00 00 2C 03 02 00

```

[dehr_v3.7z](https://xentaxbackup.github.io/file/6608_dehr_v3.7z)
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-09T13:27:46+00:00
- Post Title: [PC] Deus Ex: Human Revolution

Hehe nice j (:b... Next [target](https://www.dragonsprophetthegame.com)  ?
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-09T20:11:31+00:00
- Post Title: [PC] Deus Ex: Human Revolution

you want the models ekey? lemme ask chrrox first if it's possible and if he's interested in it. i know he likes these korean mmos moreso than i do .
## Post #4
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-09-09T21:39:42+00:00
- Post Title: [PC] Deus Ex: Human Revolution

> Reply from howfie
>
> you want the models ekey?

Nah. I just collect scripts / plugins for load models  . Although the models look very nice
## Post #5
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2013-09-12T07:25:32+00:00
- Post Title: [PC] Deus Ex: Human Revolution

Damn, that's really nice  *uhm*Hitman Absolution?
## Post #6
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2013-09-16T03:47:48+00:00
- Post Title: [PC] Deus Ex: Human Revolution

Hey howfie i really apreciate this tools for Deus Hex but iam curius what version of phyton i need on blender for this ? i have the 2.6.1
but i cant make it run.
## Post #7
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-09-16T06:07:59+00:00
- Post Title: [PC] Deus Ex: Human Revolution

that version should be fine.

to run script, you run from within blender and not the python command line.
steps are:

1.) open blender 2.49b
2.) set one of the panels to Text View
3.) open the script or paste it into the Text View
4.) run the script (Alt + P I think is the shortcut).
5.) select an SMC file and click OK/Open/Whatever.
6.) done
## Post #8
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2013-10-21T23:05:33+00:00
- Post Title: [PC] Deus Ex: Human Revolution

is there a better way of navigating trough the files?

its really hard to find the characters i want, and weapons to.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-10-28T04:42:00+00:00
- Post Title: [PC] Deus Ex: Human Revolution

can anyone tell me if ripper works with director's cut or do i have to update it?
## Post #10
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2013-11-02T10:11:04+00:00
- Post Title: [PC] Deus Ex: Human Revolution

Will drop a line once I set aside those five bucks
## Post #11
- Username: CharlieV
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Dec 30, 2019 5:29 pm
- Post datetime: 2020-03-06T02:16:23+00:00
- Post Title: [PC] Deus Ex: Human Revolution

> Reply from howfie ↑Mon Oct 28, 2013 12:42 pm at Mon Oct 28, 2013 12:42 pm
>
> 
can anyone tell me if ripper works with director's cut or do i have to update it?

Many years later... It does. Although it took 11 hours because there are more bigfiles. Whether I ever actually look through the 10,000(!) folders is another matter entirely though lol.
## Post #12
- Username: DasFroggy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 25, 2020 8:02 am
- Post datetime: 2020-04-25T00:35:49+00:00
- Post Title: [PC] Deus Ex: Human Revolution

> Reply from CharlieV ↑Fri Mar 06, 2020 10:16 am at Fri Mar 06, 2020 10:16 am
>
> 
howfie wrote: ↑Mon Oct 28, 2013 12:42 pm
can anyone tell me if ripper works with director's cut or do i have to update it?


Many years later... It does. Although it took 11 hours because there are more bigfiles. Whether I ever actually look through the 10,000(!) folders is another matter entirely though lol.

Unfortunately, it doesn't seem to work. A number of the files listed in the original post are missing, and when initiating the program the window opens only for a brief second before closing again. Can you provide some assistance in troubleshooting this issue?
## Post #13
- Username: MilkyWay
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 12, 2022 1:27 am
- Post datetime: 2022-07-13T12:45:20+00:00
- Post Title: [PC] Deus Ex: Human Revolution

damn
## Post #14
- Username: Bigarrow
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Mar 19, 2022 10:03 pm
- Post datetime: 2022-08-31T10:22:59+00:00
- Post Title: [PC] Deus Ex: Human Revolution

Works if you find a vanilla copy, but its about 9k assets that have no names.

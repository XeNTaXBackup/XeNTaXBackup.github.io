## Post #1
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2021-10-27T11:56:23+00:00
- Post Title: Sword and Fairy 7 .uexp material files for pre-order DLC

Hello guys!
recently I'm trying to port this game's pre-order weapon skin files for steam version.
after compare game files between two verisons many times,I finally find which files are needed.so I dumped these files,packed them up as a mod,then put it into the ~mods folder.the pre-order skin models are showed up,however all textures are missing 
I was very confused,then I packed a normal weapon files as a mod(not a dlc,existed in both versions),then the normal weapon's textures went missing too.after some boring file replacements,I found why the textures go missing.because the .uexp files under the material folders are different.the .uasset files have the same sha1 values,but the .uexp files aren't,although their sizes are same.
well I know very little about unreal engine(actually nothing at all),but is there a way to edit these dlc .uexp files?so maybe people can use these skins on steam version.
Many Thanks
## Post #2
- Username: Watcher
- Rank: n00b
- Number of posts: 14
- Joined date: Thu Sep 24, 2015 3:43 pm
- Post datetime: 2021-10-27T12:05:16+00:00
- Post Title: Sword and Fairy 7 .uexp material files for pre-order DLC

here are some sample files,btw the steam version's aes key is 0xE53BEBDBCEC82995F37033B62CFD8243E02C10C03AB12EA682F654DC805F4009.
[https://www.mediafire.com/file/vg2xg3xv ... s.rar/file](https://www.mediafire.com/file/vg2xg3xv8s6hp43/Samples.rar/file)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-07-28T15:28:02+00:00
- Post Title: Sword and Fairy 7 .uexp material files for pre-order DLC

Hah, well, I know, I'm a bit late to the party, but for the sake of completeness here's a picture:
.



MSK_XieHe-uexp.jpg (88.86 KiB) Viewed 47 times



> Reply from Watcher ↑Wed Oct 27, 2021 7:56 pm at Wed Oct 27, 2021 7:56 pm
>
> 
,but is there a way to edit these dlc .uexp files?Therefore it's required to fully understand the file structure.
(Usually you'd use an unity assets explorer, afair.)

## Post #1
- Username: takoyaki111
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Oct 22, 2013 2:43 am
- Post datetime: 2022-11-03T18:35:40+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

[https://cdn.discordapp.com/attachments/ ... 05/amy.pac](https://cdn.discordapp.com/attachments/977931120198959194/1037797125930635305/amy.pac)


Dumped the game and ran into .pacs, I'm unfamiliar with this filetype
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-03T22:24:26+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

Format is known. Check out this article [http://wiki.xentax.com/index.php/Sonic_Games_PAC](http://wiki.xentax.com/index.php/Sonic_Games_PAC)
Some tools are listed on the wiki, you can try them.
## Post #3
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-11-08T18:20:35+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

Its a new pac format, so the existing tools are unable to unpack it.
PACx403L

Tried:
HedgeTools - ERROR: Unknown or Unsupported PACx version.
sfpac.bms - this one: "PACx403L"   50 41 43 78 34 30 33 4c   expected: "PACx301L"  50 41 43 78 33 30 31 4c
Switch Toolbox - Unable to read beyond the end of the stream.
## Post #4
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2022-11-08T18:47:39+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

> Reply from 09williamsad ↑Wed Nov 09, 2022 2:20 am at Wed Nov 09, 2022 2:20 am
>
> Its a new pac format, so the existing tools are unable to unpack it.You can, actually, if you use the development build of HedgeLib here:
[https://github.com/Radfordhound/HedgeLib](https://github.com/Radfordhound/HedgeLib)
## Post #5
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-11-08T19:59:26+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

As a followup for this games archive formats.
It has a folder called "texture_streaming" with ntsp extension archive files.
They have PSTN in the header, but I have not been able to find any tools or information on this format.

Samples [https://drive.google.com/drive/folders/ ... share_link](https://drive.google.com/drive/folders/1clIrssrZXijsAi4T9xw9OqMcAvC1NJXe?usp=share_link)
## Post #6
- Username: 09williamsad
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-11-08T21:29:58+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

> They have PSTN in the header, but I have not been able to find any tools or information on this format.

Here is the file format [http://wiki.xentax.com/index.php/Sonic_Frontiers_NTSP](http://wiki.xentax.com/index.php/Sonic_Frontiers_NTSP)
Now you just need to find a way to parse it properly in Noesis
## Post #7
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2022-11-08T21:33:15+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

> Reply from ikskoks ↑Wed Nov 09, 2022 5:29 am at Wed Nov 09, 2022 5:29 am
>
> 
Here is the file format http://wiki.xentax.com/index.php/Sonic_Frontiers_NTSP
Now you just need to find a way to parse it properly in Noesis

I have no clue how I did not find that when googling the format.
## Post #8
- Username: Skyth
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 06, 2016 2:28 am
- Post datetime: 2022-11-09T05:16:15+00:00
- Post Title: Sonic Frontiers .pac (With Sample file)

I've made a tool for the .ntsp files, check here in Sonic Frontiers folder (also read README for usage instructions): [https://github.com/blueskythlikesclouds/SkythTools](https://github.com/blueskythlikesclouds/SkythTools)
I'll share format specification & source code later.

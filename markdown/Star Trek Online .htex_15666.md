## Post #1
- Username: clairegrube
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Feb 14, 2011 6:35 am
- Post datetime: 2015-02-19T19:48:44+00:00
- Post Title: Star Trek Online .htex

I would appreciate if someone could help me with this.
There is a Noesis plugin that can open Star Trek Online .wtex texture files, but i haven't been able to convert the higher-resolution .htex versions.

I've also found an oddity converting the .wtex normal maps with Noesis:
Those ending with _Nx.wtex work fine, they just have their channels switched. Some, however, are ending with _N.wtex. Their channels aren't switched, but it looks like they are mixed up with their own mip maps, and they are impossible to reconstruct since parts are missing.
This (possibly) is not too big an issue if the (higher-res) .htex normal maps can be converted, since they all seem to end with _Nx.htex
I've provided an example of an .htex diffuse map. I can upload a normal map too if required.

Thanks in advance to anyone taking the time to look into my issue.
[htex diffuse.rar](https://xentaxbackup.github.io/file/8709_htex diffuse.rar)
## Post #2
- Username: HaloNE0
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Nov 05, 2016 3:34 am
- Post datetime: 2016-12-30T14:34:48+00:00
- Post Title: Star Trek Online .htex

Hello, I've seen the that the older format (wtex) has been convertable for some time, but the newer HTEX has not. Since NinjaRipper does not work for me, I have no way to get access to a chunk of textures in the game. And with the changes to the game, it looks as if NinjaRipper is looking to be less and less of an option for asset extraction.

 Could someone look more indepth, I think a request was made a little under a year ago, but no one had any response to it. 

I have attached two HTEX files, more can be provided on request.
[M_UniformU_Odyssey_01.zip](https://xentaxbackup.github.io/file/12141_M_UniformU_Odyssey_01.zip)
## Post #3
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2021-02-03T15:49:31+00:00
- Post Title: Star Trek Online .htex

Hi all, in the past there were some tools available for decompiling the wtex and htex format of textures from Star Trek: Online, however it seems their latest update from a week or so ago changed the encryption or something in the textures and now those tools from years past no longer work, Noesis no longer views the wtex or htex textures with that python script for it, and Wtex2DDS doesn't work for me either anymore.

I've attached a sample of some textures here: [https://ufile.io/fdxg5umx](https://ufile.io/fdxg5umx)

It would be much appreciated if someone might be able to update tools to work on these textures again.
## Post #4
- Username: gwlogan
- Rank: beginner
- Number of posts: 26
- Joined date: Mon May 12, 2008 4:23 pm
- Post datetime: 2022-02-01T16:08:31+00:00
- Post Title: Star Trek Online .htex

Using a version of Noesis included in this pack: [https://drive.google.com/file/d/1QRHPcI ... xPDQH/view](https://drive.google.com/file/d/1QRHPcIxzR2bYfY8utrdHlhMKkJsxPDQH/view) seems to work for some of the STO textures after renaming them to .CRN. The two textures in your sample load properly when doing this. However the Noesis script can't properly decode all of the newer STO textures so it will need to be updated to handle them properly.
## Post #5
- Username: zhelatinobambino
- Rank: Moderator
- Number of posts: 1672
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-01T21:28:41+00:00
- Post Title: Star Trek Online .htex

CRN is a texture format used by crunch library.
See description here [http://wiki.xentax.com/index.php/Crunch_CRN](http://wiki.xentax.com/index.php/Crunch_CRN)

And you can get crunch executable here [https://github.com/BinomialLLC/crunch](https://github.com/BinomialLLC/crunch)
## Post #6
- Username: digitalutopia1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2017 10:43 am
- Post datetime: 2023-07-07T06:43:30+00:00
- Post Title: Star Trek Online .htex

> Reply from ikskoks ↑Wed Feb 02, 2022 5:28 am at Wed Feb 02, 2022 5:28 am
>
> 
CRN is a texture format used by crunch library.
See description here http://wiki.xentax.com/index.php/Crunch_CRN

And you can get crunch executable here https://github.com/BinomialLLC/crunch

The problem is that Cryptic altered the crunch compression in these files so that they cannot be decompressed with any of the standard tools/libraries 

It's likely something simple, but these files will need to be investigated by someone knowledgeable about the crn format in order to see what's been altered. Or, possibly, crunch a dds from ninja ripper and compare it to the same Cryptic compressed texture.
## Post #7
- Username: digitalutopia1
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Nov 09, 2017 10:43 am
- Post datetime: 2023-07-08T05:36:38+00:00
- Post Title: Star Trek Online .htex

Okay, so - good news first. I got the files to play nice with crunch. Cryptic has all their sizes/offsets based off the end of the header, instead of crunch which includes the header. So that means m_data_size is 198 bytes short (because of Cryptic's massive 198 byte header - a normal crn file only has a 74 byte header). This also means that the first palette offset is set to 0, instead of 198 like it should be, and the other 3 palette offsets, as well as the table offset are all 198 bytes off of where they should be. Once I fixed that, crunch easily decompressed it into a dds file. 

Now, the bad news - the dds file I got back is a mess. Like, you can kinda see what it's supposed to be, but that's about it.

working off of Ship_Fed_FCA_Type1.htex - immediately after the final value in the normal header there's the int 15924, then 60 bytes later there's the int 174044, followed by another 60 bytes of nothing. That closes out the extra 128 bytes that Cryptic tagged onto the header.

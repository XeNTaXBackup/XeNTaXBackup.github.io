## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-08T21:39:36+00:00
- Post Title: Devil may cry 5 RE engine file list.

So I used the hook by eskey to generate a filekist since the re 2 tool works to extract the files. Problem is how to take the contents of the log file and turn them into a list file for the tool to read.

Thx.
## Post #2
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-09T11:14:19+00:00
- Post Title: Devil may cry 5 RE engine file list.

Really interested as well, in theory process should be exactly the same as with RE2 remake
## Post #3
- Username: Very Cool Dude
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 16, 2018 7:35 am
- Post datetime: 2019-03-09T13:06:59+00:00
- Post Title: Devil may cry 5 RE engine file list.

.
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-09T13:12:10+00:00
- Post Title: Devil may cry 5 RE engine file list.

I bought it and used the steam version. Just dropped the two dlls in the directory with the main exe.

As for the list in have a theory on how to convert the log. Just take the offsets from the printout from the BMW script and add them at the beginning of the directories. Transfer over to list file. Assuming the order if the file list generated is the same as the actual pak file itself. Might need excel to do this.
## Post #5
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T13:27:28+00:00
- Post Title: Devil may cry 5 RE engine file list.

I also tried it with the RE2 tool. The models were extracted from the pak file, but there was a problem. I can't convert the tex file to the dds format. Using the RE7 tool for the file, the result was the same. I checked all MES files, but I couldn't extract all of the models because I used the RE2 file list. Most of all, the biggest problem is that TEX files can't be converted to DDS format... Because of this, I can't even mapping the material to the some extracted models. I think it is possible to extract a complete model if the RE2 tool is modified a little and the file list is complete.
## Post #6
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-09T13:33:33+00:00
- Post Title: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sat Mar 09, 2019 9:27 pm at Sat Mar 09, 2019 9:27 pm
>
> 
I also tried it with the RE2 tool. The models were extracted from the pak file, but there was a problem. I can't convert the tex file to the dds format. Using the RE7 tool for the file, the result was the same. I checked all MES files, but I couldn't extract all of the models because I used the RE2 file list. Most of all, the biggest problem is that TEX files can't be converted to DDS format... Because of this, I can't even mapping the material to the some extracted models. I think it is possible to extract a complete model if the RE2 tool is modified a little and the file list is complete.

So did You manage to extract any meshes at all ?
## Post #7
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T13:38:23+00:00
- Post Title: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Sat Mar 09, 2019 9:33 pm at Sat Mar 09, 2019 9:33 pm
>
> 
uroborostestsubject wrote: ↑Sat Mar 09, 2019 9:27 pm
I also tried it with the RE2 tool. The models were extracted from the pak file, but there was a problem. I can't convert the tex file to the dds format. Using the RE7 tool for the file, the result was the same. I checked all MES files, but I couldn't extract all of the models because I used the RE2 file list. Most of all, the biggest problem is that TEX files can't be converted to DDS format... Because of this, I can't even mapping the material to the some extracted models. I think it is possible to extract a complete model if the RE2 tool is modified a little and the file list is complete.


So did You manage to extract any meshes at all ?

Sure. I succeeded in extracting four boss models. The problem is that the texture file can't be converted from Tex format to DDS. and it does not have all the characters' meshes in the files extracted using this method. I think it is because I use RE2 file list. If there is a complete list of Devil May Cry 5 files, I think it is possible to extract all the meshes.
## Post #8
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-09T13:42:55+00:00
- Post Title: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sat Mar 09, 2019 9:38 pm at Sat Mar 09, 2019 9:38 pm
>
> 
lyhtem wrote: ↑Sat Mar 09, 2019 9:33 pm
uroborostestsubject wrote: ↑Sat Mar 09, 2019 9:27 pm
I also tried it with the RE2 tool. The models were extracted from the pak file, but there was a problem. I can't convert the tex file to the dds format. Using the RE7 tool for the file, the result was the same. I checked all MES files, but I couldn't extract all of the models because I used the RE2 file list. Most of all, the biggest problem is that TEX files can't be converted to DDS format... Because of this, I can't even mapping the material to the some extracted models. I think it is possible to extract a complete model if the RE2 tool is modified a little and the file list is complete.


So did You manage to extract any meshes at all ?


Sure. I succeeded in extracting four boss models. The problem is that the texture file can't be converted from Tex format to DDS. and it does not have all the characters' meshes in the files extracted using this method. I think it is because I use RE2 file list. If there is a complete list of Devil May Cry 5 files, I think it is possible to extract all the meshes.

yeah was thinking about same thing, as some files are bound to have same names as RE2, Honestly i`m only interested in Meshes especially Weapons and Some environment stuff, 

although game is still Downloading:(
## Post #9
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T13:55:25+00:00
- Post Title: Devil may cry 5 RE engine file list.

I think it is possible to utilize all the meshes of this game if we convert the texture files properly and have a list of all the files. The RE2 tool was not perfect, but it worked in part. I don't know much about programming, but If programmers build new tools based on RE2 tool, they could work more easily. I hope to be able to fully extract the models of this game soon.
## Post #10
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T14:11:24+00:00
- Post Title: Devil may cry 5 RE engine file list.

This is a TEX file I extracted using the above method. This file is hardly converted to DDS format... If you are an expert in programming, I would like you to study with this sample. Both the RE7 and RE2 tool did not work for this file.
[0000000000000001.zip](https://xentaxbackup.github.io/file/15850_0000000000000001.zip)
## Post #11
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2019-03-09T15:10:12+00:00
- Post Title: Devil may cry 5 RE engine file list.

I have noesis plugin for .tex textures, it was made for RE2 remake, though of course it's working with DMC 5 too. I'll upload it here later, if no one update tools for Noesis or Blender by that time. I suggest you to check RE2 remake topic, guys there did a great job, so if they will be interested in DMC5 too, they'll just fix scripts a bit (or better everyone should wait a bit for proper extractor and re2 remake tools will work even without editing xD)
## Post #12
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-03-09T15:43:05+00:00
- Post Title: Devil may cry 5 RE engine file list.

Can someone post their hooked logs here please?
## Post #13
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T15:45:42+00:00
- Post Title: Devil may cry 5 RE engine file list.

> Reply from zaramot ↑Sat Mar 09, 2019 11:10 pm at Sat Mar 09, 2019 11:10 pm
>
> 
I have noesis plugin for .tex textures, it was made for RE2 remake, though of course it's working with DMC 5 too. I'll upload it here later, if no one update tools for Noesis or Blender by that time. I suggest you to check RE2 remake topic, guys there did a great job, so if they will be interested in DMC5 too, they'll just fix scripts a bit (or better everyone should wait a bit for proper extractor and re2 remake tools will work even without editing xD)

Is this the script you were talking about? ([http://www.mediafire.com/file/c3mfq9reb ... ex.py/file](http://www.mediafire.com/file/c3mfq9rebss8921/fmt_RE2_REMAKE_tex.py/file)) This script shows me this error in the picture. If not, could you please give me a link?
[error.JPG](https://xentaxbackup.github.io/file/15853_error.JPG)
## Post #14
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T15:58:33+00:00
- Post Title: Devil may cry 5 RE engine file list.

> Reply from devilsnake88 ↑Sat Mar 09, 2019 11:43 pm at Sat Mar 09, 2019 11:43 pm
>
> 
Can someone post their hooked logs here please?

Is this the log you mentioned?
[Log.JPG](https://xentaxbackup.github.io/file/15854_Log.JPG)
## Post #15
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-03-09T16:06:07+00:00
- Post Title: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sat Mar 09, 2019 11:58 pm at Sat Mar 09, 2019 11:58 pm
>
> 
devilsnake88 wrote: ↑Sat Mar 09, 2019 11:43 pm
Can someone post their hooked logs here please?


Is this the log you mentioned?
No I mean the one from re2hook wich is filenames like "natives/x64/streaming/sectionroot/character/player/pl0000/pl0002/pl0002_jacket_albm.tex.10"
## Post #16
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T16:12:21+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from devilsnake88 ↑Sun Mar 10, 2019 12:06 am at Sun Mar 10, 2019 12:06 am
>
> 
uroborostestsubject wrote: ↑Sat Mar 09, 2019 11:58 pm
devilsnake88 wrote: ↑Sat Mar 09, 2019 11:43 pm
Can someone post their hooked logs here please?


Is this the log you mentioned?

No I mean the one from re2hook wich is filenames like "natives/x64/streaming/sectionroot/character/player/pl0000/pl0002/pl0002_jacket_albm.tex.10"

Oh, I understand. When I extracted the pak file using the RE2 tool, there were no files in the "Native" folder. Other files(MES,TEX,ect) are only created outside the folder.
## Post #17
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-03-09T16:29:18+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 12:12 am at Sun Mar 10, 2019 12:12 am
>
> 
Oh, I understand....

Yes but @OrangeC said he was able to make it work for himself so I'm just asking for his .log file or anyone else for who this tool is working ^^
## Post #18
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T16:40:16+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from devilsnake88 ↑Sun Mar 10, 2019 12:29 am at Sun Mar 10, 2019 12:29 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 12:12 am
Oh, I understand....


Yes but @OrangeC said he was able to make it work for himself so I'm just asking for his .log file or anyone else for who this tool is working ^^

I also did what he said. But in my case, valid file did not exist in the folder. Could you please share the information you learned about log files?  I also want to know more about how to convert textures.
## Post #19
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T17:35:23+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information. 
[test.JPG](https://xentaxbackup.github.io/file/15860_test.JPG)
## Post #20
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-09T17:49:16+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 1:35 am at Sun Mar 10, 2019 1:35 am
>
> 
Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information.

Any luck with weapon meshes? still got about 15gb to download
## Post #21
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-09T17:58:22+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Sun Mar 10, 2019 1:49 am at Sun Mar 10, 2019 1:49 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 1:35 am
Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information. 


Any luck with weapon meshes? still got about 15gb to download

Does it take a long time to download? If you download it via Steam, it will be downloaded in an hour. The objects has too many files so I can not find it all at once.
## Post #22
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-03-09T18:14:00+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

So I assume the format is the same as RE2 remake then?
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-09T18:26:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sat Mar 09, 2019 11:45 pm at Sat Mar 09, 2019 11:45 pm
>
> Is this the script you were talking about? (http://www.mediafire.com/file/c3mfq9reb ... ex.py/file) This script shows me this error in the picture.
that script has some obvious discrepancies, for instance, 
3 different conditions decoding "dxtType 7" as dxt1, ATI1 and rgba32,
also  "dxtType 26" with 3 different conditions decoding as dxt3, dxt5 and ATI2.
post more samples and we'll have a look see.
## Post #24
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-09T18:29:59+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 1:58 am at Sun Mar 10, 2019 1:58 am
>
> 
lyhtem wrote: ↑Sun Mar 10, 2019 1:49 am
uroborostestsubject wrote: ↑Sun Mar 10, 2019 1:35 am
Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information. 


Any luck with weapon meshes? still got about 15gb to download


Does it take a long time to download? If you download it via Steam, it will be downloaded in an hour. The objects has too many files so I can not find it all at once.

Yeah takes ages Joys of having really slow internet, Current download speed is arround 350-500Kb/s
## Post #25
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-03-09T19:23:56+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

@OrangeC Can you post the log you got from the hook? I want to see what it looks like.
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-09T21:17:24+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I will post it when I get home. Btw it's not a complete log but it s up to the main menu.
## Post #27
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T02:11:30+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I've uploaded a one more sample. This is the TEX file of RE2. Only RE2 Tex files are converted, and DMC5 files are not converted. If we analyze the difference between these two files, I think it would be possible to convert DMC5 TEX files to DDS.
[0000000000006393.zip](https://xentaxbackup.github.io/file/15864_0000000000006393.zip)
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T02:40:54+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Okay here is a sample.


 RE2Hook-[08.10][08.03.19].rar
(24.55 KiB) Downloaded 83 times
## Post #29
- Username: EXshinlaSS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 10, 2019 10:45 am
- Post datetime: 2019-03-10T02:56:59+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Sat Mar 09, 2019 9:12 pm at Sat Mar 09, 2019 9:12 pm
>
> 
I bought it and used the steam version. Just dropped the two dlls in the directory with the main exe.

As for the list in have a theory on how to convert the log. Just take the offsets from the printout from the BMW script and add them at the beginning of the directories. Transfer over to list file. Assuming the order if the file list generated is the same as the actual pak file itself. Might need excel to do this.

hey OrangeC,I'm curious how can I extract the offsets of dmc5 files，where can I find the BMW script you mention? is there any tutorial about how to get the offsets ? thanks bruh
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T03:16:32+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Actually i meant the BMS script used for extracting resident evil 2. My thoery might not work as the offsets might be CRC hashes tied to the files themselves.

So not sure how to conver those into a .list file.
## Post #31
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T03:33:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Sun Mar 10, 2019 11:16 am at Sun Mar 10, 2019 11:16 am
>
> 
Actually i meant the BMS script used for extracting resident evil 2. My thoery might not work as the offsets might be CRC hashes tied to the files themselves.

So not sure how to conver those into a .list file.

Thank you so much for uploading the hook file.   I deleted the first line at the top of your hook file and was able to extract some files using the RE2 tool. but the problem is TEX file. As you already know, DMC5's texture files take TEX11 format. However, RE2 tools seem to convert only TEX10 format files to DDS... Do you know how to convert TEX11 files to DDS?
## Post #32
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T03:36:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Sorry im only focused on the sounds/music names atm. How did you get some of the files to extract with names? did you delete the first line then change the extension to .list?
## Post #33
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T03:46:07+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Sun Mar 10, 2019 11:36 am at Sun Mar 10, 2019 11:36 am
>
> 
Sorry im only focused on the sounds/music names atm. How did you get some of the files to extract with names? did you delete the first line then change the extension to .list?

No. I just deleted the first line in your log file. Then I just used the RE2 tool. I have not checked everything yet, but some files were extracted this way too.
## Post #34
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-10T03:53:08+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 10:11 am at Sun Mar 10, 2019 10:11 am
>
> 
I've uploaded a one more sample. This is the TEX file of RE2. Only RE2 Tex files are converted, and DMC5 files are not converted. If we analyze the difference between these two files, I think it would be possible to convert DMC5 TEX files to DDS.
if you uploaded a folder full of "DMC5 TEX" samples i can get you a Noesis python script to open them.  
i only have the one sample you attached so far which was dxt1 by the way.
## Post #35
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T03:54:35+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 11:46 am at Sun Mar 10, 2019 11:46 am
>
> 
OrangeC wrote: ↑Sun Mar 10, 2019 11:36 am
Sorry im only focused on the sounds/music names atm. How did you get some of the files to extract with names? did you delete the first line then change the extension to .list?


No. I just deleted the first line in your log file. Then I just used the RE2 tool. I have not checked everything yet, but some files were extracted this way too.

Not quite sure i understand. So the tool just extracted a bunch of dat nameless files like xxxxx.dat?
## Post #36
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T04:06:04+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Sun Mar 10, 2019 11:54 am at Sun Mar 10, 2019 11:54 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 11:46 am
OrangeC wrote: ↑Sun Mar 10, 2019 11:36 am
Sorry im only focused on the sounds/music names atm. How did you get some of the files to extract with names? did you delete the first line then change the extension to .list?


No. I just deleted the first line in your log file. Then I just used the RE2 tool. I have not checked everything yet, but some files were extracted this way too.


Not quite sure i understand. So the tool just extracted a bunch of dat nameless files like xxxxx.dat?

This is a modification of your log file. Try this one. I was able to extract some files with this modified list.
[re2_pak_names_demo.zip](https://xentaxbackup.github.io/file/15866_re2_pak_names_demo.zip)
## Post #37
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T04:09:10+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Acewell ↑Sun Mar 10, 2019 11:53 am at Sun Mar 10, 2019 11:53 am
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 10:11 am
I've uploaded a one more sample. This is the TEX file of RE2. Only RE2 Tex files are converted, and DMC5 files are not converted. If we analyze the difference between these two files, I think it would be possible to convert DMC5 TEX files to DDS.
if you uploaded a folder full of "DMC5 TEX" samples i can get you a Noesis python script to open them.  
i only have the one sample you attached so far which was dxt1 by the way.

Sorry. If I upload all TEX files that way, the file size gets too big. and I don't have the means to do it.
## Post #38
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T04:14:35+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 12:06 pm at Sun Mar 10, 2019 12:06 pm
>
> 
OrangeC wrote: ↑Sun Mar 10, 2019 11:54 am
uroborostestsubject wrote: ↑Sun Mar 10, 2019 11:46 am


No. I just deleted the first line in your log file. Then I just used the RE2 tool. I have not checked everything yet, but some files were extracted this way too.


Not quite sure i understand. So the tool just extracted a bunch of dat nameless files like xxxxx.dat?


This is a modification of your log file. Try this one. I was able to extract some files with this modified list.

Its just extracting the naeless stuff atleast for me. We need thje actual hashes to assign them to the filepaths inside the log file.
## Post #39
- Username: EXshinlaSS
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 10, 2019 10:45 am
- Post datetime: 2019-03-10T04:50:15+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I extracted .pak with REtool and without .list file， and got lots of .bin files 
and i find some texture flies ,though their extension is .bin
textures i got :[https://tieba.baidu.com/p/6061635138](https://tieba.baidu.com/p/6061635138)
## Post #40
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-10T05:32:41+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 12:09 pm at Sun Mar 10, 2019 12:09 pm
>
> Sorry. If I upload all TEX files that way, the file size gets too big. and I don't have the means to do it.
i don't need all, just 20 or 30 zipped and uploaded to mega or something, 
if not, well, no samples no party. i will move along to the next project.
## Post #41
- Username: Very Cool Dude
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 16, 2018 7:35 am
- Post datetime: 2019-03-10T05:41:13+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

.
## Post #42
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T06:22:15+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Acewell ↑Sun Mar 10, 2019 1:32 pm at Sun Mar 10, 2019 1:32 pm
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 12:09 pmSorry. If I upload all TEX files that way, the file size gets too big. and I don't have the means to do it.
i don't need all, just 20 or 30 zipped and uploaded to mega or something, 
if not, well, no samples no party. i will move along to the next project.

([http://www.mediafire.com/file/pcdg0xxfs ... x.zip/file](http://www.mediafire.com/file/pcdg0xxfscywbcq/tex.zip/file)) Here is the link. This is a part of the TEX files from DMC5.
## Post #43
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T06:24:21+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from EXshinlaSS ↑Sun Mar 10, 2019 12:50 pm at Sun Mar 10, 2019 12:50 pm
>
> 
I extracted .pak with REtool and without .list file， and got lots of .bin files 
and i find some texture flies ,though their extension is .bin
textures i got :https://tieba.baidu.com/p/6061635138

This means that you succeeded in converting TEX files? If so, could you share with us how you convert files?
## Post #44
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-10T06:55:43+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

here is Noesis python script to open all the supplied samples so far.  


 tex_DevilMayCry5_PC_tex.zip
(734 Bytes) Downloaded 270 times


supports dxt1, ati1, BC7, top level mip only.
i used some of zaramot's findings and reworked the script a bit for DMC5.
## Post #45
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T07:09:14+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Acewell ↑Sun Mar 10, 2019 2:55 pm at Sun Mar 10, 2019 2:55 pm
>
> 
here is Noesis python script to open all the supplied samples so far.   
tex_DevilMayCry5_PC_tex.zip
supports dxt1, ati1, BC7, top level mip only.
i used some of zaramot's findings and reworked the script a bit for DMC5.

My God! Thank you so much!  It seems to have solved the texture problem. All that remains is meshes that have not been extracted with the RE2 tool. I'm checking all MES files now. but some of the boss&enemy models aren't there.(Urizen second form and Angelo, ect).   How could we solve this problem?
## Post #46
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-03-10T07:09:54+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Sun Mar 10, 2019 10:40 am at Sun Mar 10, 2019 10:40 am
>
> 
Okay here is a sample.

Thank you very much 

@Ekey BTW the issue with W10 users using your re2hook is with the dinput8.dll file.
I tried to take the ones on my computer but I saw your is a custom one.
Any chances to make a w10 version?
## Post #47
- Username: Very Cool Dude
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 16, 2018 7:35 am
- Post datetime: 2019-03-10T07:52:53+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

.
## Post #48
- Username: devilsnake88
- Rank: beginner
- Number of posts: 32
- Joined date: Fri Dec 06, 2013 12:14 am
- Post datetime: 2019-03-10T08:58:57+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Very Cool Dude ↑Sun Mar 10, 2019 3:52 pm at Sun Mar 10, 2019 3:52 pm
>
> 
Is that why I can't launch the game after putting the dlls next to the exe? I am on Windows 10. Does it not work on there?
It looks like, yes.
## Post #49
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-03-10T09:30:32+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Where's the tool you're using to extract the files? This list is not suitable for BMS script since it just has names and not corresponding hashes.

EDIT: Ah, found some C# code for generating hashes: [https://zenhax.com/viewtopic.php?p=42344#p42344](https://zenhax.com/viewtopic.php?p=42344#p42344). I've adapted it to convert the log into hash dictionary. Attaching the resulting file. Here's BMS script for extraction: [https://pastebin.com/TctyRd8s](https://pastebin.com/TctyRd8s)
[re_pak_names.zip](https://xentaxbackup.github.io/file/15868_re_pak_names.zip)
## Post #50
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2019-03-10T10:10:59+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I also (just) generated a list file for the REtool from FluffyQuack to extract the files. But looks like I got beaten to the punch.

By the statistics, the hooked log file courtesy of @OrangeC has ~2200 file names out of a total ~64000. Which makes sense, since it's from just loading in the main menu.

Unfortunately, I'm running Windows 10 and don't have a Windows 7 machine so I can't get any more file names without a log file from a longer run.

Anyway, if anyone wants that it's attached here. I included the hashes that we don't yet know the plaintext for, and the order is whatever chunk order it's in the pak.

EDIT: Newer list on page 5
## Post #51
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T11:12:21+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Sun Mar 10, 2019 6:10 pm at Sun Mar 10, 2019 6:10 pm
>
> 
I also (just) generated a list file for the REtool from FluffyQuack to extract the files. But looks like I got beaten to the punch.

By the statistics, the hooked log file courtesy of @OrangeC has ~2200 file names out of a total ~64000. Which makes sense, since it's from just loading in the main menu.

Unfortunately, I'm running Windows 10 and don't have a Windows 7 machine so I can't get any more file names without a log file from a longer run.

Anyway, if anyone wants that it's attached here. I included the hashes that we don't yet know the plaintext for, and the order is whatever chunk order it's in the pak.

EDIT: Here's a link, since my file limit's too low: https://mega.nz/#!rvgA3CCJ!Ebsva0U0u9Hm ... qMUbmXiwDg

I am currently using Windows 8.1. The list of file names we currently have is not complete, so it was impossible to extract all the files in game. The texture files was partially extracted.. I also want to get a complete list of files but don't know the exact method for this process.  If I could get a complete list on my computer, I'm going to try it. Could you tell me how you got the list of file names?
## Post #52
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-10T11:36:47+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 1:35 am at Sun Mar 10, 2019 1:35 am
>
> 
Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information.

Just a Quick one which extensions are the mesh files?
## Post #53
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T11:38:28+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Sun Mar 10, 2019 7:36 pm at Sun Mar 10, 2019 7:36 pm
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 1:35 am
Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information. 


Just a Quick one which extensions are the mesh files?

It's MES format.
## Post #54
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T11:44:22+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Does anyone have a complete list of file names? If you have a complete log file, please share it with us.
## Post #55
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2019-03-10T11:45:56+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 7:12 pm at Sun Mar 10, 2019 7:12 pm
>
> I am currently using Windows 8.1. The list of file names we currently have is not complete, so it was impossible to extract all the files in game. The texture files was partially extracted.. I also want to get a complete list of files but don't know the exact method for this process.  If I could get a complete list on my computer, I'm going to try it. Could you tell me how you got the list of file names?

Pretty sure people are using Ekey's hook DLLs from RE2 Remake to get the log. The latest version, I believe, is here: [https://zenhax.com/download/file.php?id=6350](https://zenhax.com/download/file.php?id=6350)

You put the two DLLs in the same directory as your DevilMayCry5.exe and then it outputs to a log text file in the same directory. AFAIK, the way it works is it just intercepts each file load and logs the name of it. So the way to get a more complete log would be just to play the game more. I believe the one posted was just from loading into the main menu.

I don't know if Windows 8.1 will have the same problem as in 10, but in my case the game just fails to load if those DLLs are present.
## Post #56
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T11:57:12+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Sun Mar 10, 2019 7:45 pm at Sun Mar 10, 2019 7:45 pm
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 7:12 pmI am currently using Windows 8.1. The list of file names we currently have is not complete, so it was impossible to extract all the files in game. The texture files was partially extracted.. I also want to get a complete list of files but don't know the exact method for this process.  If I could get a complete list on my computer, I'm going to try it. Could you tell me how you got the list of file names?


Pretty sure people are using Ekey's hook DLLs from RE2 Remake to get the log. The latest version, I believe, is here: https://zenhax.com/download/file.php?id=6350

You put the two DLLs in the same directory as your DevilMayCry5.exe and then it outputs to a log text file in the same directory. AFAIK, the way it works is it just intercepts each file load and logs the name of it. So the way to get a more complete log would be just to play the game more. I believe the one posted was just from loading into the main menu.

I don't know if Windows 8.1 will have the same problem as in 10, but in my case the game just fails to load if those DLLs are present.

Thank you.   So if I put these in the appropriate folder and then run the game, will it automatically record the list?
## Post #57
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2019-03-10T12:27:40+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Yes, it will automatically create a RE{timestamp}.log file (or something like that) in the same directory as the game, which will log each file that your game tries to load.
## Post #58
- Username: lyutor1945
- Rank: beginner
- Number of posts: 39
- Joined date: Tue Nov 03, 2015 1:24 am
- Post datetime: 2019-03-10T12:55:24+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Sun Mar 10, 2019 8:27 pm at Sun Mar 10, 2019 8:27 pm
>
> 
Yes, it will automatically create a RE{timestamp}.log file (or something like that) in the same directory as the game, which will log each file that your game tries to load.

After I put these two dll files into the exe folder, the game not working
## Post #59
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T13:52:23+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I succeeded in extracting the new log file. Here is the log file. ([http://www.mediafire.com/file/yku9q3j3a ... e.zip/file](http://www.mediafire.com/file/yku9q3j3ar7w28v/Log_File.zip/file)) The problem is that my log file have more content, but the meshes extracted when using the RE2 tool are no different than before.
## Post #60
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T14:02:48+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Whoa looks like you guys are busy here too, I posted on Zenhax asking how to convert a log file into a list file and then I heard you guys are already busy here

How did you guys make the list file?

We need someone with a completed save file to load up every mission once so the log file gets filled, then upload it here so another guy can turn it into a list file with hashes (can someone explain to me how to turn it into a list file?)


Here is a completed campaign save file, if someone has the time to load up everything in the game, please do:

[https://drive.google.com/open?id=1B8Lq0 ... xFW1VUAunw](https://drive.google.com/open?id=1B8Lq0JBWmH7_V8FbwRA2BvxFW1VUAunw)
## Post #61
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T14:11:57+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Crux ↑Sun Mar 10, 2019 10:02 pm at Sun Mar 10, 2019 10:02 pm
>
> 
Whoa looks like you guys are busy here too, I posted on Zenhax asking how to convert a log file into a list file and then I heard you guys are already busy here

How did you guys make the list file?

We need someone with a completed save file to load up every mission once so the log file gets filled, then upload it here so another guy can turn it into a list file with hashes (can someone explain to me how to turn it into a list file?)


Here is a completed campaign save file, if someone has the time to load up everything in the game, please do:

https://drive.google.com/open?id=1B8Lq0 ... xFW1VUAunw

My log file was also created from completed save file. I selected Mission 17 and 20 to clear it, and then I got this log file. The problem is that when I use the RE2 tool, it is no different than before... Only the same files as before are extracted and new mesh files are rarely extracted.
## Post #62
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T14:23:49+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 10:11 pm at Sun Mar 10, 2019 10:11 pm
>
> 
Crux wrote: ↑Sun Mar 10, 2019 10:02 pm
Whoa looks like you guys are busy here too, I posted on Zenhax asking how to convert a log file into a list file and then I heard you guys are already busy here

How did you guys make the list file?

We need someone with a completed save file to load up every mission once so the log file gets filled, then upload it here so another guy can turn it into a list file with hashes (can someone explain to me how to turn it into a list file?)


Here is a completed campaign save file, if someone has the time to load up everything in the game, please do:

https://drive.google.com/open?id=1B8Lq0 ... xFW1VUAunw


My log file was also created from completed save file. I selected Mission 17 and 20 to clear it, and then I got this log file. The problem is that when I use the RE2 tool, it is no different than before... Only the same files as before are extracted and new mesh files are rarely extracted.

Wait, do you mean LOG file or LIST file, that's two different things, if you have a LIST file, link it to me I will try to extract
## Post #63
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T14:38:09+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I don't know how to correctly convert log file to list file. however, if you look at the structure of the list file, you could see that it was created from the log file. It is not perfect, but there is a way to convert the log file to list file. Delete only the first line of my log file, and save the extension of the file as a 'list'. Then change name of the list file with your RE2 tool using. Running the RE2 tool will extract the files. 

The problem is that if you do this way, your files will not be organized and have to check the files one by one. I thought I could extract new meshes this way, but it was not successful.
## Post #64
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T14:44:54+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 10:38 pm at Sun Mar 10, 2019 10:38 pm
>
> 
I don't know how to correctly convert log file to list file. however, if you look at the structure of the list file, you could see that it was created from the log file. It is not perfect, but there is a way to convert the log file to list file. Delete only the first line of my log file, and save the extension of the file as a 'list'. Then change name of the list file with your RE2 tool using. Running the RE2 tool will extract the files. 

The problem is that if you do this way, your files will not be organized and have to check the files one by one. I thought I could extract new meshes this way, but it was not successful.

That's not how it works, a list file is generated from the log file, a list file is exactly the log file but with the hashes next to it.

Fluffy just said in discord that if we wait an hour or so, he will have made a tool to convert the log to the list file.
## Post #65
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T15:01:17+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Crux ↑Sun Mar 10, 2019 10:44 pm at Sun Mar 10, 2019 10:44 pm
>
> 
uroborostestsubject wrote: ↑Sun Mar 10, 2019 10:38 pm
I don't know how to correctly convert log file to list file. however, if you look at the structure of the list file, you could see that it was created from the log file. It is not perfect, but there is a way to convert the log file to list file. Delete only the first line of my log file, and save the extension of the file as a 'list'. Then change name of the list file with your RE2 tool using. Running the RE2 tool will extract the files. 

The problem is that if you do this way, your files will not be organized and have to check the files one by one. I thought I could extract new meshes this way, but it was not successful.  


That's not how it works, a list file is generated from the log file, a list file is exactly the log file but with the hashes next to it.

Fluffy just said in discord that if we wait an hour or so, he will have made a tool to convert the log to the list file.

Thank you for information.   So that means we're going to have a new tools to extract new meshes. But I have a question. I got this log file by selecting 17 and 20 mission. I'm not sure if I could get a log file of the entire game just by choosing two missions. I want other experts to make sure there's no problem in this area.
## Post #66
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T15:16:09+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 11:01 pm at Sun Mar 10, 2019 11:01 pm
>
> 
Crux wrote: ↑Sun Mar 10, 2019 10:44 pm
uroborostestsubject wrote: ↑Sun Mar 10, 2019 10:38 pm
I don't know how to correctly convert log file to list file. however, if you look at the structure of the list file, you could see that it was created from the log file. It is not perfect, but there is a way to convert the log file to list file. Delete only the first line of my log file, and save the extension of the file as a 'list'. Then change name of the list file with your RE2 tool using. Running the RE2 tool will extract the files. 

The problem is that if you do this way, your files will not be organized and have to check the files one by one. I thought I could extract new meshes this way, but it was not successful.  


That's not how it works, a list file is generated from the log file, a list file is exactly the log file but with the hashes next to it.

Fluffy just said in discord that if we wait an hour or so, he will have made a tool to convert the log to the list file.


Thank you for information.   So that means we're going to have a new tools to extract new meshes. But I have a question. I got this log file by selecting 17 and 20 mission. I'm not sure if I could get a log file of the entire game just by choosing two missions. I want other experts to make sure there's no problem in this area.

Exactly we need to merge everyone's log file together, for example one guy plays first half of game, you the 2nd half, with that we will have all the necessary file paths, the tool I just mentioned will be able to create the list file out of that log file and we are all done
## Post #67
- Username: Very Cool Dude
- Rank: n00b
- Number of posts: 11
- Joined date: Thu Aug 16, 2018 7:35 am
- Post datetime: 2019-03-10T16:05:33+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

.
## Post #68
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T16:50:33+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Nicknine ↑Sun Mar 10, 2019 5:30 pm at Sun Mar 10, 2019 5:30 pm
>
> 
Where's the tool you're using to extract the files? This list is not suitable for BMS script since it just has names and not corresponding hashes.

EDIT: Ah, found some C# code for generating hashes: https://zenhax.com/viewtopic.php?p=42344#p42344. I've adapted it to convert the log into hash dictionary. Attaching the resulting file. Here's BMS script for extraction: https://pastebin.com/TctyRd8s

How did you implement the C# code?
## Post #69
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-10T17:02:06+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Very Cool Dude ↑Mon Mar 11, 2019 12:05 am at Mon Mar 11, 2019 12:05 am
>
> 
You can't just look through the game's model viewer and make a log from that? I'd say that's all I would need to get working with it.

([http://www.mediafire.com/file/7z0f8c4gb ... 2.zip/file](http://www.mediafire.com/file/7z0f8c4gbn8mmmn/log_file_2.zip/file)) I have uploaded more log samples. Three files with the same name contain chapters 1 through 8. and the file named Model Viewer is a log of all the characters and enemies in the game.
## Post #70
- Username: Nicknine
- Rank: beginner
- Number of posts: 22
- Joined date: Sun Oct 04, 2015 3:29 am
- Post datetime: 2019-03-10T17:14:07+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Mon Mar 11, 2019 12:50 am at Mon Mar 11, 2019 12:50 am
>
> 
Nicknine wrote: ↑Sun Mar 10, 2019 5:30 pm
Where's the tool you're using to extract the files? This list is not suitable for BMS script since it just has names and not corresponding hashes.

EDIT: Ah, found some C# code for generating hashes: https://zenhax.com/viewtopic.php?p=42344#p42344. I've adapted it to convert the log into hash dictionary. Attaching the resulting file. Here's BMS script for extraction: https://pastebin.com/TctyRd8s


How did you implement the C# code?

Just took the Hash generation code and made a program that runs through the log file line by line generating new lines with hashes.
## Post #71
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T17:17:55+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Nicknine ↑Mon Mar 11, 2019 1:14 am at Mon Mar 11, 2019 1:14 am
>
> 
OrangeC wrote: ↑Mon Mar 11, 2019 12:50 am
Nicknine wrote: ↑Sun Mar 10, 2019 5:30 pm
Where's the tool you're using to extract the files? This list is not suitable for BMS script since it just has names and not corresponding hashes.

EDIT: Ah, found some C# code for generating hashes: https://zenhax.com/viewtopic.php?p=42344#p42344. I've adapted it to convert the log into hash dictionary. Attaching the resulting file. Here's BMS script for extraction: https://pastebin.com/TctyRd8s


How did you implement the C# code?


Just took the Hash generation code and made a program that runs through the log file line by line generating new lines with hashes.

How did you do that?

I tried pasting it in visual studio, building an exe, then dragging the log file onto it but it didn't work
## Post #72
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-10T17:23:47+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Is this a C# or C++ program?
## Post #73
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-10T18:50:48+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Ok just went through 80% of meshes, two things, theres 2 at least 2 types of each mesh i assume high/mid poly gallery mesh and in game mesh which is low poly so possibly iit`s better to just log gallery instead of wasting time on playing to get lower res models
## Post #74
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-03-10T19:19:10+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I added a feature to my RE PAK tool which should hopefully help with managing file lists for PAK extraction.

More info about the tool here: [http://residentevilmodding.boards.net/t ... iting-tool](http://residentevilmodding.boards.net/thread/10567/pak-tex-editing-tool)

The tool can extract PAK files, but it has a new feature which lets you combine file lists:

```
REtool.exe -combineHashlists list1.txt list2.txt
```


This will create a list called list1.txt.new which is a combination of both lists with all duplicates removed. Either list can be in the style of re2_pak_names_release.list (hash and filepath for each line) or the log files dumped by Ekey's tool ([https://zenhax.com/viewtopic.php?p=43537#p43537](https://zenhax.com/viewtopic.php?p=43537#p43537)).

Note that it will be slow with really large log files, but give it a few minutes and it will finish.

It would be nice if someone would take the responsibility of managing a "master" file list which is a combination of the various path dumbs people are creating with Ekey's tool.
## Post #75
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2019-03-10T19:44:43+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Mon Mar 11, 2019 1:02 am at Mon Mar 11, 2019 1:02 am
>
> (http://www.mediafire.com/file/7z0f8c4gb ... 2.zip/file) I have uploaded more log samples. Three files with the same name contain chapters 1 through 8. and the file named Model Viewer is a log of all the characters and enemies in the game.

Ok, using all the log files you posted (this one and previous), and my hacked together program, here's the list file: [https://mega.nz/#!GuYAUQIL!c8101qbwyEnV ... sohm6zu9IY](https://mega.nz/#!GuYAUQIL!c8101qbwyEnVzvr1ThfyA-2EYipBB2I2jsohm6zu9IY)

FluffyQuack/Sectus' RE PAK tool now says:

```
22839 (34%) unknown filenames
```


So it's about 2/3 complete.
## Post #76
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-03-10T21:22:00+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Mon Mar 11, 2019 3:44 am at Mon Mar 11, 2019 3:44 am
>
> 
uroborostestsubject wrote: ↑Mon Mar 11, 2019 1:02 am(http://www.mediafire.com/file/7z0f8c4gb ... 2.zip/file) I have uploaded more log samples. Three files with the same name contain chapters 1 through 8. and the file named Model Viewer is a log of all the characters and enemies in the game.

Ok, using all the log files you posted (this one and previous), and my hacked together program, here's the list file: https://mega.nz/#!GuYAUQIL!c8101qbwyEnV ... sohm6zu9IY

FluffyQuack/Sectus' RE PAK tool now says:
Code: Select all44109 (65%) known filenames
22839 (34%) unknown filenames

So it's about 2/3 complete.
Just combined a log I made with your list: [http://www.fluffyquack.com/temp/dmc5_pa ... lease.list](http://www.fluffyquack.com/temp/dmc5_pak_names_release.list)

That brings us to:

```
48380 (72%) known filenames
```
## Post #77
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T21:38:51+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Thanks guys I managed to extract lots of files, got all the sound files and music.

Noticed theres a mission21, but that's just the name for all the credits stuff.
Also noticed mission63, with 4 soundtracks in a bnk/pck file, it's only distant storms and thunder, maybe bloodypalace?

Also the player ID's are seen, pl0000 for nero, pl0100 for Dante, pl0200 V, pl0300 Vergil, this made me think Vergil is playable (for maybe bloodypalace) so maybe with memory editing we can make him playable in any mission? But then I saw pl0400, pl0500, pl0600 for trish, nico, morrison etc.

Also, does anyone know how to view the meshes/3d models/textures?
## Post #78
- Username: TheDante
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 11, 2019 3:40 am
- Post datetime: 2019-03-10T21:42:32+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Hi guys , im new to this things , i need some 3d models from this game(Demon Dante Sword etc.)
I tried ninja ripper but not working , anyone help for me please , where can i start ?
## Post #79
- Username: Crux
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Mar 10, 2019 9:53 pm
- Post datetime: 2019-03-10T21:45:47+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Sun Mar 10, 2019 1:35 am at Sun Mar 10, 2019 1:35 am
>
> 
Now I have progressed to this state. All that remains is to convert the TEX file. I would appreciate if anyone who is capable of programming could share information.

How can I view the 3d models like you?
## Post #80
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-10T22:03:16+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Crux ↑Mon Mar 11, 2019 5:38 am at Mon Mar 11, 2019 5:38 am
>
> 
Thanks guys I managed to extract lots of files, got all the sound files and music.

Noticed theres a mission21, but that's just the name for all the credits stuff.
Also noticed mission63, with 4 soundtracks in a bnk/pck file, it's only distant storms and thunder, maybe bloodypalace?

Also the player ID's are seen, pl0000 for nero, pl0100 for Dante, pl0200 V, pl0300 Vergil, this made me think Vergil is playable (for maybe bloodypalace) so maybe with memory editing we can make him playable in any mission? But then I saw pl0400, pl0500, pl0600 for trish, nico, morrison etc.

Also, does anyone know how to view the meshes/3d models/textures?

any chance You could point me to direction of music? or upload it somewhere?
## Post #81
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-11T00:02:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Mon Mar 11, 2019 3:44 am at Mon Mar 11, 2019 3:44 am
>
> 
uroborostestsubject wrote: ↑Mon Mar 11, 2019 1:02 am(http://www.mediafire.com/file/7z0f8c4gb ... 2.zip/file) I have uploaded more log samples. Three files with the same name contain chapters 1 through 8. and the file named Model Viewer is a log of all the characters and enemies in the game.

Ok, using all the log files you posted (this one and previous), and my hacked together program, here's the list file: https://mega.nz/#!GuYAUQIL!c8101qbwyEnV ... sohm6zu9IY

FluffyQuack/Sectus' RE PAK tool now says:
Code: Select all44109 (65%) known filenames
22839 (34%) unknown filenames

So it's about 2/3 complete.

([http://www.mediafire.com/file/u2iab1c47 ... e.zip/file](http://www.mediafire.com/file/u2iab1c47ias7io/Enemy_Sample.zip/file)) Thank you very much! You are my hero.  This link is an enemy sample extracted from your list. The only remaining problem is that Noesis needs to convert these files, but both texture(tex.11) files or mesh(1808282334) files are not converted. I would like you to create new Noesis script based on this sample.
## Post #82
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-11T00:11:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Can anyone update the list to include the remaining PACK files for the wwise folder?

Seems some bgm mission packs are missing like mission 13 14 15 and 16.
## Post #83
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-11T00:14:21+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Mon Mar 11, 2019 8:11 am at Mon Mar 11, 2019 8:11 am
>
> 
Can anyone update the list to include the remaining PACK files for the wwise folder?

Seems some bgm mission packs are missing like mission 13 14 15 and 16.

sorry to bother, any idea how to convert those audio files to something possible to listen to?
## Post #84
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2019-03-11T00:16:02+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from uroborostestsubject ↑Mon Mar 11, 2019 8:02 am at Mon Mar 11, 2019 8:02 am
>
> (http://www.mediafire.com/file/u2iab1c47 ... e.zip/file) Thank you very much! You are my hero.  This link is an enemy sample extracted from your list. The only remaining problem is that Noesis needs to convert these files, but both texture(tex.11) files or mesh(1808282334) files are not converted. I would like you to create new Noesis script based on this sample.

The script posted on page 3: [https://forum.xentax.com/download/file.php?id=15867](https://forum.xentax.com/download/file.php?id=15867) does convert textures in Noesis. You have to just rename the texture from tex.11 to just .tex, and it'll recognize it. I was able to extract textures and change the UI to swap out to the DualShock buttons.
## Post #85
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2019-03-11T00:58:39+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Mon Mar 11, 2019 8:14 am at Mon Mar 11, 2019 8:14 am
>
> 
OrangeC wrote: ↑Mon Mar 11, 2019 8:11 am
Can anyone update the list to include the remaining PACK files for the wwise folder?

Seems some bgm mission packs are missing like mission 13 14 15 and 16.


sorry to bother, any idea how to convert those audio files to something possible to listen to?

rename the .x64 bgm packs to .pck extension, use ravioligameextractor to extract the packs each into a subdirectory. convert the wems with foobar2000 with the vgmstream plugin.
## Post #86
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-03-11T02:36:08+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

So can someone upload the log tool or provide a link to it? Can't seem to find it on XeNTaX............................................................................................................

Also explain how to use it with DMC5.
## Post #87
- Username: superspider51
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 11, 2019 8:07 am
- Post datetime: 2019-03-11T02:40:48+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

some more logs for y'all. [http://www.mediafire.com/file/8v5s2b0c7 ... g.zip/file](http://www.mediafire.com/file/8v5s2b0c77ozckp/log.zip/file)
## Post #88
- Username: uroborostestsubject
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Nov 23, 2017 7:11 pm
- Post datetime: 2019-03-11T02:57:39+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Mon Mar 11, 2019 8:16 am at Mon Mar 11, 2019 8:16 am
>
> 
uroborostestsubject wrote: ↑Mon Mar 11, 2019 8:02 am(http://www.mediafire.com/file/u2iab1c47 ... e.zip/file) Thank you very much! You are my hero.  This link is an enemy sample extracted from your list. The only remaining problem is that Noesis needs to convert these files, but both texture(tex.11) files or mesh(1808282334) files are not converted. I would like you to create new Noesis script based on this sample. 


The script posted on page 3: https://forum.xentax.com/download/file.php?id=15867 does convert textures in Noesis. You have to just rename the texture from tex.11 to just .tex, and it'll recognize it. I was able to extract textures and change the UI to swap out to the DualShock buttons.

Thank you very much! Now I'm ready to extract all the models. The rest of the log files will be uploaded around the weekend. Thank you again!
## Post #89
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-03-11T03:16:36+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Gh0stBlade ↑Mon Mar 11, 2019 10:36 am at Mon Mar 11, 2019 10:36 am
>
> 
So can someone upload the log tool or provide a link to it? Can't seem to find it on XeNTaX............................................................................................................

Also explain how to use it with DMC5.
BUMP

Or is everyone being selfish with private tools again?
## Post #90
- Username: chalon
- Rank: n00b
- Number of posts: 16
- Joined date: Sun May 22, 2011 3:20 am
- Post datetime: 2019-03-11T03:31:45+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Gh0stBlade ↑Mon Mar 11, 2019 10:36 am at Mon Mar 11, 2019 10:36 am
>
> 
So can someone upload the log tool or provide a link to it? Can't seem to find it on XeNTaX............................................................................................................

Also explain how to use it with DMC5.

People are using Ekey's hook DLLs from RE2 Remake to get the log. The latest version, I believe, is here: [https://zenhax.com/download/file.php?id=6350](https://zenhax.com/download/file.php?id=6350)

Once you run that, you can use Sectus' tool to combine it with the list file posted above.
## Post #91
- Username: rugalytto
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2019-03-11T03:39:11+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from chalon ↑Mon Mar 11, 2019 11:31 am at Mon Mar 11, 2019 11:31 am
>
> 
Gh0stBlade wrote: ↑Mon Mar 11, 2019 10:36 am
So can someone upload the log tool or provide a link to it? Can't seem to find it on XeNTaX............................................................................................................

Also explain how to use it with DMC5.


People are using Ekey's hook DLLs from RE2 Remake to get the log. The latest version, I believe, is here: https://zenhax.com/download/file.php?id=6350

Once you run that, you can use Sectus' tool to combine it with the list file posted above.
Thank you
## Post #92
- Username: pandoodles
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 10, 2019 9:09 pm
- Post datetime: 2019-03-11T08:14:28+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I am so happy I finally found a thread making steady progress on DMC5 modding! 

Does anyone know how to get those .mesh files into Blender 2.8 by any chance? Some kind of format converter perhaps?
## Post #93
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-11T08:28:36+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Mon Mar 11, 2019 8:58 am at Mon Mar 11, 2019 8:58 am
>
> 
lyhtem wrote: ↑Mon Mar 11, 2019 8:14 am
OrangeC wrote: ↑Mon Mar 11, 2019 8:11 am
Can anyone update the list to include the remaining PACK files for the wwise folder?

Seems some bgm mission packs are missing like mission 13 14 15 and 16.


sorry to bother, any idea how to convert those audio files to something possible to listen to?


rename the .x64 bgm packs to .pck extension, use ravioligameextractor to extract the packs each into a subdirectory. convert the wems with foobar2000 with the vgmstream plugin.

Thank You
## Post #94
- Username: TheDante
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 11, 2019 3:40 am
- Post datetime: 2019-03-11T09:29:15+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Which extention contain the 3d models ? .mes files ? 
And how can i open them ? ? Any plugin for noesis ?
## Post #95
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-11T09:44:38+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from TheDante ↑Mon Mar 11, 2019 5:29 pm at Mon Mar 11, 2019 5:29 pm
>
> 
Which extention contain the 3d models ? .mes files ? 
And how can i open them ? ? Any plugin for noesis ?

Read everything carefully all is explained
## Post #96
- Username: pandoodles
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 10, 2019 9:09 pm
- Post datetime: 2019-03-11T10:01:33+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Mon Mar 11, 2019 5:44 pm at Mon Mar 11, 2019 5:44 pm
>
> 
TheDante wrote: ↑Mon Mar 11, 2019 5:29 pm
Which extention contain the 3d models ? .mes files ? 
And how can i open them ? ? Any plugin for noesis ?


Read everything carefully all is explained
I'm having similar issues to TheDante. I've read the thread carefully to the best of my ability but I cannot find out how to get the meshes to load in noesis. It seems only the textures works while the meshes gives me a "This file cannot be previewed" pop-up. Do you have an idea of what I could be doing wrong?
## Post #97
- Username: TheDante
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 11, 2019 3:40 am
- Post datetime: 2019-03-11T10:03:56+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Mon Mar 11, 2019 5:44 pm at Mon Mar 11, 2019 5:44 pm
>
> 
TheDante wrote: ↑Mon Mar 11, 2019 5:29 pm
Which extention contain the 3d models ? .mes files ? 
And how can i open them ? ? Any plugin for noesis ?


Read everything carefully all is explained

Sorry but i cannot find any script/plugin/tool for .mes files.I am new at this thing.I extract it can open tex file but dont find any tool for .mes files.
## Post #98
- Username: vainiuss1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2015 1:05 am
- Post datetime: 2019-03-11T10:05:35+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

tried the re2hook thing on dmc5 to make a file list
here is what I quickly got.
played mission 1-3, went trough some menus, played some void and watched all cutscenes in jap language
[http://www.mediafire.com/file/77u224x9m ... y+Cry+5.7z](http://www.mediafire.com/file/77u224x9my141fj/Devil+May+Cry+5.7z)

What else can I do to help out with this list?
## Post #99
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-03-11T11:36:26+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from vainiuss1 ↑Mon Mar 11, 2019 6:05 pm at Mon Mar 11, 2019 6:05 pm
>
> 
tried the re2hook thing on dmc5 to make a file list
here is what I quickly got.
played mission 1-3, went trough some menus, played some void and watched all cutscenes in jap language
http://www.mediafire.com/file/77u224x9m ... y+Cry+5.7z

What else can I do to help out with this list?
Doing rare stuff is the key thing now. I'm pretty sure the biggest list we have right now is based on one playthrough. So now it's a matter of finding the unusual stuff.
## Post #100
- Username: wanwanthw
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 11:03 pm
- Post datetime: 2019-03-11T12:51:06+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

sorry my bad english...
I don't know how to see %...
But...
FluffyQuack update list, have 48,895 lines
superspider51 update 3 .log, add 11,287 lines
vainiuss1 update 2 .log, add 3,335 lines
now is 63,517 lines

[http://www.mediafire.com/file/7kwwprzf9 ... e.zip/file](http://www.mediafire.com/file/7kwwprzf9sydqw2/dmc5_pak_names_release.zip/file)
## Post #101
- Username: DioBrando
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Sep 06, 2010 11:59 am
- Post datetime: 2019-03-11T12:51:32+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from pandoodles ↑Mon Mar 11, 2019 6:01 pm at Mon Mar 11, 2019 6:01 pm
>
> 
lyhtem wrote: ↑Mon Mar 11, 2019 5:44 pm
TheDante wrote: ↑Mon Mar 11, 2019 5:29 pm
Which extention contain the 3d models ? .mes files ? 
And how can i open them ? ? Any plugin for noesis ?


Read everything carefully all is explained

I'm having similar issues to TheDante. I've read the thread carefully to the best of my ability but I cannot find out how to get the meshes to load in noesis. It seems only the textures works while the meshes gives me a "This file cannot be previewed" pop-up. Do you have an idea of what I could be doing wrong?
After you extract files with quickbms and the name list here:
[https://forum.xentax.com/viewtopic.php? ... 75#p149386](https://forum.xentax.com/viewtopic.php?f=10&t=19608&start=75#p149386)
edit: use the one wanwanthw just posted above

get this noesis script fmt_RE2_mesh_1_7.zip from the RE2 thread
[https://forum.xentax.com/viewtopic.php? ... 20#p148651](https://forum.xentax.com/viewtopic.php?f=10&t=19304&sid=5acf5d8b7f632aa0f388f55a2cbdac70&start=120#p148651)

it will work with DMC5 if you edit the extensions inside the py to .1808282334 and .11 (except for .mdf2.10)
If you want the textures to auto-load make sure the .mdf2.10 and .1808282334 have the same name. So you would rename something like pl0500.mdf2.10 to pl0500.mesh.mdf2.10. Read the RE2 thread
Not sure about the skeletons exporting well from noesis but I think the 3dsmax script in that thread works better for them. That's what I used for RE2.
## Post #102
- Username: pandoodles
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 10, 2019 9:09 pm
- Post datetime: 2019-03-11T14:03:05+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from DioBrando ↑Mon Mar 11, 2019 8:51 pm at Mon Mar 11, 2019 8:51 pm
>
> 
pandoodles wrote: ↑Mon Mar 11, 2019 6:01 pm
lyhtem wrote: ↑Mon Mar 11, 2019 5:44 pm


Read everything carefully all is explained

I'm having similar issues to TheDante. I've read the thread carefully to the best of my ability but I cannot find out how to get the meshes to load in noesis. It seems only the textures works while the meshes gives me a "This file cannot be previewed" pop-up. Do you have an idea of what I could be doing wrong?

After you extract files with quickbms and the name list here:
https://forum.xentax.com/viewtopic.php? ... 75#p149386
edit: use the one wanwanthw just posted above

get this noesis script fmt_RE2_mesh_1_7.zip from the RE2 thread
https://forum.xentax.com/viewtopic.php? ... 20#p148651

it will work with DMC5 if you edit the extensions inside the py to .1808282334 and .11 (except for .mdf2.10)
If you want the textures to auto-load make sure the .mdf2.10 and .1808282334 have the same name. So you would rename something like pl0500.mdf2.10 to pl0500.mesh.mdf2.10. Read the RE2 thread
Not sure about the skeletons exporting well from noesis but I think the 3dsmax script in that thread works better for them. That's what I used for RE2.

Thanks a bunch! That script worked wonders here(it turns out I had to update Noesis as well). Also it appears that the FBX export does indeed keep the bones and skinning intact from what I can tell!
## Post #103
- Username: vainiuss1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2015 1:05 am
- Post datetime: 2019-03-11T14:07:34+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from wanwanthw ↑Mon Mar 11, 2019 8:51 pm at Mon Mar 11, 2019 8:51 pm
>
> 
sorry my bad english...
I don't know how to see %...
But...
FluffyQuack update list, have 48,895 lines
superspider51 update 2 .log, add 11,287 lines
vainiuss1 update 3 .log, add 3,335 lines
now is 63,517 lines

http://www.mediafire.com/file/7kwwprzf9 ... e.zip/file

did you use both of my txt files?
## Post #104
- Username: wanwanthw
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 11:03 pm
- Post datetime: 2019-03-11T14:23:19+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from vainiuss1 ↑Mon Mar 11, 2019 10:07 pm at Mon Mar 11, 2019 10:07 pm
>
> 
wanwanthw wrote: ↑Mon Mar 11, 2019 8:51 pm
sorry my bad english...
I don't know how to see %...
But...
FluffyQuack update list, have 48,895 lines
superspider51 update 2 .log, add 11,287 lines
vainiuss1 update 3 .log, add 3,335 lines
now is 63,517 lines

http://www.mediafire.com/file/7kwwprzf9 ... e.zip/file


did you use both of my txt files?
Yes.
and, sorry, two .log, not three.
someone has played mission 1 to mission 8, you will only have 3,335 lines added, 
because your many .log is already included in the FluffyQuack update list.
## Post #105
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-03-11T15:34:48+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from wanwanthw ↑Mon Mar 11, 2019 8:51 pm at Mon Mar 11, 2019 8:51 pm
>
> 
sorry my bad english...
I don't know how to see %...
But...
FluffyQuack update list, have 48,895 lines
superspider51 update 3 .log, add 11,287 lines
vainiuss1 update 2 .log, add 3,335 lines
now is 63,517 lines

http://www.mediafire.com/file/7kwwprzf9 ... e.zip/file

```
5263 (7%) unknown filenames
```


So that's pretty good. Only 7% of files are unknown.
## Post #106
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-03-11T18:12:22+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

For people interested in modding DMC5, I updated my mod manager to support installing and uninstalling mods for the game: [http://residentevilmodding.boards.net/t ... -pak-files](http://residentevilmodding.boards.net/thread/10142/modding-pak-files)

Sample mods here: [http://www.fluffyquack.com/mods/DMC5/by-fluffyquack/](http://www.fluffyquack.com/mods/DMC5/by-fluffyquack/)
## Post #107
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2019-03-11T18:41:13+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Sectus ↑Tue Mar 12, 2019 2:12 am at Tue Mar 12, 2019 2:12 am
>
> 
For people interested in modding DMC5, I updated my mod manager to support installing and uninstalling mods for the game: http://residentevilmodding.boards.net/t ... -pak-files

Sample mods here: http://www.fluffyquack.com/mods/DMC5/by-fluffyquack/

Thanks!!! Thank you so so much!
I found what I needed to create new skins here:
[http://residentevilmodding.boards.net/t ... g-tutorial](http://residentevilmodding.boards.net/thread/10549/re2-ultimate-modding-tutorial)
## Post #108
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-12T02:09:57+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Sectus ↑Mon Mar 11, 2019 11:34 pm at Mon Mar 11, 2019 11:34 pm
>
> 
wanwanthw wrote: ↑Mon Mar 11, 2019 8:51 pm
sorry my bad english...
I don't know how to see %...
But...
FluffyQuack update list, have 48,895 lines
superspider51 update 3 .log, add 11,287 lines
vainiuss1 update 2 .log, add 3,335 lines
now is 63,517 lines

http://www.mediafire.com/file/7kwwprzf9 ... e.zip/file

Code: Select all61685 (92%) known filenames
5263 (7%) unknown filenames

So that's pretty good. Only 7% of files are unknown.

I went through the unknown .mes files and all of them are from stages. Most likely secret missions or parts of the map the player did not go to.
## Post #109
- Username: stage0610
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Nov 08, 2018 11:04 pm
- Post datetime: 2019-03-12T09:12:16+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Does anyone know if there is any plugin or scripts for Blender 2.79?
The 3dsmax scripts went some errors when i import dmc5's model
Or is there any new scripts on 3dsmax for dmc5?
## Post #110
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-12T10:22:40+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from OrangeC ↑Mon Mar 11, 2019 8:58 am at Mon Mar 11, 2019 8:58 am
>
> 
lyhtem wrote: ↑Mon Mar 11, 2019 8:14 am
OrangeC wrote: ↑Mon Mar 11, 2019 8:11 am
Can anyone update the list to include the remaining PACK files for the wwise folder?

Seems some bgm mission packs are missing like mission 13 14 15 and 16.


sorry to bother, any idea how to convert those audio files to something possible to listen to?


rename the .x64 bgm packs to .pck extension, use ravioligameextractor to extract the packs each into a subdirectory. convert the wems with foobar2000 with the vgmstream plugin.

OK tried that Yesterday, ended up with loads of files but no Joy after that, all seem to be unreadable after i try to listen to them using foobar, everything was installed correctly
## Post #111
- Username: NeoTokyo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 12, 2019 1:31 am
- Post datetime: 2019-03-12T19:13:09+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

alright so ive been trying to get this to work for about a whole day now. I managed to extract all the files sucessfully, however all the names are like 000000000001057.mes and there is no way for me to know what is what.
All I want is the .mes file of Nero's Devil breaker so I can 3d print it. Any help would be much appreciated. I am really new to this so please bear with me if I dont get what you said straight away (simple intructions as possible) thanks!
## Post #112
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2019-03-12T20:12:17+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from NeoTokyo ↑Wed Mar 13, 2019 3:13 am at Wed Mar 13, 2019 3:13 am
>
> 
alright so ive been trying to get this to work for about a whole day now. I managed to extract all the files sucessfully, however all the names are like 000000000001057.mes and there is no way for me to know what is what.
All I want is the .mes file of Nero's Devil breaker so I can 3d print it. Any help would be much appreciated. I am really new to this so please bear with me if I dont get what you said straight away (simple intructions as possible) thanks!

those are unprintable, way to many one sided polys, and thickening will cause the model to look like crap
## Post #113
- Username: sydie
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Nov 30, 2016 6:45 am
- Post datetime: 2019-03-12T21:13:14+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Gh0stBlade ↑Mon Mar 11, 2019 11:39 am at Mon Mar 11, 2019 11:39 am
>
> 
chalon wrote: ↑Mon Mar 11, 2019 11:31 am
Gh0stBlade wrote: ↑Mon Mar 11, 2019 10:36 am
So can someone upload the log tool or provide a link to it? Can't seem to find it on XeNTaX............................................................................................................

Also explain how to use it with DMC5.


People are using Ekey's hook DLLs from RE2 Remake to get the log. The latest version, I believe, is here: https://zenhax.com/download/file.php?id=6350

Once you run that, you can use Sectus' tool to combine it with the list file posted above.

Thank you
@Gh0stBlade Thank you for your work on RE2 and your Noesis Python importer !!!
I've modified this script to work for DMC5 and so far it works like a charm.
One small fix added on line 157, so there's no need to manually go and rename the materials file.

Thank you!
[fmt_DMC5_mesh_1_7.zip](https://xentaxbackup.github.io/file/15871_fmt_DMC5_mesh_1_7.zip)
## Post #114
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-13T01:34:02+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from lyhtem ↑Tue Mar 12, 2019 6:22 pm at Tue Mar 12, 2019 6:22 pm
>
> 
OrangeC wrote: ↑Mon Mar 11, 2019 8:58 am
lyhtem wrote: ↑Mon Mar 11, 2019 8:14 am


sorry to bother, any idea how to convert those audio files to something possible to listen to?


rename the .x64 bgm packs to .pck extension, use ravioligameextractor to extract the packs each into a subdirectory. convert the wems with foobar2000 with the vgmstream plugin.


OK tried that Yesterday, ended up with loads of files but no Joy after that, all seem to be unreadable after i try to listen to them using foobar, everything was installed correctly

update the vgm plugin
## Post #115
- Username: Krauser Kahn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2017 11:49 pm
- Post datetime: 2019-03-13T01:52:38+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Tried to run the Hook without success, when I start the game with the hook it does nothing. Process is running in the background but game window doesn't appear. 

I wanted to know which files are for the EX costumes as a quick search in the logs didn't help much as I don't know the exact names.
## Post #116
- Username: pandoodles
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 10, 2019 9:09 pm
- Post datetime: 2019-03-13T03:28:15+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

After successfully editing a model in Blender 2.8 how do you export/convert the format back to .mesh?
## Post #117
- Username: yourgayfather
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 13, 2019 6:14 pm
- Post datetime: 2019-03-13T10:19:44+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Upon dragging any of the .pak files onto the extract-pak batch file, the batch closes immediately and nothing happens. Can anybody help with this?
## Post #118
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-13T12:46:48+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from yourgayfather ↑Wed Mar 13, 2019 6:19 pm at Wed Mar 13, 2019 6:19 pm
>
> 
Upon dragging any of the .pak files onto the extract-pak batch file, the batch closes immediately and nothing happens. Can anybody help with this?

Batch? Use quickbms.
## Post #119
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-13T12:48:13+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Krauser Kahn ↑Wed Mar 13, 2019 9:52 am at Wed Mar 13, 2019 9:52 am
>
> 
Tried to run the Hook without success, when I start the game with the hook it does nothing. Process is running in the background but game window doesn't appear. 

I wanted to know which files are for the EX costumes as a quick search in the logs didn't help much as I don't know the exact names.

The ex costumes may be in the dlc folders but there are low quality textures in player folder with "c" eg. "pl000_c00_nero"
## Post #120
- Username: Krauser Kahn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2017 11:49 pm
- Post datetime: 2019-03-13T14:28:00+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from LordKiriYT ↑Wed Mar 13, 2019 8:48 pm at Wed Mar 13, 2019 8:48 pm
>
> 
Krauser Kahn wrote: ↑Wed Mar 13, 2019 9:52 am
Tried to run the Hook without success, when I start the game with the hook it does nothing. Process is running in the background but game window doesn't appear. 

I wanted to know which files are for the EX costumes as a quick search in the logs didn't help much as I don't know the exact names.


The ex costumes may be in the dlc folders but there are low quality textures in player folder with "c" eg. "pl000_c00_nero"
I'm not 100% sure, but I think some files missing in the lists are indeed the EX colors of NPCs which you can change in cinematics. I tried to extract Nico's EX textures but in the current .list we don't have anything like 'pl0400_c00_nico'. So I'll try to make the Hook work and see if I can catch those.
## Post #121
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2019-03-13T15:57:48+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

I hate having to ask but can someone please tell me what I'm doing wrong? I cant seem to export anything other then .bin from the pak files with the RE Engine tool and if I try the BMS script it just fails . I've re-read the threads multiple times but I just don't get it. All I'm after is the models.
## Post #122
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-13T16:39:36+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Since so many people are having pRoBlEmS extracting data from Devil May Cry 5. Heres a simple tutorial. All links to files are in this forum and the programs used can be quickly googled and downloaded. 

1. Download quickbms. 
2. Download noesis. (make sure it is up to date)
3. Download the .pak unpacker.
4. Download the latest file list for dmc5 and ensure that inside the quickbms script (using notepad) the .list filename matches the .list file you downloaded.
5. Download the latest noesis plugin for dmc5 and install.
6. Unpack the .pak file using noesis
7. Boom you're done. Use noesis to find whatever models and textures you want.
## Post #123
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-13T16:50:09+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Krauser Kahn ↑Wed Mar 13, 2019 10:28 pm at Wed Mar 13, 2019 10:28 pm
>
> 
LordKiriYT wrote: ↑Wed Mar 13, 2019 8:48 pm
Krauser Kahn wrote: ↑Wed Mar 13, 2019 9:52 am
Tried to run the Hook without success, when I start the game with the hook it does nothing. Process is running in the background but game window doesn't appear. 

I wanted to know which files are for the EX costumes as a quick search in the logs didn't help much as I don't know the exact names.


The ex costumes may be in the dlc folders but there are low quality textures in player folder with "c" eg. "pl000_c00_nero"

I'm not 100% sure, but I think some files missing in the lists are indeed the EX colors of NPCs which you can change in cinematics. I tried to extract Nico's EX textures but in the current .list we don't have anything like 'pl0400_c00_nico'. So I'll try to make the Hook work and see if I can catch those.

you right you right. I just opened files with the unkown filenames and i saw v's ex colour, too lazy to browse the rest tho
## Post #124
- Username: Krauser Kahn
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Apr 05, 2017 11:49 pm
- Post datetime: 2019-03-13T19:16:07+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from LordKiriYT ↑Thu Mar 14, 2019 12:50 am at Thu Mar 14, 2019 12:50 am
>
> 
Krauser Kahn wrote: ↑Wed Mar 13, 2019 10:28 pm
LordKiriYT wrote: ↑Wed Mar 13, 2019 8:48 pm


The ex costumes may be in the dlc folders but there are low quality textures in player folder with "c" eg. "pl000_c00_nero"

I'm not 100% sure, but I think some files missing in the lists are indeed the EX colors of NPCs which you can change in cinematics. I tried to extract Nico's EX textures but in the current .list we don't have anything like 'pl0400_c00_nico'. So I'll try to make the Hook work and see if I can catch those.


you right you right. I just opened files with the unkown filenames and i saw v's ex colour, too lazy to browse the rest tho

Hook is not working for me, which is a shame. By the way, how do you open the files that aren't in the list to browse its contents? Like the .DAT and so forth.
## Post #125
- Username: LordKiriYT
- Rank: n00b
- Number of posts: 13
- Joined date: Sun Oct 28, 2018 2:55 am
- Post datetime: 2019-03-13T19:56:38+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Krauser Kahn ↑Thu Mar 14, 2019 3:16 am at Thu Mar 14, 2019 3:16 am
>
> 
LordKiriYT wrote: ↑Thu Mar 14, 2019 12:50 am
Krauser Kahn wrote: ↑Wed Mar 13, 2019 10:28 pm

I'm not 100% sure, but I think some files missing in the lists are indeed the EX colors of NPCs which you can change in cinematics. I tried to extract Nico's EX textures but in the current .list we don't have anything like 'pl0400_c00_nico'. So I'll try to make the Hook work and see if I can catch those.


you right you right. I just opened files with the unkown filenames and i saw v's ex colour, too lazy to browse the rest tho


Hook is not working for me, which is a shame. By the way, how do you open the files that aren't in the list to browse its contents? Like the .DAT and so forth.

idk I only checked the .tex and .mes files
## Post #126
- Username: pandoodles
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 10, 2019 9:09 pm
- Post datetime: 2019-03-14T11:58:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Has anyone gotten to the point where they can port custom models back into the game?
## Post #127
- Username: Brochacholaa
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 11, 2019 7:15 pm
- Post datetime: 2019-03-14T13:57:08+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

How exactly do you get the meshes, I have the noesis plugin for textures but nothing for mesh

The RE2R mesh importer for 3ds max also crashes the entire program on most imports
## Post #128
- Username: dracosfire83
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Nov 13, 2015 7:48 am
- Post datetime: 2019-03-14T14:19:05+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from LordKiriYT ↑Thu Mar 14, 2019 12:39 am at Thu Mar 14, 2019 12:39 am
>
> 
Since so many people are having pRoBlEmS extracting data from Devil May Cry 5. Heres a simple tutorial. All links to files are in this forum and the programs used can be quickly googled and downloaded. 

1. Download quickbms. 
2. Download noesis. (make sure it is up to date)
3. Download the .pak unpacker.
4. Download the latest file list for dmc5 and ensure that inside the quickbms script (using notepad) the .list filename matches the .list file you downloaded.
5. Download the latest noesis plugin for dmc5 and install.
6. Unpack the .pak file using noesis
7. Boom you're done. Use noesis to find whatever models and textures you want.

Thanks this is what I missed.
## Post #129
- Username: pandoodles
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sun Mar 10, 2019 9:09 pm
- Post datetime: 2019-03-14T14:38:54+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Brochacholaa ↑Thu Mar 14, 2019 9:57 pm at Thu Mar 14, 2019 9:57 pm
>
> 
How exactly do you get the meshes, I have the noesis plugin for textures but nothing for mesh

The RE2R mesh importer for 3ds max also crashes the entire program on most imports

The previous page has a great script for noesis that handles meshes: [https://forum.xentax.com/viewtopic.php? ... 05#p149466](https://forum.xentax.com/viewtopic.php?f=10&t=19608&start=105#p149466)
## Post #130
- Username: Brochacholaa
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Mar 11, 2019 7:15 pm
- Post datetime: 2019-03-14T16:08:01+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from pandoodles ↑Thu Mar 14, 2019 10:38 pm at Thu Mar 14, 2019 10:38 pm
>
> 
Brochacholaa wrote: ↑Thu Mar 14, 2019 9:57 pm
How exactly do you get the meshes, I have the noesis plugin for textures but nothing for mesh

The RE2R mesh importer for 3ds max also crashes the entire program on most imports


The previous page has a great script for noesis that handles meshes: https://forum.xentax.com/viewtopic.php? ... 05#p149466

Was having some issues with the code but got it working now
## Post #131
- Username: kitakadze
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 14, 2019 11:55 am
- Post datetime: 2019-03-14T18:16:21+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Hello guys!
I'm trying to follow the instructions for extracting dmc models. But I have a problem with the bms script. I use the file re2_pak_unpack.bms  and it gives me an unpacking error. What could be the reason?

> 4. Download the latest file list for dmc5 and ensure that inside the quickbms script (using notepad) the .list filename matches the .list file you downloaded. This step is completed.
## Post #132
- Username: vainiuss1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jun 19, 2015 1:05 am
- Post datetime: 2019-03-16T07:19:22+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

[http://www.mediafire.com/file/a6o9x33o5 ... k+nr+2.rar](http://www.mediafire.com/file/a6o9x33o5z5f4ts/hook+nr+2.rar)

cutscenes watched with ex costumes, should add like 0.5%

need to unlock vergils and v ex costumes first, and play trough the game with different subtitles
## Post #133
- Username: z1035240324
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Sep 25, 2017 9:04 pm
- Post datetime: 2019-03-16T12:17:05+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Among the files I unpacked not have. 1808282334  
How can I solve it?
## Post #134
- Username: ponaromixxx
- Rank: beginner
- Number of posts: 29
- Joined date: Thu Jul 17, 2014 11:52 am
- Post datetime: 2019-03-16T14:40:58+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

A new list of hashes, + 241 hash names!

[dmc5_pak_names_release.list](https://www.mediafire.com/file/q9o2zp0covcbbbs/dmc5_pak_names_release.list/file)
## Post #135
- Username: wanwanthw
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 11:03 pm
- Post datetime: 2019-03-16T14:55:08+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

+241 lines result:
Extracted 66948 files from F:\Devil May Cry 5\re_chunk_000.pak
Extracted 4766 files with zero compression
Extracted 22268 files compressed with deflate
Extracted 39914 files compressed with zstd
## Post #136
- Username: caocuong113
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 16, 2019 6:27 pm
- Post datetime: 2019-03-17T03:25:06+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

i'm stuck at inside V Book . 
how to convert it in a right way?

i'm using HXD
## Post #137
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-03-17T08:06:08+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from caocuong113 ↑Sun Mar 17, 2019 11:25 am at Sun Mar 17, 2019 11:25 am
>
> 
i'm stuck at inside V Book . how to convert it in a right way?
upload the problem sample please.
## Post #138
- Username: caocuong113
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 16, 2019 6:27 pm
- Post datetime: 2019-03-18T14:05:11+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

i'm fixed it , 
but do you know the name of vergil coat file
## Post #139
- Username: NeoTokyo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 12, 2019 1:31 am
- Post datetime: 2019-03-18T18:06:45+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Hi there, I extracted all of the weapon files however there are some high poly and low poly models, the high poly ones when opened in 3ds max look glitched and unusable to print however there are some usable low poly files such as Nero's Devil Breaker. has anyone been able to extract a usbale version of Red Queen and Blue Rose?
## Post #140
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2019-03-19T01:24:49+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from caocuong113 ↑Mon Mar 18, 2019 10:05 pm at Mon Mar 18, 2019 10:05 pm
>
> 
i'm fixed it , 
but do you know the name of vergil coat file

if you used the latest .list file all the folders are self explanatory
## Post #141
- Username: MarcoReckless
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 20, 2019 12:46 pm
- Post datetime: 2019-03-20T14:05:34+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Any idea on how to get the image back to the texture format after editing it?
## Post #142
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2019-03-20T20:21:06+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from MarcoReckless ↑Wed Mar 20, 2019 10:05 pm at Wed Mar 20, 2019 10:05 pm
>
> 
Any idea on how to get the image back to the texture format after editing it?

pvr textool
## Post #143
- Username: MarcoReckless
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Mar 20, 2019 12:46 pm
- Post datetime: 2019-03-21T00:28:06+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Lord Kiri ↑Thu Mar 21, 2019 4:21 am at Thu Mar 21, 2019 4:21 am
>
> 
MarcoReckless wrote: ↑Wed Mar 20, 2019 10:05 pm
Any idea on how to get the image back to the texture format after editing it?


pvr textool

How? I can only convert to .pvr, .ktx and .dds using PVR.
## Post #144
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2019-03-21T14:31:30+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from MarcoReckless ↑Thu Mar 21, 2019 8:28 am at Thu Mar 21, 2019 8:28 am
>
> 
Lord Kiri wrote: ↑Thu Mar 21, 2019 4:21 am
MarcoReckless wrote: ↑Wed Mar 20, 2019 10:05 pm
Any idea on how to get the image back to the texture format after editing it?


pvr textool


How? I can only convert to .pvr, .ktx and .dds using PVR.

oof mb wrong software. Honestly i formatted my pc just the otherday and didnt back up nothin. Forgot the name of it
## Post #145
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2019-03-22T18:00:56+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

anyone able to get nico's van or the full cavaliere in motorcycle form?
## Post #146
- Username: caocuong113
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 16, 2019 6:27 pm
- Post datetime: 2019-04-01T03:08:35+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

how to edit file reportcharacter.msg.14 guys?
i found the nametag but i didn't know how to edit it
## Post #147
- Username: wanwanthw
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Feb 10, 2019 11:03 pm
- Post datetime: 2019-04-01T14:54:24+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from caocuong113 ↑Mon Apr 01, 2019 11:08 am at Mon Apr 01, 2019 11:08 am
>
> 
how to edit file reportcharacter.msg.14 guys?
i found the nametag but i didn't know how to edit it
can also edit DMC5 .msg.14
[https://zenhax.com/viewtopic.php?t=9364](https://zenhax.com/viewtopic.php?t=9364)
## Post #148
- Username: Amitabh
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Sep 16, 2017 9:58 pm
- Post datetime: 2019-04-02T14:20:07+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

can you upload the 3d model of Hell Judecca please
## Post #149
- Username: caocuong113
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Mar 16, 2019 6:27 pm
- Post datetime: 2019-04-02T15:32:54+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from wanwanthw ↑Mon Apr 01, 2019 10:54 pm at Mon Apr 01, 2019 10:54 pm
>
> 
caocuong113 wrote: ↑Mon Apr 01, 2019 11:08 am
how to edit file reportcharacter.msg.14 guys?
i found the nametag but i didn't know how to edit it

can also edit DMC5 .msg.14
https://zenhax.com/viewtopic.php?t=9364
i'm stuck at the font and i don't know how to convert or edit it :'(
## Post #150
- Username: Rayne85
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 16, 2019 10:50 pm
- Post datetime: 2019-04-04T09:18:11+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Hi, I need help here please. I have tried the 3d max script for DMC5 and I was able to import the mesh models, all except for the head event mesh model (The one for the cutscene) Everytime I try to import that, my 3d max stops responding. I really want to know how to import that mesh because I need to try to fix Trish's ugly nose or Vergil's fat jawline in the cutscene    any advices? Thanks a lot
## Post #151
- Username: Zekfad
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 16, 2018 10:45 pm
- Post datetime: 2019-04-04T15:25:46+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from ponaromixxx ↑Sat Mar 16, 2019 10:40 pm at Sat Mar 16, 2019 10:40 pm
>
> 
A new list of hashes, + 241 hash names!

dmc5_pak_names_release.list

To help people in searching by file I sorted it: [dmc5_pack_names_sorted.zip](https://drive.google.com/open?id=1UpdlBuOi4uT98z4BBR6J3CY0J5qrytem) (GDrive)
Statistics:

```
4766 (7%) files stored uncompressed
22268 (33%) files stored compressed with deflate
39914 (59%) files stored compressed with zstd
61926 (92%) known filenames
5022 (7%) unknown filenames

```
## Post #152
- Username: pepodmc
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 28, 2017 1:29 pm
- Post datetime: 2019-04-17T12:14:57+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Zekfad ↑Thu Apr 04, 2019 11:25 pm at Thu Apr 04, 2019 11:25 pm
>
> 
ponaromixxx wrote: ↑Sat Mar 16, 2019 10:40 pm
A new list of hashes, + 241 hash names!

dmc5_pak_names_release.list


To help people in searching by file I sorted it: dmc5_pack_names_sorted.zip (GDrive)
Statistics:
Code: Select allListed 66948 files from ...Steam\steamapps\common\Devil May Cry 5\re_chunk_000.pak
4766 (7%) files stored uncompressed
22268 (33%) files stored compressed with deflate
39914 (59%) files stored compressed with zstd
61926 (92%) known filenames
5022 (7%) unknown filenames

I extracted "re_chunk_000.pak" but i cant find the dlc music files, and i have the deluxe edition
## Post #153
- Username: Zekfad
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jun 16, 2018 10:45 pm
- Post datetime: 2019-04-17T14:44:34+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from pepodmc ↑Wed Apr 17, 2019 8:14 pm at Wed Apr 17, 2019 8:14 pm
>
> 
I extracted "re_chunk_000.pak" but i cant find the dlc music files, and i have the deluxe edition  :o

It need to be reindexed by using dll hook, read about it in 1-4 pages.
## Post #154
- Username: Azelician
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 29, 2019 7:31 pm
- Post datetime: 2019-04-29T14:25:59+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Hello guys, how to convert back to mesh.1808282334 the edited objects (.obj, .fbx etc)?
## Post #155
- Username: Sectus
- Rank: veteran
- Number of posts: 98
- Joined date: Wed Sep 16, 2009 12:47 am
- Post datetime: 2019-06-21T10:10:23+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

New filelist which includes files related to Bloody Palace:

```
22268 (33%) files stored compressed with deflate
39914 (59%) files stored compressed with zstd
62827 (93%) known filenames
4121 (6%) unknown filenames
```

[https://cdn.discordapp.com/attachments/ ... elease.rar](https://cdn.discordapp.com/attachments/549682452608712705/591570013723295744/dmc5_pak_names_release.rar)
## Post #156
- Username: nerosparda
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Aug 28, 2020 8:06 am
- Post datetime: 2020-08-28T00:09:08+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

any update to the file list for dante's office/agency (the one from the in-game cutscene in mission 10)?
## Post #157
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-12-29T15:28:51+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from Nicknine ↑Sun Mar 10, 2019 5:30 pm at Sun Mar 10, 2019 5:30 pm
>
> 
Where's the tool you're using to extract the files? This list is not suitable for BMS script since it just has names and not corresponding hashes.

EDIT: Ah, found some C# code for generating hashes: https://zenhax.com/viewtopic.php?p=42344#p42344. I've adapted it to convert the log into hash dictionary. Attaching the resulting file. Here's BMS script for extraction: https://pastebin.com/TctyRd8s

The link for that BMS script is 404 and I cannot find it anywhere else in the thread, is it avaliable anywhere?
I have been trying to get the new vergil audio and models, which are not in the latest list file, RE2Hook logs [https://mega.nz/file/OG5VwapD#-XZT164Zz ... Hp1awutDlM](https://mega.nz/file/OG5VwapD#-XZT164ZzufSoFfNyB_66CPzpq3cXxhAxHp1awutDlM)

On a side note In my troubleshooting I found that Win 10 2020 and 1909 do not work with REHook, Win 10 1903 sometimes works and RE2Hook_0.05 crashes alot with DMC5 while RE2Hook_0.04 does not crash as much.
The logs are from a Win 7 PC.

Update
Nevermind, I did not reasile that for RETool they are both usable.
## Post #158
- Username: errormdl
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 24, 2017 6:47 am
- Post datetime: 2021-05-20T02:02:43+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

Does anyone have an updated file list (or even just logs) including the Vergil DLC content? Unfortunately the link to the log 09williamsad posted is dead, and as I'm on windows 10 I can't get either version 0.04 or 0.05 of Ekey's RE2 hook to work (obtained from here:[https://zenhax.com/viewtopic.php?f=9&t= ... ook#p52885](https://zenhax.com/viewtopic.php?f=9&t=9253&p=52891&hilit=hook#p52885)).
## Post #159
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2021-05-20T15:59:53+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from errormdl ↑Thu May 20, 2021 10:02 am at Thu May 20, 2021 10:02 am
>
> 
Does anyone have an updated file list (or even just logs) including the Vergil DLC content? Unfortunately the link to the log 09williamsad posted is dead, and as I'm on windows 10 I can't get either version 0.04 or 0.05 of Ekey's RE2 hook to work (obtained from here:https://zenhax.com/viewtopic.php?f=9&t= ... ook#p52885).

Its here [https://residentevilmodding.boards.net/ ... iting-tool](https://residentevilmodding.boards.net/thread/10567/pak-tex-editing-tool)
## Post #160
- Username: errormdl
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 24, 2017 6:47 am
- Post datetime: 2021-05-20T20:59:50+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from 09williamsad ↑Thu May 20, 2021 11:59 pm at Thu May 20, 2021 11:59 pm
>
> 
Its here https://residentevilmodding.boards.net/ ... iting-tool

Thanks! I saw that thread, but I assumed the file list was old. Since the provided list was just the filenames, I've made a list with the hashes:

[https://mega.nz/file/AKp0RCCS#YyPL9xr4p ... sncqSF46uU](https://mega.nz/file/AKp0RCCS#YyPL9xr4pEmxvBq--TO8Ozm2kNiKi6_7vsncqSF46uU)

I also made a list for use with Scobalula's Tyrant RE Engine Extractor ([https://github.com/Scobalula/Tyrant](https://github.com/Scobalula/Tyrant)). Just remove DevilMayCry5NameCache0.tcache from the TyrantCache folder and replace it with the below file

[https://mega.nz/file/caoC3ASB#gwoLCyEoO ... QXKQPFusFo](https://mega.nz/file/caoC3ASB#gwoLCyEoOTBX8tRLIs7ZDZo_6H9KMAeJUQXKQPFusFo)
## Post #161
- Username: XieLongWu
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 27, 2022 5:30 pm
- Post datetime: 2022-05-27T09:34:34+00:00
- Post Title: Re: Devil may cry 5 RE engine file list.

> Reply from errormdl ↑Fri May 21, 2021 4:59 am at Fri May 21, 2021 4:59 am
>
> 
09williamsad wrote: ↑Thu May 20, 2021 11:59 pm
Its here https://residentevilmodding.boards.net/ ... iting-tool


Thanks! I saw that thread, but I assumed the file list was old. Since the provided list was just the filenames, I've made a list with the hashes:

https://mega.nz/file/AKp0RCCS#YyPL9xr4p ... sncqSF46uU

I also made a list for use with Scobalula's Tyrant RE Engine Extractor (https://github.com/Scobalula/Tyrant). Just remove DevilMayCry5NameCache0.tcache from the TyrantCache folder and replace it with the below file

https://mega.nz/file/caoC3ASB#gwoLCyEoO ... QXKQPFusFo

The information you provided helped me a lot and saved me a lot of time, thank you very much.

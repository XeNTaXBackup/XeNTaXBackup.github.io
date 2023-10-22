## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-12T04:31:15+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

Just in case someone needs it. A bms script for unpacking fbmod archives from FIFA20, and a Noesis script for importing extracted mesh (*.f20m) and texture (*.f20t) files.
[FIFA20.zip](https://xentaxbackup.github.io/file/18604_FIFA20.zip)
## Post #2
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-07-12T12:03:31+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

Doesn't work on most of tested files (Unsupported compression: type 0x0000000d).
Can you please add skinning (blendindices/blendweights)?
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-12T12:24:40+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from DmitryFM ↑Sun Jul 12, 2020 8:03 pm at Sun Jul 12, 2020 8:03 pm
>
> 
Doesn't work on most of tested files (Unsupported compression: type 0x0000000d).
Well. it's based on the couple of samples from this thread.
[viewtopic.php?f=18&t=21570](viewtopic.php?f=18&t=21570)

You should probably provide some samples of that specific error meaasge.
There's no guarantee that it'll work with everything though.

> Reply from DmitryFM ↑Sun Jul 12, 2020 8:03 pm at Sun Jul 12, 2020 8:03 pm
>
> 
Can you please add skinning (blendindices/blendweights)?
This is just a quick patch of an old script of mine and there won't be any further supports other than existing features.
## Post #4
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-07-12T19:36:25+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Sun Jul 12, 2020 12:31 pm at Sun Jul 12, 2020 12:31 pm
>
> 
Just in case someone needs it. A bms script for unpacking fbmod archives from FIFA20, and a Noesis script for importing extracted mesh (*.f20m) and texture (*.f20t) files.

Here are two more samples, that I have error with, the first is posted in the texture section  
[https://www.mediafire.com/file/98qv2wck ... s.rar/file](https://www.mediafire.com/file/98qv2wck3btaamt/two_samples.rar/file)
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-13T08:36:31+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from greenlemonade1 ↑Mon Jul 13, 2020 3:36 am at Mon Jul 13, 2020 3:36 am
>
> 
Here are two more samples, that I have error with

Scripts updated at the main post. Added support for more pixel formats to the Noesis script.
## Post #6
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-07-14T08:03:52+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Mon Jul 13, 2020 4:36 pm at Mon Jul 13, 2020 4:36 pm
>
> 
greenlemonade1 wrote: ↑Mon Jul 13, 2020 3:36 am
Here are two more samples, that I have error with


Scripts updated at the main post. Added support for more pixel formats to the Noesis script.

I extract without any problems, but when I tried to convert .fbx or obj to rx3 I ran into problems, and don't happen before, and I see in noesis that head_mat and eyes mat can't be read. Here is mega link, with the textures that can't be seen in noesis:
[https://mega.nz/file/orJR0aCT#1CRLbrRjf ... Oqbf4Bf5bc](https://mega.nz/file/orJR0aCT#1CRLbrRjfVs5GRaSElTXT1hjdwuSesPfxOqbf4Bf5bc)
[aa.PNG](https://xentaxbackup.github.io/file/18463_aa.PNG)
## Post #7
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-14T15:48:04+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from greenlemonade1 ↑Tue Jul 14, 2020 4:03 pm at Tue Jul 14, 2020 4:03 pm
>
> 
but when I tried to convert .fbx or obj to rx3 I ran into problems, and don't happen before, and I see in noesis that head_mat and eyes mat can't be read.
That's because the script does NOT parse any material info. And as far as I can remember, there's no texture binding info in the mesh reference files (*.f20m). Also what you were asking was to export the models, which's exactly what the script does, nothing more, nothing less.
## Post #8
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2020-08-05T17:09:39+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Tue Jul 14, 2020 11:48 pm at Tue Jul 14, 2020 11:48 pm
>
> 
greenlemonade1 wrote: ↑Tue Jul 14, 2020 4:03 pm
but when I tried to convert .fbx or obj to rx3 I ran into problems, and don't happen before, and I see in noesis that head_mat and eyes mat can't be read. 

That's because the script does NOT parse any material info. And as far as I can remember, there's no texture binding info in the mesh reference files (*.f20m). Also what you were asking was to export the models, which's exactly what the script does, nothing more, nothing less.

I hope you doing well, I got this bug when I tried to see mesh with noesis. Here is the sample, take care. mate 
[https://www.mediafire.com/file/ktdd1d9q ... fbmod/file](https://www.mediafire.com/file/ktdd1d9q9womi14/fifa20+bug.fbmod/file)
[bug.PNG](https://xentaxbackup.github.io/file/18568_bug.PNG)
## Post #9
- Username: DmitryFM
- Rank: beginner
- Number of posts: 21
- Joined date: Mon Jan 27, 2020 11:04 pm
- Post datetime: 2020-08-12T21:34:53+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

FIFA 20 models use 8 bones per vertex, is it possible to reflect this in noesis?
## Post #10
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-14T15:37:59+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from DmitryFM ↑Thu Aug 13, 2020 5:34 am at Thu Aug 13, 2020 5:34 am
>
> 
FIFA 20 models use 8 bones per vertex, is it possible to reflect this in noesis?
I don't see why not.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-08-14T15:38:15+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from greenlemonade1 ↑Thu Aug 06, 2020 1:09 am at Thu Aug 06, 2020 1:09 am
>
> I got this bug when I tried to see mesh with noesis.
Updated BMS and Noesis scripts.
## Post #12
- Username: Mewv
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 16, 2020 1:53 pm
- Post datetime: 2020-11-19T06:23:51+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

I tried using this script on BF2 because it also uses fbmod, and it partially works. 
But, it errors out with this 
"Last script line before the error or that produced the error: 62  goto entryOffset MEMORY_FILE2"
Would you consider modifying this script to work for BF2?
## Post #13
- Username: gep55
- Rank: veteran
- Number of posts: 81
- Joined date: Fri Feb 01, 2019 9:33 pm
- Post datetime: 2020-12-04T19:27:07+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

Many Thanks for a great tool 

I'm having problems extracting a .fmod file and I was wondering if I could upload a sample here?

Cheers
## Post #14
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2021-01-04T10:37:52+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Fri Aug 14, 2020 11:38 pm at Fri Aug 14, 2020 11:38 pm
>
> 
greenlemonade1 wrote: ↑Thu Aug 06, 2020 1:09 amI got this bug when I tried to see mesh with noesis.

Updated BMS and Noesis scripts.

Mate, I hope you are doing well during this tough times with corona virus. I wanna ask you why isn't skeleton or skinning data in the model, can those parts be apply in updated version, maybe. Here is the sample and Happy New Year to you and your family:
[https://www.mediafire.com/file/ump1nm0h ... o.rar/file](https://www.mediafire.com/file/ump1nm0hbbtn7av/Mascerano.rar/file)
## Post #15
- Username: Makoto
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Jun 12, 2016 1:41 am
- Post datetime: 2021-01-05T00:08:56+00:00
- Post Title: FIFA 20 fbmod unpacker + mesh/texture importer

Is this for the ps4 ver? I donwloaded it and couldn't really find any file to run the bms on, i don't understand where are the players stored
## Post #16
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-12T03:52:42+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

Hello everyone, 
I hope everyone is safe and healthy.
is this thread dead or can i still ask for help ?
i have a problem with extracting fbmod and f20t both give errors with scripts from here i don't Know why ? need help
and Yes I'm trying modding Fifa.
## Post #17
- Username: TheSeeker25
- Rank: beginner
- Number of posts: 20
- Joined date: Tue Jan 12, 2021 11:20 am
- Post datetime: 2021-01-12T18:38:06+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

Hello mates,
I hope everyone is safe and healthy and happy.
Now I have a fbmod, f20t and other texture files I need to extract it from a mod but I failed with it..
I tried all the possible way I found here in the site but I end up with empty hands.
And I'm desperate to get help and I hope I can find it here.
Thanks
## Post #18
- Username: ugo9p5
- Rank: advanced
- Number of posts: 57
- Joined date: Fri May 17, 2019 5:56 am
- Post datetime: 2021-01-13T00:24:43+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Sun Jul 12, 2020 12:31 pm at Sun Jul 12, 2020 12:31 pm
>
> 
Just in case someone needs it. A bms script for unpacking fbmod archives from FIFA20, and a Noesis script for importing extracted mesh (*.f20m) and texture (*.f20t) files.

do you think it would be possible to extract Battlefront 2 mod with this script ?
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-01-13T05:19:00+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from ugo9p5 ↑Wed Jan 13, 2021 8:24 am at Wed Jan 13, 2021 8:24 am
>
> 
do you think it would be possible to extract Battlefront 2 mod with this script ?
I don't know. Never look into any samples from that game so no way to tell how different they're. But aren't there some existing tools that can do the job? I seem to have to seen that title a couple of times in this forum.
## Post #20
- Username: Passingthrough2
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Dec 28, 2020 11:44 am
- Post datetime: 2021-01-13T05:52:30+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Wed Jan 13, 2021 1:19 pm at Wed Jan 13, 2021 1:19 pm
>
> 
ugo9p5 wrote: ↑Wed Jan 13, 2021 8:24 am
do you think it would be possible to extract Battlefront 2 mod with this script ?

I don't know. Never look into any samples from that game so no way to tell how different they're. But aren't there some existing tools that can do the job? I seem to have to seen that title a couple of times in this forum.

Sadly there is not. Yours almost does it - it extracts everything but the textures. There might be an additional issue with the 3d models yours extracts as well, but at least half of the extracted content is perfectly intact.
## Post #21
- Username: greenlemonade1
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Oct 31, 2019 3:22 am
- Post datetime: 2021-01-13T08:09:54+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from greenlemonade1 ↑Mon Jan 04, 2021 6:37 pm at Mon Jan 04, 2021 6:37 pm
>
> 
Bigchillghost wrote: ↑Fri Aug 14, 2020 11:38 pm
greenlemonade1 wrote: ↑Thu Aug 06, 2020 1:09 amI got this bug when I tried to see mesh with noesis.

Updated BMS and Noesis scripts.


Mate, I hope you are doing well during this tough times with corona virus. I wanna ask you why isn't skeleton or skinning data in the model, can those parts be apply in updated version, maybe. Here is the sample and Happy New Year to you and your family:
https://www.mediafire.com/file/ump1nm0h ... o.rar/file

What about the update script, can you check the file, please?
## Post #22
- Username: Noobmod
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Feb 06, 2021 11:20 am
- Post datetime: 2021-02-06T03:22:35+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

Hi, great work
Can you look into its latest iteration meant for FIFA 21, works almost the same just the format is albeit different this time

.fbmod -> .fifamod

Really appreciate if you have a look into it

Here is a sample file:  [https://www.mediafire.com/file/x3ws8js6 ... famod/file](https://www.mediafire.com/file/x3ws8js63ua4mwx/Tagliafico+By+BAR10+2.0.fifamod/file)
## Post #23
- Username: MrMarty25
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 05, 2021 10:03 am
- Post datetime: 2021-03-05T03:13:47+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

Someone who can help me out with extracting the  .f20t/.f20m files?
## Post #24
- Username: ben10x
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 10, 2022 3:10 pm
- Post datetime: 2022-04-10T07:46:35+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Bigchillghost ↑Sun Jul 12, 2020 12:31 pm at Sun Jul 12, 2020 12:31 pm
>
> 
Just in case someone needs it. A bms script for unpacking fbmod archives from FIFA20, and a Noesis script for importing extracted mesh (*.f20m) and texture (*.f20t) files.
First of all, wanna thank you, @Bigchillghost, for helping so many people here, you are made people happy. I've bump into this thread, and saw that no one posted FIFA22 sample yet, although this files are pain in the ass, as I see here.

So can someone see the sample of FIFA22, and see If it's possible to extract it and possibly to use it in noesis?
Again, thank you, Bigchillghost!

[https://www.mediafire.com/file/acubclbs ... t.rar/file](https://www.mediafire.com/file/acubclbsgish4r4/FIFA22+test.rar/file)
## Post #25
- Username: Godzukin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 18, 2022 7:18 am
- Post datetime: 2022-04-17T23:21:59+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

Hi mate, is it possible to unpack fifamod files from FIFA22 with this tool? pls answer
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-04-18T00:01:53+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Godzukin ↑Mon Apr 18, 2022 7:21 am at Mon Apr 18, 2022 7:21 am
>
> 
Hi mate, is it possible to unpack fifamod files from FIFA22 with this tool? pls answer
Try it on your own. I have no idea why the heck someone changed the topic but I clearly stated that this is for FIFA20 only. And I'm not interested in working further on this.
## Post #27
- Username: LethalSwampApe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 11, 2022 9:31 am
- Post datetime: 2022-05-11T01:50:49+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Passingthrough2 ↑Wed Jan 13, 2021 1:52 pm at Wed Jan 13, 2021 1:52 pm
>
> 
Bigchillghost wrote: ↑Wed Jan 13, 2021 1:19 pm
ugo9p5 wrote: ↑Wed Jan 13, 2021 8:24 am
do you think it would be possible to extract Battlefront 2 mod with this script ?

I don't know. Never look into any samples from that game so no way to tell how different they're. But aren't there some existing tools that can do the job? I seem to have to seen that title a couple of times in this forum.


Sadly there is not. Yours almost does it - it extracts everything but the textures. There might be an additional issue with the 3d models yours extracts as well, but at least half of the extracted content is perfectly intact.

You can use Ninjaripper to get the textures(and meshs too, but not UVs). 

If the mesh is identical, vertex/polygon wise, you can copy the UVs from a vanilla mesh to the messed up ninjaripped mesh. This method works great with Clone Trooper tweaks. As for meshes that are completely different(like RotS Vader), there's no way to get the proper UVs for them as the vanilla mesh has different polygons(hence why I made an account here). However considering what this forum says, I really hope I learn how to use this script, as I can potentially get the proper UVs for those custom meshes.

Edit: I got the fbmod extracted but can't seem to get it into Noesis properly.
## Post #28
- Username: LethalSwampApe
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed May 11, 2022 9:31 am
- Post datetime: 2022-05-11T02:27:43+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

I apologize for being amoral and resurrecting this thread.

Message when trying to export out of Noesis

.fbx - Autodesk FBX
Detected file type: FIFA 20
handling C:\Users\NAME\Pictures\b extract test\ROTS Darth Vader\darthvader_01_mesh.f20m
Traceback (most recent call last):
  File "C:\Users\NAME\Pictures\noesisv4464\plugins\python\fmt_FIFA20_f20m_f20t.py", line 55, in modelLoadModel
    bs.seek(lodOffset, NOESEEK_ABS)
IndexError: list index out of range
## Post #29
- Username: kaizxc8991
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Nov 17, 2022 8:37 pm
- Post datetime: 2023-01-25T02:40:26+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

Noesis unpacking coeff，Displays the error：module object has no attribute fourcc—BC7，How to solve it, please?thanks
## Post #30
- Username: tonaz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 08, 2023 8:08 pm
- Post datetime: 2023-02-08T12:35:01+00:00
- Post Title: Re: FIFA 20 fbmod unpacker + mesh/texture importer

> Reply from Godzukin ↑Mon Apr 18, 2022 7:21 am at Mon Apr 18, 2022 7:21 am
>
> 
Hi mate, is it possible to unpack fifamod files from FIFA22 with this tool? pls answer
unfortunately no. and fifa23 neither.
i really need a fifamod extractor for fifa23 fifamod files

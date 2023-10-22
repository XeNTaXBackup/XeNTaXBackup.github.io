## Post #1
- Username: KiSteem64
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 01, 2010 9:40 am
- Post datetime: 2011-06-15T16:08:11+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-06-15T16:27:00+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

Here is a quick bms script to seperate the model parts

```
goto 0x4
get files long
math files / 16
goto 0x0
for i = 0 < files
getdstring type 4
get offset long
get size long
get unk01 long
set name name2
string name + .
string name + type
if size != 0
log name offset size
else
endif
next i


```
## Post #3
- Username: KiSteem64
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 01, 2010 9:40 am
- Post datetime: 2011-06-16T01:21:59+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

Thanks for the fast reply it  works.
## Post #4
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2011-06-27T14:22:42+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

How do you plan to use those models and textures? Is there importer/converter for this model format?
## Post #5
- Username: KiSteem64
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 01, 2010 9:40 am
- Post datetime: 2011-07-04T17:10:41+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

Yes i found people who have the converter but no one wants to give it out.
## Post #6
- Username: napoleon321
- Rank: advanced
- Number of posts: 60
- Joined date: Tue Nov 16, 2010 7:11 pm
- Post datetime: 2011-07-07T01:22:04+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

I see... I made my own reserch on that topic and I have found few usable tools... Whith AFS Explorer tool you can look throgh the ico files of both  games (File #1 and #2), and you can extract all the files incide. You end up with some .NBD files. There's a batch file  out there on the net that will convert the .NBD files into .OBJ, where you can import them into practically any 3D modeling application. Since youdidn't provided any clues on those tools you plan to use, I'm not going to share the tolls I have found. (but I have provided more than enoth info to find them just by making a simple google serach)
## Post #7
- Username: markko19861
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 07, 2011 9:47 am
- Post datetime: 2011-07-07T01:51:57+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

can you post the tool that converts the .NBD's to .OBJs? 
I can't find it anywhere! I already have the extracted the NBD's from the netbio00.dat with the AFS Explorer.
I already have the textures from the models and everything: I just need the models now! please help me
## Post #8
- Username: Denis
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Oct 03, 2009 10:15 pm
- Post datetime: 2011-07-07T22:42:00+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

> Reply from markko19861
>
> can you post the tool that converts the .NBD's to .OBJs? 
I can't find it anywhere! I already have the extracted the NBD's from the netbio00.dat with the AFS Explorer.
I already have the textures from the models and everything: I just need the models now! please help me

Look Here [http://z6.invisionfree.com/Resident_Evi ... opic=11075](http://z6.invisionfree.com/Resident_Evil_4_PC/index.php?showtopic=11075)
## Post #9
- Username: markko19861
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 07, 2011 9:47 am
- Post datetime: 2011-07-07T23:49:11+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

> Reply from Denis
>
> markko19861 wrote:can you post the tool that converts the .NBD's to .OBJs? 
I can't find it anywhere! I already have the extracted the NBD's from the netbio00.dat with the AFS Explorer.
I already have the textures from the models and everything: I just need the models now! please help me

Look Here http://z6.invisionfree.com/Resident_Evi ... opic=11075

thanks for the reply but i cannot download the file from that page. if it's not a bother could you please upload it somewhere else if you can download it or if the file is to big can you just upload the tools I need? 
thanks
## Post #10
- Username: KiSteem64
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Fri Oct 01, 2010 9:40 am
- Post datetime: 2011-07-08T20:58:15+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: markko19861
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 07, 2011 9:47 am
- Post datetime: 2011-07-09T11:19:27+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

For the textures use Texmod+pscx2 anda emulate resident evil outbreak, and you'll be able to extract the textures. See this link 
[http://s4.invisionfree.com/Resident_Evi ... r/t908.htm](http://s4.invisionfree.com/Resident_Evil_1_2_3/ar/t908.htm)
it'll teach you everything you need to know. Hope it helps
## Post #12
- Username: gimmethatherb
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jul 13, 2011 3:18 am
- Post datetime: 2011-07-12T19:42:03+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

alright im very new at this 3d model stuff and all that so bare with me. but so were you successful in getting and converting the models from Resident Evil Outbreak, and if so, is there a way you could PLEASE upload them? im desperate to get 5 more characters (Alyssa, David, Yoko, Jim, and George) and i made an account here just for this purpose. Thanks
## Post #13
- Username: markko19861
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 07, 2011 9:47 am
- Post datetime: 2011-07-15T02:11:41+00:00
- Post Title: Resident Evil Outbreak File 2 .nbd

> Reply from gimmethatherb
>
> alright im very new at this 3d model stuff and all that so bare with me. but so were you successful in getting and converting the models from Resident Evil Outbreak, and if so, is there a way you could PLEASE upload them? im desperate to get 5 more characters (Alyssa, David, Yoko, Jim, and George) and i made an account here just for this purpose. Thanks

Check these two topics [http://z4.invisionfree.com/Resident_Evi ... wtopic=908](http://z4.invisionfree.com/Resident_Evil_1_2_3/index.php?showtopic=908)
and [http://z4.invisionfree.com/Resident_Evi ... topic=1192](http://z4.invisionfree.com/Resident_Evil_1_2_3/index.php?showtopic=1192)
All the tools you need are explanations are on those two topics

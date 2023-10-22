## Post #1
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2020-09-27T15:37:13+00:00
- Post Title: Info about FIFA PS2 texture files

one of the reasons for not having the mods for the PS2 fifa, is that it is not yet possible to modify the textures.
fifa contains ssh files, which are texture files,after some research I noticed that the file structure is the same as tm2 files, so it is possible to edit the textures.
## Post #2
- Username: leo90nan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 02, 2016 2:12 am
- Post datetime: 2020-09-27T20:24:20+00:00
- Post Title: Info about FIFA PS2 texture files

hello do you think you can edit the kits, one ps2 mod would be great
## Post #3
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2020-09-27T20:57:05+00:00
- Post Title: Info about FIFA PS2 texture files

maybe yes,I was able to find the team kit,menu,stadium and others.
## Post #4
- Username: leo90nan
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Nov 02, 2016 2:12 am
- Post datetime: 2020-09-27T21:34:25+00:00
- Post Title: Info about FIFA PS2 texture files

I already adapted cm08 to work with the fifa ps2 database, I am using CCT for logos but not having good results. Of kits I have not been able either.
## Post #5
- Username: DAlex
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 11, 2021 5:53 am
- Post datetime: 2021-04-09T07:45:11+00:00
- Post Title: Info about FIFA PS2 texture files

> Reply from lusji2011 ↑Mon Sep 28, 2020 4:57 am at Mon Sep 28, 2020 4:57 am
>
> 
maybe yes,I was able to find the team kit,menu,stadium and others.

Yes, I'm already able to do this, since 2019.
Do you know how to bring out the menu, it's difficult to produce the offset and palette in CtE, since the menu size wasn't specified in the ssh.
How can you get the menu, give me your Gmail, fb or Whatsapp to talk more
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-09T08:57:30+00:00
- Post Title: Info about FIFA PS2 texture files

It''s worth to mention that recently I have made some detailed research on SSH Images from EA games.
Maybe someone will find this article useful [http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image)
## Post #7
- Username: Spotifychild
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 10, 2021 1:20 am
- Post datetime: 2021-04-09T17:30:23+00:00
- Post Title: Info about FIFA PS2 texture files

I thought EA used .fsh format
## Post #8
- Username: Gut007
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 16, 2021 2:07 am
- Post datetime: 2021-04-15T18:11:56+00:00
- Post Title: Info about FIFA PS2 texture files

hi gysa can you tell me how to edit the kits, one ps2 mod would be great
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-04-15T18:19:08+00:00
- Post Title: Info about FIFA PS2 texture files

> Reply from Gut007 ↑Fri Apr 16, 2021 2:11 am at Fri Apr 16, 2021 2:11 am
>
> 
hi gysa can you tell me how to edit the kits, one ps2 mod would be great

There are some tools listed in my wiki article, you can check them.
## Post #10
- Username: Jsc1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 27, 2022 10:02 am
- Post datetime: 2022-05-27T02:05:45+00:00
- Post Title: Info about FIFA PS2 texture files

I tried the same, for logos I replaced the SSH of one using other from FIFA 06 in ZDATA01.BIG but the game still using the current logo, this mean that probably the logos is in FIFA.db file, I used bigGUI and Apache to insert the new file in the ISO
## Post #11
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-05-27T13:39:06+00:00
- Post Title: Info about FIFA PS2 texture files

I did a search, it seems to me that the some of SSH files are divided into parts, like FIFA player faces,team kits, and that why some tools cant  recognize that, and they do this to save disk memory, I checked the files 
t226__17_0.ssh
t226__17_1.ssh
t226__17_3.ssh.
if you join all their data image we will probably have a single texture.
they all contain the same name, id, image size.
## Post #12
- Username: Jsc1
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 27, 2022 10:02 am
- Post datetime: 2022-05-27T15:28:44+00:00
- Post Title: Info about FIFA PS2 texture files

Maybe I can contribute something to the check that I did some years ago, t226 is team Id, you can see the team ID's here [https://www.fifaindex.com/es/team/226/fc-sochaux/](https://www.fifaindex.com/es/team/226/fc-sochaux/) I opened some SSH without problems like the logos or some numbers for kits using EAGT  but the rest usually gives an error
## Post #13
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-05-27T19:46:00+00:00
- Post Title: Info about FIFA PS2 texture files

I'm creating a tool for that. I already have a knowledge of the files and how to convert bmp to textures.
## Post #14
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-28T18:32:46+00:00
- Post Title: Info about FIFA PS2 texture files

There is really no need to create duplicate topics on SSH files.
I've merged both topics.


Btw, new tool for viewing and converting SSH, FSH, MSH, XSH and PSH images is already in development.
It's called EA Graphics Manager [https://github.com/bartlomiejduda/EA-Graphics-Manager](https://github.com/bartlomiejduda/EA-Graphics-Manager)

I'm also working on Noesis script to support all EA image types
[https://github.com/bartlomiejduda/EA-Gr ... _script.py](https://github.com/bartlomiejduda/EA-Graphics-Manager/blob/main/src/scripts/ea_graph_man_noesis_script.py)


And all the format documentation is here [http://wiki.xentax.com/index.php/EA_SSH_FSH_Image](http://wiki.xentax.com/index.php/EA_SSH_FSH_Image)
## Post #15
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-05-28T18:52:28+00:00
- Post Title: Info about FIFA PS2 texture files

sorry for the double topics. I had forgotten that I had already made a topic related to this.
I'm also developing my tool,I've made some discoveries over the years, if you want to just call me in private.
## Post #16
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-05-28T19:35:45+00:00
- Post Title: Re: Info about FIFA PS2 texture files

> I've made some discoveries over the years, if you want to just call me in private.

You can share your discoveries here, in this topic.

That's what we do on reverse engineering forum. We share our findings, tools and knowledge publicly with others.
## Post #17
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-05-29T17:12:51+00:00
- Post Title: Re: Info about FIFA PS2 texture files

I was able to mod/import  FIFA 14 menu textures, here is my tutorial [https://www.youtube.com/watch?v=re61RdV ... el=BigEvil](https://www.youtube.com/watch?v=re61RdVeepg&ab_channel=BigEvil)
## Post #18
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-05-30T17:07:50+00:00
- Post Title: Re: Info about FIFA PS2 texture files

here some PCSX2 textures dump

on the left was Tottenham's main kit with the texture of socks, with unknow pixel format
on the  right was the second kit just shorts and shirt, with pal 8/4 pixel format.

maybe we can use the same format on the main kit.


for menus was pal8 with 256 colors.
## Post #19
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-05-31T13:53:22+00:00
- Post Title: Re: Info about FIFA PS2 texture files

for players face, the textures was swizzled from 128x128 to 16x64 (probably 4bit).
on the player model, I found some EAGL runtime function about Texture colors.

> PS2EXTOBJ_SetColourComponent=EAGL::PS2CC_RGBA.

on the comments at the end of ssh file, the values 1,0 - 1,1 before the texture size could be the matrix values.
## Post #20
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-06-03T15:38:52+00:00
- Post Title: Re: Info about FIFA PS2 texture files

I got some face preview.
it's was Hugo Lorris from Tottenham hotspur.



size :  256x128 - 8bit 256 colors Swizzled 
SSH Entry type : 0x0E = 14
## Post #21
- Username: lusji2011
- Rank: n00b
- Number of posts: 18
- Joined date: Tue Dec 06, 2016 6:52 pm
- Post datetime: 2022-06-13T19:18:08+00:00
- Post Title: Re: Info about FIFA PS2 texture files

The metal bin attachment contains info about the texture swizzling

80000000 = 128
So 128*128 = 16384
16384 is 00400000 in hex

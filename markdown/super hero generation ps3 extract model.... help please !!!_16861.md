## Post #1
- Username: ryukem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 09, 2015 5:59 am
- Post datetime: 2017-08-12T17:18:49+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

Hi, can anyone help me extract the obj model from this file, try it with hex2obj_0.24c and I did not get a good result  
This is the model thunder darambia [https://vignette1.wikia.nocookie.net/ul ... 0709075049](https://vignette1.wikia.nocookie.net/ultra/images/1/1d/Thunder_Drrmb.png/revision/latest/scale-to-width-down/210?cb=20130709075049)

here the files 
[https://drive.google.com/file/d/0B7fQsP ... sp=sharing](https://drive.google.com/file/d/0B7fQsPRd0eU0cTVCQlAxaXVKaTA/view?usp=sharing)
or
[https://mega.nz/#!0fIGnRaQ!yEyNV_FtrRoA ... hLdIltIfPQ](https://mega.nz/#!0fIGnRaQ!yEyNV_FtrRoASjUeTy-hE5WGr-YObrpG0hLdIltIfPQ)


I hope you can help me, regards
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-12T19:20:12+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

this is all i managed to find so far, first submesh in mbg file  



mbg_body.png (52.7 KiB) Viewed 396 times


no UVs yet, maybe someone else will have better luck
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-12T22:11:41+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

uvpos= 17?



mbg_uv.jpg (96.68 KiB) Viewed 408 times
## Post #4
- Username: ryukem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 09, 2015 5:59 am
- Post datetime: 2017-08-13T02:13:34+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

wow very very thanks , the model is very good , Only the arms are missing, For textures is also used hex2obj_0.24c ??

Thanks for your time !!
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-13T04:53:39+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

> Reply from shakotay2
>
> uvpos= 17?
yeah looks good to me, i had checked every even number from 12 - 90 as Float, HF_UV, and wordUV, but not the odd numbers  

edit
here is the settings for the hands



mbg_hands.png (38.96 KiB) Viewed 396 times
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-13T08:55:15+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

you're gonna need some textures for that model too, in your samples there is a zip file named tex.txd.zip in "eu039_0002_01 thunder darambia\cmn" folder
extract the file named "texture" from tex.txd.zip and give it this extension ".sht" which is just short for "super hero texture"
now you can open texture.sht with this Noesis python script  
*script updated Oct 8, 2017*


 tex_SuperHeroGeneration_PS3_sht.zip
(1.01 KiB) Downloaded 57 times


supports dxt5 and morton swizzled argb8 normal map
## Post #7
- Username: ryukem
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Oct 09, 2015 5:59 am
- Post datetime: 2017-08-18T04:01:15+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

Thanks for the help, I already have the model and the arms, also the texture but with this I have problems I will try to fix it

Thank you very much for the help !!!!
[Imagen2.jpg](https://xentaxbackup.github.io/file/13214_Imagen2.jpg)
## Post #8
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2017-10-06T14:16:59+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

> Reply from AceWell
>
> you're gonna need some textures for that model too, in your samples there is a zip file named tex.txd.zip in "eu039_0002_01 thunder darambia\cmn" folder
extract the file named "texture" from tex.txd.zip and give it this extension ".sht" which is just short for "super hero texture"
now you can open texture.sht with this Noesis python script  
tex_SuperHeroGeneration_PS3_sht.zip
supports dxt5 and morton swizzled argb8 normal map
this script was written specifically for this file, so it will likely crash on any others you try it on.
Can you make a blender script to import .mbg character models from PS3 Super Hero Generation?
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-06T15:58:39+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

no i don't know anything about Blender python api
## Post #10
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2017-10-08T09:20:43+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

[quote="AceWell"]you're gonna need some textures for that model too, in your samples there is a zip file named tex.txd.zip in "eu039_0002_01 thunder darambia\cmn" folder
extract the file named "texture" from tex.txd.zip and give it this extension ".sht" which is just short for "super hero texture"
now you can open texture.sht with this Noesis python script  
tex_SuperHeroGeneration_PS3_sht.zip
supports dxt5 and morton swizzled argb8 normal map
this script was written specifically for this file, so it will likely crash on any others you try it on.  

Please~ help, some files cause problems
Here is a sample file http://www.mediafire.com/file/st9obpve4ex993l
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-08T16:58:58+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

> Reply from leyme
>
> Please~ help, some files cause problems
Here is a sample file http://www.mediafire.com/file/st9obpve4ex993l
i have updated the previous script to open all your samples
## Post #12
- Username: leyme
- Rank: advanced
- Number of posts: 50
- Joined date: Wed Apr 04, 2012 5:17 pm
- Post datetime: 2017-10-08T17:56:23+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

> Reply from AceWell
>
> leyme wrote:Please~ help, some files cause problems
Here is a sample file http://www.mediafire.com/file/st9obpve4ex993l
i have updated the previous script to open all your samples

I appreciate all your hard work
## Post #13
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2017-10-09T11:52:33+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

> Reply from AceWell
>
> no i don't know anything about Blender python api
Can you make a plugin for noesis?
## Post #14
- Username: DrifterDx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Sep 02, 2016 8:37 pm
- Post datetime: 2018-02-28T14:22:43+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

so that's it? no further discussions on this game?
no research into it figuring out the MBG and CPZ files?
no development in scripts or tools to make it easier to extract files
from this game?

why is it when someone asks for help extracting something it's
ONE model and that's it; conversation over?

this game has a WEALTH of things in it, yeah Thunder whathisface is nice
but there are other things in this game Dark Lugiel, Kamila, Bogal, U- Killersaurus
Alien Valky, Evil Tiga, so many things that other people might enjoy!
not just Ultra fans but Kamen rider and gundam fans!

i know when i extract things from games that when i share the fruits of my labor
with others and see them in pictures BEST DAMN FEELING IN DA WORLD!!!
## Post #15
- Username: 100nadzmi
- Rank: n00b
- Number of posts: 16
- Joined date: Mon May 30, 2011 6:01 pm
- Post datetime: 2018-06-17T02:54:25+00:00
- Post Title: super hero generation ps3 extract model.... help please !!!

> Reply from shakotay2
>
> uvpos= 17?
mbg_uv.jpg
   Hey man . Could you make scripts or tools for me to laod this model?
I try so many times , but I still not know how to extract it from MakeObj tool. its difficult for me
But i really want model in these mbg files.
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-22T18:26:44+00:00
- Post Title: Re: super hero generation ps3 extract model.... help please

> Reply from 100nadzmi
>
> I try so many times , but I still not know how to extract it from MakeObj tool. its difficult for meYou need to know 'C' if you want to make use of the Make_obj project. Currently there's no plans to integrate the mbg format into it.

You could use hex2obj to get the first submesh displayed or exported as obj.

I'm not sure if it works for other mbg files but search for -mesh (4 finds here).
First find is at 0x4A7, adding 0x3B results in 0x4E2, this is the start of vertices (first submesh).

Then search for 0000 0001 0002 (also 4 finds), first one is at 0x8FC35, start of face index block.

For the counts (of the first submesh) see picture:



mbg-counts.jpg (226.21 KiB) Viewed 101 times



For the remaining 3 submeshes it should be similar.

If you can confirm this to work for another mbg sample I could think of adding the format to the Make_obj project.

edit: well, from the mbg sample in your other thread I can see that the offset between "-mesh" and startOfVertices is 0x3E so it's required to search for the next signature bytes 01 000000 0C then.

You'll find SuperHeroGeneration, PS3 mbg file support in the Make_obj project:
[viewtopic.php?f=29&t=15955&p=141547#p141547](http://forum.xentax.com/viewtopic.php?f=29&t=15955&p=141547#p141547)
in the post as of Sat Jun 23, 2018 9:27 pm
## Post #17
- Username: wjj162446
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Jul 10, 2019 7:01 pm
- Post datetime: 2019-07-19T15:00:06+00:00
- Post Title: Re: super hero generation ps3 extract model.... help please

Thanks so much

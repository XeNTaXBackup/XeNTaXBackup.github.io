## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-22T01:54:53+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

Okay, so I've managed to find the player models for the core cast of the Hellboy series from the Playstation 3 "Science of Evil" game thanks to Luigi's RKV4 script, and I'm wondering if there's someone out there that might be able to help me bring all this together to a format that can be used in either Blender of 3DS Max -- whether it's and Xnalara mesh, and fbx, whatever, anything that can be used really! I'm pretty certain that everything pertaining to the characters is in there -- the textures (which I'm told are pretty straight forward DDS textures, only I'm no good with hex reading), the models and the bones/rigging, it's all in there -- I'm just lost as to how to bring it all together. 

I know there are folks out there that've managed to put these pieces together from previous KROME releases, so I'm hoping someone might be able to help me with these...!

Here's a sample file: [Abe Sapien](https://mega.nz/#!LAQy2CDQ!3gP1rC0CpgrZrBzo9H7OUT-gMi9x7H5fXdjOMF_O7e8)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-22T06:41:26+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

previous research
[http://zenhax.com/viewtopic.php?p=16719#p16719](http://zenhax.com/viewtopic.php?p=16719#p16719)

i made a version 1 python texture script for Noesis to open the tex files


 tex_HellboyScienceofEvil_PS3_tex.zip
(820 Bytes) Downloaded 68 times


i have seen only one normal map texture giving me problems so far
looks like it uses some kind of morton swizzling

i could make a model script easily if i could just figure out
how to read from more than one file at the same time.
## Post #3
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-22T11:10:16+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

YOU. ARE. AMAZING! Thanks for the help with this Ace!
## Post #4
- Username: JoeBlack777J
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 03, 2015 10:49 am
- Post datetime: 2016-08-29T10:27:05+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

You rock Acewell! Hope you have some more luck on these soon!
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-29T21:49:08+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

here is the Noesis python model script  


 fmt_HellboyScienceofEvil_PS3_mdl.zip
(1.2 KiB) Downloaded 132 times



this script was a lesson in reading more than one file in the same folder   
supports geometry and UVs

you open the mdl files with it but you must also have the corresponding mdg files in the same folder
i have seen some mdl files with CX in the name that look like model data, but i have not looked at them closely enough yet,
so they are not supported.

edit
*script updated* to open more models   

i am still seeing some files with CI and CF in the name that cannot open yet, will look at those later
so if you see a mdl with CX, CI or CF in the file name don't try to open those.  

edit again
*script updated* to open even more models  
CX, CI and CF are still unsupported and might remain that way
## Post #6
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-30T03:55:41+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

Oh, wow! Thanks man! Having a look through now! Some great looking models...! Bummer I can't actually see Hellboy himself yet, but Lobster Johnson and Abe all look fantastic!! Some enemies in there I wasn't expecting... Might be able to get some of those levels out for SFM, too!
## Post #7
- Username: Nintendude
- Rank: advanced
- Number of posts: 57
- Joined date: Wed Oct 19, 2011 11:25 am
- Post datetime: 2016-08-31T22:58:44+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

Was the Hound of Hell, or Kroenen from Hellboy 1 in there by any chance?
## Post #8
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-01T02:36:04+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

Yeah pretty sure Kroenen is -- most of the soldiers are based on his design too. Von Klemp (the Nazi head in a jar accompanied by the Gorilla with the rocket fist on a chain) is the main villain.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-02T16:48:45+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

trexjones asked me to look at these files. So this is what I'm getting for Abe skeleton:



And this is Liz (she has about 20 more bones - her hair)



So if you like, I can explain how to get bones and you can try adding them to your script

1. Bone names and hierarchy is in animation files. I think you can take any of them, seems they always using all bones.

2. Bone matrices are in .MDL file. Bones are described with big structures 192 bytes each, having local and global rotations and translations for each bone, and some more data, probably not needed.

Let me know how much detail you need me to explain to get this working.
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-02T23:02:58+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

i've taken it about as far as i can and i still can't say i have a good handle on
what i'm already doing in python, basically i'm flying by the seat of my pants.
i still haven't figured out how to set up material and texture assignments.   
i'm not really interested in bones anyway becasue most major 3d programs
come with humanoid skeleton templates and easy to use skinning tools with
weight painting etc. this project is all yours  

edit
also, while sharing tools is nice, if you have some research about the formats
to share you should post it here so anyone interested can learn about it.
## Post #11
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-09-03T03:55:09+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

Well, that's a bummer... I was hoping to be able to get these with their in-game skeletons.
## Post #12
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-03T21:27:38+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

> Reply from AceWell
>
> also, while sharing tools is nice, if you have some research about the formats
to share you should post it here so anyone interested can learn about it.

Well, I'm not sure what you mean. Model formats are usually easy and all alike. What is the reason to post one more vertex/face format? For example, this one. It looks exactly like all others.

The place where things get really different and exotic is bones/animations. But you're saying its not interesting.
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-04T05:18:02+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

> Reply from daemon1
>
> Well, I'm not sure what you mean.
didn't think my post was cryptic    of course i was referring to the skeleton images
you posted, you seem to have the format specs all figured out so why not post here
what you know so others might learn something "different and exotic" as you put it.
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-05T17:54:48+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

There's not much exotic in this particular game except that bone hierarchy is in animations, while usually its in model or separate skeleton file.

And bones are not divided into subgroups, or have any crazy remappings that can be seen in other games. They are just in one big array, having usual local and global matrices as I said before.
## Post #15
- Username: JoeBlack777J
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Oct 03, 2015 10:49 am
- Post datetime: 2016-09-23T09:29:13+00:00
- Post Title: Hellboy: Science of Evil PS3/KROME models

Would love to see these extractable with in game bones too. The bi-ped bodies are easy enough to rig but I suck so hard at face rigging. Keep up the great work fellas! You rock!
## Post #16
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-25T19:43:42+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

Today I found some time to return to this game. Well, it really has submeshes for each material and crazy bone remappings.

Here's the tool. Use it on .MDG or .MDL file. It will only work with skeletal model files. To get the skeleton structure and bone names, it needs any .ANM file of that character. Put it in the same folder. If there will be many .anm files from different characters in the same folder, the result is non-predictable.


[hellboy_model.rar](https://xentaxbackup.github.io/file/11736_hellboy_model.rar)
## Post #17
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-27T16:32:38+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

Tool posted.
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-10T18:36:50+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

> Reply from daemon1
>
> ..... it really has submeshes for each material....
i can't find any of this submesh information, where in the mdl or mdg file are you seeing this data?   
can you please use the abe files as example and tell me where the offset to this data is so i know what to look for?
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-10T19:16:46+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

> Reply from AceWell
>
> daemon1 wrote:..... it really has submeshes for each material.... 
i can't find any of this submesh information, where in the mdl or mdg file are you seeing this data?   
can you please use the abe files as example and tell me where the offset to this data is so i know what to look for?

sure.

mdl offset 0x68 ---> points to material table.

material table has offsets for all submeshes according to their materials. These are offsets to a table in the end of ABE_BINDPOSE.mdg file.

A row of this table contains starting face number and number of faces for this material part.

But each material may cover different parts of the model, so there's actually a linked list inside of that table that will contain data for each part (each with its own bone remapping). But since you're not interested in bones, you can just put all parts of given material into one.
## Post #20
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-10T22:03:09+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

> Reply from daemon1
>
> A row of this table contains starting face number and number of faces for this material part.

But each material may cover different parts of the model, so there's actually a linked list inside of that table that will contain data for each part ... you can just put all parts of given material into one.
i've seen this table at the end of the mdg before but i can't make sense of the numbers, it looks like that 
table is in seven 32 byte blocks and i can see 2 pointers there (50b60 at 0x50b4c and 50ba0 at 0x50b8c)
but nothing else there looks familiar, is the starting face number and number of faces data stored as shorts?  

edit
nevermind, the numbers makes no sense to me because there are too many details left out
and i don't think these are submeshes, but material groups....
## Post #21
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-10-15T09:54:00+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

well, if you'll ever decide to increase you skill level, yes, face counts/numbers are stored as shorts. And those pointers are to define a linked list inside of that table. Its needed when a material covers many parts of a model, for example, body and arms.
## Post #22
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2019-10-10T00:40:05+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

I know that this thread hasn't really been active in years but this is what happened when I tried using the model tool.


[Hellboy.PNG](https://xentaxbackup.github.io/file/16884_Hellboy.PNG)
## Post #23
- Username: ShadowLuigi
- Rank: beginner
- Number of posts: 20
- Joined date: Sun May 13, 2018 3:27 am
- Post datetime: 2022-01-24T21:24:27+00:00
- Post Title: Re: Hellboy: Science of Evil PS3/KROME models

Did some more experimenting with models from other KROME studios games like Viva Pinata Party Animals and I seem to get the following for certain models and certain animations. 


VPPA MODEL 2.PNG (4.4 KiB) Viewed 68 times

## Post #1
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2020-02-09T08:52:52+00:00
- Post Title: One Punch Man A Hero Nobody Knows

I was recently able to extract files from this game (yes, it was leaked early, but I will not be sharing the full ps4 game files with anyone besides the included files in this post), and it uses drpv3 srd compression, but sadly none of the tools/scripts works on it.

instead of files being in a .spc archive, they're in npk, npki, and npkv files, so here's an accessory file set, and 1 character file set, I would also like the models to be extractable.

[Accessory_000](https://cdn.discordapp.com/attachments/371877754217562112/675933154112176138/acc0000_model_00.7z)
[Character_000](https://cdn.discordapp.com/attachments/371877754217562112/675934405696552980/chr0000_model.7z)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-02-21T06:14:57+00:00
- Post Title: One Punch Man A Hero Nobody Knows

This type of file is similar to the One Piece Burning Blood, the difference is that, in each file of this game it is compressed in $CMP, while the One piece had a container (*SCZ) that was also compressed in $CMP, but in a single file where these three types of files are extracted.

To decompressing these files, use this script: [https://aluigi.altervista.org/bms/cmp_scz.bms](https://aluigi.altervista.org/bms/cmp_scz.bms)
(The files will be decompressed with another type of extension, just rename them to the formats they were in before)

There is a tool made by shakotay2 which can extract the models from One Piece Burning Blood,

> Reply from shakotay2 ↑Thu Jul 11, 2019 2:40 pm at Thu Jul 11, 2019 2:40 pm
>
> 
I've updated the tool for various uvb sizes (tested one model only!):
.
Make_obj-OnePBB.zip
but it will not work with these files, because the .npk file, where the model information is, should probably store the information differently.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-21T09:42:01+00:00
- Post Title: One Punch Man A Hero Nobody Knows

> Reply from reh ↑Fri Feb 21, 2020 2:14 pm at Fri Feb 21, 2020 2:14 pm
>
> but it will not work with these files, because the .npk file, where the model information is, should probably store the information differently.yeah, would need some patching.
.



acc0000_model_00.dat.npki.png (112.42 KiB) Viewed 845 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-21T17:44:14+00:00
- Post Title: One Punch Man A Hero Nobody Knows

Patch done! (OnePBB -> OnePunchMan... files) This was rather simple so there's a high chance that it will not cover all model files.
(In fact I tested two of them only.  )
.


 Make_obj-OnePunchMan.zip
(136.17 KiB) Downloaded 77 times
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-21T17:51:55+00:00
- Post Title: One Punch Man A Hero Nobody Knows

This is the 2nd model I tested:
.



chr0000_model.png (73.45 KiB) Viewed 828 times



There's 52 valid obj files and about 39 *.objx files (plus 10 with zero bytes each) created when using hex2obj's multi mesh feature on the resulting H2Os (from Make_obj_OnePunchMan.exe, see zip in post above).

*.objx means, hex2obj tried an automatic correction of the vertexCount because of weird face indices. (Sometimes you can use the related H2O files for displaying point clouds at least.)

(I didn't care for*.objx here because of lack of time.)
## Post #6
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-02-22T06:37:28+00:00
- Post Title: One Punch Man A Hero Nobody Knows

What a quick update, good!
This was the way I got to get the textures:



chr0000_model.npkv.png (122.27 KiB) Viewed 798 times


Apparently, there are several textures concatenated in a single file, therefore, if you change the offset, you must obtain the other textures.
## Post #7
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-02-22T18:45:13+00:00
- Post Title: One Punch Man A Hero Nobody Knows

Will there be a Noesis plugin? This person named Hiroshi made one but they aren't releasing the plugin.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-02-22T18:50:47+00:00
- Post Title: One Punch Man A Hero Nobody Knows

> Reply from qs12 ↑Sun Feb 23, 2020 2:45 am at Sun Feb 23, 2020 2:45 am
>
> 
Will there be a Noesis plugin?Not from my side - I'm usually done once I've "a working solution". (Even if it's a little bit unhandy.  )

> This person named Hiroshi made one but they aren't releasing the plugin.§$%&!
## Post #9
- Username: Lord Kiri
- Rank: beginner
- Number of posts: 37
- Joined date: Fri Aug 25, 2017 9:40 am
- Post datetime: 2020-02-23T15:21:52+00:00
- Post Title: One Punch Man A Hero Nobody Knows

Shouldn't you guys wait for pc release of the game?
## Post #10
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-02-23T19:26:27+00:00
- Post Title: One Punch Man A Hero Nobody Knows

> Reply from Lord Kiri ↑Sun Feb 23, 2020 11:21 pm at Sun Feb 23, 2020 11:21 pm
>
> 
Shouldn't you guys wait for pc release of the game?

That will be best to wait, Besides it comes out on Thursday the 27th
## Post #11
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-02-28T16:22:19+00:00
- Post Title: One Punch Man A Hero Nobody Knows

So the PC game came out recently, has anyone been able to get models from the .cpk files?

I've tried with the cpk.bms script, but that results with a huge amount (about 5.5k) of files without file format
## Post #12
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-02-28T16:47:22+00:00
- Post Title: One Punch Man A Hero Nobody Knows

> Reply from Lord Kiri ↑Sun Feb 23, 2020 11:21 pm at Sun Feb 23, 2020 11:21 pm
>
> 
Shouldn't you guys wait for pc release of the game?
Don't think so, the PC files are divided in chunks without extensions, the PS4 files are way easier to manipulate.

> Reply from shakotay2 ↑Sat Feb 22, 2020 1:44 am at Sat Feb 22, 2020 1:44 am
>
> 
Patch done! (OnePBB -> OnePunchMan... files) This was rather simple so there's a high chance that it will not cover all model files.
(In fact I tested two of them only.  )
.
Make_obj-OnePunchMan.zip

I can confirm it works on other models, a friend and I tried on Tatsumaki. Thanks for your work.


> Reply from reh ↑Sat Feb 22, 2020 2:37 pm at Sat Feb 22, 2020 2:37 pm
>
> 
What a quick update, good!
This was the way I got to get the textures:
chr0000_model.npkv.png
Apparently, there are several textures concatenated in a single file, therefore, if you change the offset, you must obtain the other textures.

Inside the .npk there are TXR entries that points to the texture data inside the .npkv, here is a table of the values I've found.
## Post #13
- Username: Eag1e
- Rank: beginner
- Number of posts: 27
- Joined date: Sun Mar 17, 2019 11:48 am
- Post datetime: 2020-02-29T14:31:43+00:00
- Post Title: One Punch Man A Hero Nobody Knows

Would anyone be able to share their PS4 game files? I'd like to try extracting the models
## Post #14
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-02-29T16:31:11+00:00
- Post Title: One Punch Man A Hero Nobody Knows

same format as OPBB?
then getting skeletons to work with mesh is hopeless
## Post #15
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-02-29T22:45:56+00:00
- Post Title: One Punch Man A Hero Nobody Knows

> Reply from ngovandang ↑Sun Mar 01, 2020 12:31 am at Sun Mar 01, 2020 12:31 am
>
> 
same format as OPBB?
then getting skeletons to work with mesh is hopeless

Someone named Hiroshi got it working, He's not releasing the tool yet [https://www.youtube.com/watch?v=We8rqnQU33w](https://www.youtube.com/watch?v=We8rqnQU33w)
## Post #16
- Username: Ruisuu18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 16, 2019 3:03 am
- Post datetime: 2020-03-01T00:13:02+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

Has anyone managed to rip from the pc files yet? All I get are a bunch of unknown files?
## Post #17
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2020-03-01T15:15:28+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

> Reply from qs12 ↑Sun Mar 01, 2020 6:45 am at Sun Mar 01, 2020 6:45 am
>
> 
Someone named Hiroshi got it working, He's not releasing the tool yet https://www.youtube.com/watch?v=We8rqnQU33w

I know, he is here in this forum, he comes from my country, however I dont think he will share his scripts or plugins at all.
This is hopeless
## Post #18
- Username: qs12
- Rank: veteran
- Number of posts: 92
- Joined date: Sat Sep 21, 2019 7:55 am
- Post datetime: 2020-03-02T23:37:23+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

Raw texture cooker is not converting the textures correctly, They convert into a static texture. Is there another way to convert the .npkv?
## Post #19
- Username: mcmanus82
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 12, 2017 9:45 pm
- Post datetime: 2020-03-10T08:55:06+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

I managed to extract textures and find the transformed models (alternative appearance) so i decided to share my findings.

The alternative mode appearance is in the same file as the regular mode, so for Mosquito girl it is chr1002_model. So that file basically contains two sets of meshes. MakeObj cannot properly find these and the results are the xobj files which are corrupt. I have made h2o files for Mosquito girl's transformation meshes by hand (attached as zip to next post) but i'm not willing to do any other models as it takes hours. If you want another transformed model read the tutorial for hex2obj and try to reverse engineer the good h2o files made by MakeObj. That is what i did.

As for textures the directions provided by JosouKitsune ar mostly correct but most people would need addition details to figure it out.
The yellow data relates to image size 2 is 512, 4 is 1024 and 8 is 2048, same as before.
Data in the red green and blue rectangles are the offset in that order. If red is zero then you can ignore it (it will be for the first few images) and the end is always two zeros so for this example (0) 35 68 00.
Another example, if this is what it writes in the hex editor for that line 00 b4 90 41 .. .. .. .. than the offset is 1 90 b4 00

For transformed mode textures, you will have to find the first texture for that set (usually in the 2nd half of the dat file) note its first data address and add the offset noted in NPA for each texture to that. So first texture of the second pack start at 0x02BDA0 and 2nd textures offset is 4b2a00, you add these together and get that the texture starts at 0x4de7a0



Tex_extr.jpg (236.95 KiB) Viewed 361 times
## Post #20
- Username: mcmanus82
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Dec 12, 2017 9:45 pm
- Post datetime: 2020-03-10T08:58:01+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

Mosquito girl transformed mode h2o files, plus texture format.

Diffues maps (_c) and specular maps (_s) are BC1
Normal maps (_n) are BC5U
TGA textures used where alpha channel is present:
RGB can be extracted with BC2 and alpha with BC5U - if you know a simpler method, let me know.
[Mosquito_Trans_h2o.zip](https://xentaxbackup.github.io/file/17676_Mosquito_Trans_h2o.zip)
## Post #21
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2020-03-14T10:47:09+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

> Reply from Ruisuu18 ↑Sun Mar 01, 2020 8:13 am at Sun Mar 01, 2020 8:13 am
>
> 
Has anyone managed to rip from the pc files yet? All I get are a bunch of unknown files?

Would be interested in this too. Tried some tools but they always give me random file names.
## Post #22
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-14T15:57:02+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

Hiroshi already released his script here [viewtopic.php?f=16&t=21863](https://forum.xentax.com/viewtopic.php?f=16&t=21863)
It's only partially working with form changes, I have one of my own that doesn't seem to have issues, but I'm using part of his code, so I don't know if I should release it due to respect to him.
## Post #23
- Username: Ahri
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Apr 11, 2012 11:23 pm
- Post datetime: 2020-03-14T18:11:57+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

> Reply from JosouKitsune ↑Sat Mar 14, 2020 11:57 pm at Sat Mar 14, 2020 11:57 pm
>
> 
Hiroshi already released his script here viewtopic.php?f=16&t=21863
It's only partially working with form changes, I have one of my own that doesn't seem to have issues, but I'm using part of his code, so I don't know if I should release it due to respect to him.

It doesn't extract the main files though or? opm_data_main_ww.cpk and opm_data_sub_ww.cpk
Those give me the useless filenames
## Post #24
- Username: JosouKitsune
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Jun 26, 2017 9:01 am
- Post datetime: 2020-03-14T19:57:53+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

> Reply from Ahri ↑Sun Mar 15, 2020 2:11 am at Sun Mar 15, 2020 2:11 am
>
> 
It doesn't extract the main files though or? opm_data_main_ww.cpk and opm_data_sub_ww.cpk
Those give me the useless filenames

PC files aren't extractable atm, the script is only for PS4 files.
## Post #25
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2021-04-19T05:07:41+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

> Reply from JosouKitsune ↑Sun Mar 15, 2020 3:57 am at Sun Mar 15, 2020 3:57 am
>
> 
Ahri wrote: ↑Sun Mar 15, 2020 2:11 am
It doesn't extract the main files though or? opm_data_main_ww.cpk and opm_data_sub_ww.cpk
Those give me the useless filenames


PC files aren't extractable atm, the script is only for PS4 files.

Hello! sorry for the quote, but I wanna know if the PC files can be extracted or not yet, I'm getting the same result as Ahri :/
## Post #26
- Username: david056
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 08, 2021 9:44 pm
- Post datetime: 2021-06-08T13:44:48+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

Any one punch man lover here ?
## Post #27
- Username: ramon82155
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jul 30, 2021 5:59 am
- Post datetime: 2021-07-29T22:10:21+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

Hello, I was able to extract the 3d model of Garou using Ninja Ripper but for some strange reason the textures look strange, I share the model with you in case you find a solution.



[https://www.mediafire.com/file/mauygkn3 ... u.rar/file](https://www.mediafire.com/file/mauygkn34je5y3r/Garou.rar/file)
## Post #28
- Username: Ruisuu18
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Mar 16, 2019 3:03 am
- Post datetime: 2021-08-03T03:56:31+00:00
- Post Title: Re: One Punch Man A Hero Nobody Knows

> Reply from ramon82155 ↑Fri Jul 30, 2021 6:10 am at Fri Jul 30, 2021 6:10 am
>
> 
Hello, I was able to extract the 3d model of Garou using Ninja Ripper but for some strange reason the textures look strange, I share the model with you in case you find a solution.



https://www.mediafire.com/file/mauygkn3 ... u.rar/file

Yeah I tried to rip using ninjaripper too, doesn't rip the UV maps properly, so you'd need to re-UV map the model yourself

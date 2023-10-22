## Post #1
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-10T13:13:23+00:00
- Post Title: [Fantasy Tennis] Need Help on models

Hi there everyone.

I have some problems with acquiring file type from the game 'Fantasy Tennis'
I tried to extract the model from the game file, what I got is UV map files in .TEX format (which I later converted to .DDS) 
However, the model files are in .DAT format which I don't know how to open it.

Does anyone know how to open those files (or know the program that used to create the files)?
I really want to extract these models to make a memory book and post it to the Facebook group where many players missed this game.

This is the example of the files I mentioned.
: [https://drive.google.com/open?id=1ymTvH ... o_l9V7SI3X](https://drive.google.com/open?id=1ymTvHx9Gr6dElKFgsGxbgio_l9V7SI3X)

If you have any concerns or questions regarding this issue, please let me know.
Thanks in advance.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-10T17:36:26+00:00
- Post Title: [Fantasy Tennis] Need Help on models

Using AMR for exmaple:



Preview of the first 4 submeshes:
## Post #3
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-11T05:40:50+00:00
- Post Title: [Fantasy Tennis] Need Help on models

Wow, this is incredible. Thank you for lighting the way for me.

About AMR, I tried reading your topic about AMR and I think that this might be too hard for me to execute (like I don't know where to get the .plf file from my files or how to split file to submeshes as you do)

Could you please indicate the steps of doing this thing (if it's not too much)?
But if this is bothering you, I understand.

But in any way, I would like to thank you a million times, cause at least I now know that there's a way to open these files.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-11T09:38:51+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Tue Feb 11, 2020 1:40 pm at Tue Feb 11, 2020 1:40 pm
>
> 
About AMR, I tried reading your topic about AMR and I think that this might be too hard for me to execute (like I don't know where to get the .plf file from my files or how to split file to submeshes as you do)
You can't get the plf file for your model from nowhere unless you create one yourself. To correctly use AMR, it requires you to obtain the basic knowledge of reverse engineering a game model. You can read the tutorial series from the 1st link in my signature if you're interested in the details. There's no specific tutorial about AMR yet but you can easilly move to it if you're familiar with Hex2Obj which is used in the mentioned tutorials.

> Reply from mcjnp4864 ↑Tue Feb 11, 2020 1:40 pm at Tue Feb 11, 2020 1:40 pm
>
> 
Could you please indicate the steps of doing this thing (if it's not too much)?
Extracting data manually is tedious but since this format is relatively simple I guess it's OK to make a demonstration.

First you'll need an hex editor. Open your file in the editor and jump to address 0xE0:

As shown above, the green rectangle field is the value of the vertex count, the blue field, the polygon indices count, where the red field is a flag that indicates the vertex structure size. The vertex data follow right after the red field. Same representation is used below.

You can use the hex editor to interpret these values as 32-bit integers, so the vertex count is 0x329 alias 809 in decimal; the polygon indices count 0x6E2 alias 1,762 in decimal, but remember the actual count is 2 bigger than it in this format, so 1,764 for the actual count. The vertex address as shown in the screenshot above is 0xEC. As for the vertex data stride of this format, if the flag is 0, the stride'd be 36, and if the flag is 2, the stride'd be 56. Here the flag is 0, so its stride is 36.

Place these values in AMR as below:


Just keep the rest parameters in sync at the moment. Now you can press the Proceed button to preview the model, normal and UV. If everything's fine, press the Add button of the Parameters group box to add the current parameters to the list. You can rename it for the mesh by pressing the Ren button if you'd like to.

Now for the next submesh. Press the Indices button and the Postions button successively you'll see this in the digest message box:


0x2AD6C is the address of the polygon indices for the next submesh. Jump to address 0x72B0 in the hex editor:


Vertex count 0x3C2 alias 962 in decimal; polygon indices count 0x77D+2 alias 1,919 in decimal. Note the flag here is 2 so the vertex stride is 56. The vertex address is 0x72C4 as read from the editor. Change the corresponding parameters as below:


Preview and press the Add button if it's okay.

Then you can repeat these steps untill you get all submeshes handled. If you encounter some data like this:


Just look for the 8-zero bytes below that as in the purple thin rectangle, then you can locate to the info you need.

If you see a string like this when you jump to the vertex header of another submesh then you've got all submeshes handled.


You can navigate to the Options menu and preview all submesh in the list.



Press the Save button if you want to preserve your effort for later reference and that's how you generate your plf file. 

As a final step you can export them by navigating to File > Export from List.
## Post #5
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-11T12:53:08+00:00
- Post Title: [Fantasy Tennis] Need Help on models

Thank you very much for your help (also your link, it helps me learn many things)
Now I'm able to extract the model I posted and other models using your method too.

[](https://uppic.cc/v/6SrY)

Now I will finish the model and move to the next step, which is putting UV-map into the model. 
I will now have model.fbx and uv-map.jpeg. Can I do it in simple ways?
Do you have any suggestions for this?
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-11T17:17:46+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Tue Feb 11, 2020 8:53 pm at Tue Feb 11, 2020 8:53 pm
>
> 
Now I will finish the model and move to the next step, which is putting UV-map into the model. 
I will now have model.fbx and uv-map.jpeg. Can I do it in simple ways?
Do you have any suggestions for this?
You can import FBX into a lot of 3D apps. Then you can apply the texture onto the models. Here's how it looks like in 3Ds Max:



texture.png (129.37 KiB) Viewed 185 times



Sadly there's one thing you need to know. The UVs need to be flipped so you need to check the flip UV option in AMR and export it again.


I hope you had kept your plf files.  Or you can flip the UVs in the 3D app.
## Post #7
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-12T10:04:41+00:00
- Post Title: [Fantasy Tennis] Need Help on models

Hi again, I've done 3 models (with color) so far and have no problems at all thanks to you.
Just to let you know that you helped me a lot.
## Post #8
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-12T12:30:47+00:00
- Post Title: [Fantasy Tennis] Need Help on models

May I ask if there's any modification for some cases?

I tried to make this model 3 times already but what I get were incomplete models as shown below.

[](https://uppic.cc/v/6SEP)

Here's a link to this file: [https://drive.google.com/open?id=1CGWP5 ... zaJy4Tv-CG](https://drive.google.com/open?id=1CGWP5vZGd-bxoWlZxmjxprzaJy4Tv-CG)
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-13T15:50:31+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Wed Feb 12, 2020 8:30 pm at Wed Feb 12, 2020 8:30 pm
>
> 
May I ask if there's any modification for some cases?

I tried to make this model 3 times already but what I get were incomplete models as shown below.
You've got all 34 objects exported so I guess by "incomplete" you mean the missing face of some meshes? It's because there're extra data in the indices which were mistaken as part of the polygon indices.

This's how the model looks like:


Here's a Noesis script for this format. Skeleton can be loaded but weights are not handled yet.

[fmt_FantasyTennis_dat.zip](https://xentaxbackup.github.io/file/17503_fmt_FantasyTennis_dat.zip)
## Post #10
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-13T17:27:28+00:00
- Post Title: [Fantasy Tennis] Need Help on models

I tried doing it once again, I could finally make it way better than my first three.

[](https://uppic.cc/v/64MC)
>> You can see that there are some mistakes in the model but I guess it is fine

Also, thanks for your work on that model, I really appreciate it. And right now I'm absorbed into this thing.

But sir, may I need your help again?
I have done all bosses now and moved to the NPCs in the game.
What I do was the same as you taught me, the model seemed to be fine; however, when I applied the UV-map into the model, it became like this again and I couldn't fix it in any way. (I tried to find my mistake but couldn't find one and it is too 'error' to use in my document)

[](https://uppic.cc/v/64M7)
>> Mesh002 is miscolored

This also applied to the next NPC I've done. 
[](https://uppic.cc/v/64Mq)
>> I think only Mesh001 and Mesh006 are correct

Could you please look into these for me? 
Here are the .dat and uv-map files for those models and the .plf file that I have done. 
(in case you can check where my mistakes are at)
Sadly I didn't save the plf file of the owl one.

[https://drive.google.com/open?id=1odTkM ... hx8feuJCzA](https://drive.google.com/open?id=1odTkMaFERp6QqZPFqPRJD_hx8feuJCzA)

Thanks in advance.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-14T05:43:43+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Fri Feb 14, 2020 1:27 am at Fri Feb 14, 2020 1:27 am
>
> 
however, when I applied the UV-map into the model, it became like this again and I couldn't fix it in any way. (I tried to find my mistake but couldn't find one and it is too 'error' to use in my document)

Did you press the Push button of the UV settings?


That's for multiple UV channels only and if you pressed it unintentionally but didn't delete or update it for the next parameter set it'll remain there considered as the UV params you save for this mesh.

> Reply from mcjnp4864 ↑Fri Feb 14, 2020 1:27 am at Fri Feb 14, 2020 1:27 am
>
> 
Here are the .dat and uv-map files for those models and the .plf file that I have done. 
(in case you can check where my mistakes are at)
FYI, it's recommended to enable the "Use Relative Path" option when you need to create a shareable plf so it doesn't rely on the actual path of your model data file.


Anyway these two samples have animation data before the polygon indices section so the Noesis script needs to be updated. You can redownload it at the same post.

With texture applied in 3Ds Max:
## Post #12
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-14T06:29:34+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from Bigchillghost ↑Fri Feb 14, 2020 1:43 pm at Fri Feb 14, 2020 1:43 pm
>
> 
Did you press the Push button of the UV settings?

After I clicked del on the program, I could finally make it.
Thank you so much
## Post #13
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-15T17:51:23+00:00
- Post Title: [Fantasy Tennis] Need Help on models

Hi again, Mr.Bigchillghost.

I've made many models now and I'm really proud of them.
Now I wonder something. I attempted to make a model of an in-game item (the file size is quite small), I found these codes but I can't find what number(s) should I put into the program.

[](https://uppic.cc/v/64Ea)

Could you please help me? Here is the link to this file:
[https://drive.google.com/file/d/18abfJL ... bg6fr/view](https://drive.google.com/file/d/18abfJLhst01RWCxHZqt9Jz3okj3bg6fr/view)

Thanks in advance.
## Post #14
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-17T04:06:55+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Sun Feb 16, 2020 1:51 am at Sun Feb 16, 2020 1:51 am
>
> 
I've made many models now and I'm really proud of them.
You did that manually? 

> Reply from mcjnp4864 ↑Sun Feb 16, 2020 1:51 am at Sun Feb 16, 2020 1:51 am
>
> 
Now I wonder something. I attempted to make a model of an in-game item (the file size is quite small), I found these codes but I can't find what number(s) should I put into the program.
Well this is a new case where some fields in the header are missing.

The value 4 in the red field indicates the stride, which is 32 here, is different than the previous 2 cases.





Since it's unclear which field in the header determines this situation, the Noesis script won't be updated unless more similar samples are provided.
## Post #15
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-17T08:22:10+00:00
- Post Title: [Fantasy Tennis] Need Help on models

> Reply from Bigchillghost ↑Mon Feb 17, 2020 12:06 pm at Mon Feb 17, 2020 12:06 pm
>
> 
You did that manually?

Indeed. What do you mean by that, does it have other easy ways to do this?

> The value 4 in the red field indicates the stride, which is 32 here, is different than the previous 2 cases.

Thanks a lot.
## Post #16
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-17T08:43:56+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Mon Feb 17, 2020 4:22 pm at Mon Feb 17, 2020 4:22 pm
>
> 
Indeed. What do you mean by that, does it have other easy ways to do this?
Of course, by using the Noesis script provided already in this [post](https://forum.xentax.com/viewtopic.php?p=159938&sid=fc6984276a0b45e0c9192b0282b2b84f#p159938).
## Post #17
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-17T11:02:22+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from Bigchillghost ↑Mon Feb 17, 2020 4:43 pm at Mon Feb 17, 2020 4:43 pm
>
> 
mcjnp4864 wrote: ↑Mon Feb 17, 2020 4:22 pm
Indeed. What do you mean by that, does it have other easy ways to do this?

Of course, by using the Noesis script provided already in this post.

I tried to do it once, but I got an error message in some models. So I do manually instead.
[](https://uppic.cc/v/6ZQx)
## Post #18
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-17T11:40:19+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Mon Feb 17, 2020 7:02 pm at Mon Feb 17, 2020 7:02 pm
>
> 
I tried to do it once, but I got an error message in some models.
Well, you can't guarantee a script written based on a limited number of samples to work with all files. Just upload a couple of the files that crash the script.
## Post #19
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-18T06:34:33+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from Bigchillghost ↑Mon Feb 17, 2020 7:40 pm at Mon Feb 17, 2020 7:40 pm
>
> 
mcjnp4864 wrote: ↑Mon Feb 17, 2020 7:02 pm
I tried to do it once, but I got an error message in some models.

Well, you can't guarantee a script written based on a limited number of samples to work with all files. Just upload a couple of the files that crash the script.

Here are some files that cause an error.

>> [https://drive.google.com/open?id=1E4K-a ... lwCWkNivKO](https://drive.google.com/open?id=1E4K-aU9PsYocj_vNG1FKYMlwCWkNivKO)
## Post #20
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-02-18T08:06:24+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

Here's the updated script compatible for all current samples. Not sure if it works with other item files.
[fmt_FantasyTennis_dat.zip](https://xentaxbackup.github.io/file/17511_fmt_FantasyTennis_dat.zip)
## Post #21
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2020-02-18T08:54:47+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from Bigchillghost ↑Tue Feb 18, 2020 4:06 pm at Tue Feb 18, 2020 4:06 pm
>
> 
Here's the updated script compatible for all current samples. Not sure if it works with other item files.

Thanks a lot.
If there is another error occurring, I can do it manually so no problem on that.
## Post #22
- Username: LionRnD
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Mar 25, 2020 9:46 pm
- Post datetime: 2020-03-25T14:44:45+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

I tried to open some Player mesh file still the same error.
## Post #23
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-19T00:58:00+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from mcjnp4864 ↑Mon Feb 10, 2020 9:13 pm at Mon Feb 10, 2020 9:13 pm
>
> ...what I got is UV map files in .TEX format (which I later converted to .DDS) 

This is the example of the files I mentioned.
: https://drive.google.com/open?id=1ymTvH ... o_l9V7SI3X
the tex sample has the first 128 bytes xored by 0xff,
here is Noesis python script to unxor the header and open the image.  


 tex_FantasyTennis_tex.zip
(574 Bytes) Downloaded 25 times
## Post #24
- Username: mcjnp4864
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Mar 19, 2019 12:58 pm
- Post datetime: 2021-07-19T15:53:02+00:00
- Post Title: Re: [Fantasy Tennis] Need Help on models

> Reply from Bigchillghost ↑Tue Feb 18, 2020 4:06 pm at Tue Feb 18, 2020 4:06 pm
>
> 
Here's the updated script compatible for all current samples. Not sure if it works with other item files.

> Reply from Acewell ↑Tue May 19, 2020 8:58 am at Tue May 19, 2020 8:58 am
>
> 
the tex sample has the first 128 bytes xored by 0xff,
here is Noesis python script to unxor the header and open the image.   
tex_FantasyTennis_tex.zip

Hello Bigchillghost and Acewell, I tried to open these two files with your script but there's an error when I tried to open them. May I ask for your help?

I uploaded the files through Google Drive (as it is too large to upload here)
: [https://drive.google.com/file/d/1O12Ui4 ... YXxIb/view](https://drive.google.com/file/d/1O12Ui4ePwHVepFqhkkQVziPh5zQYXxIb/view)

Thanks.

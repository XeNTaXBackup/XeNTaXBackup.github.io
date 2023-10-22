## Post #1
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-10T17:24:34+00:00
- Post Title: HeatBlast.et_decomp model?

Hello Hex2obj users.
I've moved onto finding some face indices (finds) from my HeatBlast galactic racing model.
Here's the picture of the vertices data:



HeatBlast_____00000000.et_decomp_Tue_Aug_31_17-44-38_2021.png (25.37 KiB) Viewed 216 times


(note I can try to find the face indices with HexEdit, and the face indices in alphabetical type couldn't be counted. any help? using Hex2obj?)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-10T19:45:21+00:00
- Post Title: HeatBlast.et_decomp model?

Search for 000001000200 to find start addresses of face indices blocks. Some *.et_decomp files, such as FourArms_Teen (size: 2102848 bytes) don't contain any 000001000200 sequence - maybe it's texture files, dunno.
## Post #3
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-10T21:08:34+00:00
- Post Title: HeatBlast.et_decomp model?

Thanks!
Edit: Tho what's the decoded address with Hex2obj?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-11T19:29:29+00:00
- Post Title: HeatBlast.et_decomp model?

dunno, I don't have that model. Also keep in mind that this forum isn't meant to care for each single model you have.
There's params for some .et_decomp models. Learn, understand, use them for other models.

(People who help you here are not  your servants, btw. That's what I feel when reading your last pm. So please: stop that! Immediately.)
## Post #5
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-11T19:32:42+00:00
- Post Title: HeatBlast.et_decomp model?

I'll send the google drive link, and sorry for serving.
[https://drive.google.com/file/d/1q90S4g ... sp=sharing](https://drive.google.com/file/d/1q90S4gbAFTR2MX4jB3icIiqynPPedBSS/view?usp=sharing)
Here you go.
Edit: I found the params. Any help of finding the indices?



heatblast_params_found_by_numbers.png (42.71 KiB) Viewed 177 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-11T20:45:34+00:00
- Post Title: HeatBlast.et_decomp model?

Not sure about your question.  
At 0x2096C a face index block of a sub mesh seems to start.

edit: no, it's 0x2096B, because it's big endian (I forgot about that, sorry)
## Post #7
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-20T17:11:34+00:00
- Post Title: HeatBlast.et_decomp model?

Umm, I found this but, the verts count and offset is kinda missing, can I have some help finding the whole model?


heatblast_finds_offset_no_real_verts_offset.png (16.25 KiB) Viewed 110 times


There's no FVFsize and UVpos values in,
so what happens if I try and put 187c7 in?
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-20T17:52:43+00:00
- Post Title: HeatBlast.et_decomp model?

> Reply from lilyampykidXeNTaXalt ↑Tue Sep 21, 2021 1:11 am at Tue Sep 21, 2021 1:11 am
>
> so what happens if I try and put 187c7 in?As what? A vertex start address? Why?

As a hint, the address 9095 here (tool from Lazov?) 

> Reply from lilyampykidXeNTaXalt ↑Sat Sep 11, 2021 1:24 am at Sat Sep 11, 2021 1:24 am
>
> 
appears to be a decimal value, afaics.

hex2obj expects the addresses as hexadecimal values. Obviously you don't know this?
(It adds 0x automatically so no need to enter 0x in the address editboxes.)

(Also the vertex blocks starts earlier in the file at 155f: 5471 dec..)
.



HeatBlast.png (89.23 KiB) Viewed 100 times


Well, I have the strange feeling that we were already at this point some months ago (maybe another model, dunno).

Sadly I have to tell you that I have no time and no interest to solve the issue(s).
## Post #9
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-20T17:58:32+00:00
- Post Title: HeatBlast.et_decomp model?

Okay, that should do for now.
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-20T17:59:42+00:00
- Post Title: HeatBlast.et_decomp model?

And ever, for me.
## Post #11
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-10-03T14:56:02+00:00
- Post Title: HeatBlast.et_decomp model?

Hey, I did a resolution to the vertices offset, @shakotay2
the offset is here: 1547, might have face indices and vertices missing to get the full model.
Any help here to fix the model later?
.



heatblast_fixed_but_some_missing.png (57.22 KiB) Viewed 53 times


edit: i forgot to put the image to show the fix and some missing indices and vertices.

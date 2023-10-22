## Post #1
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-08-07T23:20:43+00:00
- Post Title: Just Cause 3 .rbm models

Hi,i want to extract models from Just Cause 3. I hope someone can help.

Here is documentation about this format:
[http://justcause.wikia.com/wiki/Render_Block_Model](http://justcause.wikia.com/wiki/Render_Block_Model)

Here is models samples:
[https://mega.nz/#!Igc21Cia!kdWzWoJ0k0Ei ... NmBeqtxP2I](https://mega.nz/#!Igc21Cia!kdWzWoJ0k0Ei4RpdrXKX_sKBQgyMD_JsMNmBeqtxP2I)

I only found tools for Just Cause 2 but not for JC3.

Models in archive is a car with parts from screenshot below:
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-08T03:01:13+00:00
- Post Title: Just Cause 3 .rbm models

ladbil_body_lod1.rbm  



ladbil_body_lod1_rbm.png (18.58 KiB) Viewed 474 times
## Post #3
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-08-08T16:40:20+00:00
- Post Title: Just Cause 3 .rbm models

> Reply from AceWell
>
> ladbil_body_lod1.rbm  
ladbil_body_lod1_rbm.png

Thank you,but how to find uv maps? Im extract wheel model,but uvs broken.
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-08T23:18:17+00:00
- Post Title: Just Cause 3 .rbm models

ladbil_wheel_f_l_lod1.rbm  



ladbil_wheel_f_l_lod1_rbm.png (54.13 KiB) Viewed 452 times
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-12T13:29:34+00:00
- Post Title: Just Cause 3 .rbm models

here is a Noesis python script to open your *.rbm model samples  


 fmt_JustCause3_rbm.zip
(1006 Bytes) Downloaded 101 times


supports mesh and UVs
## Post #6
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-08-16T07:50:41+00:00
- Post Title: Just Cause 3 .rbm models

> Reply from AceWell
>
> here is a Noesis python script to open your *.rbm model samples  
fmt_JustCause3_rbm.zip
supports mesh and UVs

Thank you very much! But here is a problem with other vehicle models,seems like they have more than 1 mesh in single file so script doesnt work with them all.

There is more samples. Script doesnt work with that:

[https://mega.nz/#!w1VkjThY!JCc69z-WctxI ... 1tVV1k3Xts](https://mega.nz/#!w1VkjThY!JCc69z-WctxIZ60SrYn0JgC5_KGyBQfRp1tVV1k3Xts)
## Post #7
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-09-22T20:01:58+00:00
- Post Title: Just Cause 3 .rbm models

Can anyone help me please?

I cant open model in hex2obj what am i doing wrong?


That one for file "propaganda_smallvan_body_lod1.rbm"


Here is examples of models and errors from AceWell script.

[https://mega.nz/#!w1VkjThY!JCc69z-WctxI ... 1tVV1k3Xts](https://mega.nz/#!w1VkjThY!JCc69z-WctxIZ60SrYn0JgC5_KGyBQfRp1tVV1k3Xts)
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-22T21:17:17+00:00
- Post Title: Just Cause 3 .rbm models

> Reply from dropoff
>
> I cant open model in hex2obj what am i doing wrong?there's a different FVFsize and you're lost?  

Plus you need vertex block mode (VB) here, not seq(uential).

Have a look at the obj file:
# 0x991: verts= 2585
v -0.870186 1.970598 0.784575 
v 32639.496094 893225992192.000000 3065015957662111300000000000.000000 
v -0.873055 1.955190 0.784573 
v 32639.496094 897520959488.000000 3065015662514206200000000000.000000 
v -0.880382 1.970598 0.784575 

Plain to see that an FVFsize of 12 bytes is wrong here, as simple as that. 24 obviously seems to fit better
(where the UVB size is 32 bytes, you'll need some experience to see that, or use trial 'n error):



propaganda_smallvan_body_lod1-rbm.jpg (173.42 KiB) Viewed 321 times
## Post #9
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-09-23T09:45:00+00:00
- Post Title: Just Cause 3 .rbm models

Thanks a lot.
I need more experience in that 
And last question,how to find that FBED value in FVF size graph?
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-23T10:33:46+00:00
- Post Title: Just Cause 3 .rbm models

> Reply from dropoff
>
> And last question,how to find that FBED value in FVF size graph?0xFBED is the start of the uv blocks.

calculating end of vertex data block:
0x991 + 2585x24 (dec.) = 0xFBE9
skipping 4 bytes
0xFBE9 + 4 = 0xFBED

4 bytes (little endian) at 0xFBE9 are DWORD uvs_count
19 0A 00 00 -> 0x00000A19 = 2585 (dec.), uvs count (=vertex count)
---------------------------

years later, smallvan_engine_lod1.rbm, just because this post did not have an attachment:  
.



smallvan_engine.jpg (197.71 KiB) Viewed 46 times
## Post #11
- Username: dropoff
- Rank: veteran
- Number of posts: 140
- Joined date: Sun Dec 18, 2016 10:32 am
- Post datetime: 2017-10-24T17:53:05+00:00
- Post Title: Just Cause 3 .rbm models

Hello again,sorry for maybe too many questions but i dont understand how to find start address of uv when model is sequential.
Model is ok but uv's not:


Here is file: [https://mega.nz/#!8gVnzKQD!nDrd_8vrtRQc ... 6YUqueaqi4](https://mega.nz/#!8gVnzKQD!nDrd_8vrtRQchptOZIKZGmUt5VRapZTMf6YUqueaqi4)

Same problem with 2 other meshes from that file.
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-26T08:26:02+00:00
- Post Title: Just Cause 3 .rbm models

> Reply from dropoff
>
> i dont understand how to find start address of uv when model is sequential.
start by searching for an 8 byte pattern, i just use "VB" mode for everything now, i wish it was default 



cargotransport_body_lod1_rbm.png (44.75 KiB) Viewed 246 times

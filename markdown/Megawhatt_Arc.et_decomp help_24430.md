## Post #1
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-08-30T10:49:32+00:00
- Post Title: Megawhatt_Arc.et_decomp help

Hi! i need help wth Megawhatt's .et_DECOMP, so is there any help required?
[https://drive.google.com/file/d/1HKrNMk ... sp=sharing](https://drive.google.com/file/d/1HKrNMkRMDv_lFTcnox2-jEt--Lz8izw4/view?usp=sharing)
I could have the model, obviously.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-30T11:31:50+00:00
- Post Title: Megawhatt_Arc.et_decomp help

Didn't we have a solution for spidermonkey.et or Jetray.et already? So why not use the information from that?
## Post #3
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-08-30T11:34:58+00:00
- Post Title: Megawhatt_Arc.et_decomp help

Oh, I might get the vertices data for the Megawhatt Arc model.
Edit: Here's a screenshot showing the vertices data.



MegaWhatt_Arc_____00000000.et_decomp_Mon_Aug_30_12-35-29_2021.png (20.11 KiB) Viewed 163 times


note, I couldn't get the faces.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-30T11:36:07+00:00
- Post Title: Megawhatt_Arc.et_decomp help

That's the way it works! 
You know that the parameters for hex2obj will be different for different models? Usually only the stride (FVFsize) and format ("float" for example) will remain the same. (For more complex formats even that may change.) The endianness (litE or BigE) is always the same, of course.
## Post #5
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-08-30T13:05:41+00:00
- Post Title: Megawhatt_Arc.et_decomp help

Hey Shakotay2, is the search of one submesh done?
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-08-30T18:45:00+00:00
- Post Title: Megawhatt_Arc.et_decomp help

When you search for 000000010002 there's more than one finds, so guess no.

Btw, having the params for FourArms_WC_____00000000.et_decomp as an example it's no rocket science to get them for MegaWhatt_Arc:
.



MegaWhatt_Arc_____00000000-et_decomp.png (89.35 KiB) Viewed 133 times
## Post #7
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-08-31T16:19:25+00:00
- Post Title: Megawhatt_Arc.et_decomp help

Can you help me resolve my Heatblast Galactic Racing model? I'll send the data and the et_decomp link.



HeatBlast_____00000000.et_decomp_Mon_Aug_30_22-02-53_2021.png (35.1 KiB) Viewed 97 times


[https://drive.google.com/file/d/1q90S4g ... sp=sharing](https://drive.google.com/file/d/1q90S4gbAFTR2MX4jB3icIiqynPPedBSS/view?usp=sharing)
There we go. I put the url and the image for the vertices data, note there are UVs data too. sorry if I mess up the wrong way!

## Post #1
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-10-20T03:57:44+00:00
- Post Title: Super Hero Generations *.MBG

I have been looking looking for a way to convert the models form this game to at lest a un-rigged mesh. if anyone is to help me i have the files uncompressed and with it's textures. No Normal Map because i didn't understand the format of the DDS.

[https://www.dropbox.com/s/bikcc9ypc18mq ... K.rar?dl=0](https://www.dropbox.com/s/bikcc9ypc18mq2v/SHG%20ANHK.rar?dl=0) 
Includes:
The Model File (Uncompressed?). the Diffuse Specular and Alpha Mask Textures. the Model is the  Bird Greeed Ankh (Arm) from Kamen Rider OOO.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-20T11:03:44+00:00
- Post Title: Super Hero Generations *.MBG

this MBG file is not compressed - the format is just a little bit funny 



SuperHeroGen-hr038_0001_01_b0_m01.jpg (75.03 KiB) Viewed 95 times


(After some superfluous C coding I realized that getting a wavefront obj should be possible with hex2obj, too.)
## Post #3
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-10-20T15:53:46+00:00
- Post Title: Super Hero Generations *.MBG

ooh how did you do that did you write a script for it? i haven't under stood for hex editing works yet for models. hex2obj was just giving me bloated obj files that don't load.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-20T16:21:07+00:00
- Post Title: Super Hero Generations *.MBG

i did not see how simple the format is:



hr038.jpg (179.45 KiB) Viewed 79 times
## Post #5
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-10-20T17:44:13+00:00
- Post Title: Super Hero Generations *.MBG

hmm interesting Thanks a bundle. I need to figure out how this works... there are other models i want to pop out from this game too.

edit:
Also it seems that the Torn Cloths are missing
They are in the first picture.
i figure out how to find the models but thats it...

er45_01 The White Wizard.

[https://www.dropbox.com/s/ot7opi7nwkcb1 ... 1.mbg?dl=0](https://www.dropbox.com/s/ot7opi7nwkcb1xw/er045_0001_02_m01.mbg?dl=0)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-20T22:15:20+00:00
- Post Title: Super Hero Generations *.MBG

well, yes, using hex2obj is more than copying addresses  

Here you have to search for the first occurence of the pattern 01 00 00 00 0C to get the vertices start address: 0x59E.
(First submesh?)



er045.jpg (37.35 KiB) Viewed 64 times
## Post #7
- Username: Arymond
- Rank: advanced
- Number of posts: 54
- Joined date: Sun Feb 12, 2012 7:49 am
- Post datetime: 2015-10-20T22:45:01+00:00
- Post Title: Super Hero Generations *.MBG

> Reply from shakotay2
>
> well, yes, using hex2obj is more than copying addresses  

Here you have to search for the first occurence of the pattern 01 00 00 00 0C to get the vertices start address: 0x59E.
(First submesh?)
er045.jpg

yeah it should have more meshs: his hands, the chest ring holders, the Belt, cloak, coat tails and his cane.
\

Edit: i think i got the wrong address because it seems incomplete in the face. or the wrong face count?

thank you for explaining how it works in a way i understand

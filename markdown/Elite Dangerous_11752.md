## Post #1
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-08-06T17:34:58+00:00
- Post Title: Elite Dangerous

Anyone had a look at Elite Dangerous ovl files? I can rip files out with offzip but knowing the structure would be helpful.

Here's the beginning of one
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2014-08-06T18:21:52+00:00
- Post Title: Elite Dangerous

Upload samples.
## Post #3
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2014-08-07T15:42:08+00:00
- Post Title: Elite Dangerous

If anyone needs samples drop me a PM.
## Post #4
- Username: zzz
- Rank: beginner
- Number of posts: 21
- Joined date: Wed May 21, 2014 9:36 pm
- Post datetime: 2014-12-31T19:12:45+00:00
- Post Title: Elite Dangerous

```
https://www.mediafire.com/?tznzxrbxoqjbseb
```


Sample files from the Combat Demo Items\Ship\Eagle folder. Almost all files types are in the OVL format. Regarding sound I found this:

> The OVL and OVS files are compressed with zlib.
>
> 
>
> OVL files make up parts of a virtual serialized filesystem, and are partially compressed. OVS files are completely compressed and contains most of the bulk data.
>
> 
>
> Can't give you more info than that at the moment as I'm at work and I've not looked at them for a while.

though replacing models is the thing I'm most interested in.
## Post #5
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-02-05T01:07:33+00:00
- Post Title: Elite Dangerous

Bump? 

[viewtopic.php?f=21&t=12572&p=103469#p103469](http://forum.xentax.com/viewtopic.php?f=21&t=12572&p=103469#p103469) I'm looking for the same thing. Although I made a new thread.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-05T12:56:09+00:00
- Post Title: Elite Dangerous

> Reply from zzz
>
> though replacing models is the thing I'm most interested in.would be the last step in the chain just started:
[Eagle_Debris_.JPG](https://xentaxbackup.github.io/file/8608_Eagle_Debris_.JPG)
## Post #7
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-02-08T20:34:43+00:00
- Post Title: Elite Dangerous

How'd you do it^
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-02-10T09:28:26+00:00
- Post Title: Elite Dangerous

I used hex2obj (view link in my sig)
Press the tut(orial) button in hex2obj to read more.

But it's not a one click solution. Do the tutorial example to understand how it works.
## Post #9
- Username: blinxies
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 21, 2012 7:11 pm
- Post datetime: 2015-03-31T17:52:58+00:00
- Post Title: Elite Dangerous

> Reply from shakotay2
>
> I used hex2obj (view link in my sig)
Press the tut(orial) button in hex2obj to read more.

But it's not a one click solution. Do the tutorial example to understand how it works.

I have tried your example and it worked very well. Ended up with a female torso.
But now I tried what you said with the Eagle_Debris and It doesn't work, even with your screenshot settings matching.
None of Data.ovl, Data.ovs.models_l0 and Data.ovs.models_l1 result in anything.

I want the vulture model to 3D print it but yeah, I just cannot understand that part.
Did Frontier changed the files lately or something ?

Because I am sure that none of the files have anything starting at 130
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-31T20:44:41+00:00
- Post Title: Elite Dangerous

> Reply from blinxies
>
> But now I tried what you said with the Eagle_Debris and It doesn't work, even with your screenshot settings matching.
None of Data.ovl, Data.ovs.models_l0 and Data.ovs.models_l1 result in anything.
Eagle_Debris-models_l0.dat (742700 bytes) is working with hex2obj v.0.23

> I want the vulture model to 3D print it but yeah, I just cannot understand that part.
>
> Did Frontier changed the files lately or something ?
>
> 
>
> Because I am sure that none of the files have anything starting at 130I don't have that vulture model but starting address of face indices may vary from model to model.
## Post #11
- Username: blinxies
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Feb 21, 2012 7:11 pm
- Post datetime: 2015-03-31T22:58:36+00:00
- Post Title: Elite Dangerous

This is the vulture from the Demo [https://mega.co.nz/#!kMtT1L6Q!dhEHiReG2 ... bSJ0tfoJss](https://mega.co.nz/#!kMtT1L6Q!dhEHiReG2Imde0Hv5SM6MyZX5pC0-8V6lbSJ0tfoJss)
(Link is a zipped file of the folder containing the data.ovl, and both LOD models, where only data.ovs.models_l0 is important.
This link should not be an issue with the site rule)

I have tried and succeeded with the debris model example you have provided in your screenshot previously.
I noticed I had to deflate the zlib stream from the OVS first.

Regardless, I am unable to reproduce the same manip with any other files that is not the eagle debris.
And your tutorial does not explain how you end up with a VB size of 20 and UV pos of 16
When I tried with a Nav Beacon, the render ended up being totally flat.

Would be nice to provide a quick example with E:D files.
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-04-01T12:11:32+00:00
- Post Title: Elite Dangerous

> Reply from blinxies
>
> This is the vulture from the Demothx, but I can't download it atm (I'm not at my working PC).

> And your tutorial does not explain how you end up with a VB size of 20 and UV pos of 16
After you got the vertex count (from max face indices) just devide the vertex section size (VSS) by vertexcount -> VBsize
(may not work for all models; you'll get VSS by experience or not)

UV pos you get by experience or just VBsize - (size of uv coords), as simple as that. (Does not work always.)

> When I tried with a Nav Beacon, the render ended up being totally flat.yeah, I know this problem

> Would be nice to provide a quick example with E:D files.
But iirc it was not easy to extract models from this format.

edit: well, for the vulture's first submesh it was:



Vulture_1.JPG (39.67 KiB) Viewed 348 times
## Post #13
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-04-12T19:56:54+00:00
- Post Title: Elite Dangerous

Any more updates on this?
## Post #14
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-05-04T20:30:01+00:00
- Post Title: Elite Dangerous

bump
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-04T21:56:34+00:00
- Post Title: Elite Dangerous

> Reply from eriger777
>
> Any more updates on this?I'm not working on these models.
Why don't you try it out for yourself?
It's pretty simple:



vulture_SM_3.JPG (71.78 KiB) Viewed 307 times
## Post #16
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2015-05-05T18:43:20+00:00
- Post Title: Re: Elite Dangerous

Can I just check are you unpacking the OVL / OVS files before looking at them in hexedit as I'm not see any vertex patten (alphabet) in there. Could you put up a few screen shots showing the marker points in hexedit please for a small object I can follow along and try for myself. Once I get one, I should be fine.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-05T19:43:42+00:00
- Post Title: Re: Elite Dangerous

Vulture-I0-00000000.dat, first submesh:



vulture_dat.JPG (124.15 KiB) Viewed 476 times
## Post #18
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2015-05-05T21:57:21+00:00
- Post Title: Re: Elite Dangerous

Thanks for that. I got it to work by following the 8b00 numbers you gave and got the mesh out as an OBJ. I also got it to work on the previous example starting at E5D8. There wasn't any UVs in those exports from what I saw. There seems to be multiple face indices in the files as well as multiple vertex lists too. 

Still trying to wrap my head around this. Hopefully others, smarter than me, can pick up on this and see where it goes. maybe make a few elite specific tutorials.
## Post #19
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2015-05-05T22:59:09+00:00
- Post Title: Re: Elite Dangerous

Seems the 2nd block of data follows immediately after the first block (at least I thought). both your examples seem to yet I tried one from another mesh and got only partial success.
## Post #20
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2015-05-06T08:37:38+00:00
- Post Title: Re: Elite Dangerous

More digging this morning. It looks like there are multiple face indices, then a block of vertices. The face indices blocks reference this one large block of vertices.

Sorry if this is all noob stuff! trying to get up to speed so I don't have to keep pestering. Hex2Obj seems to do the job just fine once it gets the right set of numbers. Still not seen any UVs transferred though.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-06T10:35:15+00:00
- Post Title: Re: Elite Dangerous

> Reply from prefim
>
> More digging this morning. It looks like there are multiple face indices, then a block of vertices.searching for 0000 0100 0200 gives many finds, then to decide which are the correct face indices blocks' startaddresses. (That's what you do I hope.)

> Hex2Obj seems to do the job just fine once it gets the right set of numbers.That's correct, sire.

> Still not seen any UVs transferred though.Trying out the columns marked by small blue outlines as signed shorts gives a sphere,
so guess these values might be part of the normals (didn't bother).

You might try out other columns:



vulture_uvs_.JPG (169.77 KiB) Viewed 459 times



edit: got the next submesh:
[](http://www.pic-upload.de/view-26945686/vulture_chassis.jpg.html)

(First I thought I couldn't get the additional offsets other than by guessing. Then I saw they were contained in some magic table.
 So once I've more spare time I will include it into the Make_H2O project.)
## Post #22
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2015-05-06T18:09:57+00:00
- Post Title: Re: Elite Dangerous

Magic table! that sounds promising! 

yeah, the 0000 0100 0200 search was a great way to find the starting point. end points seemed less obvious as sometimes it just ends, other times it the number order seems to get jumbled a bit. Not sure if I should just trim those out or include.

It would be awesome if your software could scan the whole document (looking for the 0000 0100 etc.) and find the blocks for us. especially if you can now find the offsets accurately. 

Looking forward to where this is going!
## Post #23
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-05-08T19:10:31+00:00
- Post Title: Re: Elite Dangerous

yeah, seems I finally got the correct uvs. They were simply too small sized (divided by 10000?):



Eagle_SM4_and_vulture.JPG (246.46 KiB) Viewed 445 times



Can't wait to create a Make_H2O project but it's on low priority.

btw: would be nice to have a texture - at least for the vulture. (Hope it will look cooler than Han Solo's Millennium Falcon.  )
## Post #24
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-05-12T18:55:43+00:00
- Post Title: Re: Elite Dangerous

I can get the textures no problem. It seems that you guys have made a huge step forward. Would this be useful for a converter?
## Post #25
- Username: prefim
- Rank: n00b
- Number of posts: 19
- Joined date: Fri May 21, 2010 6:10 pm
- Post datetime: 2015-05-14T07:13:59+00:00
- Post Title: Re: Elite Dangerous

I own the vulture so ripping not a problem and with eriger777's ripper method for getting the DDS's out, maybe we can combine the two.

Even if H2O just scanned the files, and offered up what it things are the blocks of verts and faces, we could simply have a yes no option based on how it looks. the software basically says 'does this look right?' and if you say yes, it saves it off and moves onto the next bit.
## Post #26
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-08-09T10:45:07+00:00
- Post Title: Re: Elite Dangerous

Hi,

do anyone still researching the model files?
I'm fiddling with it, the models are pretty easy to find, and found some data aswell, but most of it still unknown.
Sometimes there are padding bytes between face indices and vertex indices, sometimes there isn't, sometimes the vblock is 20, sometimes it's 24 even in one file (but the suspected vblock size value says otherwise tho).

So do anyone found anything?

Ripping files is a tedious task, and didn't even remotely as fun as creating a converter 

Plus I don't have imperial Eagle
## Post #27
- Username: Vindis
- Rank: advanced
- Number of posts: 44
- Joined date: Sat Apr 09, 2011 4:31 am
- Post datetime: 2017-08-17T14:34:05+00:00
- Post Title: Re: Elite Dangerous

My converter is getting into shape \m/

Now just have to figure out texture files, and UV coordinates, and ovls
## Post #28
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-17T16:13:41+00:00
- Post Title: Re: Elite Dangerous

> Reply from Vindis
>
> Hi,

do anyone still researching the model files?not really/unfinished. 
I used the exe file from my ForzaHor3 project (which has EagleDeb in its drop down list) - view link in my sig - 
to create H2O files from Vulture-I0-00000000.dat then hex2obj-024d (menu File/SaveAs Mmesh) to get obj files.

Most of them are not valid (-> .objx) but some work:



Vulture-I0-00000000_dat-red.jpg (216.69 KiB) Viewed 248 times

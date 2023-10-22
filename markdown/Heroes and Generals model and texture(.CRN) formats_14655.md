## Post #1
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-20T17:16:17+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

I have been looking into extracting models from HoG, and since ninjaripper did not work, I have looked into the game files.
I have not yet figured out where the models are kept, and the game client is suspiciously small, but I have located the textures, which seem to in .crn format.
Now I do not know much about cracking texture formats. Actually, I do not know anything about it. So I thought to ask here, since someone might be able to help me.

Here is a sample:
[http://www.mediafire.com/download/3fgq9 ... _02A_D.crn](http://www.mediafire.com/download/3fgq9vz79z2470i/Submachine_Gun_GM_02A_D.crn)
## Post #2
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2016-07-20T18:53:14+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

Already here: [viewtopic.php?f=16&t=12721](http://forum.xentax.com/viewtopic.php?f=16&t=12721)
## Post #3
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-20T19:02:27+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

Oh. I do not know how I missed that.
This is helpful, but there's still the issue of the models.
## Post #4
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-22T12:59:03+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

Here's a sample of a .bin file. Any clues how to open it?
[1d8aabe33ad4d49956a34f1f9c21423e.rar](https://xentaxbackup.github.io/file/11329_1d8aabe33ad4d49956a34f1f9c21423e.rar)
## Post #5
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-07-25T00:13:44+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

So far, still no luck with rippers. Anyone got better luck with the file I posted?
## Post #6
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-08-08T10:35:38+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

This time I posted a larger sample:
[http://www.mediafire.com/download/6y24g ... sample.rar](http://www.mediafire.com/download/6y24gnjb1yh54ar/sample.rar)
## Post #7
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-10-22T23:48:36+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

Sorry for necroing, but anyone found anything?
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-23T00:54:06+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

> Reply from Portugalotaku
>
> http://www.mediafire.com/download/6y24g ... sample.rar
the bin is zlib compressed, the first byte was a hint, use offzip to extract 00000000.dat from it  

```
offzip -a c5531570cd93ce62402a65fedcb2cde9.bin c:\offzip
```

How to recognize the compression algorithms with your eyes
[http://zenhax.com/viewtopic.php?t=27](http://zenhax.com/viewtopic.php?t=27)

then you can parse the mesh inside the dat, first submesh here



00000002_dat.png (39.51 KiB) Viewed 414 times
## Post #9
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2016-10-26T10:05:13+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

Oh nice! You think extracting models from those files is viable?
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-11-15T02:56:40+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

of course! you can use Hex2obj to get the meshes but would no doubt be easier with a script or tool
## Post #11
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-01-19T16:10:46+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

So how exactly do I open these files? Sorry, I just have no clue how to use this hex thingies.

And for some bizarre reason ninjaripper does not work for me in this game, so I cannot use that.
## Post #12
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-05T11:44:46+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

So can you tell me the hex2obj process you used on this mesh?
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-05T18:33:37+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

its all in the image, the offsets and counts and settings, you can start
learning it by using the same sample i did above, just dive in man!
## Post #14
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-06T13:30:11+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

It worked, but how do I do this on other models?
## Post #15
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-08T13:47:01+00:00
- Post Title: Heroes and Generals model and texture(.CRN) formats

I mean it worked on that one model, but not any others.
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-08T18:52:50+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

and what did you learn from the first model?
## Post #17
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-08T20:32:11+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

Basically nothing....
This is so completely beyond me it's not even funny. I am considering offering payment for someone who can make me a max/blender script for these models.
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-09T03:53:58+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

well until you get those scripts here is a Noesis python script to open your sample  
*updated Feb 16, 2017*


 fmt_HeroesandGenerals_dat.zip
(1.01 KiB) Downloaded 89 times


supports geometry and UVs
## Post #19
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-09T12:06:28+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

Thanks. It does not work on any other DAT files, but it seems to have opened more than hex2obj could. 
Now I just need to find someone willing to expand on this that doesn't bankrupt me :V
## Post #20
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-09T12:22:25+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

Here's another sample:
[http://www.mediafire.com/file/b3ewjsd10 ... 000000.dat](http://www.mediafire.com/file/b3ewjsd101wm1wa/00000000.dat)

If anyone is interested in making a noesis/maxscript/blender script for this, state your price.
## Post #21
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-09T18:56:38+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

no idea what that sample is, it looks like it has compressed data to me
## Post #22
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-09T19:50:22+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

I used offzip like you told me to.
## Post #23
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-13T13:59:04+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

Anyone interested?
## Post #24
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-13T21:10:30+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

i updated the script here
[viewtopic.php?p=127424#p127424](http://forum.xentax.com/viewtopic.php?p=127424#p127424)
to work with your sample here too
[viewtopic.php?p=120589#p120589](http://forum.xentax.com/viewtopic.php?p=120589#p120589)

 

> Reply from Portugalotaku
>
> It does not work on any other DAT files..
you have to upload some not-working samples to expand support
## Post #25
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-14T01:08:22+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

Thank you so much man, you are a lifesaver.

I updated sample.rar with 4 files I could not open.

[http://www.mediafire.com/file/6y24gnjb1 ... sample.rar](http://www.mediafire.com/file/6y24gnjb1yh54ar/sample.rar)
## Post #26
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-15T02:10:47+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

i got it working with your new samples but i need to see
this sample again to make sure i didn't break something   
c5531570cd93ce62402a65fedcb2cde9.bin
## Post #27
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-15T11:59:11+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

I cannot find this file anymore, it seems it was renamed in an update....
## Post #28
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-02-16T05:24:40+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

okay then, i have done all i can, i updated the script to open your other samples   
[viewtopic.php?p=127424#p127424](http://forum.xentax.com/viewtopic.php?p=127424#p127424)
## Post #29
- Username: medwed
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Sep 03, 2010 3:45 pm
- Post datetime: 2017-02-16T19:17:13+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

hex2obj. for me it is black magic.Too stupid I am for it
## Post #30
- Username: Portugalotaku
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Fri Oct 02, 2015 10:35 pm
- Post datetime: 2017-02-16T22:24:06+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

You are a God among men. I cannot thank you enough for this.

Most files work now, with a few still not opening. Like you predicted, the first file no longer opens, and while I dont have the bin anymore, I still have a copy of DAT file extracted with offzip. Trenches.dat is the name.

Updated sample with all non-opening files and trenches.dat

[http://www.mediafire.com/file/6y24gnjb1 ... sample.rar](http://www.mediafire.com/file/6y24gnjb1yh54ar/sample.rar)

Now to see if I can find what I am looking for in this giant mess of files.
## Post #31
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-04-02T03:19:16+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

here is a better way to decompress your bin samples in batch with a bms script  

```

comtype zlib_noerror
get ZSIZE asize
math SIZE = ZSIZE
get NAME basename
string NAME + ".dat"
clog NAME 0 ZSIZE SIZE
```

i'd like to phase out using offzip for decompressing in batch because of the naming conflict hurdle you have to leap over.
## Post #32
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2017-08-27T19:37:52+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

> Reply from AceWell
>
> here is a better way to decompress your bin samples in batch with a bms script  
Code: Select allcomtype zlib_noerror
get ZSIZE asize
math SIZE = ZSIZE
get NAME basename
string NAME + ".dat"
clog NAME 0 ZSIZE SIZE
i'd like to phase out using offzip for decompressing in batch because of the naming conflict hurdle you have to leap over.

How to use it? man do a tutorial!
## Post #33
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-27T23:27:08+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

its a script for QuickBMS, copy it to a text file then download Quickbms and run it and follow the on-screen prompts   
[http://aluigi.altervista.org/quickbms.htm](http://aluigi.altervista.org/quickbms.htm)
## Post #34
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2017-08-28T14:22:28+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

> Reply from AceWell
>
> its a script for QuickBMS, copy it to a text file then download Quickbms and run it and follow the on-screen prompts   
http://aluigi.altervista.org/quickbms.htm

I did it, it gave me a .Dat file, what now?  

I opened with noesis, doesn't work 

SOMEONE HELP ME PLEASE
## Post #35
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2017-09-27T13:52:06+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

> Reply from AceWell
>
> its a script for QuickBMS, copy it to a text file then download Quickbms and run it and follow the on-screen prompts   
http://aluigi.altervista.org/quickbms.htm

nobody wants to help me?
## Post #36
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-27T14:35:23+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

> Reply from ALIEN31ITA
>
> 
I did it, it gave me a .Dat file, what now?  

I opened with noesis, doesn't workHow do you think that Noesis would support Heroes and Generals?
Do you have a Noesis .py script for that?
Only supported .dat I see is for Bayonetta.

Also .dat output from a quickbms script is a general naming, iirc.
It could also be named .bin, .raw, whatever.

The .dat is easy to track using hex2obj (view link in my sig):



f8abe_40e97.jpg (189.54 KiB) Viewed 167 times

(first submesh only)
## Post #37
- Username: ALIEN31ITA
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Mar 15, 2017 11:59 pm
- Post datetime: 2017-09-28T19:12:56+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

> Reply from shakotay2
>
> ALIEN31ITA wrote:
I did it, it gave me a .Dat file, what now?  

I opened with noesis, doesn't work How do you think that Noesis would support Heroes and Generals?
Do you have a Noesis .py script for that?
Only supported .dat I see is for Bayonetta.

Also .dat output from a quickbms script is a general naming, iirc.
It could also be named .bin, .raw, whatever.

The .dat is easy to track using hex2obj (view link in my sig):
f8abe_40e97.jpg(first submesh only)

Strange, your software doesn't work for me, (windows 10)
## Post #38
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-09-28T19:39:56+00:00
- Post Title: Re: Heroes and Generals model and texture(.CRN) formats

You're probably missing libgcc_s_dw2-1.dll from hex2obj_0.24c.zip in the Extracting simple models thread.

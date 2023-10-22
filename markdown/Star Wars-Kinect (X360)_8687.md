## Post #1
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-04T01:00:54+00:00
- Post Title: Star Wars-Kinect (X360)

Hello all,

Does anyone know anything about this archive format?

Star Wars Kinect 

Developer: Terminal Reality

Sample:
[http://www.sendspace.com/file/9nwv9p](http://www.sendspace.com/file/9nwv9p)

Smaller sample:
[http://www.sendspace.com/file/wya3ha](http://www.sendspace.com/file/wya3ha)

Here's how the ISO directory looks:




I'm trying to unpack the art resources from the proper archive, but can't seem to find which archive is which.

Edit:Updated links to smaller PODLZX file.
## Post #2
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-04T01:41:37+00:00
- Post Title: Star Wars-Kinect (X360)

nxeart it's XBOX PIRS archive. Use wxPirs for extract

[http://img27.imageshack.us/img27/438/pirs.png](http://img27.imageshack.us/img27/438/pirs.png)

here extracted

[http://img834.imageshack.us/img834/1244/nxeslot.jpg](http://img834.imageshack.us/img834/1244/nxeslot.jpg)
[http://img4.imageshack.us/img4/807/nxebg.jpg](http://img4.imageshack.us/img4/807/nxebg.jpg)
## Post #3
- Username: AlphaTwentyThree
- Rank: double-veteran
- Number of posts: 982
- Joined date: Tue Aug 25, 2009 5:55 am
- Post datetime: 2012-04-04T04:24:34+00:00
- Post Title: Star Wars-Kinect (X360)

For the pod files, use my script: [viewtopic.php?f=13&p=70398#p70398](http://forum.xentax.com/viewtopic.php?f=13&p=70398#p70398)
## Post #4
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2012-04-04T06:20:00+00:00
- Post Title: Star Wars-Kinect (X360)

any change of extracting the models and textures?, cause this game has some good models. i wont ask about a max script or converter yet since we haven't got around to extracting the models yet unless i missed something
## Post #5
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-04T14:47:03+00:00
- Post Title: Star Wars-Kinect (X360)

> Reply from Ekey
>
> nxeart it's XBOX PIRS archive. Use wxPirs for extract

http://img27.imageshack.us/img27/438/pirs.png

here extracted

http://img834.imageshack.us/img834/1244/nxeslot.jpg
http://img4.imageshack.us/img4/807/nxebg.jpg
Thanks for clarifying this archive. I was looking for 3D models and such.
## Post #6
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-04T14:52:30+00:00
- Post Title: Star Wars-Kinect (X360)

> Reply from AlphaTwentyThree
>
> For the pod files, use my script: viewtopic.php?f=13&p=70398#p70398
Many thanks, your script worked great. All .pod files have been unpacked successfully. As I suspected, they contained bnk, bik, pkg, and wem files. I think thats video, sound, cinematics, and possibly 3D models.
## Post #7
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-04T14:54:30+00:00
- Post Title: Star Wars-Kinect (X360)

> Reply from JakeGreen
>
> any change of extracting the models and textures?, cause this game has some good models. i wont ask about a max script or converter yet since we haven't got around to extracting the models yet unless i missed something
I'm analyzing the PKG files now, I think they are either the 3D model format or cinematics. I know another game used PKG for their model format.
## Post #8
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2012-04-04T14:54:47+00:00
- Post Title: Star Wars-Kinect (X360)

> Reply from mazor
>
> Thanks for clarifying this archive. I was looking for 3D models and such.
So try to use script by AlphaTwentyThree to unpack POD files. I'm not sure that the script will work with the files PODLZX

> Reply from AlphaTwentyThree
>
> use my script: viewtopic.php?f=13&p=70398#p70398
## Post #9
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-04T14:57:43+00:00
- Post Title: Star Wars-Kinect (X360)

> Reply from Ekey
>
> mazor wrote:Thanks for clarifying this archive. I was looking for 3D models and such.
So try to use script by AlphaTwentyThree to unpack POD files. I'm not sure that the script will work with the files PODLZX
AlphaTwentyThree wrote:use my script: viewtopic.php?f=13&p=70398#p70398
AlphaTwentyThree's script worked on the POD files, but didn't do the trick for the PODLZX. I'm curious about whats archived in the PODLZX file. They are the largest files on the disk by far.
## Post #10
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-05T04:27:42+00:00
- Post Title: Star Wars-Kinect (X360)

Having taken a closer look at the contents of the POD archives, it appears that the 3D data must be located in the PODLZX files. I assume the PODLZX format is similar to the before mentioned POD, but is compressed with an LZX algorithm. This compression I believe is used in the compression of XBOX 360 avatars. Furthermore, the PODLZX format must be investigated in greater depth before the final verdict is given. 

Any assistance would be much appreciated.
## Post #11
- Username: mazor
- Rank: advanced
- Number of posts: 44
- Joined date: Wed Jun 08, 2011 4:22 am
- Post datetime: 2012-04-05T12:16:57+00:00
- Post Title: Star Wars-Kinect (X360)

Uploaded smaller PODLZX file for convenience. I have suspicion that 3D data is located specifically in XB2PKGART.PODLZX or such.
[http://www.sendspace.com/file/wya3ha](http://www.sendspace.com/file/wya3ha)
## Post #12
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2015-06-19T01:59:17+00:00
- Post Title: Star Wars-Kinect (X360)

Sorry for asking here, but does anybody know what the file or archive format that holds the sound files is? I want to help somebody extract the sound effects for video projects and whatnot. Any help would be appreciated.
## Post #13
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-06-19T06:08:27+00:00
- Post Title: Star Wars-Kinect (X360)

Your looking for xb2pkgsnd.POD for the sound effects.
## Post #14
- Username: ARAJediMaster
- Rank: beginner
- Number of posts: 29
- Joined date: Fri Jun 12, 2015 12:17 pm
- Post datetime: 2015-06-19T13:38:09+00:00
- Post Title: Star Wars-Kinect (X360)

> Reply from durandal217
>
> Your looking for xb2pkgsnd.POD for the sound effects.
Thank you.

Is there a way to extract the sound files from those files?
## Post #15
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-06-20T03:57:33+00:00
- Post Title: Star Wars-Kinect (X360)

You use XBdecompress to uncompress the POD file then use the .pod bms script to unpack the contents. Then you use Xmash to extract the XMA stream from the BNK container and use towav to convert from xma to wav. 

All of these tool can be easily found.
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-06-28T02:19:11+00:00
- Post Title: Re: Star Wars-Kinect (X360)

> Reply from durandal217
>
> You use XBdecompress to uncompress the POD file then use the .pod bms script to unpack the contents. Then you use Xmash to extract the XMA stream from the BNK container and use towav to convert from xma to wav.
xb2pkgsnd.POD has no Xbox compression. Alpha23's POD script extracts the bnk files perfectly, but this is where the trail ends for me. Xmash 0.8 only extracts a bunch of bin files of which only 1 is said to be a successful WWise, even this file is no good and will not convert with towav. I tried bnkextr with the /swap switch and it produced a bunch of wav files identical to the bin files extracted by Xmash. What is the correct way to convert the bnk files to something playable?
## Post #17
- Username: durandal217
- Rank: veteran
- Number of posts: 95
- Joined date: Tue Jul 17, 2012 10:52 am
- Post datetime: 2015-06-28T22:56:47+00:00
- Post Title: Re: Star Wars-Kinect (X360)

it's been awhile since I extracted the sounds, if those two didn't work, just take the .bnk and drag and drop it into ToWav it should convert it, it wasn't really difficult. 

If that doesn't do it than use Alpha 23's XMA script.
## Post #18
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2015-06-29T04:37:11+00:00
- Post Title: Re: Star Wars-Kinect (X360)

Ok thanks, this works
extract the bnk files from the .POD file with Alph23's POD archive extractor
use Xmash to extract bin files from the bnk files*
use Alpha23's XMA transform script on the bin files
convert the xma files to wav with ToWav

*You could also use bnkextr with the /swap switch to extract files from the bnk files, they will just be wav instead of bin.

[POD archive extractor](http://forum.xentax.com/viewtopic.php?f=13&p=74993#p74993)
[Xmash](http://www.hcs64.com/vgm_ripping.html) / [bnkextr](http://www.hcs64.com/mboard/forum.php?showthread=40224)
[XMA transform](http://forum.xentax.com/viewtopic.php?f=17&t=9023)
[ToWav](http://www.ctpax-x.org/?goto=files&show=24)

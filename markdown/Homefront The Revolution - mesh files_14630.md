## Post #1
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-11T15:40:55+00:00
- Post Title: Homefront: The Revolution - mesh files

apparently, m0xf released an archive extractor for the .pak files,
which can be found here:

[viewtopic.php?f=10&p=120289#p120289](http://forum.xentax.com/viewtopic.php?f=10&p=120289#p120289)

however, since the game is using a modified version of the CryEngine, 
obviously none of the files are readable yet.
for whoever is interested in that file format, here's some sample files
from the game. including static meshes, as well as rigged ones.
another thing i noticed, none of the .dds files seem to be readable.
*.dds.0 file missing? Crysis, Ryse, Evolve etc. at least seem to have these.

so everything in that package is how the extractor spits them out.

Sample:
[HF2_SF.7z](http://www.file-upload.net/download-11757546/HF2_SF.7z.html)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-07-11T23:36:46+00:00
- Post Title: Homefront: The Revolution - mesh files

binocular.cgfm  



binocular_cgfm.png (42.93 KiB) Viewed 905 times




the vertex and face counts are 16 bytes before their start address
the dds textures are split up into separate parts like the header (unnumbered), the main image data (highest numbered) and the mipmaps
## Post #3
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-12T10:10:07+00:00
- Post Title: Homefront: The Revolution - mesh files

I tried my script for Ryse and got models with weights and bones, I suggest you to use this script, in the Ryse thread - should work!

[viewtopic.php?f=16&t=12085&start=60](http://forum.xentax.com/viewtopic.php?f=16&t=12085&start=60)
## Post #4
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-12T10:40:04+00:00
- Post Title: Homefront: The Revolution - mesh files

i must be blind and can't find a script there, uploaded by you. only marius' head file.
if you mean joqqys script, i iwll try that.

well, there is one in my scripts folder already, which is called "Ryse_Son_of_Rome_Fix.ms"
(3DSMax 2014) but it's giving me an error with all files i tried so far:
"undefined in Typ: Integer64"
downloaded from here:
[viewtopic.php?f=16&t=12252](http://forum.xentax.com/viewtopic.php?f=16&t=12252)
so is there even another version, which i've overseen?

will static meshes work? i love these urban props!
okay, obviously it's for skinned meshes only, as you described.
## Post #5
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-12T12:43:09+00:00
- Post Title: Homefront: The Revolution - mesh files

It's not hard to make static objects work, I would take a look at Revolution more detailed, but since format is almost the same as Ryse (and there's another scripter who did big job making a tool), I think, you should contact him and send some samples, if he will say, that he's not interested in supporting Homefront I will share maxscript for model import.
## Post #6
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-12T12:46:25+00:00
- Post Title: Homefront: The Revolution - mesh files

thank you!
i've asked here.
[viewtopic.php?f=16&t=12085&start=60](http://forum.xentax.com/viewtopic.php?f=16&t=12085&start=60)
## Post #7
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-07-22T11:05:31+00:00
- Post Title: Homefront: The Revolution - mesh files

> Reply from TheMask85
>
> thank you!
i've asked here.
viewtopic.php?f=16&t=12085&start=60

Hi,
I took a quick look at the samples you provided yesterday, and there should be no problem adding support for Homefront - The Revolution
see videolinks:
[https://youtu.be/0QS4BqBO_bw](https://youtu.be/0QS4BqBO_bw)
[https://youtu.be/ej_fJCHVCwM](https://youtu.be/ej_fJCHVCwM)

It is a slightly(I think) modified version of the CryEngine.
I will have to examine the format a bit more to add all of the support that it needs.

[EDIT] As for Wolcen, I do not have the game, and would need samples of that in case you are still interested.
## Post #8
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-22T16:00:24+00:00
- Post Title: Homefront: The Revolution - mesh files

this is great news! is support for skinned meshes also planned?
i still can't find that certain script, Zaramot mentioned.
as for Wolcen, i tried to unpack .pak files. but seems to be decrypted.
## Post #9
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-07-22T16:25:56+00:00
- Post Title: Homefront: The Revolution - mesh files

> Reply from TheMask85
>
> this is great news! is support for skinned meshes also planned?
i still can't find that certain script, Zaramot mentioned.
as for Wolcen, i tried to unpack .pak files. but seems to be decrypted.

Yes, I plan to support the skinned meshes as well - the skinned meshes  and skeletons actually work as well - same support as for Ryse, but I have to take a closer look at the Homefront format too see just how much modification has been made.
Zaramot provided you a link I believe.
## Post #10
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-22T17:27:09+00:00
- Post Title: Homefront: The Revolution - mesh files

> Reply from joqqy
>
> 
Zaramot provided you a link I believe.

> Reply from zaramot
>
> I tried MY script for Ryse

yes. but the link is leading to the thread, where YOUR (joqqy) script can be found.
sorry, if i get confused easily.
## Post #11
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-07-22T17:47:15+00:00
- Post Title: Homefront: The Revolution - mesh files

> Reply from TheMask85
>
> joqqy wrote:
Zaramot provided you a link I believe.
zaramot wrote:I tried MY script for Ryse

yes. but the link is leading to the thread, where YOUR (joqqy) script can be found.
sorry, if i get confused easily.

You are right, I think this is the correct link
[viewtopic.php?f=16&t=12252](http://forum.xentax.com/viewtopic.php?f=16&t=12252)
## Post #12
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-22T18:01:39+00:00
- Post Title: Homefront: The Revolution - mesh files

> Reply from joqqy
>
> TheMask85 wrote:joqqy wrote:
Zaramot provided you a link I believe.
zaramot wrote:I tried MY script for Ryse

yes. but the link is leading to the thread, where YOUR (joqqy) script can be found.
sorry, if i get confused easily.

You are right, I think this is the correct link
viewtopic.php?f=16&t=12252

yes, i have also tried that one. 3DSMax 2014 and 2017. 
it does not work with Homefront 2 files.
## Post #13
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2016-07-22T19:10:09+00:00
- Post Title: Homefront: The Revolution - mesh files

You shouldn't be too much confused and blame yourself, I have edited, a bit improved script for CryTek models (like I have for many other games), especially for Ryse - it's not the same script I posted earlier, old one will not work. I just reported, that format is almost the same and suggested you to contact  Joqqy  Just I didn't explain this detailed like I should, sorry xD
## Post #14
- Username: TheMask85
- Rank: veteran
- Number of posts: 80
- Joined date: Sun May 19, 2013 7:55 am
- Post datetime: 2016-07-22T19:35:37+00:00
- Post Title: Homefront: The Revolution - mesh files

thank you guys!
i will let this thread rest and just wait patiently to see if one of you will upload something.
## Post #15
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-07-23T22:18:53+00:00
- Post Title: Homefront: The Revolution - mesh files

> Reply from TheMask85
>
> this is great news! is support for skinned meshes also planned?

Nearly done for the support for Homefront 2, you can see some progress of the skinned meshes in the video link.
The modifications of the engine seems to be trivial.

[https://youtu.be/e6-WCZxAuNQ](https://youtu.be/e6-WCZxAuNQ)

/joq
## Post #16
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-07-25T21:23:04+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

There is is basic support for HFR now.
(Choose "HFR" from the CryEngine Game dropdown list)

For bug reporting, you can contact me here or in a private message.

To extend the support for more sophisticated features, I would need to take a look at the full game (for example, I would need to look at the resource lists for assets and textures, and additional info), and probably will - if I get the game.

Update: bug fix - get the new file

/joq
[CryImport.7z](https://xentaxbackup.github.io/file/11431_CryImport.7z)
## Post #17
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-08-02T17:53:47+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Some extended support is added.

Better skin support
Support for .cga .cgam
Option to choose a custom temporary database/resource (see video links)
Better material support
and more...
[https://youtu.be/_PSirm9uXP4](https://youtu.be/_PSirm9uXP4)
[https://youtu.be/DpLlE_iZ3yA](https://youtu.be/DpLlE_iZ3yA)
[https://youtu.be/yTk9YwUzR5c](https://youtu.be/yTk9YwUzR5c)

Images:
[http://imgur.com/a/eLCGu](http://imgur.com/a/eLCGu)
[CryImport.7z](https://xentaxbackup.github.io/file/11469_CryImport.7z)
## Post #18
- Username: redbluwtf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 03, 2016 1:01 am
- Post datetime: 2016-08-02T20:27:27+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

@joqqy Good Job!, please bro create cabal2 importer .chr + .caf [Cryengine], 
I would appreciate it very much

here sample files:

[http://www.mediafire.com/download/4g16v ... cabal2.zip](http://www.mediafire.com/download/4g16vsbdb44iir5/sample_cabal2.zip)
## Post #19
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-08-02T21:50:06+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

> Reply from redbluwtf
>
> @joqqy Good Job!, please bro create cabal2 importer .chr + .caf [Cryengine], 
I would appreciate it very much

here sample files:

http://www.mediafire.com/download/4g16v ... cabal2.zip

I tested your sample .chr
See videolink:
[https://youtu.be/YE-j5nqCua8](https://youtu.be/YE-j5nqCua8)

Now there are probably some issues with skin mirroring etc but I am not sure, since I haven't done any research on Cabal 2.
But as of now, .chr seems to load, but probably needs some tweaking.

Until (and if ) I look at Cabal 2 as far as .caf is concerned, you can try it out using this script:
[CryImport.7z](https://xentaxbackup.github.io/file/11459_CryImport.7z)
## Post #20
- Username: redbluwtf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 03, 2016 1:01 am
- Post datetime: 2016-08-02T22:18:51+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

yes work, but i need animations
## Post #21
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-08-02T22:25:49+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

> Reply from redbluwtf
>
> yes work, but i need animations

I plan to support animation, but, that is further down the road, and unfortunately, I cannot give an ETA on that.
## Post #22
- Username: redbluwtf
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Jul 03, 2016 1:01 am
- Post datetime: 2016-08-02T23:26:48+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Great job with Cryimporter, Look forward to support animation
## Post #23
- Username: joqqy
- Rank: advanced
- Number of posts: 51
- Joined date: Tue Feb 21, 2012 7:40 pm
- Post datetime: 2016-08-07T19:18:54+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Update now supports:

Vertex Normals and Vertex Colors
Support added for XML format in addition to Binary XML
Better Character support

As a side note, I also added support for "Armored Warfare"

Lots of bugfixes...

[https://youtu.be/rRKiApNdzrs](https://youtu.be/rRKiApNdzrs)
[CryImport.7z](https://xentaxbackup.github.io/file/11534_CryImport.7z)
## Post #24
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2016-08-24T14:38:47+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Hey guys! I've just installed 3ds Max 2017 and tried running your script but get this error... any idea what I might be doing wrong? Dying to play with some of these models!



Capture.JPG (19.47 KiB) Viewed 433 times
## Post #25
- Username: ClubOn
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 05, 2016 1:26 am
- Post datetime: 2016-09-19T19:51:22+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

> Reply from joqqy
>
> Update now supports:

Vertex Normals and Vertex Colors
Support added for XML format in addition to Binary XML
Better Character support

As a side note, I also added support for "Armored Warfare"

Lots of bugfixes...

https://youtu.be/rRKiApNdzrs

Hi joggy, great work you done with this script... One question, it is possible export animations from HFR with your max script ? and apply them to the characters like UEviewer script ?
## Post #26
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-04-05T00:05:24+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Hey joqqy,

I tried your last script after finally being able to extract the game files from Homefront, sadly though i can't seem to get anything imported correctly, when i try to do the same import as you did
in the video it only imports the head without any assigned materials, also on most cdfs i get a texture i/o error, Anything that i am missing?
## Post #27
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-05T05:34:36+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

I was actually thinking about this just the other day -- was there ever any progress in regards to bones?
## Post #28
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-11T02:16:43+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Okay, so I've gone back and had a look through things and got the importer to work, but for some reason I can't get textures to work. I've used HxD to combine the first and last dds files (the standard .dds and the .dds.7) files...



 ...and then converted them to TGA files. When I apply the texture, it looks like this...


head.JPG (46.92 KiB) Viewed 267 times



Anyone able to figure out what's going wrong? The UV's all seem to be offset a little, but I'm not sure if that's something that's going wrong in the process or not.
## Post #29
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-11T09:32:11+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Hey! You guys could try my script for this game. It's not very pleasant for common users, though you should have a bit better luck with it



Some guide: if folder/character have head/face.cgf, at first import head.cgf (bones will be with correct hierarchy). So, if there's head.cgf import (choose) this file twice - to get rigged head. Import head.cgf first and any other .skinm of this character - this will get you rigged parts of him/her. And if there's no head.cgf then just import .skin - .skinm (always) and if there's only one .skin file and no .skinm with same name near - import .skin file twice. I disabled materials on purpose, since in many cases, if not most it will make more troubles than help, though I didn't have any troubles finding textures, so I'm sure no one should have them too xD
[Homefront_Revolution.7z](https://xentaxbackup.github.io/file/15321_Homefront_Revolution.7z)
## Post #30
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2017-04-11T14:10:16+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Damn, dude! Happy to see you are still alive!!  
Thanks! Glad to see some support's come through for this after all this time!  Spent the whole day getting everything out of this with the other script, but am curious to see which makes things easier! Hope you are well!
## Post #31
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-11T15:13:33+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Yeah, lets hope it will help you more or less:) Though, don't expect much - I haven't tried hard with this one, since joqqy's tool should be in all means superior xD
## Post #32
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2017-04-12T13:46:49+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Hey zaramot,

Thanks for this script, tried to use it on a few meshes but i always get this error:

-- Error occurred in anonymous codeblock; filename: E:\Temp\hf_script\Homefront_Revolution.ms; position: 38512; line: 1739
-- MAXScript FileIn Exception:
-- No ""+"" function for undefined
-- MAXScript callstack:

Using Max 2017, any idea why this happens?
## Post #33
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-04-12T14:30:15+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

You need older version - from 2011 to 2014, haven't tested it in 2015 but shouldn't be problem, though most likely in 2016-2017 it will not work at all. To be sure attach one model you tried, I will check it on my end (don't have the game and I can't test it out well myself)
## Post #34
- Username: junk angel
- Rank: veteran
- Number of posts: 82
- Joined date: Thu Jan 14, 2010 11:38 pm
- Post datetime: 2017-12-10T19:41:14+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

> Reply from zaramot
>
> You need older version - from 2011 to 2014, haven't tested it in 2015 but shouldn't be problem, though most likely in 2016-2017 it will not work at all. To be sure attach one model you tried, I will check it on my end (don't have the game and I can't test it out well myself)
Hi, 
I've tested it on 2011 and it generally works without issues. Where I seem to get the -- no ""+"" function defined error is whenever I encounter a model which does not have a skinm. As instructed opening the .skin twice, but it fails.

Interestingly the model also seems to have also the following
kpa_sniper_a.cdf
kpa_sniper_a.fxl
kpa_sniper_a.mtl
kpa_sniper_a.skin
## Post #35
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2017-12-10T19:47:53+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

Need to take a look at those files. If you could upload them, maybe I'll be able to solve the problem xD
## Post #36
- Username: UberBlack
- Rank: advanced
- Number of posts: 44
- Joined date: Fri Oct 23, 2009 3:54 am
- Post datetime: 2017-12-30T08:26:57+00:00
- Post Title: Re: Homefront: The Revolution - mesh files

I will try with 3DSMax 2018 and let you know.. Also animation would be awesome for Ryse & Crysis.
The source code has been released from Crytek, which should make it easier to integrate in your tool.
Really looking for animation. Great job!!

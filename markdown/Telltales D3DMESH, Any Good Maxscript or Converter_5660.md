## Post #1
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2010-12-28T23:41:47+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

Hi folks, just wondering if anyone knew about importing 3D3MESH from telltale into 3ds max. Anyone also know a good extraction for the textures? Any help is appreciated!
## Post #2
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-29T12:08:00+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

> Reply from Trancelikestate
>
> Hi folks, just wondering if anyone knew about importing 3D3MESH from telltale into 3ds max. Anyone also know a good extraction for the textures? Any help is appreciated!

 Aluigi's ttarch extractor tool will get the textures (converted to dds) using -m option    [viewtopic.php?f=10&t=3254&p=46619#p46619](http://forum.xentax.com/viewtopic.php?f=10&t=3254&p=46619#p46619) 

So like you, i'm trying to find a way to ger the D3DMesh files into 3dsmax (or blender, or milkshape. Preferably 3dsmax    )
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-29T12:15:21+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

How can anyone help without samples.
## Post #4
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-29T13:08:18+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

> Reply from chrrox
>
> How can anyone help without samples.

I guess that would be helpful! Duh...

[BTTF Samples](http://www.highendgames.net/Lee/bttf_samples.rar)

Sample animation, character, object
## Post #5
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2010-12-29T14:36:39+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

Yeah, i got all the files out of the archive using aluigi's extractor, but i didn't know it would automatically convert the textures. Thanks! And definatly lets find a way to import these models! 

Edit: Hang on, i used the -m option. I guess i've just never heard of dds.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-29T15:23:33+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

sorry 3d models will not be happening atleast from me.
They are using the same 3d format they always use.
I can read everything except faces.
Someone would need to reverse engineer what they are doing because they hide them purposely.
## Post #7
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2010-12-29T15:27:40+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

I figured as much. That sucks. Has anyone ever extracted a model successfully from a TT game? 

Also SLIFallen, I only see the tool which changes the font and or translates it. How are you getting these textures?
## Post #8
- Username: SLIFallen
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Sep 28, 2010 11:26 pm
- Post datetime: 2010-12-29T16:24:52+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

> Reply from Trancelikestate
>
> I figured as much. That sucks. Has anyone ever extracted a model successfully from a TT game? 

Also SLIFallen, I only see the tool which changes the font and or translates it. How are you getting these textures?

Ummm..you said it yourself: -m option. Converts them to dds.

Like so: ttarchext.exe -m 41 "C:\Your game folder location\4_BackToTheFuture101_pc_tx.ttarch" c:\your extract folder location\4_BackToTheFuture101_pc_tx 

Wala!
## Post #9
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-12-29T16:55:17+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

I'm also interested in this.

On the Facepunch forums of Garry's Mod someone converted Strong Bad and Tycho from Poker Night at the Inventory.
But I can't ask how he did it, I can't post there because the email after registration doesn't work and it's not getting fixd.
Here's the thread in case anyone wants to/can ask there: [http://www.facepunch.com/threads/103515 ... Strong-Bad](http://www.facepunch.com/threads/1035157-Tycho-and-Strong-Bad)
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-12-29T17:12:15+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

you could use 3d ripper dx
## Post #11
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2010-12-29T17:18:08+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

Please forgive me as this technique is new to me. How might one accomplish this? I have never used a 3d ripper. You simply download the program and follow tutorials?
## Post #12
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-12-29T17:36:23+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

> Reply from chrrox
>
> you could use 3d ripper dx

Didn't work for me when I tried to get the Guybrush model from Tales Of Monkey Island. =/
## Post #13
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2010-12-29T19:59:36+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

I tried just now and all it does is crash the game.
## Post #14
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-29T21:37:52+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

> Reply from chrrox
>
> How can anyone help without samples.

chrrox I have here $100dlls its not mutch but i am greath fan of saint seiya series, i have 2 options pay you for a script to import the models with textures in max or donate to xentax or pay a external coder to make one scrypt,  i really love this series and search this models by 4 years.

Tread with files format samples, fatduck tell me he not have pc just now but he advance on this investigation

[viewtopic.php?f=16&t=5525](http://forum.xentax.com/viewtopic.php?f=16&t=5525)
## Post #15
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2011-01-04T00:28:38+00:00
- Post Title: Telltales D3DMESH, Any Good Maxscript or Converter?

A question:

I immediately suspect the reason the game crashes during a 3d rip is because it's an obvious safeguard put in place to prevent exactly this type of thing. Would it be possible to hack the exe to bypass it? Is that a breach of the forum rules to ask? Forgive me, i'm a new blood.
## Post #16
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2011-01-06T19:33:29+00:00
- Post Title: Re: Telltales D3DMESH, Any Good Maxscript or Converter?

actually quite a few games crash when using DXripper and it is MAINLY down to the software protection, but there are other things that come into play as well. system specs play a part, the gfx cards capability mainly, the better your gfx card the more data you can capture, if that amount of data is too much for the rest of the system that can also crash the game ( ive also had it crash the computer ) what i mean is, i used to have a nvidia 7600 and could rip from test drive unlimited, it would capture the car and about 100meters of landscape with it. when i upgraded my card it would capture the car and what looked like  about a mile of landscape and it would often crash my game/ pc coz the rest of my system couldn't handle that much data. Once i upgraded the rest of my system i didn't have anywhere near as many problems. 
but as someone said software protection is one of the biggest causes, there are ways around a lot of that tho. Now im not advocating everyone to go and steal ( so mods/admins please don't ban me for saying this ) but pirate software usually works much better. As the software protections have mainly been removed ( esp in cases of steam games ) a cracked steam game is usually " de-steamed" and ripping becomes a lot easier then.  it wont fix every thing every time, but i have a lot more dxripping success with cracked games than store bought ones.
## Post #17
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2011-01-06T19:48:46+00:00
- Post Title: Re: Telltales D3DMESH, Any Good Maxscript or Converter?

Thanks for the advice, that had occurred to me actually. I don't think it's the computer cuz I have used it to rip models before. Also the game loads up, it says ready to capture, and only crashes when it's activated. Plus it is a legitamtly purchased version. If I get any results I'll post them.
## Post #18
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2011-01-07T17:58:53+00:00
- Post Title: Re: Telltales D3DMESH, Any Good Maxscript or Converter?

Ok so for the record that doesn't work. It did get the textures but no models.
## Post #19
- Username: Trancelikestate
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Dec 25, 2010 11:57 pm
- Post datetime: 2011-02-19T19:04:32+00:00
- Post Title: Re: Telltales D3DMESH, Any Good Maxscript or Converter?

So totally my bad. i did not have the latest version of the 3d ripper. After updating, it works like a charm. i recommend it.

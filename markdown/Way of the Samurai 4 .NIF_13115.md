## Post #1
- Username: kazumaru
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 18, 2015 9:55 pm
- Post datetime: 2015-07-26T02:11:08+00:00
- Post Title: Way of the Samurai 4 .NIF

The .nif files for Way of the Samurai 4 aren't loading in 3ds max, nifskope or noesis

in nifskope there's a msg
""version 30.1.0.3 (30.1.0.3) is not supported yet"" 
""failed to load file header (version 1e010003, 30.1.0.3)"" 
"failed to load nif from 'C:/Steam/steamapps/common/Way of the Samurai 4/Common/Character/Model/Pack/DLCDona01_af.nif'" 

The textures are stuck in these nif files as well, anyone mind taking a look at these?

[http://sta.sh/0lqodmrflq2](http://sta.sh/0lqodmrflq2)
## Post #2
- Username: kazumaru
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 18, 2015 9:55 pm
- Post datetime: 2015-07-26T06:26:31+00:00
- Post Title: Way of the Samurai 4 .NIF

ohhh seems they can be exported :v

but the textures come out weird, the bump maps are normal though
[chonin01_niftex_9.png](https://xentaxbackup.github.io/file/9458_chonin01_niftex_9.png)
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-07-26T09:40:00+00:00
- Post Title: Way of the Samurai 4 .NIF

Those textures are so-called "shader masks", where you take just one color channel and multiply it by a color. I remember it being used in Street Fighter X Tekken, Soul Calibur V and a bunch of other games, but I haven't found any good explanation of them.
## Post #4
- Username: locakert22
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Mar 28, 2011 9:47 pm
- Post datetime: 2015-07-28T18:55:05+00:00
- Post Title: Way of the Samurai 4 .NIF

> Reply from kazumaru
>
> ohhh seems they can be exported :v

but the textures come out weird, the bump maps are normal though

How do i extract .NIF files?
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-29T07:26:16+00:00
- Post Title: Way of the Samurai 4 .NIF

did you try Rick's fmt_gamebryo_nif.py?

For some models patching might be required but I get some oddities:



DLCDona01.JPG (47.54 KiB) Viewed 350 times
## Post #6
- Username: locakert22
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Mar 28, 2011 9:47 pm
- Post datetime: 2015-07-29T08:31:46+00:00
- Post Title: Way of the Samurai 4 .NIF

> Reply from shakotay2
>
> did you try Rick's fmt_gamebryo_nif.py?

For some models patching might be required but I get some oddities:
DLCDona01.JPG

How to extract and archive  NIF from the file?
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-29T08:58:24+00:00
- Post Title: Way of the Samurai 4 .NIF

1) what exactly do you mean by "extract"?

> Reply from locakert22
>
> How to extract and archive  NIF from the file?2) which file?
3) what does that mean "archive  NIF from the file"? Never heard such thing.

what I have is a rar file from the opening post with DLCDona01_af.nif contained

The nif contains the mesh and textures which can be extracted (mesh to obj, texture to png) using the (patched) python file (.py) I mentioned before with Noesis.
## Post #8
- Username: locakert22
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Mar 28, 2011 9:47 pm
- Post datetime: 2015-07-29T18:28:02+00:00
- Post Title: Way of the Samurai 4 .NIF

> Reply from shakotay2
>
> 1) what exactly do you mean by "extract"?



.

sorry

I can't extract these .nif files.    
thank you
## Post #9
- Username: kazumaru
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Jun 18, 2015 9:55 pm
- Post datetime: 2015-07-31T00:41:17+00:00
- Post Title: Way of the Samurai 4 .NIF

Well I got something something going so far, but the NIF's with full body bones are bugged.

Maybe a script or something to pack these files back up into the nifs, for retextures and other things :v
## Post #10
- Username: ngovandang
- Rank: veteran
- Number of posts: 121
- Joined date: Sun Aug 10, 2014 5:33 pm
- Post datetime: 2017-10-31T04:38:38+00:00
- Post Title: Way of the Samurai 4 .NIF

How did you extract diffuse maps?
## Post #11
- Username: hodlersho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 13, 2018 2:34 am
- Post datetime: 2018-02-12T18:38:59+00:00
- Post Title: Way of the Samurai 4 .NIF

Hello there!
Noob reporting in...

Ok, this is my first time ever trying to extract models. How did kazumaru managed to extract / view the model with textures applied?

What I got so far using Noesis:

(It extracts the FBX thart I need and some DDS maps but no texture.

I managed to get it working but headless and no texture hehehe
## Post #12
- Username: hodlersho
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Feb 13, 2018 2:34 am
- Post datetime: 2018-02-12T21:12:22+00:00
- Post Title: Way of the Samurai 4 .NIF

Ok I get it.

This model that looks good is a Event Scene model with no bones, it is looking perfect to me. But the Character models are fd up...
It seems to be duplicating some stuff and miss placing their heads into their stomach   

Please someone give me some advice hehehe

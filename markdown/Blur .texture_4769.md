## Post #1
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-07-19T18:38:15+00:00
- Post Title: Blur .texture

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2010-08-13T16:38:26+00:00
- Post Title: Blur .texture

I think i can. gimme some minutes.

Okay, im not sure if the colors are right though, but atleast its viewable.
[s10.texture3234b.jpg](https://xentaxbackup.github.io/file/3318_s10.texture3234b.jpg)
## Post #3
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-09T16:07:31+00:00
- Post Title: Blur .texture

> Reply from Strobe
>
> I think i can. gimme some minutes.

Okay, im not sure if the colors are right though, but atleast its viewable.
OMG, how you can do this?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-12T02:54:34+00:00
- Post Title: Blur .texture

yeah the colors are off here is what it should look like.
## Post #5
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-12T05:04:18+00:00
- Post Title: Blur .texture

.texture is just a dds file without the header I suppose, isn't it?
## Post #6
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-12T13:37:56+00:00
- Post Title: Blur .texture

2chrrox
So how did you manage to find this. I'm very interesting in this
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-12T21:06:55+00:00
- Post Title: Blur .texture

Just paste a valid dds header on the image.
a dds header is 0x80 bytes
this header ends 8 bytes after the word DXT5
## Post #8
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-15T11:33:13+00:00
- Post Title: Blur .texture

> Reply from chrrox
>
> Just paste a valid dds header on the image.
a dds header is 0x80 bytes
this header ends 8 bytes after the word DXT5
I attached [files](http://www.sendspace.com/file/iu80w4) (my new and original).
Every time i'm trying to paste right (i think) header. I always get something strange. So tell me what i'm doing wrong.
[hf03.jpg](https://xentaxbackup.github.io/file/3445_hf03.jpg)
## Post #9
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-15T12:03:34+00:00
- Post Title: Blur .texture

You used wrong DDS header, and the dimensions are also wrong.

Create a dds file with 2048x512 dimensions, and DXT5 No mipmap compression, and paste the header.
## Post #10
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-15T12:08:57+00:00
- Post Title: Blur .texture

> Reply from evin
>
> You used wrong DDS header, and the dimensions are also wrong.

Create a dds file with 2048x512 dimensions, and DXT5 No mipmap compression, and paste the header.
Thank you. Now everything is work. But how can i guess what size each image? 

And i get images like in firs Strobe post. Mess colors.
## Post #11
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-15T12:16:42+00:00
- Post Title: Blur .texture

If the color is wrong, you leaved some non-image data after the header, and the image data is shifted. Or if you deleted too much data.

Image size:
offset38: 4byte width, 4byte height (00080000 00020000)
## Post #12
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-15T12:20:51+00:00
- Post Title: Blur .texture

> Reply from evin
>
> If the color is wrong, you leaved some non-image data after the header, and the image data is shifted. Or if you deleted too much data.

Image size:
offset38: 4byte width, 4byte height (00080000 00020000)
Can you explain more simple and maybe with sample?. I'm not understand
## Post #13
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-15T12:38:06+00:00
- Post Title: Blur .texture

Which part?
## Post #14
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-15T13:05:00+00:00
- Post Title: Blur .texture

> Reply from evin
>
> Image size:
offset38: 4byte width, 4byte height (00080000 00020000)in here.
Maybe if you explain or show to me samples how should looks like header of the file i can use this to convert other image.
## Post #15
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-15T13:17:28+00:00
- Post Title: Blur .texture

There is you file, f01c.texture. If you open it to read in hex view (or with hex editor), left side you can see a counter. These are the offset values. At the offset 38(hex) begin the width and the height data.
[blur_tex.jpg](https://xentaxbackup.github.io/file/3446_blur_tex.jpg)
## Post #16
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-15T13:38:15+00:00
- Post Title: Re: Blur .texture

> Reply from evin
>
> There is you file, f01c.texture. If you open it to read in hex view (or with hex editor), left side you can see a counter. These are the offset values. At the offset 38(hex) begin the width and the height data.
Ok, thanks to you i found this part, finaly  How i can use this info to get right colors?
[01.jpg](https://xentaxbackup.github.io/file/3447_01.jpg)
## Post #17
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-15T13:43:10+00:00
- Post Title: Re: Blur .texture

The .texture header is 84 byte big (54h). If you delete exactly this part, no more or less, the color will be ok.
## Post #18
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-15T14:18:26+00:00
- Post Title: Re: Blur .texture

> Reply from evin
>
> The .texture header is 84 byte big (54h). If you delete exactly this part, no more or less, the color will be ok.
sorry   but i'm not understand which part i must delete and which part i must replace with dds-header.
## Post #19
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-15T17:14:40+00:00
- Post Title: Re: Blur .texture

If you deleted the first 84 byte from the beginning of the .texture, just paste the first 128 byte from the dds to the beginning of the .texture.
## Post #20
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-18T01:30:15+00:00
- Post Title: Re: Blur .texture

I've got the same problems with colors.
I created a new DXT5 DDS using Photoshop DDS plugin and moved its header to the .texture file.
But I hadn't gotten the right colors.
Could anyone give me the right header and explain which bytes are responsible for colors?
I've almost done the converter and it's the only problem I haven't solved.
## Post #21
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-18T18:51:06+00:00
- Post Title: Re: Blur .texture

Here is my test batch converter.
It'll be in test status until I solve color problems with DXT5.
DXT1 converting is fine (I think so  )
[Blur_Texture_Converter_v1.0.zip (with sources in Delphi)](http://www.mediafire.com/?qfh9f6684bbweo6)
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-09-18T19:28:39+00:00
- Post Title: Re: Blur .texture

> Reply from RoadTrain
>
> Here is my test batch converter.
It'll be in test status until I solve color problems with DXT5.
DXT1 converting is fine (I think so  )
Blur_Texture_Converter_v1.0.zip (with sources in Delphi)
Thanks  I try your program on several files, works great.
## Post #23
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-19T02:53:28+00:00
- Post Title: Re: Blur .texture

> Reply from Tosyk
>
> RoadTrain wrote:Here is my test batch converter.
It'll be in test status until I solve color problems with DXT5.
DXT1 converting is fine (I think so  )
Blur_Texture_Converter_v1.0.zip (with sources in Delphi)
Thanks  I try your program on several files, works great.
Ok. But the color problem with sky textures (DXT5) remained. I hope anyone will help me with it and I'll update this tool.
## Post #24
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-20T08:29:42+00:00
- Post Title: Re: Blur .texture

Upload an unhandled dxt5 file, because your program works fine with Tosyk's f01c.texture file, which is a dxt5 file.
## Post #25
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-20T15:21:51+00:00
- Post Title: Re: Blur .texture

The contents of this post was deleted because of possible forum rules violation.
## Post #26
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-20T18:35:08+00:00
- Post Title: Re: Blur .texture

Don't as what I did.  I just pasted one of my dds header sample, and it's worked.
[dds_header.zip](https://xentaxbackup.github.io/file/3461_dds_header.zip)
## Post #27
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-20T20:20:53+00:00
- Post Title: Re: Blur .texture

> Reply from evin
>
> Don't as what I did.  I just pasted one of my dds header sample, and it's worked.
When using this header I get the same colors as in the second post.
But I need to get colors as in the fourth post.
## Post #28
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-09-20T22:31:22+00:00
- Post Title: Re: Blur .texture

use a different program to view the dds files i looked at the texture you posted and it looks fine.
## Post #29
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-21T06:53:26+00:00
- Post Title: Re: Blur .texture

> Reply from RoadTrain
>
> When using this header I get the same colors as in the second post.
But I need to get colors as in the fourth post.

Your dds file is wrong. But with my header the new dds is fine in Photoshop and Xnview.
Try to generate a new header with these data: DXT5, Mipmap 1
## Post #30
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-21T18:59:31+00:00
- Post Title: Re: Blur .texture

I'm confused.
Here is what I get with dds header provided by evin.
[](http://radikal.ru/F/s04.radikal.ru/i177/1009/fa/d59f978475a6.png.html)

I doubt that it's what it should look like.
## Post #31
- Username: Evin
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Sat Aug 05, 2006 9:04 pm
- Post datetime: 2010-09-22T07:01:37+00:00
- Post Title: Re: Blur .texture

I think this is a good image (sunset?). But if you find more image like this, we/you can be sure.
## Post #32
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2010-09-22T09:41:34+00:00
- Post Title: Re: Blur .texture

> Reply from evin
>
> I think this is a good image (sunset?). But if you find more image like this, we/you can be sure.
I supposed that this image should look like in [chrrox post](http://img823.imageshack.us/img823/6448/test55.png).
E.g. I'm not sure that hf10 should really look like that
[](http://radikal.ru/F/s03.radikal.ru/i176/1009/19/9327edcc0d6f.png.html)
## Post #33
- Username: JGZinv
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Apr 06, 2011 11:44 am
- Post datetime: 2011-04-06T05:53:06+00:00
- Post Title: Re: Blur .texture

As I mention over in the .model thread, you can get textures out with 3D Ripper DX 1.8 or later.
1.8 seems to do a better job than 1.8.1 unfortunately.

The problem actually is that we need a utility or something to repack them into Blur, then we'd
be in good shape as to car or level texture modification.
## Post #34
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2020-08-16T03:20:42+00:00
- Post Title: Re: Blur .texture

> Reply from Tosyk ↑Sun Sep 19, 2010 3:28 am at Sun Sep 19, 2010 3:28 am
>
> 
RoadTrain wrote:Here is my test batch converter.
It'll be in test status until I solve color problems with DXT5.
DXT1 converting is fine (I think so  )
Blur_Texture_Converter_v1.0.zip (with sources in Delphi)
Thanks  I try your program on several files, works great.

Hey bro could you please give me a link for the converter 
Blur_texture_converter.zip
The link you provided is no longer work. 
Thank you.
## Post #35
- Username: RoadTrain
- Rank: advanced
- Number of posts: 54
- Joined date: Thu Dec 13, 2007 12:57 am
- Post datetime: 2020-08-16T16:43:22+00:00
- Post Title: Re: Blur .texture

> Reply from rkthelegend ↑Sun Aug 16, 2020 11:20 am at Sun Aug 16, 2020 11:20 am
>
> 
Tosyk wrote: ↑Sun Sep 19, 2010 3:28 am
RoadTrain wrote:Here is my test batch converter.
It'll be in test status until I solve color problems with DXT5.
DXT1 converting is fine (I think so  )
Blur_Texture_Converter_v1.0.zip (with sources in Delphi)
Thanks  I try your program on several files, works great.


Hey bro could you please give me a link for the converter 
Blur_texture_converter.zip
The link you provided is no longer work. 
Thank you.

Man you are lucky!
Still got that stuff after 10 years   
[https://yadi.sk/d/KNmR1ZVne6Gx_w](https://yadi.sk/d/KNmR1ZVne6Gx_w)
## Post #36
- Username: Rkpaarsa
- Rank: beginner
- Number of posts: 38
- Joined date: Wed Jun 20, 2018 11:58 pm
- Post datetime: 2020-08-16T19:31:40+00:00
- Post Title: Re: Blur .texture

> Reply from RoadTrain ↑Mon Aug 17, 2020 12:43 am at Mon Aug 17, 2020 12:43 am
>
> 
rkthelegend wrote: ↑Sun Aug 16, 2020 11:20 am
Tosyk wrote: ↑Sun Sep 19, 2010 3:28 am

Thanks  I try your program on several files, works great.


Hey bro could you please give me a link for the converter 
Blur_texture_converter.zip
The link you provided is no longer work. 
Thank you.


Man you are lucky!
Still got that stuff after 10 years   
https://yadi.sk/d/KNmR1ZVne6Gx_w

Thank you very much and could you please give some information on how to reimport those texture back to pak file?
i unpacked the root.pak using bms script from alugi but seems it can not reimport.
as i tried many times i found that the file root.pak is a compressed archive and i dont know how to decompress it.
help?

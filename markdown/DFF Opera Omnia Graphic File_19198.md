## Post #1
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-16T11:31:21+00:00
- Post Title: DFF Opera Omnia Graphic File

Help   
How to open the g1t files with Noesis? I tried to open it with KaizokuMusou3, Atelier Firis, Attack on Titan script but it just gave an error.

These are the files after I extract with quickbms.
[http://www.mediafire.com/file/n7gzfc19q ... 4.g1t/file](http://www.mediafire.com/file/n7gzfc19q1m4u98/stl_weapon_equipment_0004.g1t/file)
[http://www.mediafire.com/file/elhl1199i ... 1.g1t/file](http://www.mediafire.com/file/elhl1199iycvy4d/stl_mon_face_0621.g1t/file)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-16T11:45:07+00:00
- Post Title: DFF Opera Omnia Graphic File

my "Dissidia Opera Omnia" Noesis python script here opens your samples.   
[viewtopic.php?p=137208#p137208](http://forum.xentax.com/viewtopic.php?p=137208#p137208)

i guess i should rename it "Dissidia Final Fantasy: Opera Omnia"
## Post #3
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-16T13:04:39+00:00
- Post Title: DFF Opera Omnia Graphic File

> Reply from Acewell
>
> my "Dissidia Opera Omnia" Noesis python script here opens your samples.   
viewtopic.php?p=137208#p137208

i guess i should rename it "Dissidia Final Fantasy: Opera Omnia"

Oh, wow. Thank you sooooo much.   

I can't open this g1t [https://www.mediafire.com/file/4w9tdca0 ... 3.rar/file](https://www.mediafire.com/file/4w9tdca05t0i13s/MessageImage0003.rar/file)

Now, I want to view the 3D model but got an error   

I include all the files, that's all I have for the same character code. Is it possible to open the model with Noesis?
[http://www.mediafire.com/file/n18k1wb1n ... 0.rar/file](http://www.mediafire.com/file/n18k1wb1n2r0159/10.rar/file)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-17T04:55:01+00:00
- Post Title: DFF Opera Omnia Graphic File

> Reply from flay
>
> I can't open this g1t https://www.mediafire.com/file/4w9tdca0 ... 3.rar/file
okay i updated the Noesis python script here to support your rgb565 sample   
[viewtopic.php?p=137208#p137208](http://forum.xentax.com/viewtopic.php?p=137208#p137208)

i don't deal with the models, you have to create new thread in 3d model section.
## Post #5
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-17T17:07:52+00:00
- Post Title: DFF Opera Omnia Graphic File

> Reply from Acewell
>
> flay wrote:I can't open this g1t https://www.mediafire.com/file/4w9tdca0 ... 3.rar/file
okay i updated the Noesis python script here to support your rgb565 sample   
viewtopic.php?p=137208#p137208

i don't deal with the models, you have to create new thread in 3d model section.

Thank you so much. You're awesome
## Post #6
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-19T19:52:52+00:00
- Post Title: DFF Opera Omnia Graphic File

Sorry to bother you again, I can't view this g1t. Looks like a texture? Can't even get the correct colors after extract.

[https://www.mediafire.com/file/3won5ea2 ... x.rar/file](https://www.mediafire.com/file/3won5ea2w89966c/tex.rar/file)
[https://www.mediafire.com/file/uo4f6unz ... e.rar/file](https://www.mediafire.com/file/uo4f6unzlkcqqbz/te.rar/file)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-20T06:46:33+00:00
- Post Title: DFF Opera Omnia Graphic File

those are etc1 compressed and are not supported directly by Noesis except by using 3rd party tools.   
you will have to use PVRTexTool to convert the image data to usable formats until i work out solution.

your CT_0005.g1t sample contains 1 256x256 image in 2 parts
first part is the rgb data then the alpha data

your CT_011401.g1t sample contains 3 512x512 images each in 2 parts
image 1:
rgb data
alpha data

image2:
rgb data
alpha data

image3:
rgb data
alpha data

the offsets in the header don't make sense to me though.
## Post #8
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-20T12:14:00+00:00
- Post Title: DFF Opera Omnia Graphic File

> Reply from Acewell
>
> those are etc1 compressed and are not supported directly by Noesis except by using 3rd party tools.   
you will have to use PVRTexTool to convert the image data to usable formats until i work out solution.

your CT_0005.g1t sample contains 1 256x256 image in 2 parts
first part is the rgb data then the alpha data

your CT_011401.g1t sample contains 3 512x512 images each in 2 parts
image 1:
rgb data
alpha data

image2:
rgb data
alpha data

image3:
rgb data
alpha data

the offsets in the header don't make sense to me though.

I don't understand too
## Post #9
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-21T18:22:44+00:00
- Post Title: DFF Opera Omnia Graphic File

Could you take a look at this file?

[https://www.mediafire.com/file/4i4fh0z6 ... h.rar/file](https://www.mediafire.com/file/4i4fh0z6iaxbajb/stch.rar/file)
[https://www.mediafire.com/file/152qzaw3 ... d.rar/file](https://www.mediafire.com/file/152qzaw333xkgai/fld.rar/file)
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-12-21T21:13:40+00:00
- Post Title: DFF Opera Omnia Graphic File

more of the same, all etc1
fld.g1t has one 2048x2048 image
stch.g1t has one 256x256 image
stchr.g1t has one 256x256 image
## Post #11
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2018-12-22T12:24:11+00:00
- Post Title: DFF Opera Omnia Graphic File

What would I do without you....   

[https://www.mediafire.com/file/yzdau98j ... l.rar/file](https://www.mediafire.com/file/yzdau98jhb51a29/fl.rar/file)
## Post #12
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2019-01-01T07:50:04+00:00
- Post Title: DFF Opera Omnia Graphic File

Can you display what textures have you managed to rip so far?
## Post #13
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-01-17T06:06:48+00:00
- Post Title: DFF Opera Omnia Graphic File

> you will have to use PVRTexTool to convert the image data to usable formats until i work out solution.
okay solution found, download the updated script and the PVRTEXTool4Noesis.zip here   
[viewtopic.php?f=18&t=17558&p=137208#p137208](http://forum.xentax.com/viewtopic.php?f=18&t=17558&p=137208#p137208)
follow the instructions in the post.

i think i'm done with this script now, it worked on all samples i tried except one,
your CT_011401.g1t sample contains 3 images but the second one is missing a header
and this throws off the stored offset of the third one. nothing i can do with it script
wise because it breaks the structure and i see no flags indicating any of this.
## Post #14
- Username: flay
- Rank: n00b
- Number of posts: 19
- Joined date: Sat Dec 15, 2018 11:59 pm
- Post datetime: 2019-01-23T20:45:58+00:00
- Post Title: DFF Opera Omnia Graphic File

> Reply from kinlyki
>
> Can you display what textures have you managed to rip so far?

This for example...But I don't understand to apply the textures to the model.....  
[gs.jpg](https://xentaxbackup.github.io/file/15559_gs.jpg)
## Post #15
- Username: kinlyki
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Jun 21, 2015 12:36 am
- Post datetime: 2019-01-27T13:00:12+00:00
- Post Title: DFF Opera Omnia Graphic File

> Reply from flay
>
> kinlyki wrote:Can you display what textures have you managed to rip so far?

This for example...But I don't understand to apply the textures to the model.....
I can't even find the character and weapon textures. Are they actually in the apk? Or is there something else I am missing.
## Post #16
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2019-01-29T07:44:20+00:00
- Post Title: Re: DFF Opera Omnia Graphic File

They won't be in the apk, you have to have the game installed and then get the cache files that download when you start up the game.

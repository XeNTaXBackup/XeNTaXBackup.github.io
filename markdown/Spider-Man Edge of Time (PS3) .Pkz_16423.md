## Post #1
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-06-19T18:29:00+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

Greetings everyone,i'll would like to extract models & textures from console exclusive game called "Spider-Man : Edge of Time" .
I downloaded a PS3 version of the game,extracted several game files and used chroxx's script on them,it worked,and i was able to view some textures through TextureFinder 
[http://i.imgur.com/qriuEeL.jpg](http://i.imgur.com/qriuEeL.jpg)
[http://i.imgur.com/RDfxI9W.jpg](http://i.imgur.com/RDfxI9W.jpg)
Now i need to know how to extract meshes (and properly extract textures,if this possible)
Ps3 pkz samples in case if anyone want take a look :
[https://mega.nz/#!esBwVSKR!daGdjn7e2qS7 ... tTndmRxNuw](https://mega.nz/#!esBwVSKR!daGdjn7e2qS7Ix7UjU1u_nOszqgXzAQq4tTndmRxNuw)
Thanks in advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-21T19:16:35+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

(upps, wrong thread, sry)
## Post #3
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-06-23T08:11:04+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

> Reply from shakotay2
>
> here you go:
Cos_Cnct00_01-msb.jpg(uvs format may be word/shorts)
I tried vaules on your screenshot with BossAntiVenom.pkz.ext  file (opening gallery.pkz shows me an error message [http://i.imgur.com/J6qbQcJ.png](http://i.imgur.com/J6qbQcJ.png) ) but they are doesn't work..
"Vertex count must be set to maxFaceIndex"
Thanks
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-25T06:49:31+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

> Reply from Rutabaga
>
> I tried vaules on your screenshot with BossAntiVenom.pkz.ext  file (opening gallery.pkz shows me an error message http://i.imgur.com/J6qbQcJ.png ) but they are doesn't work..
"Vertex count must be set to maxFaceIndex"
thats because he posted an image of a sample for a different game from a different thread, this one
[viewtopic.php?p=131537#p131537](http://forum.xentax.com/viewtopic.php?p=131537#p131537)
just a little mixup i presume   

i already looked at your samples and they are too chaotic for my experience level in regards to proper extraction.  
i have nothing more to add here, maybe aluigi will have better luck?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-26T15:15:30+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

Whoever made that script, did it wrong. Files are corrupted after extraction. Though, after 10 minutes I was able to correct the data and here is that BossAntiVenom or something. It can NOT be extracted with hex2obj, i had to write a tool for that.
## Post #6
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-26T20:04:00+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

Bones and weights also working
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-06-27T02:57:14+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

> Reply from daemon1
>
> Whoever made that script, did it wrong. Files are corrupted after extraction.
> Reply from Rutabaga
>
> extracted several game files, used chroxx's script on them
there's your hint   
which parts are corrupt? the texture data at least looks ok to me   

@Rutabaga
can you upload some original pkz archives, i am curious to see what they look like before running that bms script on them
## Post #8
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-27T06:22:19+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

> Reply from AceWell
>
> the texture data at least looks ok to me

No, textures are also corrupted. There are extra bytes all around the whole file, which must not be there.
## Post #9
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-06-27T08:04:23+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

> Reply from daemon1
>
> Whoever made that script, did it wrong. Files are corrupted after extraction. Though, after 10 minutes I was able to correct the data and here is that BossAntiVenom or something. It can NOT be extracted with hex2obj, i had to write a tool for that.
Firstly Spider-Man 3 and now Spider-Man EoT,collection of extractable spider-man games are growing   
Thanks a lot man,you are awesome!

> Reply from AceWell
>
> 
@Rutabaga
can you upload some original pkz archives, i am curious to see what they look like before running that bms script on them
Ok,here you go:
[https://mega.nz/#!j8ZnUJpI!FregGgOSki7s ... CnSwaFxhc4](https://mega.nz/#!j8ZnUJpI!FregGgOSki7sdW_e4QmiQV0RWwy0QA_xYCnSwaFxhc4)
Archive have sample files from PS3 and Xbox 360 versions (just in case)
## Post #10
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-27T13:02:44+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

> Reply from Rutabaga
>
> Archive have sample files from PS3 and Xbox 360 versions (just in case)

Thanks! I finally have correct files and all the data is perfect! Now I can make a tool.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-29T14:34:06+00:00
- Post Title: Spider-Man: Edge of Time (PS3) .Pkz

Tool posted here:

[viewtopic.php?f=16&t=16471](http://forum.xentax.com/viewtopic.php?f=16&t=16471)

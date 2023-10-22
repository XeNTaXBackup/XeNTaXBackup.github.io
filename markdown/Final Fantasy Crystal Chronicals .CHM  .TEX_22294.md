## Post #1
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2020-06-18T11:58:42+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

Hey guys, I'm hoping someone can take a look into this game and come up with a quick noesis script for the models / textures. This is a great game and with the release of the remaster in a few months I'd love to have this collection.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1sLbno6wPvHL-odx_spJkGgU48OMgdtZe?usp=sharing)

I've uploaded samples to my Drive account, and hopefully we can get the ball rolling on this.

Thanks
## Post #2
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2020-06-21T01:01:44+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

Bumping this thread, in the hopes of getting a reply
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-06-21T01:53:05+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

> Reply from Ecelon ↑Thu Jun 18, 2020 7:58 pm at Thu Jun 18, 2020 7:58 pm
>
> 
Hey guys, I'm hoping someone can take a look into this game and come up with a quick noesis script for the ... textures.
here is Noesis python script to open your *.tex samples.  


 tex_FinalFantasyCrystalChronicals_GC_tex.zip
(1.33 KiB) Downloaded 25 times


thanks to Zheneq for the nintendo texture library and Allen for one of his streamlined scripts i used as template.
## Post #4
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2020-06-22T02:01:26+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

> Reply from Acewell ↑Sun Jun 21, 2020 9:53 am at Sun Jun 21, 2020 9:53 am
>
> 
Ecelon wrote: ↑Thu Jun 18, 2020 7:58 pm
Hey guys, I'm hoping someone can take a look into this game and come up with a quick noesis script for the ... textures.
here is Noesis python script to open your *.tex samples.   
tex_FinalFantasyCrystalChronicals_GC_tex.zip
thanks to Zheneq for the nintendo texture library and Allen for one of his streamlined scripts i used as template.

Thannk you so much Ace mate. That's so cool. Thanks too Zheneq and Allen Ace well <<< See what I did there.  . Hopefully someone can work on the meshes in the future though!
## Post #5
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2020-06-22T03:37:25+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

I don't know how to read the faces.



c200_root.chm.png (24.65 KiB) Viewed 172 times
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-06-22T06:37:53+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

> Reply from reh ↑Mon Jun 22, 2020 11:37 am at Mon Jun 22, 2020 11:37 am
>
> I don't know how to read the faces.Me, too.  Another annoying puzzle:
Skipping each 2nd row doesn't help. Odd and even counter columns.

address 0x5010 (c100_root.chm):
    3   247   248   249    15   206     1   250 
   15   207     1   251    15   208     1   252 
   15   209     1   253    16   210     1   254 
   16   211     1   255     4   212     1   256 
   16   213     1   257     4   214     1   258 
   16   215     1   259    15   216     1   260 
   15   217     1   261    15   218     1   262 
   15   219     1   263    16   220     1   264 
   16   221     1   265     4   222     1   266 
    4   223     1   267    16   224     1   268 
   16   225     1   269    17   226     1   270 
   17   227     1   271    17   228     1   272 
   17   229     1   273    17   230     1   274 
   17   231     1   275    17   232     1   276 
   17   233     1   277    18   234     1   278 
   18   235     1   279    18   236     1   280 
address 0x5110:
   18   237     1   281    18   238     1   282 
   18   239     1   283    18   240     1   284 
   18   241     1   285    18   242     1   286 
   18   243     1   287    18   244     1   288 
   18   245     1   289    18   246     1   290 
   18   247     1   291    18   248     1   292 
   18   249     1   293     0   250     1   294 
    0   251     1   295     0   252     1   296 
    1   253     1   297     1   254     1   298 
    1   255     1   299     1   256     1   300 
    1   257     1   301     0   258     1   302 
    0   259     1   303     0   260     1   304 
    1   261     1   305     1   262     1   306 
    1   263     1   307     1   264     1   308 
    1   265     1   309     1   266     1   310 
    0   267     1   311     4   268     1   312

----------------------------------------------------

maybe just another rule for creating face indices?
a=548, b=500
f 548 500 549   a   b a+1
f 501 550 502   b+1 a+2 b+2

then a += 3, b += 3
551 503 552
504 553 505
and so on
## Post #7
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2020-06-23T00:18:55+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

> Reply from reh ↑Mon Jun 22, 2020 11:37 am at Mon Jun 22, 2020 11:37 am
>
> 
I don't know how to read the faces.
c200_root.chm.png

Nicely done mate, that's awesome. It sucks that it's such a pain in the ass. Thanks for trying though.

> Reply from shakotay2 ↑Mon Jun 22, 2020 2:37 pm at Mon Jun 22, 2020 2:37 pm
>
> 
reh wrote: ↑Mon Jun 22, 2020 11:37 amI don't know how to read the faces.Me, too.  Another annoying puzzle:
Skipping each 2nd row doesn't help. Odd and even counter columns.

address 0x5010 (c100_root.chm):
    3   247   248   249    15   206     1   250 
   15   207     1   251    15   208     1   252 
   15   209     1   253    16   210     1   254 
   16   211     1   255     4   212     1   256 
   16   213     1   257     4   214     1   258 
   16   215     1   259    15   216     1   260 
   15   217     1   261    15   218     1   262 
   15   219     1   263    16   220     1   264 
   16   221     1   265     4   222     1   266 
    4   223     1   267    16   224     1   268 
   16   225     1   269    17   226     1   270 
   17   227     1   271    17   228     1   272 
   17   229     1   273    17   230     1   274 
   17   231     1   275    17   232     1   276 
   17   233     1   277    18   234     1   278 
   18   235     1   279    18   236     1   280 
address 0x5110:
   18   237     1   281    18   238     1   282 
   18   239     1   283    18   240     1   284 
   18   241     1   285    18   242     1   286 
   18   243     1   287    18   244     1   288 
   18   245     1   289    18   246     1   290 
   18   247     1   291    18   248     1   292 
   18   249     1   293     0   250     1   294 
    0   251     1   295     0   252     1   296 
    1   253     1   297     1   254     1   298 
    1   255     1   299     1   256     1   300 
    1   257     1   301     0   258     1   302 
    0   259     1   303     0   260     1   304 
    1   261     1   305     1   262     1   306 
    1   263     1   307     1   264     1   308 
    1   265     1   309     1   266     1   310 
    0   267     1   311     4   268     1   312

----------------------------------------------------

maybe just another rule for creating face indices?
a=548, b=500
f 548 500 549   a   b a+1
f 501 550 502   b+1 a+2 b+2

then a += 3, b += 3
551 503 552
504 553 505
and so on

Nice mate, thanks for the input. Wish the format was easier, but this is the hand we were dealt. Considering 3 of you guys had a look and it's a nightmare is disappointing, but it's awesome to know you guys gave it a go. Thanks!
## Post #8
- Username: darelf
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 01, 2023 4:25 am
- Post datetime: 2023-06-30T21:01:15+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

Hello reviving this thread because I'm looking to decompile FFCC and with the remaster it seems to be a lot easier, as it is made with Unity. Is anyone interested in doing this? we can make a group.
## Post #9
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2023-07-07T20:22:17+00:00
- Post Title: Final Fantasy: Crystal Chronicals .CHM / .TEX

Just download the APK(X) file, aproxamatly 2GB, extract it and see what you get by using the Unity Asset Studio



wireframe.png (167.73 KiB) Viewed 79 times

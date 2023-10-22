## Post #1
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2017-12-05T12:24:30+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

Hey,

I'm looking for an unpacker for DRIVECLUB.
This game has several .dat files in numerical order.
I uploaded a bunch of them (06, 08, 09) and a few unrelated files, in case there is some information there - I dont really know. lol
If more files are needed, let me know.

[https://drive.google.com/drive/u/2/fold ... T6nmhPpU9-](https://drive.google.com/drive/u/2/folders/1dcjCr-SkAcU-8lM06FswQKT6nmhPpU9-)

Thanks.


edit: if you want/need the decrypted files, PM me!
## Post #2
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2017-12-10T13:24:27+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

Same thing here !

I'm ready to start reversing cars/maps, but I will need an unpacker first.
## Post #3
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2017-12-10T14:43:47+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

[http://zenhax.com/viewtopic.php?f=9&t=7 ... a1d#p30525](http://zenhax.com/viewtopic.php?f=9&t=7036&sid=d56ba6f5e4268e27d774d6f3f400ea1d#p30525)

According to aluigi, it's a terrible format.
And he is THE quickBMS guy!
## Post #4
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2017-12-10T15:24:30+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

> Reply from lolwatt
>
> http://zenhax.com/viewtopic.php?f=9&t=7 ... a1d#p30525

According to aluigi, it's a terrible format.
And he is THE quickBMS guy!

Oh yeah, I just saw that.



But it seems we can already see and extract things manually after using this script.
## Post #5
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2017-12-10T15:46:00+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

Really?! I didn't even try that - he said it was useless. hahah 

If you have a Zenhax account, maybe you can keep him updated of what you are doing?
Maybe he will update for better compatibility.
## Post #6
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2017-12-10T15:54:24+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

> Reply from lolwatt
>
> Really?! I didn't even try that - he said it was useless. hahah 

If you have a Zenhax account, maybe you can keep him updated of what you are doing?
Maybe he will update for better compatibility.

yeah, that's what I did ;D
## Post #7
- Username: zaykho
- Rank: mega-veteran
- Number of posts: 217
- Joined date: Fri Dec 03, 2010 8:20 pm
- Post datetime: 2017-12-11T13:01:03+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

[](https://www.hostingpics.net/viewer.php?id=468968sfdsfsdf.png)
(^ using this host to avoid uploading big pictures)

So finally succeeded to output some 3D from Driveclub.

I took the game034_unpack.dat (I use the complete decompress .dat)

Then, vertices indices starting at 0x132DE, prior to that, at 0x132D8, 0C = 12 (will be the strip for the vertices).

The faces indices start at 0x3D35DD (I think).
## Post #8
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-05-21T12:48:17+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

any progress on this?
## Post #9
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2022-06-29T12:57:54+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

Hi all!
Hope someone can help me. I'm trying to extract models from Driveclub. While it is possible to get the model vertices, but it is not possible to extract the faces. It also looks like the model is initially flattened. I used 3D Model Researcher to view the models. Did anyone manage to fully extract the models from the game?
[https://imgur.com/UudumoQ.png](https://imgur.com/UudumoQ.png)
## Post #10
- Username: Nenkai
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Jul 30, 2016 7:29 am
- Post datetime: 2022-10-01T15:48:00+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

I have released an unpacker for .ndx/.dat files. It has been tested with 1.28.
It is unrelated to RPK/Resource Packs however, those are containers with all sorts of data.

[https://github.com/Nenkai/DriveClubFS](https://github.com/Nenkai/DriveClubFS)


Additionally i've figured and documented the RPK ToC.
[https://github.com/Nenkai/010GameTempla ... rcePack.bt](https://github.com/Nenkai/010GameTemplates/blob/main/Evolution%20Studios/RPK_ResourcePack.bt)
## Post #11
- Username: micro777
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Oct 01, 2018 5:57 am
- Post datetime: 2022-10-10T20:55:12+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

Nenkai,
Thank you so much for the tool!
Now you can start opening models. So far, here's what
## Post #12
- Username: centiousanomaly
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jul 15, 2021 2:12 am
- Post datetime: 2023-04-14T04:31:37+00:00
- Post Title: PS4 DRIVECLUB - dat - Unpacker needed

Would you be able to show me how you got to this stage?

> Reply from micro777 ↑Tue Oct 11, 2022 4:55 am at Tue Oct 11, 2022 4:55 am
>
> 
Nenkai,
Thank you so much for the tool!
Now you can start opening models. So far, here's what

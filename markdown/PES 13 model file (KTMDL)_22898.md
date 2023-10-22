## Post #1
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2020-10-25T04:51:31+00:00
- Post Title: PES 13 model file (KTMDL)

Can anyone help me to open or extract this 3d.bin model files. Please. theres only one tool but that can't open the files. Here is some samples.
[http://www.mediafire.com/file/hngbz9dt6 ... s.zip/file](http://www.mediafire.com/file/hngbz9dt673fqgr/bin_samples.zip/file)
## Post #2
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2020-10-25T09:19:14+00:00
- Post Title: PES 13 model file (KTMDL)

@Bigchillghost @Acewell mate please help me out with this. I'm trying to figure it out for years. Please take a look.
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-10-25T21:19:13+00:00
- Post Title: PES 13 model file (KTMDL)

Pro Evolution Soccer 2013 is it?
what platform does your samples comes from?
looks like a model followed by some rgba8888 texture



5Five_ballbin.png (73.65 KiB) Viewed 254 times



you can decompress the bin with this bms script:

```

get NAME basename
string NAME + _decmp.bin
getdstring MAGIC 8
get ZSIZE long
get SIZE long
clog NAME 0x10 ZSIZE SIZE
```



edit
i see you have a thread going on here too:
[https://zenhax.com/viewtopic.php?f=5&t=13747](https://zenhax.com/viewtopic.php?f=5&t=13747)
## Post #4
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2020-10-26T09:03:38+00:00
- Post Title: PES 13 model file (KTMDL)

After decompress how can i open them? I really don't konw how to use hex2obj. I'm a noob at it. There's a tool named "FEI 2010b" that can read and export models from .bin files to another format. But it can't open this samples. Truly it can't open moded files which i need Specially. But i need them to use in another game. So i want to extract the model. Please help me.
## Post #5
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2020-10-26T09:07:26+00:00
- Post Title: PES 13 model file (KTMDL)

Is there any noesis script that can save me?  Like you did last time.   or if you help me how to use hex2obj.
## Post #6
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2020-10-26T16:47:14+00:00
- Post Title: PES 13 model file (KTMDL)

Mate I did what you said. But why I'm getting uv and model into seperate obj? uv should be in the ball.obj file. But the uv map is in seperate file which is also a model without any uv map. What a mess!! what I'm doing wrong?
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-10-26T20:59:19+00:00
- Post Title: PES 13 model file (KTMDL)

> Reply from Mishuk598 ↑Tue Oct 27, 2020 12:47 am at Tue Oct 27, 2020 12:47 am
>
> why I'm getting uv and model into seperate obj? uv should be in the ball.obj file. But the uv map is in seperate file which is also a model without any uv map. what I'm doing wrong?
sounds like you using the test files and not exporting the obj, after you 
enter all values in Hex2obj you must export the obj with File>SaveAs mesh.
## Post #8
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2020-10-27T04:41:43+00:00
- Post Title: PES 13 model file (KTMDL)

But this values are not same for all bin files.  I can't understand the method.
## Post #9
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2021-02-21T04:27:28+00:00
- Post Title: PES 13 model file (KTMDL)

> Reply from Mishuk598 ↑Tue Oct 27, 2020 12:41 pm at Tue Oct 27, 2020 12:41 pm
>
> 
But this values are not same for all bin files.  I can't understand the method.

I made this simple python script that extracts the necessary info for hex2obj and Model Researcher.
You just need to have python installed, then you can just drag and drop the model file on the script and it will display the info in a console window.
[KTMDL_fix.zip](https://xentaxbackup.github.io/file/19577_KTMDL_fix.zip)
## Post #10
- Username: piratesephiroth
- Rank: beginner
- Number of posts: 29
- Joined date: Sun Nov 08, 2009 6:05 pm
- Post datetime: 2021-02-21T12:29:51+00:00
- Post Title: PES 13 model file (KTMDL)

I updated the KTMDL script.
Adjusted some stuff like the display in Python 2 and hope to have fixed the UV calculation.

Here's it working with a model from an unrelated Konami game (Harmony of Despair)
## Post #11
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2021-03-16T10:14:44+00:00
- Post Title: PES 13 model file (KTMDL)

Thanks my friend. I will check it soon.
## Post #12
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2021-03-26T12:21:20+00:00
- Post Title: PES 13 model file (KTMDL)

mate is it possible to get solid mesh from it?
File obj:[https://drive.google.com/file/d/1HlKps1 ... ADu1H/view](https://drive.google.com/file/d/1HlKps1PNBrXrzZWu9mEfq2yhZJAADu1H/view)
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-26T15:53:11+00:00
- Post Title: PES 13 model file (KTMDL)

You need to use triangle strips, mate, look here again:
.

> Reply from Acewell ↑Mon Oct 26, 2020 5:19 am at Mon Oct 26, 2020 5:19 am
>
> 

What me makes wonder what you're doing is this post of your own:

> Reply from Mishuk598 ↑Tue Oct 27, 2020 12:47 am at Tue Oct 27, 2020 12:47 am
>
> 
where you already had the correct mesh - so what?
## Post #14
- Username: Mishuk598
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Oct 21, 2020 5:22 pm
- Post datetime: 2021-04-17T04:33:02+00:00
- Post Title: PES 13 model file (KTMDL)

I can't make it use mate. 
When I use hex2obj I'm getting this triangle type( can't convert it to desired format because of the triangle type)
(But uv map is correct)

But when I use model researcher im getting proper mesh but the there's a big error with uv calculation.
## Post #15
- Username: Guti
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 10, 2020 10:41 am
- Post datetime: 2021-12-28T16:22:35+00:00
- Post Title: PES 13 model file (KTMDL)

maybe my message is too late. but with the faces and hair tool it can be opened.
[https://youtu.be/E1vQf5eZ2eo](https://youtu.be/E1vQf5eZ2eo)
Also fei_2010 opens balls
[https://www.moddingway.com/file/2608.html](https://www.moddingway.com/file/2608.html)

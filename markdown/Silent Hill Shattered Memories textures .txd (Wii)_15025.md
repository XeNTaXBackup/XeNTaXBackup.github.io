## Post #1
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2016-09-09T10:04:31+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

Hi everybody! I tried to extract textures from the .txd files using almost all txd tools that are available and not one works   . Do you know how to extract them or could anyone take a look at this file format for this game? I've added a few samples but if you want more for test just let me know. Any help would be greatful   .

[https://mega.nz/#!5htDAIwD!5jML-GNxkEmQ ... 1iX7uxy71E](https://mega.nz/#!5htDAIwD!5jML-GNxkEmQztv0djhgPeaBJJ1JkZViW1iX7uxy71E)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-09-11T18:38:06+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

here is a generic bms script to split the textures from your txd samples with names  

```
do
    goto OFFSET
    get DUMMY long
    findloc NEXT_OFFSET binary "\x43\x48\x5f" 0 ""
    if NEXT_OFFSET == ""
        get SIZE asize
    else
        math SIZE = NEXT_OFFSET
    endif
    math SIZE -= OFFSET
    savepos TMP
    math TMP - 0x04
    goto TMP
    getdstring NAME 0x20
    math OFFSET - 0x3c
    string NAME + ".tx"
    log NAME OFFSET SIZE
    math OFFSET = NEXT_OFFSET
while NEXT_OFFSET != ""

```

i just gave them a tx extension


the textures are big-endian swizzled/tiled dxt but i can't figure out the swizzling/tiling thing.
## Post #3
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2016-10-24T13:10:57+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

(Sorry for the late reply xD) Thanks a lot for the help and the script AceWell  I can see textures with TextureFinder as DXT3 or DXT5 formats but all have bad colors and are very pixelated :S Do you have an idea of what can be done in this case?  
[1c.png](https://xentaxbackup.github.io/file/11836_1c.png)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-10-25T17:16:39+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

> Reply from CaxUchiha
>
> Do you have an idea of what can be done in this case?
no not yet, maybe some time down the road we'll figure it out, 
but until then you can dump what you need with an emulator

[https://wiki.vg-resource.com/wiki/GameC ... re_Dumping](https://wiki.vg-resource.com/wiki/GameCube#Sprite.2FTexture_Dumping)
## Post #5
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2016-10-27T08:51:51+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

Thanks AceWell, I know that way for dump textures but my laptop can't run the emulador properly 

Btw, some time ago I dumped the textures from one of the character models which txd file I included inside the file of the download link that I posted before.. Did they could be useful for try to figure out how they are compressed?
## Post #6
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-10-31T22:12:46+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

.tx plugin for Noesis is in my repo.
## Post #7
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2017-11-01T02:48:29+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

Thanks zheneq
## Post #8
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-01T22:51:14+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

> Reply from CaxUchiha
>
> https://mega.nz/#!5htDAIwD!5jML-GNxkEmQ ... 1iX7uxy71E
can you upload those samples again?   
i'm trying to learn from zheneq's script and i need samples to walk through as i read the script.
## Post #9
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-11-01T23:51:08+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

You could just go to the [specs page](http://wiki.tockdom.com/wiki/Image_Formats).

[Samples](https://yadi.sk/d/18mk-6xa3PKmFa).
## Post #10
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-01T23:57:47+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

thank you, do you happen to still have the txd sample too?  
i think i need to modify the bms script to work with more samples  

edit

> Reply from zheneq
>
> You could just go to the specs page.
no i've seen that and you have all of it under control, i just wanted to see what this was:

```
unks = [bs.readUInt() for i in range(15)]
```

i have never seen a loop used like that to define a variable
## Post #11
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-11-02T00:02:44+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

I have never had any. By the way, maybe I'd better make a plugin for txd so that we don't spread artificial extensions? I guess I could just go and adapt your bms but I'd prefer to have samples at hand too =)
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-02T00:10:22+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

yeah as i posted before the script was just a generic search for bytes that happened to be in the samples he shared.
but it will not work if others have different name prefix. i don't know what the correct extension is supposed to be,
i was not a developer of the game (  ) , the bms script was a quick write-up to work with provided samples.
i would like to try making a proper bms extraction script and discard previous one.
## Post #13
- Username: zheneq
- Rank: advanced
- Number of posts: 43
- Joined date: Fri Jul 17, 2015 1:09 pm
- Post datetime: 2017-11-02T00:20:03+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

Ah, that's why some of the files have some weird stuff happening after texture data
## Post #14
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2017-11-02T12:15:52+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

> Reply from AceWell
>
> can you upload those samples again?   
i'm trying to learn from zheneq's script and i need samples to walk through as i read the script.

Yes, I'll upload more samples guys just let me extract them again xD
## Post #15
- Username: Brandondorf9999
- Rank: n00b
- Number of posts: 14
- Joined date: Sat May 12, 2012 10:08 am
- Post datetime: 2017-11-05T16:53:02+00:00
- Post Title: Silent Hill: Shattered Memories textures .txd (Wii)

> Reply from CaxUchiha
>
> Hi everybody! I tried to extract textures from the .txd files using almost all txd tools that are available and not one works   . Do you know how to extract them or could anyone take a look at this file format for this game? I've added a few samples but if you want more for test just let me know. Any help would be greatful   .

https://mega.nz/#!5htDAIwD!5jML-GNxkEmQ ... 1iX7uxy71E

There's a tool called Magic.TXD which allows you to extract textures from the txd archive since this is indeed an RenderWare game. The tool is found here:

[https://www.gtamodding.com/wiki/Magic.TXD](https://www.gtamodding.com/wiki/Magic.TXD)
## Post #16
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-11-05T19:55:34+00:00
- Post Title: Re: Silent Hill: Shattered Memories textures .txd (Wii)

i got my hands on the arc files of this game and extracted txd files from them using the bms script here by AlphaTwentyThree
[viewtopic.php?p=36213#p36213](http://forum.xentax.com/viewtopic.php?p=36213#p36213) 
i see a few variations in the structure and they don't seem to work with Magic.TXD linked by Brandondorf9999,
i may just sit this bms project on the back burner for a while and work on other things.

## Post #1
- Username: greenbingo
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 08, 2011 10:21 pm
- Post datetime: 2019-02-08T15:04:00+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

Please hlep

PSVITA Dynasty Warriors 8 G1TG file to dds

[www.mediafire.com/file/kcsxss661spmavi/G1TG.7z/file](http://www.mediafire.com/file/kcsxss661spmavi/G1TG.7z/file)
## Post #2
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-08T20:09:03+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

here is Noesis python script to open your 2 samples.  


 tex_DynastyWarriors8_PSVita_g1t.zip
(1012 Bytes) Downloaded 61 times


supports dxt5 and morton swizzled dxt5

need more samples to extend the script.
## Post #3
- Username: greenbingo
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 08, 2011 10:21 pm
- Post datetime: 2019-02-09T00:03:19+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

> Reply from Acewell
>
> here is Noesis python script to open your 2 samples.  
tex_DynastyWarriors8_PSVita_g1t.zip
supports dxt5 and morton swizzled dxt5

need more samples to extend the script.

Thank you very much~!

One more question.

Can I convert pc font to vita font?

pc font is broken in the game(vita)

[http://www.mediafire.com/file/970m74v34 ... kor%29.dat](http://www.mediafire.com/file/970m74v3400wruy/pc+font%28kor%29.dat)
## Post #4
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-02-09T01:21:49+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

> Reply from greenbingo
>
> Can I convert pc font to vita font?
pc font is broken in the game(vita)
i'm sure you can, you'd need to reswizzle the image for PSV,
but that is game modding and is not my area.
## Post #5
- Username: greenbingo
- Rank: n00b
- Number of posts: 15
- Joined date: Tue Nov 08, 2011 10:21 pm
- Post datetime: 2019-02-11T05:33:53+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

> Reply from Acewell
>
> greenbingo wrote:Can I convert pc font to vita font?
pc font is broken in the game(vita)
i'm sure you can, you'd need to reswizzle the image for PSV,
but that is game modding and is not my area.

Can I see other kinds of g1t files?

[https://www.mediafire.com/file/ywqnzyza ... et.7z/file](https://www.mediafire.com/file/ywqnzyza8h0h640/target.7z/file)
## Post #6
- Username: mxscrr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 11, 2020 12:10 am
- Post datetime: 2020-05-10T18:22:28+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

Hello,

Thank you very much, I was desperately looking for such a script, it's the only one that appears to work in my case : tex_DynastyWarriors8_PSVita_g1t.zip
I am a n00b and litterally crawled the web day and night (yes, I didn't sleep...) to open that G1TG asset.
The game I am modding is Attack on Titans 2 on PS Vita, this is really my 1st experience and I know nothing at programming.

You saved my weekend, you can't imagine how many tools I tryed because I don't understand what I am doing, but at least I found your message !
Next step, try to pack it back into PS Vita   [https://www.romhack.org/viewtopic.php?f ... 69#p121269](https://www.romhack.org/viewtopic.php?f=1&p=121269#p121269)

Mmmh how can this script be adapted to DTX1 for my ".GT1" files ? example 1024x1024 [https://anonfile.com/dc49eayfof/000000a0_gt1](https://anonfile.com/dc49eayfof/000000a0_gt1)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-11T00:14:26+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

there is universal script here to open these sample types from multiple games:
[viewtopic.php?p=158890#p158890](https://forum.xentax.com/viewtopic.php?p=158890#p158890)
the script is set to open g1t extension instead of gt1 extension.
you will either have to change the extension to g1t or change line 9
in the script to this to support both extensions:

```
    handle = noesis.register("G1T Image", ".g1t;.gt1")
```
## Post #8
- Username: mxscrr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 11, 2020 12:10 am
- Post datetime: 2020-05-11T18:09:53+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

Hi,
Thank you, this universal script works very well.
Now I am done with texture editing in PNG, and I converted it to DDS "BC3/DTX5", the same format than the original.
But I need to swizzle back before rebuilding the BIN package, so basically doing the reverse operation of your suggested link !

Do you know any tool doing this ? I was not successful with my own research...
Also, the headers are different, shall I remove some bytes because the DDS is bigger ?



Left is the original file extracted from PSVita.
There are not many file to process so I can do the operation manually if necessary, but most importantly I need this swizzle operation.

Cya
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2020-05-11T22:40:10+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

im not a game modder so i can't give advice on swizzling for PSVita or headers etc 
except maybe check out other modding sites and see what others have been doing.
## Post #10
- Username: mxscrr
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon May 11, 2020 12:10 am
- Post datetime: 2020-05-12T06:51:38+00:00
- Post Title: PSVITA Dynasty Warriors 8 G1TG files

Yes, sure,
But I thought it was just about reversing the command lines of the Noesis script.
For example :

```
if TEXFMT in (0x10,0x12): data = rapi.imageFromMortonOrder(data, width>>1, height>>2, BytesPerBlock) # PSVita specific swizzling, thanks Acewell
```

Is there any way to do "imageToMortonOrder" function or such a modification in the .py ?
Then I process it with Noesis and export the image. So once the PS Vita is reading the image and 'unswizzling' the data, it just displays like normal. Unfortunately I don't understand the code, it could take me years to achieve it !   

Yay SUCCESS !! The kukki software can export to .g1t if you add "vita" in the file name and I realized that it's no different to G1TG when I load it in the PS Vita

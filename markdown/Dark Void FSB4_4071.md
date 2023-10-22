## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-21T20:15:29+00:00
- Post Title: Dark Void FSB4

I have some example from this game but no idea how to convert to wav i tried fsbext and i get:

> - input file:   e3m4_tor_026_Music001.fsb
>
> - FSB4 version 4.0 mode 32
>
> 
>
> Filename                         Size       Mode frequency channels bits
>
> ========================================================================
>
> e3m4_tor_026_Music001.wav        365920     delta,2d,multichan 44100 6 16
Here i'ts the sample:
[e3m4_tor_026_Music001.fsb - 0.35MB](http://www.zshare.net/download/715064277692a123/)
The program extracts the wav, but i can't play or convert to wav to edit
Lookgin inside the file i get 

> LAME3.98 (beta
aprox 92 Lame tag 's i found...
Thanks!!
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-21T20:23:47+00:00
- Post Title: Dark Void FSB4

This game uses Multichannel MP3.

Use mp3extract to extract the individual channels, they are surround sound tracks.

[http://www.megaupload.com/?d=MM8HENJO](http://www.megaupload.com/?d=MM8HENJO)
## Post #3
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-21T22:24:08+00:00
- Post Title: Dark Void FSB4

The example worked but i tried with a big fsb and get:
with mp3extractor

> Reading FSB file... 59731968 bytes
>
> Formatting filename...
>
> Extracting 2m03_b.wav channel 1...
>
> Exception in thread "main" java.lang.OutOfMemoryError: Java heap space
>
>         at java.util.Arrays.copyOf(Unknown Source)
>
>         at java.io.ByteArrayOutputStream.write(Unknown Source)
>
>         at java.io.OutputStream.write(Unknown Source)
>
>         at mp3extract.extractChannel(mp3extract.java:149)
>
>         at mp3extract.main(mp3extract.java:99)

If i try to extract with fsbext i get some errors too

> - input file:   musics.fsb
>
> - FSB4 version 4.0 mode 32
>
> 
>
> Filename                         Size       Mode frequency channels bits
>
> ========================================================================
>
> 2m03_b.wav                       1306272    delta,2d,multichan 44100 4 16
>
> 2m02_alt2_b.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m02_b.wav                       1120416    delta,2d,multichan 44100 4 16
>
> 2m03_a.wav                       1120416    delta,2d,multichan 44100 4 16
>
> 2m03_alt3_intro2.wav             566016     delta,2d,multichan 44100 4 16
>
> 2m03_alt1_e.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m02_a.wav                       1120416    delta,2d,multichan 44100 4 16
>
> 2m03_alt3_outro.wav              991584     delta,2d,multichan 44100 4 16
>
> 2m03_alt2_b.wav                  1306272    delta,2d,multichan 44100 4 16
>
> 2m03_c.wav                       1120416    delta,2d,multichan 44100 4 16
>
> 2m02_intro.wav                   258720     delta,2d,multichan 44100 4 16
>
> 2m01_alt1_b.wav                  1423488    delta,2d,multichan 44100 4 16
>
> 2m02_outro.wav                   535392     delta,2d,multichan 44100 4 16
>
> 2m02_c.wav                       1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt1_g.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m03_alt3_intro1.wav             563904     delta,2d,multichan 44100 4 16
>
> 2m01_alt2_c.wav                  1166880    delta,2d,multichan 44100 4 16
>
> 2m01_intro.wav                   461472     delta,2d,multichan 44100 4 16
>
> 2m03_alt2_e.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m03_d.wav                       1072896    delta,2d,multichan 44100 4 16
>
> 2m02_alt3_b.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_outro.wav                   594528     delta,2d,multichan 44100 4 16
>
> 2m01_alt1_e.wav                  1306272    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_intro.wav              501600     delta,2d,multichan 44100 4 16
>
> 2m02_alt1_b.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m03_alt3_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_f.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m03_f.wav                       1493184    delta,2d,multichan 44100 4 16
>
> 2m01_b.wav                       1423488    delta,2d,multichan 44100 4 16
>
> 2m03_intro.wav                   561792     delta,2d,multichan 44100 4 16
>
> 2m03_alt3_f.wav                  1493184    delta,2d,multichan 44100 4 16
>
> 2m03_e.wav                       1072896    delta,2d,multichan 44100 4 16
>
> 2m01_a.wav                       1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt1_intro.wav              486816     delta,2d,multichan 44100 4 16
>
> 2m02_alt2_c.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m03_outro.wav                   1030656    delta,2d,multichan 44100 4 16
>
> 2m03_alt1_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_d.wav                  1003200    delta,2d,multichan 44100 4 16
>
> 2m03_alt3_d.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m01_c.wav                       1166880    delta,2d,multichan 44100 4 16
>
> 2m02_alt2_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt1_c.wav                  1166880    delta,2d,multichan 44100 4 16
>
> 2m03_alt1_d.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m03_alt2_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_d.wav                       1003200    delta,2d,multichan 44100 4 16
>
> 2m01_alt1_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m02_alt3_c.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt1_f.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_b.wav                  1423488    delta,2d,multichan 44100 4 16
>
> 2m03_intro2.wav                  564960     delta,2d,multichan 44100 4 16
>
> 2m01_f.wav                       1072896    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_g.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m03_alt3_b.wav                  1306272    delta,2d,multichan 44100 4 16
>
> 2m03_alt2_d.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 2m02_alt1_c.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 2m01_alt2_outro.wav              607200     delta,2d,multichan 44100 4 16
>
> 2m02_alt3_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m01_e.wav                       1306272    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m01_alt1_d.wav                  1003200    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m03_alt1_b.wav                  1306272    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m01_alt2_e.wav                  1306272    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m02_alt1_a.wav                  1120416    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m01_alt1_outro.wav              591360     delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m01_g.wav                       1072896    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 2m03_alt3_e.wav                  1072896    delta,2d,multichan 44100 4 16
>
> 
>
> - Alert: the extracted file is incomplete! I continue
>
> 
>
> - 66 files processed
Here is the sample:
[musics.fsb - 56.96MB](http://www.zshare.net/download/7151113965208f93/)
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-22T00:09:02+00:00
- Post Title: Dark Void FSB4

on a big fsb file run it in FSBII, in hcs tools page, it extracts the individual files in fsb containers. then use mp3extract on a multichannel file.
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-22T00:43:47+00:00
- Post Title: Dark Void FSB4

I did it and i get anooooother file, now more smaller i tried, fsbext, fsbii and mp3extract.
fsbii:

> Type: FSB4
>
> Header: 0x30 bytes
>
> Table:  0x60 bytes
>
> Body:   0xbe6300 bytes
>
> ------------------
>
> Total:  0xbe6390 bytes
>
> File:   0xbe6390 bytes
>
> Already a single stream.
>
> Success!

fsbext (Unpacked but no playable):

> - input file:   data.fsb
>
> - FSB4 version 4.0 mode 32
>
> 
>
> Filename                         Size       Mode frequency channels bits
>
> ========================================================================
>
> e3m4_tor_025_Music002.wav        12477184   delta,2d,multichan 44100 6 16
>
> 
>
> - 1 files listed

mp3extract:

> Reading FSB file... 12477328 bytes
>
> Formatting filename...
>
> Extracting e3m4_tor_025_Music002.wav channel 1...
>
> mp3tools.IllegalHeaderException
>
>         at mp3tools.Header.<init>(Header.java:145)
>
>         at mp3tools.MP3Buffer.getNextFrame(MP3Buffer.java:58)
>
>         at mp3extract.extractChannel(mp3extract.java:136)
>
>         at mp3extract.main(mp3extract.java:99)
>
> Exception in thread "main" java.lang.NullPointerException
>
>         at mp3extract.extractChannel(mp3extract.java:148)
>
>         at mp3extract.main(mp3extract.java:99)
but nothing extracted
The file
[data.fsb - 11.90MB](http://www.zshare.net/download/7151609179f72f34/)
Thanks for the help
## Post #6
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-22T02:11:25+00:00
- Post Title: Dark Void FSB4

Make sure the file your extracting with mp3extract is a single stream file, look in a hex editor to make sure and look in fsbext to see if its a multichannel file.
## Post #7
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-22T02:24:32+00:00
- Post Title: Dark Void FSB4

The last file i attached have more than 50 LAME3.98 (beta) Tag's inside..multichannel?
I tried to play with winamp+Hcs vgstream plugin, but none of this worked.
Fsbext v 0.2.8 says it's multichannel (6)

> - input file:   data.fsb
>
> - FSB4 version 4.0 mode 32
>
> 
>
> Filename                         Size       Mode frequency channels bits
>
> ========================================================================
>
> e3m4_tor_025_Music002.wav        12477184   delta,2d,multichan 44100 6 16
>
> 
>
> - 1 files listed
## Post #8
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-22T02:35:19+00:00
- Post Title: Dark Void FSB4

Well looks to me like a multi stream files with more then one track inside, run it in fsbii again. you should get a fsb files with names.
## Post #9
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-22T02:39:52+00:00
- Post Title: Dark Void FSB4

Using fsbii 0.6: 
> fsbii.exe data.fsb
 i get:

> Type: FSB4
>
> Header: 0x30 bytes
>
> Table:  0x60 bytes
>
> Body:   0xbe6300 bytes
>
> ------------------
>
> Total:  0xbe6390 bytes
>
> File:   0xbe6390 bytes
>
> Already a single stream.
>
> Success!

So..the ASCii tags looks multichannel, fsbext says it's multichannel, mp3extract can't extract the data,  and fsbii 0.6 says it's a single stream (not channels)

Cheers!
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-22T04:51:35+00:00
- Post Title: Dark Void FSB4

HMm okay i see now, never had this problem with the 360 version though, so not sure. and i cannot contact bnw to see whats wrong.

360 version use xma.
## Post #11
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-22T06:12:35+00:00
- Post Title: Dark Void FSB4

This is similar to a DJ Hero (Wii) file I was just recently asked to look at, the MPEG frames are rounded up to some padding size (seems to be 8 but could be 16).  I've put up fsb_mpeg ([http://hcs64.com/vgm_ripping.html](http://hcs64.com/vgm_ripping.html)) which parses these out, run it like:

```
fsb_mpeg data.fsb out 3
```

to produce the three streams as out_1.mp3, out_2.mp3, out_3.mp3.  Note I use "mp3" although the parser technically should support MPEG 1 Layer I and II as well, I expect we'll only see Layer III, though.
The other tools might have had problems because there's valid MPEG audio headers in the filler, or because 44.1khz MP3 has uneven sized frames.  I look at the MPEG headers to determine frame size, then round that up to the nearest 8, but I only dump the actual valid frame.  Seems to work on this data.fsb and the DJ Hero file I'd played with.

BTW, I checked out that big file you uploaded, you didn't upload the whole thing (file is truncated).

I took a look at mp3extract, he probably has the rounding done more correctly than I do (by 16), I think it's just choking on the bit of padding at the end of the file.  His fsb handling is certainly better than mine, since I ignore it altogether (thus the need to specify the number of streams).  But since it processes one channel at a time, and everything's buffered in memory, nothing ever gets output if there's an error.  My tool expects to lose sync eventually, though it does report it so you know how much is missing, and only makes one pass through the file for all channels.

Here's a fixed version of mp3extract: [http://hcs64.com/files/mp3extract_mod1.zip](http://hcs64.com/files/mp3extract_mod1.zip)
## Post #12
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-23T02:44:50+00:00
- Post Title: Dark Void FSB4

Thanks i will try this tool
## Post #13
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2010-01-23T04:08:45+00:00
- Post Title: Dark Void FSB4

One more thing: I merged fsbii functionality into fsb_mpeg, now you can give it that master musics.fsb file and it'll work everything out from there (all subfile names, and stream counts).  0.3.

(assuming of course you start with a complete musics.fsb file, I temporarily disabled the truncation check while testing)
## Post #14
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2010-01-23T04:57:02+00:00
- Post Title: Dark Void FSB4

wow hcs great work.
## Post #15
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2010-01-23T10:28:31+00:00
- Post Title: Dark Void FSB4

> Reply from OrangeC
>
> wow hcs great work.
I agree and thanks to you too   , time make some strange things with this tools mwahha

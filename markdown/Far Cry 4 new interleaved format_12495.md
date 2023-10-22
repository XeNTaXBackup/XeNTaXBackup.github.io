## Post #1
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-01-12T16:06:36+00:00
- Post Title: Far Cry 4 new interleaved format?

Hi mates,

Step 1:

I was checking Far Cry 4 sounds when I figured that some .spk archives are not compatible with Zench's DecUbiSndGUI 0.81.
Here's the file "00074eb9.spk" in ".../fcc_main_unpacked/soundbinary" main folder.



Step 2:

So I tried to extract these with its little brother DecUbiSnd 0.80 (DOS version) with that command:

```
ren *spk3 *.wav
del *spk
```

Here's the result in Audacity:



The sound is very noisy and glitchy. 

By the way, other command options (ubi_iv9, raw, ogg, etc...) doesn't work on this kind of archive.

Step 3:

So I tried with another archive ("00448bc8.spk") and look what happened:

In DecUbiSndGUI 0.81, same result as above. No layers or sounds detected.

By DecUbiSnd 0.80 (DOS version) with the same batch command:



Note: Clear sounds but with very strong low filter (basses). Each sounds are split by a strong "click". So, that's not good.

So, I don't know if Zench is still around but those archives are very tricky. Is there someone that can help me out?

Thanks in advance.

REMINDER: Each of those archives were extracted with "ubi_raw" batch command option by "DecUbiSnd 0.80.exe"

Files are too big to upload them on the forum. Contact me if you need any info.
## Post #2
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2015-01-14T08:01:58+00:00
- Post Title: Far Cry 4 new interleaved format?

Hi Vosvoy,

From a quick glance at the files, looks like you found a new variant. Some of them even crash DecUbiSndGui (uh-oh). I'm not around these parts much any more so I can't say when or if I get around to looking at it.

- Zench
## Post #3
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2015-01-14T09:51:57+00:00
- Post Title: Far Cry 4 new interleaved format?

Hi Zench,

It's okay. It's just cool that you're aware of that new type of .spk archive (sufficient for me). But I think this variant will be commonly encountered in future Ubisoft games using this sound archive. So, I have confidence that's not the last time you've heard about this problem (by someone else at least).

Thank you for taking time to look at it though.

Cordialy.
## Post #4
- Username: Pepper
- Rank: mega-veteran
- Number of posts: 278
- Joined date: Thu Apr 17, 2008 10:48 am
- Post datetime: 2015-01-20T17:30:26+00:00
- Post Title: Far Cry 4 new interleaved format?

> Reply from Vosvoy
>
> Hi Zench,

It's okay. It's just cool that you're aware of that new type of .spk archive (sufficient for me). But I think this variant will be commonly encountered in future Ubisoft games using this sound archive. So, I have confidence that's not the last time you've heard about this problem (by someone else at least).

Thank you for taking time to look at it though.

Cordialy.

I'm pretty sure this variant was in blood dragon. I found a lot of times the audio files would be from 4-12mb, but still turn up nothing when scanned. Just trying to help if at all, I know Zench is free to do what he wants, and I'm thankful he supported his tool to this point.

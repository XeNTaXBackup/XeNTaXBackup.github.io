## Post #1
- Username: 64BTX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2022 9:26 am
- Post datetime: 2022-04-17T02:23:53+00:00
- Post Title: Priconne Grandmasters .awb/.acb files

A bit stumped on how to open and listen to these.
I've tried multiple ways to do so, but they don't seem to work. I've also tried the main way of dropping them into foobar with the latest vgmstream plugin, but I only get some kind of garbage noise. However, others have been able to listen to them this way with no problem, so it might be just my computer doing something weird, but I'd like to verify it first. Oddly enough, using the command-line vgmstream to see the file's info brings up some pretty reasonable stats like channels, bitrate, song time, etc.
The game service was discontinued after a week of uptime since it was some elaborate April Fool's thing, but you can still find the APK online [here](https://apkcombo.com/apk-downloader/#package=jp.co.cygames.priconnegrandmasters) or elsewhere. For clarity's sake, this game was completely free throughout its lifespan.

I used the MuMu Nebula emulator, but any rooted Android device should work for getting the files.
Here's a link to some of them I got, including how I got them if you want to trace my steps to look at the rest:
[https://mega.nz/file/eJJyCZoT#74sGbspxz ... MadZIz4Fs4](https://mega.nz/file/eJJyCZoT#74sGbspxzlCtu8LnKckj3uPe2KYO3CtCiMadZIz4Fs4)
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-17T20:50:47+00:00
- Post Title: Priconne Grandmasters .awb/.acb files

All your samples are playing perfectly fine for me in foobar2000 with vgmstream plugin.
For the ones "From Data Download" I had to change their names to the real ones (e.g. bgm_GM015.awb).

My plugin version is "vgmstream plugin r1721-36-g1bb9a5a8 (Apr  9 2022)". I've downloaded it directly from vgmstream's Github page.

In case of any issues with the key, you can follow tutorial from this article [http://wiki.xentax.com/index.php/HCA_Audio](http://wiki.xentax.com/index.php/HCA_Audio)
The key is 00 00 00 2B 3C EB 77 81.
## Post #3
- Username: 64BTX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2022 9:26 am
- Post datetime: 2022-04-17T21:15:50+00:00
- Post Title: Priconne Grandmasters .awb/.acb files

I can't seem to find that build of the plugin, and looking at the vgmstream website redirects me to an earlier version of the website courtesy of Cloudflare, so I'm not sure how to proceed. Thanks regardless!
## Post #4
- Username: 64BTX
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-04-17T21:20:48+00:00
- Post Title: Priconne Grandmasters .awb/.acb files

Here is the release page [https://github.com/vgmstream/vgmstream/ ... /tag/r1721](https://github.com/vgmstream/vgmstream/releases/tag/r1721)

and here's direct link [https://github.com/vgmstream/vgmstream/ ... -component](https://github.com/vgmstream/vgmstream/releases/download/r1721/foo_input_vgmstream.fb2k-component)


(By the way, it would work on the older build as well, but you would need to take care of the decryption manually - as described on the wiki)
## Post #5
- Username: 64BTX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2022 9:26 am
- Post datetime: 2022-04-17T21:36:14+00:00
- Post Title: Priconne Grandmasters .awb/.acb files

Using the key and putting it in the folder with the awb/acb got it to work properly! Thank you so much!

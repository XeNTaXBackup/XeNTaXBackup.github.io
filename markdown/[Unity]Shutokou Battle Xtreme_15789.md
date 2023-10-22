## Post #1
- Username: nosfornos
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Dec 21, 2011 4:16 pm
- Post datetime: 2017-01-26T14:12:51+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

I downloaded Shutokou Battle Xtreme, and try to rip from this game. But, extracting obb files is too risky because of rooting requirement.
What can I do?
## Post #2
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-01-31T16:08:51+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

You can install it to emulator, like [MEmu](http://www.memuplay.com/).
And how you get this game, it's out already?
## Post #3
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-01-31T19:17:33+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from Andrakann
>
> You can install it to emulator, like MEmu.
And how you get this game, it's out already?
Yes, but only in Japan...
[https://play.google.com/store/apps/deta ... .genki.sbx](https://play.google.com/store/apps/details?id=jp.co.genki.sbx)
[https://itunes.apple.com/jp/app/shou-do ... 71198?mt=8](https://itunes.apple.com/jp/app/shou-dou-gaobatoruxtreme/id1139671198?mt=8)
I got apk file and I will test. I hope is unity game
## Post #4
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-02-01T06:20:39+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from zimex25
>
> Yes, but only in Japan...
Thanks 
I found it, making an Apple ID in Japanese it's not a trivial task, but i done it too 
For Android version i just googled for apk.
It's better to use version for hardware (or emu) you have, because all useful files located in downloaded cache, which is created after you launch game.

> I got apk file and I will test. I hope is unity game
Yeah, it's Unity 5+, so you'll need to use Unity Asset Bundle Extractor for unpacking and checking content of .cache files (also for converting textures to .png), then export from UABE to .assets file, if you found car model or track/garage scene bundle, and open it in Unity Studio v0.5.1b3 for model export.
Works for me:
[](http://fastpic.ru/view/90/2017/0201/b3f5462de057a5a1ef4b9e4473c583bd.png.html) [](http://fastpic.ru/view/90/2017/0201/465ff1e5a46213bdbb32c262d7bd7f03.png.html)
Detail is low, about 15K-25K faces for one car model.
## Post #5
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-01T09:46:04+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

Yes, it works, the game has more than 20 Japanese cars.

The question is how to extract using Unity Asset Bundle Extractor cache all files at once, look for them or any part of it is very difficult there cache files are too many?
## Post #6
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-02-01T10:06:22+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from blackracer
>
> The question is how to extract using Unity Asset Bundle Extractor cache all files at once, look for them or any part of it is very difficult there cache files are too many?
Just solved it 
You need to make batch.txt file with "+DIR <full path to cache folder>" line inside. Important part here is encoding of this text file, it MUST be "UTF-8 without BOM" in therms of Notepad++.
Then put this file to UABE exe folder and run this command:
AssetBundleExtractor.exe batchexport batch.txt

I attached my files, just put them to exe folder, edit path in .txt file and run .bat file.

Upd: Cars list, ingame names:

```
c_bnr32
c_bnr34
c_cp9a
c_cz4a
c_dk5aw
c_ek9
c_fd3s
c_fk2
c_gc8
c_ggh35w
c_ha36s
c_jw5
c_krps13
c_l152s
c_la400k
c_mh21s
c_na2
c_na8c
c_ncp31
c_r35
c_se3p
c_vab
c_vmg
c_z34
c_zc6
c_zn6
c_zvw30
```

[UABE_batch_extract.zip](https://xentaxbackup.github.io/file/12363_UABE_batch_extract.zip)
## Post #7
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-02-01T18:48:36+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from Andrakann
>
> blackracer wrote:The question is how to extract using Unity Asset Bundle Extractor cache all files at once, look for them or any part of it is very difficult there cache files are too many?
Just solved it 
You need to make batch.txt file with "+DIR <full path to cache folder>" line inside. Important part here is encoding of this text file, it MUST be "UTF-8 without BOM" in therms of Notepad++.
Then put this file to UABE exe folder and run this command:
AssetBundleExtractor.exe batchexport batch.txt

I attached my files, just put them to exe folder, edit path in .txt file and run .bat file.

Upd: Cars list, ingame names:
Code: Select allc_ae86t
c_bnr32
c_bnr34
c_cp9a
c_cz4a
c_dk5aw
c_ek9
c_fd3s
c_fk2
c_gc8
c_ggh35w
c_ha36s
c_jw5
c_krps13
c_l152s
c_la400k
c_mh21s
c_na2
c_na8c
c_ncp31
c_r35
c_se3p
c_vab
c_vmg
c_z34
c_zc6
c_zn6
c_zvw30

But for me is 0 bundle extracted :/
## Post #8
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-02-01T18:55:35+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from zimex25
>
> But for me is 0 bundle extracted :/
Did you edit path in txt file and point it to your folder with .cache files?
And if you open single .cache file with UABE - it works?
## Post #9
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-02-01T19:34:21+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

Andrakann
Thank you very much, it's running ))

for Genki
I am more than confident that the guys from Genki browsing this forum, and they are not particularly pleased event, please do not do as did Namco, do not close the download cache, your games as a masterpiece, for the most part, we only look at your models and at best make convert, it is difficult to imagine that someone would use them for commercial purposes ...
Reversing is only a matter of time and the popularity of the product, all games can be opened.


And more Drift Spirits from Namco easily give models if desired car is available in the garage, it is also stored in the Unity cache files.
Guys who have any ideas how to open all the cars to get them cache Drift Spirits?
## Post #10
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-02-02T18:43:03+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from Andrakann
>
> zimex25 wrote:But for me is 0 bundle extracted :/
Did you edit path in txt file and point it to your folder with .cache files?
And if you open single .cache file with UABE - it works?

Yup I edited and I can opened
## Post #11
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-02-03T06:29:14+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

> Reply from zimex25
>
> Andrakann wrote:zimex25 wrote:But for me is 0 bundle extracted :/
Did you edit path in txt file and point it to your folder with .cache files?
And if you open single .cache file with UABE - it works?

Yup I edited and I can opened
Maybe typo in path or encoding of txt is changed?
[](http://fastpic.ru/view/91/2017/0203/265b8678c800aad3a6a1d0165d08808a.png.html)
## Post #12
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2017-02-03T15:02:22+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

Damn I didn't change :/ (I saved in normal UTF-8) thanks for help!
## Post #13
- Username: SpulX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 26, 2017 9:45 pm
- Post datetime: 2017-04-03T14:07:51+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

i tried using this method but i dont see anything in the unity studio like preview and when i try to export the 3d models i get some error and thats it 3dsmax doesnt open it.
## Post #14
- Username: blackracer
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Jun 27, 2015 8:20 pm
- Post datetime: 2017-04-03T14:21:39+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

The method is 100% working, I checked personally. Upgrade 3ds max to the latest version and download the latest versions of UABE and unity studio.
## Post #15
- Username: SpulX
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Mar 26, 2017 9:45 pm
- Post datetime: 2017-04-03T18:11:21+00:00
- Post Title: [Unity]Shutokou Battle Xtreme

i did i think i have latest all well 3dsmax is 2016 ver but it works fine with everything this is what i get [http://img02.imgland.net/nLesctG.jpg](http://img02.imgland.net/nLesctG.jpg)
## Post #16
- Username: lkw019
- Rank: veteran
- Number of posts: 96
- Joined date: Mon Jul 18, 2011 9:22 pm
- Post datetime: 2020-09-03T05:34:37+00:00
- Post Title: Re: [Unity]Shutokou Battle Xtreme

> Reply from Andrakann ↑Wed Feb 01, 2017 6:06 pm at Wed Feb 01, 2017 6:06 pm
>
> 
blackracer wrote:The question is how to extract using Unity Asset Bundle Extractor cache all files at once, look for them or any part of it is very difficult there cache files are too many?
Just solved it 
You need to make batch.txt file with "+DIR <full path to cache folder>" line inside. Important part here is encoding of this text file, it MUST be "UTF-8 without BOM" in therms of Notepad++.
Then put this file to UABE exe folder and run this command:
AssetBundleExtractor.exe batchexport batch.txt

I attached my files, just put them to exe folder, edit path in .txt file and run .bat file.

Upd: Cars list, ingame names:
Code: Select allc_ae86t
c_bnr32
c_bnr34
c_cp9a
c_cz4a
c_dk5aw
c_ek9
c_fd3s
c_fk2
c_gc8
c_ggh35w
c_ha36s
c_jw5
c_krps13
c_l152s
c_la400k
c_mh21s
c_na2
c_na8c
c_ncp31
c_r35
c_se3p
c_vab
c_vmg
c_z34
c_zc6
c_zn6
c_zvw30
Hello, I used this batch method and successfully opened the file in batch. However, when exporting PNG images, you will be prompted [unable to open the streamed data file! Unable to convert the texture data!]
[https://mega.nz/file/qyIBFQCL#sQqI8WZAd ... hSnoSR8Rqg](https://mega.nz/file/qyIBFQCL#sQqI8WZAdIygk5_dq-0CTAGN8uUMFbE-PhSnoSR8Rqg)

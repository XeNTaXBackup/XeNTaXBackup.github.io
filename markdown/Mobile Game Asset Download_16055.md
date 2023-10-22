## Post #1
- Username: HeliosAI
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-25T14:42:05+00:00
- Post Title: Mobile Game Asset Download

This tutorial Will show you how to download all the assets from a mobile game instead of 
having to play the game and the game only downloads the assets when you see them in game.
What you need for this tutorial is
Nox App Player: [https://www.bignox.com/](https://www.bignox.com/)
Process Hacker: [http://processhacker.sourceforge.net/](http://processhacker.sourceforge.net/)
Telerik Fiddler  : [https://www.telerik.com/download/fiddler](https://www.telerik.com/download/fiddler)
and the apk for the game you want to get the assets from.
We will use 放課後ガールズトライブ aka Girls Tribe After School.
[Apk Download](https://apkpure.com/%E6%94%BE%E8%AA%B2%E5%BE%8C%E3%82%AC%E3%83%BC%E3%83%AB%E3%82%BA%E3%83%88%E3%83%A9%E3%82%A4%E3%83%96/jp.ateam.girlstribe)
Start up nox and get your google account all set up.
Now drag the apk onto the home screen and this will pop up.

click open apk folder
now click on the game and choose install.
Now we need to start up fiddler and go to tools options and set it like this.

Also make sure the check mark under Connections for Allow remote computers to connect is set.
Now you can download the certificate from [http://127.0.0.1:8888](http://127.0.0.1:8888)

Copy the certificate you downloaded to Nox_share\Other folder.
use ex file explorer to copy the certificate to /sdcard
Now go into settings -> Security -> Install from sd card

Click FiddlerRoot.cer and just give it a name and click ok

Now we can point nox to our fiddler proxy.
Go to Settings - > Wifi - Click and hold on the wifi connection and choose modify network

Make sure your computer can be accessed from the internet on port 8888 (Normally called port forwarding)
and set the proxy like this (Get it from [http://whatismyip.com](http://whatismyip.com) )

Now if you launch the game you will see url's start to show up in fiddler.
the first 3 are

[http://game.jp.girls-tribe.com/system/get_game_version](http://game.jp.girls-tribe.com/system/get_game_version)
[http://game.jp.girls-tribe.com/system/resource_version](http://game.jp.girls-tribe.com/system/resource_version)
[http://res.jp.girls-tribe.com/Resource/ ... c.csv?key=](http://res.jp.girls-tribe.com/Resource/release_1.0.7/android_c.csv?key=)
We are interested in the 3rd one.
if we paste this in a browser we get a nice csv list of all files.
example entry
release_1.0.7/Android_Compressed/AssetBundle/Character,ch_nadeko_maid_00_body,a3a6ae8682cac7113ff236f479d4df84f22cff5b,
With this we can generate the download link for our computer to grab the file.
[http://res.jp.girls-tribe.com/Resource/ ... 84f22cff5b](http://res.jp.girls-tribe.com/Resource/release_1.0.7/Android_Compressed/AssetBundle/Character/ch_nadeko_maid_00_body?key=a3a6ae8682cac7113ff236f479d4df84f22cff5b)
so the download format is
release_1.0.7/Android_Compressed/AssetBundle/Character, - path
ch_nadeko_maid_00_body, - file
a3a6ae8682cac7113ff236f479d4df84f22cff5b, - key
so we do
[http://res.jp.girls-tribe.com/Resource/](http://res.jp.girls-tribe.com/Resource/) + path + file + ?key= + key
you can get the ios version of the files also with this csv file.
[http://res.jp.girls-tribe.com/Resource/ ... c.csv?key=](http://res.jp.girls-tribe.com/Resource/release_1.0.7/ios_c.csv?key=)

For some games you might not see url's in fiddler (some games use tunnels)
for those games just see where the tunnel is connecting to example might be
tunneling to res.jp.girls-tribe.com:443
just open up Process Hacker (as admin) While the game is paused downloading files
and right click noxvmhandle.exe and go to properties
click on the memory tab and choose strings

after it comes back with all the strings choose filter
and put in girls-tribe.com
and it will show you the games links even if they were hidden.
## Post #2
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-03-27T21:04:37+00:00
- Post Title: Mobile Game Asset Download

Doesnt work with DoriSupi (a.k.a Drift Spirits)   , this app dont have .csv
## Post #3
- Username: cornal
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-27T22:47:31+00:00
- Post Title: Mobile Game Asset Download

It does have a csv file.
It was inside a unity file (first file it downloads)
just extracted it and got this.
[http://s3-ap-northeast-1.amazonaws.com/ ... 0077605720](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/3af7f0990c153405547508ec0375b05dd4f5e237?datetime=131351270077605720)
[http://s3-ap-northeast-1.amazonaws.com/ ... 0086273720](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/0fdbdd25889a97702c2944ee9c7130304b12fc1a?datetime=131351270086273720)
This is the first thing logged in fiddler for the game. (these are the csv files)

some example file downloads logged.
[http://s3-ap-northeast-1.amazonaws.com/ ... 9355145860](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/3af7f0990c153405547508ec0375b05dd4f5e237?datetime=131351279355145860)
[http://s3-ap-northeast-1.amazonaws.com/ ... 9365232890](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/635578f630dcf0f5e87f76326e29548393c2332d?datetime=131351279365232890)
[http://s3-ap-northeast-1.amazonaws.com/ ... 9393202410](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/ffb091f62934f32b4f15329e91f3b771d2e04ab2?datetime=131351279393202410)
[http://s3-ap-northeast-1.amazonaws.com/ ... 9492485950](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/52e19c3944c96a147527444799c8905cfe29cc7f?datetime=131351279492485950)
[http://s3-ap-northeast-1.amazonaws.com/ ... 9533719320](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/efb15eda7831f316082cd8cbb44ddd6146f839df?datetime=131351279533719320)
[http://s3-ap-northeast-1.amazonaws.com/ ... 9549372880](http://s3-ap-northeast-1.amazonaws.com/r31x-s2eykfdcpaub/N9jUi5tm/157d62dfc645ee95396f844cfc5cc35aefc807a7/6b968a7784b95fcb7b6f41fd3cde9a7c363a00b8?datetime=131351279549372880)
[drift.zip](https://xentaxbackup.github.io/file/12704_drift.zip)
## Post #4
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-03-28T04:13:42+00:00
- Post Title: Mobile Game Asset Download

> Reply from chrrox
>
> It does have a csv file.
It was inside a unity file (first file it downloads)
just extracted it and got this.
http://s3-ap-northeast-1.amazonaws.com/ ... 0077605720
http://s3-ap-northeast-1.amazonaws.com/ ... 0086273720
This is the first thing logged in fiddler for the game. (these are the csv files)

some example file downloads logged.
http://s3-ap-northeast-1.amazonaws.com/ ... 9355145860
http://s3-ap-northeast-1.amazonaws.com/ ... 9365232890
http://s3-ap-northeast-1.amazonaws.com/ ... 9393202410
http://s3-ap-northeast-1.amazonaws.com/ ... 9492485950
http://s3-ap-northeast-1.amazonaws.com/ ... 9533719320
http://s3-ap-northeast-1.amazonaws.com/ ... 9549372880

Thanks a lot for the explanation @chrrox, I've downloaded every file from "s3-ap-northeast-1.amazonaws.com" and forget the ones with Unicode text  , but how set to download the files?
## Post #5
- Username: Paps
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Mar 07, 2017 9:58 pm
- Post datetime: 2017-03-28T13:46:08+00:00
- Post Title: Mobile Game Asset Download

Hello Chrrox

Dosen't work on Heroes Evolved file.Please do help me.

samples [http://www34.zippyshare.com/v/Lx3e6lTk/file.html](http://www34.zippyshare.com/v/Lx3e6lTk/file.html)
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-29T09:13:31+00:00
- Post Title: Mobile Game Asset Download

How far did you get?
Show me your fiddler log and where you get stuck.
## Post #7
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-04-01T12:25:17+00:00
- Post Title: Mobile Game Asset Download

> Reply from Paps
>
> Hello Chrrox

Dosen't work on Heroes Evolved file.Please do help me.

samples http://www34.zippyshare.com/v/Lx3e6lTk/file.html

[http://1725932932.apollo.cdn.myqcloud.c ... _cures.ifs](http://1725932932.apollo.cdn.myqcloud.com/1725932932/508/cures/1.1.7.12/1725932932_508_1.1.7.12_20170331232713_cures.ifs)
## Post #8
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-04-01T14:34:43+00:00
- Post Title: Mobile Game Asset Download

I can't download any file with the csv list, or maybe I'm doing something wrong   

[](http://www.imagebam.com/image/efd9ce541297130)
## Post #9
- Username: Rua
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-04T23:32:56+00:00
- Post Title: Mobile Game Asset Download

Python 3.6 script to download 

> THE iDOLM@STER Cinderella Girls: Starlight Stage
follow this guide to get your csv file
[viewtopic.php?f=16&t=15582&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=15582&start=30)
Then use this python script to have it download all files on pc.
You can edit the script to download ios or android files by un commenting the script.
just make sure your command prompt directory and the csv file are the same folder.
[imas.7z](https://xentaxbackup.github.io/file/13075_imas.7z)
## Post #10
- Username: wanglata
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-05T00:15:57+00:00
- Post Title: Mobile Game Asset Download

Here is a script that will auto decompress the files for you.
you need to do pip install lz4 for this script to work.
[imas-lz4.7z](https://xentaxbackup.github.io/file/13076_imas-lz4.7z)
## Post #11
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2017-07-05T14:02:53+00:00
- Post Title: Mobile Game Asset Download

I managed to get what I think is the csv for idolm@ster million live

```
http://td-assets.bn765.com/1/production/5.6/Android/6b976a4c875a1984592a66b621872ce44c944e72.data
```


```
User-Agent: Dalvik/1.6.0 (Linux; U; Android 4.4.2; HUAWEI GRA-CL00 Build/HUAWEIGRA-CL00)
X-Unity-Version: 5.6.2f1
Connection: Keep-Alive
Host: td-assets.bn765.com
```


I can see the file names inside but it doesn't look like a conventional csv file
## Post #12
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-07-06T23:04:10+00:00
- Post Title: Mobile Game Asset Download

So once we have all the unity3d files downloaded, what do we do with them? i cant seem to get anything out of them with unity studio
## Post #13
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-07-06T23:39:20+00:00
- Post Title: Mobile Game Asset Download

wait was i even supposed to get .unity3d files or did i mess up somewhere?
## Post #14
- Username: jpnvrh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 14, 2016 12:38 pm
- Post datetime: 2017-07-07T12:07:12+00:00
- Post Title: Mobile Game Asset Download

> Reply from chrrox
>
> Here is a script that will auto decompress the files for you.
you need to do pip install lz4 for this script to work.
[Screenshot (151).png](https://xentaxbackup.github.io/file/13084_Screenshot (151).png)
## Post #15
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-07T19:13:35+00:00
- Post Title: Mobile Game Asset Download

just remove any python you have installed.
then install [https://www.python.org/downloads/release/python-361/](https://www.python.org/downloads/release/python-361/)
to c:\python36
then open a command prompt
change to the directory
C:\Python36\Scripts
and type
pip install lz4.
The errors you got have nothing to do with the scripts I made just a problem with your install of python.
you can always use the non lz4 script and decompress the files after.
## Post #16
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-07-08T15:09:08+00:00
- Post Title: Re: Mobile Game Asset Download

Or if you guy feeling too hard with chrrox's script, you can drag manual your file into my CGSS_lz4.exe  
[CGSS_lz4.zip](https://xentaxbackup.github.io/file/13088_CGSS_lz4.zip)
## Post #17
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-07-09T22:53:23+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Python 3.6 script to download 
THE iDOLM@STER Cinderella Girls: Starlight Stage
follow this guide to get your csv file
viewtopic.php?f=16&t=15582&start=30
Then use this python script to have it download all files on pc.
You can edit the script to download ios or android files by un commenting the script.
just make sure your command prompt directory and the csv file are the same folder.

I tried to use this python script on my csv, but this is the error I got:

Can you help please?

I have the csv in the same folder. I also have Python 3.6.
## Post #18
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-10T00:21:50+00:00
- Post Title: Re: Mobile Game Asset Download

make sure you decompress the csv with the quickbms script and export it with the windows character return.
try opening the csv file in a csv editor and post a screenshot of it.
I use csved [http://csved.sjfrancke.nl/](http://csved.sjfrancke.nl/)
## Post #19
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2017-07-10T01:52:25+00:00
- Post Title: Re: Mobile Game Asset Download

Is there a file that is inside a apk that has a code that does https calls, we could get the urls way more easier.
## Post #20
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-07-10T04:39:37+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> make sure you decompress the csv with the quickbms script and export it with the windows character return.
try opening the csv file in a csv editor and post a screenshot of it.
I use csved http://csved.sjfrancke.nl/

I can't find what the windows character return is orz. I feel like an idiot. Also I think its already decompressed? I'd try n get a screenshot but the program is taking forever to load the csv, and I gotta get off.     Perhaps since I haven't done the whole character return thingy? Idk. I got it to load in another program (Took forever as well), but its all in one whole row and looks like an eyesore to pick out whats what.
## Post #21
- Username: alictzelt
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-10T12:30:06+00:00
- Post Title: Re: Mobile Game Asset Download

did you get this far?

after this all you need to do is

the newline character is set to windows right there.
## Post #22
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2017-07-10T14:07:15+00:00
- Post Title: Re: Mobile Game Asset Download

Ensemble stars uses preload for loading up files, it generates a random ep each time I open the app, could this be the csv file of the game?

http://stars.hekk.org/assets/preload?ec=guXM4tMkNvS1s5E2oShpPJdcIgoJnM4AgZ6gvzyoKYo6rs8yM4WfKWOJ0Go8KdW9&ep=Generated ep=Android&format=mpac&version=1.2.34&device=android device type

I brought in two sample files in a rar file, go check those out.
[Ensemblestars preloadfiles.rar](https://xentaxbackup.github.io/file/13094_Ensemblestars preloadfiles.rar)
## Post #23
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-07-11T02:47:02+00:00
- Post Title: Re: Mobile Game Asset Download

what do you all use for getting the stuff out of the untiy3d files? none of the tools i usually use work on them
## Post #24
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2017-07-11T05:11:18+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Python 3.6 script to download 
THE iDOLM@STER Cinderella Girls: Starlight Stage
follow this guide to get your csv file
viewtopic.php?f=16&t=15582&start=30
Then use this python script to have it download all files on pc.
You can edit the script to download ios or android files by un commenting the script.
just make sure your command prompt directory and the csv file are the same folder.

I had followed until this step and decompres the file manually, but I can't get the models both using quickbms and unity studio. Only character pictures and some bg images viewed.
## Post #25
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-11T08:57:36+00:00
- Post Title: Re: Mobile Game Asset Download

can you open
3d_tx_body0001_0_0_0.unity3d

and
3d_md_body0001_0_0_0.unity3d

in unitystudio version 0.7.0.0?
## Post #26
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2017-07-11T12:17:31+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> 
unitystudio version 0.7.0.0?

Before I used v0.5, 
Now is work using v0.7
## Post #27
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-07-13T11:21:30+00:00
- Post Title: Re: Mobile Game Asset Download

Thanks for the CGSS python code, it can work on my PC.

And here is another CY game i play, named "alternative girls".
There are so many models in game, i like them     ->_->
[https://play.google.com/store/apps/deta ... .alternajp](https://play.google.com/store/apps/details?id=jp.co.cyberagent.alternajp)

It is very easy to extarct the model, using Unity Stdio.
But i dont know how to get the resource. 
Unlike CGSS, i didn't find "mainfest" in game dir (so is "million lives theater days").

Does anyone know how to do ?
## Post #28
- Username: Meipon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 18, 2017 6:19 pm
- Post datetime: 2017-07-18T10:25:32+00:00
- Post Title: Re: Mobile Game Asset Download

Hey need some help, follow it all but then I start CGSS up nothing pops up fiddler ;3;


Any that can help me through to rip from CGSS and Million Live?
## Post #29
- Username: alictzelt
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-19T22:08:21+00:00
- Post Title: Re: Mobile Game Asset Download

ガ ー ル フ レ ン ド (♪)
Music Girlfriend
Here is a tool to download all the files from this game.
The files are normal unity3d files.


[musicGF.zip](https://xentaxbackup.github.io/file/13122_musicGF.zip)
## Post #30
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-07-20T06:36:07+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> ガ ー ル フ レ ン ド (♪)
Can you please make a tool to download all files from the game called "DC Legends"? Please? 
I tried to do that by myself but i stuck at Public IP stage.
## Post #31
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-07-20T10:44:05+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> ガ ー ル フ レ ン ド (♪)
Music Girlfriend
Excuse me chrrox, can you check for Im@s MillionLive Theaterday? I think this is game's csv

```
http://td-assets.bn765.com/1/production/5.6/Android/6b976a4c875a1984592a66b621872ce44c944e72.data
```
## Post #32
- Username: Meipon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 18, 2017 6:19 pm
- Post datetime: 2017-07-20T18:15:12+00:00
- Post Title: Re: Mobile Game Asset Download

Can anyone either make a full tutorial to rip from CGSS and ML or sent me the files or so ;3;? Wanna use it for MMD
## Post #33
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-20T22:01:39+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Meipon
>
> Can anyone either make a full tutorial to rip from CGSS and ML or sent me the files or so ;3;? Wanna use it for MMD
[viewtopic.php?f=16&t=15582&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=15582&start=30)

what part are you stuck on i give the manifest file url you need for everything?
## Post #34
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-07-21T06:39:54+00:00
- Post Title: Re: Mobile Game Asset Download

chrrox, thanks for the tools. Though I getting 'unknow module' error when run python script from this post: [viewtopic.php?p=132292#p132292](http://forum.xentax.com/viewtopic.php?p=132292#p132292)
Can you help me with this?

also, I tried download all assets from deer hunter 2017 for android but can't find game related links in fiddler. is this tutorial work for this game?
## Post #35
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-07-21T18:38:33+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Tosyk
>
> chrrox, thanks for the tools. Though I getting 'unknow module' error when run python script from this post: viewtopic.php?p=132292#p132292
Can you help me with this?

I had the same error at first, make sure you did this [https://forum.xentax.com/viewtopic.php?p=131989#p131989](https://forum.xentax.com/viewtopic.php?p=131989#p131989) and have python 3.6
## Post #36
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2017-07-21T20:54:10+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from o0Crofty0o
>
> Tosyk wrote:chrrox, thanks for the tools. Though I getting 'unknow module' error when run python script from this post: viewtopic.php?p=132292#p132292
Can you help me with this?I had the same error at first, make sure you did this https://forum.xentax.com/viewtopic.php?p=131989#p131989 and have python 3.6I actually tried but got error when install lz4 module: 
```
Command "c:\python36\python.exe -u -c "import setuptools, tokenize;__file__='C:\\Users\\Username\\AppData\\Local\\Temp\\pip-build-1gdxxa_w\\lz4\\setup.py';f=getattr(tokenize, 'open', open)(__file__);code=f.read().replace('\r\n', '\n');f.close();exec(compile(code, __file__, 'exec'))" install --record C:\Users\Username\AppData\Local\Temp\pip-42mfzv3t-record\install-record.txt --single-version-externally-managed --compile" failed with error code 1 in C:\Users\Username\AppData\Local\Temp\pip-build-1gdxxa_w\lz4\
```
not sure what to do next
## Post #37
- Username: alictzelt
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-24T00:14:25+00:00
- Post Title: Re: Mobile Game Asset Download

Here is THE iDOLM@STER: Million Live!
Just run the python script.
it auto downloads the manifest for you.

[MillionLive.zip](https://xentaxbackup.github.io/file/13138_MillionLive.zip)
## Post #38
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2017-07-24T02:38:15+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Here is THE iDOLM@STER: Million Live!
Just run the python script.
it auto downloads the manifest for you.

Thanks...this is what I looking for.

Since my fiddle not work catch web debugger, I rely on what you share.
## Post #39
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-07-24T14:10:07+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Here is THE iDOLM@STER: Million Live!
Just run the python script.
it auto downloads the manifest for you.
Oh right, my life is complete      Tks so much chrrox.
## Post #40
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-07-24T22:27:47+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Here is THE iDOLM@STER: Million Live!
Just run the python script.
it auto downloads the manifest for you.
 for some reason the script for me does not work! but the others do  it simply closes down after 2 seconds
## Post #41
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-24T22:41:38+00:00
- Post Title: Re: Mobile Game Asset Download

show me your command prompt running it.
also delete any sub folders in the directory you run it from.
## Post #42
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-07-24T22:58:24+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> show me your command prompt running it.
also delete any sub folders in the directory you run it from.
here
## Post #43
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-07-24T23:05:06+00:00
- Post Title: Re: Mobile Game Asset Download

AND btw! did you get the game to run in Emulator? for me is all pink    and i saw a redit post that it says  the game  does not want to run on  emulators
## Post #44
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-24T23:37:30+00:00
- Post Title: Re: Mobile Game Asset Download

open a normal command prompt.
then run it like this
C:\Python36\python.exe e:\Games\MillionLive.py

this is the python I am running.
Python 3.6.1 (v3.6.1:69c0db5, Mar 21 2017, 18:41:36) [MSC v.1900 64 bit (AMD64)] on win32
## Post #45
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-24T23:38:02+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from mircea
>
> AND btw! did you get the game to run in Emulator? for me is all pink    and i saw a redit post that it says  the game  does not want to run on  emulators
the game does not run in emulators you can click to get past the main screen but it stays pink.
## Post #46
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-07-24T23:51:17+00:00
- Post Title: Re: Mobile Game Asset Download

LoL it works but with "#import lz4" because it says no module lz4. Thank you!
## Post #47
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-07-27T09:21:22+00:00
- Post Title: Re: Mobile Game Asset Download

hey is there an easier way to download the latest character database from imas starlight stage? im having trouble with the emulator+fiddler combo....the wifi network im on is a public one so i cant really change my port as far as i know
## Post #48
- Username: Meipon
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 18, 2017 6:19 pm
- Post datetime: 2017-07-27T15:40:44+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Meipon wrote:Can anyone either make a full tutorial to rip from CGSS and ML or sent me the files or so ;3;? Wanna use it for MMD
viewtopic.php?f=16&t=15582&start=30

what part are you stuck on i give the manifest file url you need for everything?
When I use Fiddler it won't pop up and have checked I did everything right still it won't show up ono
## Post #49
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-08-09T13:30:31+00:00
- Post Title: Re: Mobile Game Asset Download

I'm not sure whether this is the right topic but I got a problem with Million Live files
I can't get the textures to show up correctly, though the meshes are working well, what could be wrong?
## Post #50
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-08-09T20:54:15+00:00
- Post Title: Re: Mobile Game Asset Download

update unity studio.
## Post #51
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-08-10T07:06:04+00:00
- Post Title: Re: Mobile Game Asset Download

i have the latest one though 0.7.0.0
## Post #52
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-15T15:01:29+00:00
- Post Title: Re: Mobile Game Asset Download

The MLTD code work well on my PC, 3Q.

The newest mainfest can be found in game dir(android).
But i find it that the key(hash) is different from before. The code not work on the newest mainfest.

Here is the mainfest your code get.
[https://drive.google.com/file/d/0B_EOJK ... JtUkk/view](https://drive.google.com/file/d/0B_EOJKLZ9WswRHZrLUdQV3JtUkk/view)

Here is the newest mainfest i found
[https://drive.google.com/file/d/0B_EOJK ... 1YWEU/view](https://drive.google.com/file/d/0B_EOJKLZ9WswYXp0dUJSOC1YWEU/view)

waiting for help..plz
## Post #53
- Username: Splashy
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 17, 2017 10:13 pm
- Post datetime: 2017-08-17T16:49:20+00:00
- Post Title: Re: Mobile Game Asset Download

I'm trying to open up the unity3d files after getting them from the script but when I try to open or extract them with Unity Studio 0.7 nothing happens or gets extracted
## Post #54
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-19T16:18:48+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wanglata
>
> 
Excuse me chrrox, can you check for Im@s MillionLive Theaterday? I think this is game's csv
Code: Select allhttp://td-assets.bn765.com/1/production/5.6/Android/6b976a4c875a1984592a66b621872ce44c944e72.data

Can you tell me how you get the newest mainfest url/file?

I find it in game folder, but worry it is changed.
And the python code doesn't work on the newest mainfest. Do you?
## Post #55
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-23T17:54:05+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from z22901206
>
> 

Can you tell me how you get the newest mainfest url/file?

I find it in game folder, but worry it is changed.
And the python code doesn't work on the newest mainfest. Do you?
Script still work dude, check again pls  
[Screenshot (73).jpg](https://xentaxbackup.github.io/file/13241_Screenshot (73).jpg)
## Post #56
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-28T05:24:43+00:00
- Post Title: Re: Mobile Game Asset Download

Is this possible to use this method to obtain all assets from mobile game called "Avengers Academy"? 
I can't try it,because i have no access to my laptop + i stuck in "Public Ip" stage
 Thanks in advance!
## Post #57
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-09-04T04:46:22+00:00
- Post Title: Re: Mobile Game Asset Download

Hello, is it possible to get the IDOLM@STER SideM assets this way? Is it like Starlight Stage?
## Post #58
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-09-04T13:52:05+00:00
- Post Title: Re: Mobile Game Asset Download

@chrrox I think it is SideM LoS manifest, check it pls, sir  

```
https://d2qkdj9w29igl.cloudfront.net/v1/2017082901-GQDAMNLZMRK3VrYGkTGgHt20zxIb16Z9/asset_bundles/android/android
```
## Post #59
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-09-09T03:47:07+00:00
- Post Title: Re: Mobile Game Asset Download

Whenever I try to open the unity3d files in unity studio it displays them all empty even though their filesize would suggest otherwise....,im on the latest version of unity studio, so i`m not sure what i`m doing wrong

I`m also having trouble finding the models in the million live files? theres so many folders, i`m not sure which one has them
## Post #60
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-09-12T05:08:47+00:00
- Post Title: Re: Mobile Game Asset Download

Is possible get the Manifest of Super Robot Wars X-Ω, i can't run this game and I want extract Kirarin Robo
## Post #61
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-09-14T05:00:40+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wanglata
>
> z22901206 wrote:

Can you tell me how you get the newest mainfest url/file?

I find it in game folder, but worry it is changed.
And the python code doesn't work on the newest mainfest. Do you?
Script still work dude, check again pls

Actually the code works, but i want the latest files, according to the latest mainfest.
When the game upgraded, the mainfest url may change.

Thought i can find the mainfest file in game folder, but the code didn't work with the mainfest.
Seems that resource url changed, i can't confirm it because the fiddler has something wrong in my computer.

So i wonder someone can rewrite the code to use mainfest file as source, rather than the fixed mainfest url.(just like CGSS code)

Here is the mainfest i got before, not latest one, but later than the code get.
[https://drive.google.com/file/d/0B_EOJK ... 1YWEU/view](https://drive.google.com/file/d/0B_EOJKLZ9WswYXp0dUJSOC1YWEU/view)
## Post #62
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-09-16T11:59:15+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from z22901206
>
> 

Actually the code works, but i want the latest files, according to the latest mainfest.
When the game upgraded, the mainfest url may change.

Thought i can find the mainfest file in game folder, but the code didn't work with the mainfest.
Seems that resource url changed, i can't confirm it because the fiddler has something wrong in my computer.

So i wonder someone can rewrite the code to use mainfest file as source, rather than the fixed mainfest url.(just like CGSS code)

Here is the mainfest i got before, not latest one, but later than the code get.
https://drive.google.com/file/d/0B_EOJK ... 1YWEU/view
The script still work, but you need edit manifestURL with lastest manifest file. 


```
https://td-assets.bn765.com/2200/production/5.6/Android/9977ab6a44fa1af0889d3c4d66c62d3511dd2d7a.data
```
## Post #63
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-09-17T03:53:12+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wanglata
>
> 
Code: Select allhttps://td-assets.bn765.com/2200/production/5.6/Android/9977ab6a44fa1af0889d3c4d66c62d3511dd2d7a.data

How do you get this manifestURL ? Fiddler?
Anyway the code work again, thx
## Post #64
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-09-17T21:51:19+00:00
- Post Title: Re: Mobile Game Asset Download

I have some problems with CGSS Script by Chroxx, only download certain number of assets, I've tried with the full manifest and with a edited manifest, anyone can help me
## Post #65
- Username: wanglata
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-09-28T00:36:18+00:00
- Post Title: Re: Mobile Game Asset Download

Here is the download list for THE iDOLM@STER SideM: LIVE ON ST@GE!
[123456.7z](https://xentaxbackup.github.io/file/13350_123456.7z)
## Post #66
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-10-04T02:05:02+00:00
- Post Title: Re: Mobile Game Asset Download

Ive tried to get the manifest of Super Robot Wars X omega, but I cant find it
## Post #67
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2017-11-05T09:48:08+00:00
- Post Title: Re: Mobile Game Asset Download

Sorry, chrrox.

I'm trying to get CGSS csv file, but I can't.
I've done everything I can try.

1st, I did step by step from this tutorial >> [viewtopic.php?f=16&t=15582&start=30](http://forum.xentax.com/viewtopic.php?f=16&t=15582&start=30)
* I use the URL you posted. (Not the latest one)

```
http://storage.game.starlight-stage.jp/dl/10027505/manifests/Android_AHigh_SHigh
```

The response is 200 (OK)
Okay, I click the result in the left panel of fiddler,
"Save/Response/Entire Response" as xx_Response.txt
and
"Save/Response/Response Body" as xx_.txt
[](https://imgur.com/PiXDBLg)

Then, try to use your quickbms code but it give me an error & nothing output.

[](https://imgur.com/JlSlN9g)

Yeah, both file...

DEAD END.

-----
2nd, I tried with 3d_chara_body_0001.unity3d (b094b394672f99c1ab1c952093727cb6)
^
I get hash code from somewhere in google....
Execute in Fiddler and get the response!

[](https://imgur.com/2CnMHA8)

Save the entire response and response body as above one.
Then, use quickbms........ same error...

[](https://imgur.com/X2THuH3)

I tried to use Unity Studio or Asset Bundle Extractor to open it, but end with failure.

Another DEAD END.

Did I do anything wrong?
## Post #68
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-12-02T08:32:14+00:00
- Post Title: Re: Mobile Game Asset Download

will this method work on Yu-Gi-Oh!! Duel Links?
## Post #69
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-12-12T12:01:10+00:00
- Post Title: Re: Mobile Game Asset Download

@chrrox  chrrox  can you see if this games content can be downloadable easyer?  [http://pc-play.games.dmm.co.jp/play/honeyx/](http://pc-play.games.dmm.co.jp/play/honeyx/)  I only manage to get the cache files and search in them for the models that I loaded  cuz  i can no longer use the fiddler to search for links  becouse for some reason is broken(no longer works like before with anygame that I play)  .
## Post #70
- Username: Paul Wang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 10, 2018 10:34 pm
- Post datetime: 2018-01-12T04:27:52+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Axess
>
> Sorry, chrrox.

I'm trying to get CGSS csv file, but I can't.
I've done everything I can try.

1st, I did step by step from this tutorial >> viewtopic.php?f=16&t=15582&start=30
* I use the URL you posted. (Not the latest one)
Code: Select allhttp://storage.game.starlight-stage.jp/dl/10027505/manifests/Android_AHigh_SHigh
The response is 200 (OK)
Okay, I click the result in the left panel of fiddler,
"Save/Response/Entire Response" as xx_Response.txt
and
"Save/Response/Response Body" as xx_.txt


Then, try to use your quickbms code but it give me an error & nothing output.



Yeah, both file...

DEAD END.

-----
2nd, I tried with 3d_chara_body_0001.unity3d (b094b394672f99c1ab1c952093727cb6)
^
I get hash code from somewhere in google....
Execute in Fiddler and get the response!



Save the entire response and response body as above one.
Then, use quickbms........ same error...



I tried to use Unity Studio or Asset Bundle Extractor to open it, but end with failure.

Another DEAD END.

Did I do anything wrong?

They seem LZ4 deflated. Inflate them by LZ4 tool like "CGSS_lz4" provided on Sat Jul 08, 2017 by wanglata.
## Post #71
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2018-01-20T04:30:35+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Paul Wang
>
> They seem LZ4 deflated. Inflate them by LZ4 tool like "CGSS_lz4" provided on Sat Jul 08, 2017 by wanglata.
Try to inflate it by using wanglata's tool. But still error. orz
## Post #72
- Username: CardboardBox
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Mar 01, 2018 3:40 pm
- Post datetime: 2018-03-01T08:32:38+00:00
- Post Title: Re: Mobile Game Asset Download

Nice tutorial, but unfortunately, in order to port forward on Xfinity routers now, you need to log-in on another website using your information and I don't have that, long story short, it's my brothers and he forgot it.

I'm trying to get game data from 歌マクロス スマホDeカルチャー (Uta Macross Sma-Pho De-Culture) Which is also another problem, it seems the game doesn't like Nox, I've turned off Root in the settings and tried everything I can think of, it seems to be the launcher or just Nox itself, it gives me an error trying to launch the game when I try to download the data.

If there's another way to do this with Remix OS or something else, I'd love to know, until then, I'm just stuck here trying to get log-in info for Comcast BS ;-;
## Post #73
- Username: WM86
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Nov 06, 2017 10:57 pm
- Post datetime: 2018-03-23T09:01:28+00:00
- Post Title: Re: Mobile Game Asset Download

TIM图片20180323163226.png (169.47 KiB) Viewed 443 times
## Post #74
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-03-23T23:17:19+00:00
- Post Title: Re: Mobile Game Asset Download

That game does not work on emulators it is programmed to block them.
## Post #75
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-03-25T09:19:23+00:00
- Post Title: Re: Mobile Game Asset Download

I try this game Tokimeki Idol (ときめきアイドル)
[https://apkpure.com/id/%E3%81%A8%E3%81% ... kimekiidol](https://apkpure.com/id/%E3%81%A8%E3%81%8D%E3%82%81%E3%81%8D%E3%82%A2%E3%82%A4%E3%83%89%E3%83%AB/jp.konami.tokimekiidol)



So I found this link
[https://auy-dl.akamaized.net/production ... 0325074053](https://auy-dl.akamaized.net/production/Android/00000001/bundle_info.bytes?t=20180325074053)

Is this game asset?
## Post #76
- Username: alictzelt
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-03-25T12:05:35+00:00
- Post Title: Re: Mobile Game Asset Download

its encrypted
but here are the links
[https://pastebin.com/raw/UYXDa3nw](https://pastebin.com/raw/UYXDa3nw)
## Post #77
- Username: kitayume
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 27, 2017 10:14 am
- Post datetime: 2018-03-30T12:15:46+00:00
- Post Title: Re: Mobile Game Asset Download

hi umm I want to know how to extract AssetBundleManifest from games live IDOLMASTER SideM Live On Stage?
It doesn't have any hash code...
[QQ截图20180330201612.png](https://xentaxbackup.github.io/file/14140_QQ截图20180330201612.png)
## Post #78
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-04-03T14:09:35+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> its encrypted
but here are the links
https://pastebin.com/raw/UYXDa3nw

Thanks... by the way how to read encrypted?
I also found game asset file but can't read on Unity Studio and Notepad++
Like this game


[https://apkpure.com/jp/青空アンダーガールズ](https://apkpure.com/jp/%E9%9D%92%E7%A9%BA%E3%82%A2%E3%83%B3%E3%83%80%E3%83%BC%E3%82%AC%E3%83%BC%E3%83%AB%E3%82%BA)！/com.square_enix.android_googleplay.AozoraUnderGirls

Here links I found
[http://cache.aogirl.jp/AssetBundles/And ... 0327135128](http://cache.aogirl.jp/AssetBundles/Android/Android?hash=?time=20180327135128)
[http://cache.aogirl.jp/AssetBundles/And ... 0327135120](http://cache.aogirl.jp/AssetBundles/Android/AssetBundleList.json?time=20180327135120)
## Post #79
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2018-04-06T19:51:53+00:00
- Post Title: Re: Mobile Game Asset Download

Hi guys i tried getting the MillionLive.py to download the file by using the command

but i get an error
"Traceback (most recen call last):
File "G:ML\MillionLive.py" Line 40, in <module>
with open ('MillionLive\\' + 'MillionLive.manifest' , "rb") as f:

FileNotFoundError:  (Erno 2] No such file or directory: MillionLive\\MillionLive.manifest'  "

Does anyone have an idea here ?

i'm completely stuck...thanks
[ML.png](https://xentaxbackup.github.io/file/14172_ML.png)
## Post #80
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2018-04-08T14:52:33+00:00
- Post Title: Re: Mobile Game Asset Download

Okay... well i managed to get the game (Idolmaster MLTD) to work and run on a emulator

is there anything with it that can  help me get the file using the emulator ?
[Sans titre.png](https://xentaxbackup.github.io/file/14183_Sans titre.png)
## Post #81
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-04-08T15:34:43+00:00
- Post Title: Re: Mobile Game Asset Download

Most emulators have a file transfer feature.
You can use a tool like es file explorer to move those files to the shared folder on your pc.
## Post #82
- Username: Tsunani
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Aug 24, 2014 5:25 pm
- Post datetime: 2018-04-08T17:12:25+00:00
- Post Title: Re: Mobile Game Asset Download

Well i tried but i just can't get it to work

im using Mumu Android Emulator

i just want one model from it thats all..

the only thing i could make is to save the files as pdf..
[pdf.png](https://xentaxbackup.github.io/file/14184_pdf.png)
## Post #83
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-04-09T13:55:29+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Tsunani
>
> Okay... well i managed to get the game (Idolmaster MLTD) to work and run on a emulator

is there anything with it that can  help me get the file using the emulator ?

Other ways upload the files using download file hosting like mediafire or mega on your emulator. Then download to your computer.
## Post #84
- Username: SaberCF
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jan 13, 2018 5:18 am
- Post datetime: 2018-05-13T07:36:50+00:00
- Post Title: Re: Mobile Game Asset Download

How to get the newest manifest's URL of MLTD?
## Post #85
- Username: GarrodRain
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 16, 2018 5:02 pm
- Post datetime: 2018-05-16T09:33:44+00:00
- Post Title: Re: Mobile Game Asset Download

<Deleted>
## Post #86
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-19T02:51:35+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone know how to get models from Uta Macross Smartphone Deculture? Kinda desperate since the game won't work in Nox
## Post #87
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-05-19T14:55:26+00:00
- Post Title: Re: Mobile Game Asset Download

the game works in bluestacks.
## Post #88
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2018-05-21T10:49:12+00:00
- Post Title: Re: Mobile Game Asset Download

can anyone help me get the latest database for imas starlight stage? i cant get the method to grab it to work at all
## Post #89
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-21T14:36:17+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> the game works in bluestacks.
I ain't getting any links in Fiddler with Bluestacks though. It's like it doesn't detect anything Bluestacks does, the game downloads the model data but Fiddler doesn't say where that data came from.
## Post #90
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-06-02T23:32:08+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> the game works in bluestacks.

Hi chhrox, I play Uta Macross and got cache files .XAB

do you know how to open that file?
## Post #91
- Username: Ziella
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon Jun 04, 2018 12:45 pm
- Post datetime: 2018-06-07T10:50:33+00:00
- Post Title: Re: Mobile Game Asset Download

Decided to give this a try and I tried with a few games with success.
So I finally decided to try with a game I've been wanting to get some assets from, Sengoku Asuka ZERO.
I was able to figure out a downloadable url for a zip file.

```
http://asukazero.oratta.net/multi/product/dl/manual/image/weapon/c_sd11104010.png
```

I can't seem to find any kind of database or anything though, and the only only links I could find are these two.
## Post #92
- Username: DarkBlueLagoon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jun 15, 2018 9:12 pm
- Post datetime: 2018-06-15T13:14:12+00:00
- Post Title: Re: Mobile Game Asset Download

the hack file site thing doesn't work it seems

I need help on this stuff

Reach me on my discord Lagoon#0001
## Post #93
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2018-07-05T06:27:03+00:00
- Post Title: Re: Mobile Game Asset Download

GAME: 拡張少女系トライナリー
[https://apkpure.com/jp/%E6%8B%A1%E5%BC% ... o.Kakutora](https://apkpure.com/jp/%E6%8B%A1%E5%BC%B5%E5%B0%91%E5%A5%B3%E7%B3%BB%E3%83%88%E3%83%A9%E3%82%A4%E3%83%8A%E3%83%AA%E3%83%BC/jp.co.koeitecmo.Kakutora)
[https://play.google.com/store/apps/deta ... a&hl=en_US](https://play.google.com/store/apps/details?id=jp.co.koeitecmo.Kakutora&hl=en_US)

This game is coming to close, i just wanna make a backup for it.
We can also get the resource by URL directly.
But, i didn't find anything like CSV or mainfest, anyone can help?
## Post #94
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-07-15T14:45:22+00:00
- Post Title: Re: Mobile Game Asset Download

@z22901206
here is the file list
[https://d00030400.gamecity.ne.jp/a_girl ... s_crc.json](https://d00030400.gamecity.ne.jp/a_girl/master-android/kakutora_files_crc.json)
you download the files labeled assetBundle.
example
[{"assetBundle":"battle_00battletextures.unity3d","crc":2888919526,
so download link is
[https://d00030400.gamecity.ne.jp/a_girl ... E6.unity3d](https://d00030400.gamecity.ne.jp/a_girl/master-android/battle_00battletextures@AC3169E6.unity3d)
broken down to see easier

1. - URL Base:                                    [https://d00030400.gamecity.ne.jp/a_girl/master-android/](https://d00030400.gamecity.ne.jp/a_girl/master-android/)
2. - Base FileName:                            battle_00battletextures
3. - @ symbol + crc converted to hex: @AC3169E6
4. - original file extension:                  .unity3d

Attached python script do download files.

[](https://s15.postimg.cc/91lqq076j/curan_0060.png)[](https://s15.postimg.cc/hwml0jj4b/curan_0311.png)[](https://s15.postimg.cc/5ur76epbf/curan_0476.png)[](https://s15.postimg.cc/79srv4ior/curan_0602.png)[](https://s15.postimg.cc/kdyc7tq63/curan_0603.png)
[ARGirlsTrinary.7z](https://xentaxbackup.github.io/file/14610_ARGirlsTrinary.7z)
## Post #95
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2018-07-16T15:37:01+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> @z22901206
here is the file list
...

Seems it is a little more complicated than MLTD.
Thanks for your script, and the explaining.
## Post #96
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-07-16T23:05:43+00:00
- Post Title: Re: Mobile Game Asset Download

少女前線 
Girls' Frontline
[http://sncdn.imtxwy.com/android/2018071 ... llData.dat](http://sncdn.imtxwy.com/android/20180712FE16F39849E8B2669AC7AB1C17220C46AllData.dat)
this is just a zip file extract it with 7zip.
[](https://s15.postimg.cc/ewbpk01rd/pic_svd_305-merged.png)[](https://s15.postimg.cc/62kt2heo9/pic_welrod_2103_d-merged.png)
## Post #97
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-07-16T23:16:13+00:00
- Post Title: Re: Mobile Game Asset Download

프리징
FreezingExtension
[](https://s15.postimg.cc/dju0hqei3/cut_aoi_back_1.png)[](https://s15.postimg.cc/xeg23v1ff/loading_character_35_texture.png)
Download Script attached
[freezingext.7z](https://xentaxbackup.github.io/file/14621_freezingext.7z)
## Post #98
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-07-22T12:59:17+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Tsunani
>
> Hi guys i tried getting the MillionLive.py to download the file by using the command

but i get an error
"Traceback (most recen call last):
File "G:ML\MillionLive.py" Line 40, in <module>
with open ('MillionLive\\' + 'MillionLive.manifest' , "rb") as f:

FileNotFoundError:  (Erno 2] No such file or directory: MillionLive\\MillionLive.manifest'  "

Does anyone have an idea here ?

i'm completely stuck...thanks

Here's the manifest file.
[https://drive.google.com/file/d/1cFODXm ... ResSY/view](https://drive.google.com/file/d/1cFODXmGeTIJjvD4IE8_RHehr-HNResSY/view)

Unzip the contents and copy the manifests file to the folder where you want to save the assets.
For example:    C:\MillionLive\

After copying the manifests file to your folder, run the Python script again.
Make sure your Python script file is saved in the folder above "MillionLive\"

In case anyone is still looking for it, here's the "The Idolmaster Million Live" assets URL:
[http://td-assets.bn765.com/2200/product ... d2d7a.data](http://td-assets.bn765.com/2200/production/5.6/Android/9977ab6a44fa1af0889d3c4d66c62d3511dd2d7a.data)
## Post #99
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-07-22T13:17:57+00:00
- Post Title: Re: Mobile Game Asset Download

Hello there,

I was able to grab the Million Live files.
There are like literally a "million" files : P

Can someone tell me where I can find the character 3D meshes?

Thank you!
## Post #100
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2018-07-22T17:29:23+00:00
- Post Title: Re: Mobile Game Asset Download

I can't grab the million live's files.
I run script w/ above latest url replaced in script.
The script download manifest file and created many folder under MillionLive\ but no file download after that.
The script end without failure.
How to solve this problem?
## Post #101
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-07-23T12:49:25+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Axess
>
> I can't grab the million live's files.
I run script w/ above latest url replaced in script.
The script download manifest file and created many folder under MillionLive\ but no file download after that.
The script end without failure.
How to solve this problem?

Hello,
Maybe I can help.
Trying following these instructions.

1) Create the following folder:
C:\Million\MillionLive

2) Download the manifest zip file using the URL below:
[https://drive.google.com/file/d/1cFODXm ... ResSY/view](https://drive.google.com/file/d/1cFODXmGeTIJjvD4IE8_RHehr-HNResSY/view)

3) Extract the contents of the zip file to C:\Million\MillionLive

4) Download the modified Python script zip file using the URL below:
[https://drive.google.com/file/d/1EITGev ... HRKuV/view](https://drive.google.com/file/d/1EITGev_xkCXUUsPKDqkGQ4UwJzKHRKuV/view)

5) Extract the contents of the zip file to C:\Million

6) Uninstall any existing installation of Python

7) Download Python 3.6.0 using the URL below:
[https://www.python.org/ftp/python/3.6.0 ... -3.6.0.exe](https://www.python.org/ftp/python/3.6.0/python-3.6.0.exe)

8) Run "python-3.6.0.exe" to install Python 3.6.0 (32-bit)

9) When prompted, specify to install Python to the following folder:
C:\Python36

10) After Python has finished installing, open a Command Prompt window

11) In Command Prompt, type: cd C:\Python36\Scripts

12) In Command Prompt, type: pip install lz4
This will download and install the lz4 module for Python

13) In Command Prompt, type: cd C:\Million

14) In Command Prompt, type: MillionLive1.py
If you performed all the steps correctly, this will run the Python script and download the assets to C:\Million\MillionLive

Did it work?
## Post #102
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2018-07-23T16:18:17+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from samsonyu
>
> Axess wrote:I can't grab the million live's files.
I run script w/ above latest url replaced in script.
The script download manifest file and created many folder under MillionLive\ but no file download after that.
The script end without failure.
How to solve this problem?

Hello,
Maybe I can help.
Trying following these instructions.

1) Create the following folder:
C:\Million\MillionLive

2) Download the manifest zip file using the URL below:
https://drive.google.com/file/d/1cFODXm ... ResSY/view

3) Extract the contents of the zip file to C:\Million\MillionLive

4) Download the modified Python script zip file using the URL below:
https://drive.google.com/file/d/1EITGev ... HRKuV/view

5) Extract the contents of the zip file to C:\Million

6) Uninstall any existing installation of Python

7) Download Python 3.6.0 using the URL below:
https://www.python.org/ftp/python/3.6.0 ... -3.6.0.exe

 Run "python-3.6.0.exe" to install Python 3.6.0 (32-bit)

9) When prompted, specify to install Python to the following folder:
C:\Python36

10) After Python has finished installing, open a Command Prompt window

11) In Command Prompt, type: cd C:\Python36\Scripts

12) In Command Prompt, type: pip install lz4
This will download and install the lz4 module for Python

13) In Command Prompt, type: cd C:\Million

14) In Command Prompt, type: MillionLive1.py
If you performed all the steps correctly, this will run the Python script and download the assets to C:\Million\MillionLive

Did it work?
It work!
Thank you very much!!   

Now the remaining problem of mirishita are
- where're model asset.
>> I open suspected folder and found some at /cb
- how to convert it back to model format w/ texture, bone, etc. (Using AssetStudio 0.10.0.52 it can export asset to fbx but not  all model bind with texture)
- animation.........

-----
<< Edited >>
Problem:
I used [chrrox's script](http://forum.xentax.com/viewtopic.php?f=29&t=16055&p=131911#p131911) but nothing download....

Using print(BaseException) to debug. it catch exception on

```
myArr = lz4.block.decompress(myFile[16:],size)
```

line.
*Python 3.6 /w lz4 v2.0.2 installed

Solution:
Just import "block" and it solved.

```
from lz4 import block
```


But another problems occur.
1. WinError 10054
-> Doing pool thread got this error.
-> Solution: Don't use pool thread. Slow but it can collect all files w/o overlook.
* Some files are no longer exists, just ignore it. (HTTP 404)

2. Run script again, and it will re-download again
-> Solution suggestion: Save last manifest and check hash

---
Now my problem about deresute is only how to get model and fully use it.
(Body/Head/Bone/Animation/etc.)

Thank you very much.
## Post #103
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-08-04T23:11:20+00:00
- Post Title: Re: Mobile Game Asset Download

Can someone get the baseURL for SideM LIVE ON ST@GE for me, please?
My Fiddler just won't give me any links (idk why, I did everything as the tutorial says)
and I'm trying to use a tool that gets the files automatically ([THIS](https://github.com/starjet/Msute_Cst) one)
but there's no use on using it if I can't get the most recent baseURL :/
Please help, I've been desperately trying to make Fiddler give me the URLs but it just won't work for me.
## Post #104
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-08-05T17:54:38+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from shingenseiji
>
> Can someone get the baseURL for SideM LIVE ON ST@GE for me, please?
My Fiddler just won't give me any links (idk why, I did everything as the tutorial says)
and I'm trying to use a tool that gets the files automatically (THIS one)
but there's no use on using it if I can't get the most recent baseURL :/
Please help, I've been desperately trying to make Fiddler give me the URLs but it just won't work for me.

just launch your emulator and run the game.
then run Process Hacker as admin.
click on the emulator exe (should be the one using the most memory like hdplayer.exe)
then search for strings d2qkdj9w29igl.cloudfront.net
that should get you your url.
## Post #105
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2018-08-08T21:37:23+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Here is a script that will auto decompress the files for you.
you need to do pip install lz4 for this script to work.
so i can get this script to run just fine and it seems to go through the motions but in the end the imas2 folder it creates is totally empty even though it said it downloaded all the files? the non-lz4 script works just fine so i guess its not a huge deal but itd jsut be nice to be able to skip over the decompression step
## Post #106
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-08-09T21:02:22+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> just launch your emulator and run the game.
then run Process Hacker as admin.
click on the emulator exe (should be the one using the most memory like hdplayer.exe)
then search for strings d2qkdj9w29igl.cloudfront.net
that should get you your url.
Ok, this worked perfectly.
Thanks, Chrrox!
## Post #107
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-09-07T10:12:20+00:00
- Post Title: Re: Mobile Game Asset Download

can anyone please get the csv of star ocean anamnesis (jp)?  i already have problem with dns domain. i am worried that  using telerik fiddler will make my internet connection problem worse
## Post #108
- Username: sarahcollins
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 07, 2018 3:46 am
- Post datetime: 2018-09-07T11:23:57+00:00
- Post Title: Re: Mobile Game Asset Download

I have some problems with CGSS Script by Chroxx ((
## Post #109
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2018-09-09T10:00:51+00:00
- Post Title: Re: Mobile Game Asset Download

[removed because im dumb]
## Post #110
- Username: YoKoMiRaKuRu
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Sep 01, 2016 4:15 pm
- Post datetime: 2018-09-30T17:23:47+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone know how to get asset files of "Girls und Panzer: Atsumare! Minna no Senshadou!"?
I've tried my luck through normal installation but only got encrypted files. Fiddler says it gets the files from "ab.regit56.jp".
I don't understand how it works, so i appreciate any help
## Post #111
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-10-25T02:58:32+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from YoKoMiRaKuRu
>
> Does anyone know how to get asset files of "Girls und Panzer: Atsumare! Minna no Senshadou!"?
I've tried my luck through normal installation but only got encrypted files. Fiddler says it gets the files from "ab.regit56.jp".
I don't understand how it works, so i appreciate any help

I tried 1 file
ab.regit56.jp/android/e1ddf6b87b46a1303019c1f04e27086c/831b3b3837a877d3fb7925d0ca57dd3a
I'm sure its 3d model file. I can open it on Unity Studio, but not luck, 3D mesh and textures not displayed also can't extracted. 
Only MonoBehaviour possible extraxted
## Post #112
- Username: mikoamoy
- Rank: n00b
- Number of posts: 12
- Joined date: Sat Oct 11, 2014 6:34 pm
- Post datetime: 2018-10-25T07:13:38+00:00
- Post Title: Re: Mobile Game Asset Download

Can anyone gimme the link for Alternative Girls VR?
[https://play.google.com/store/apps/deta ... .alternajp](https://play.google.com/store/apps/details?id=jp.co.cyberagent.alternajp)
idk how to get the csv files,
also are the unity files encrypted?

only found 
[http://sc-in-f128.1e100.net/](http://sc-in-f128.1e100.net/)

and this is the file from the android data folder,
are they encrypted?
## Post #113
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-11-02T22:16:38+00:00
- Post Title: Re: Mobile Game Asset Download

Here is a script to download all the costumes from ブレイド2 X指定 Honey x Blade 2.
Here is a list of all the costumes [http://honeyxicons.yolasite.com/Costumes.php](http://honeyxicons.yolasite.com/Costumes.php).
Edit the line 

```
pool = ThreadPool(100)
```
 
if your pc can't handle that much and just lower the number.
if you only want one costume un comment line 276

```
text_files = ['100001']
```

 and place in the id from the site i linked.

[HoneyX2.7z](https://xentaxbackup.github.io/file/15110_HoneyX2.7z)
## Post #114
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-11-08T03:19:53+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Here is a script to download all the costumes from ブレイド2 X指定 Honey x Blade 2.

I run python file and done without any message
It show HoneyX2 folder but the folder is empty.

I use python37 32bit. I had installed lz4 and pillow.

Is there something wrong?
## Post #115
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-11-08T09:07:38+00:00
- Post Title: Re: Mobile Game Asset Download

try lowering 
pool = ThreadPool(100)
also run it from command line so you get messages back.
why are you not running 64bit python?
## Post #116
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-11-09T04:41:03+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> try lowering 
pool = ThreadPool(100)
also run it from command line so you get messages back.
why are you not running 64bit python?

I had re-installed 64bit python

I'm noob about python. Is this right?

I put the python file into python37 folder

the result also same. No file into the folder HoneyX2
## Post #117
- Username: alictzelt
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-11-09T09:20:20+00:00
- Post Title: Re: Mobile Game Asset Download

you don't need to run the command line as admin.
Here try this install of python I am sure the problem is one of the dependencies is not installed correctly.
[https://www85.zippyshare.com/v/iMmCutkq/file.html](https://www85.zippyshare.com/v/iMmCutkq/file.html)
## Post #118
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2018-11-09T10:24:08+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> you don't need to run the command line as admin.
Here try this install of python I am sure the problem is one of the dependencies is not installed correctly.

Thanks... finally worked
## Post #119
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-11-26T21:00:12+00:00
- Post Title: Re: Mobile Game Asset Download

seems most of the ports were closed including 8888.
can I still use this method to get assets?
## Post #120
- Username: aoilysa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Dec 13, 2018 12:36 am
- Post datetime: 2018-12-12T16:44:01+00:00
- Post Title: Re: Mobile Game Asset Download

im having problem with blender i used to convert the 3d model from android game?
can you tell me where did i wrong?

[https://imgur.com/a/ROvbhTc](https://imgur.com/a/ROvbhTc)

using data from installed apk on assest studio then open it on xnalara converting into xps with noesis
when i open it on blender it success then boom after i join the texture , bones and try to export it the blender traceback

i tried to use unity studio but when i load file/folder it doesnt appear

i tried to use your way got nothing >.<
[this what i got.png](https://xentaxbackup.github.io/file/15313_this what i got.png)
## Post #121
- Username: priatnaadnyana
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 09, 2018 2:13 am
- Post datetime: 2018-12-16T12:50:47+00:00
- Post Title: Re: Mobile Game Asset Download

I Need Help for this game please : [https://play.google.com/store/apps/deta ... dive&hl=en](https://play.google.com/store/apps/details?id=jp.co.cygames.princessconnectredive&hl=en)

i want to get the audio files
## Post #122
- Username: ChaoticFusion40
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2018-12-27T16:17:52+00:00
- Post Title: Re: Mobile Game Asset Download

What about shinobi striker senran kagura
## Post #123
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-01-03T01:51:17+00:00
- Post Title: Re: Mobile Game Asset Download

Downloads for this game
刀使ノ巫女 刻みし一閃の燈火 - Toji No Miko Tomoshibi
[https://justpaste.it/7bo5f](https://justpaste.it/7bo5f)
files are plain unity3d files.
[https://play.google.com/store/apps/deta ... oTomoshibi](https://play.google.com/store/apps/details?id=com.square_enix.android_googleplay.TojinomikoTomoshibi)

game updates are listed in these url's
[http://cache.tojinomiko-tomoshibi.jp/we ... _LIST.json](http://cache.tojinomiko-tomoshibi.jp/web/pch/1.2.15.21/DOWNLOAD_LIST.json)
[http://cache.tojinomiko-tomoshibi.jp/we ... _LIST.json](http://cache.tojinomiko-tomoshibi.jp/web/pch/1.2.15.21/DOWNLOAD_BLOCK_LIST.json)
[http://cache.tojinomiko-tomoshibi.jp/we ... /androidex](http://cache.tojinomiko-tomoshibi.jp/web/pch/1.2.15.21/Android/androidex)
you will most likely need to change the 1.2.15.21 when a new version is released.
[https://i.snag.gy/9eYAUT.jpg](https://i.snag.gy/9eYAUT.jpg)
## Post #124
- Username: lisomn
- Rank: n00b
- Number of posts: 12
- Joined date: Wed Feb 07, 2018 9:20 pm
- Post datetime: 2019-01-22T12:34:59+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox
>
> Downloads for this game
刀使ノ巫女 刻みし一閃の燈火 - Toji No Miko Tomoshibi
https://justpaste.it/7bo5f
files are plain unity3d files.
https://play.google.com/store/apps/deta ... oTomoshibi

game updates are listed in these url's
http://cache.tojinomiko-tomoshibi.jp/we ... _LIST.json
http://cache.tojinomiko-tomoshibi.jp/we ... _LIST.json
http://cache.tojinomiko-tomoshibi.jp/we ... /androidex
you will most likely need to change the 1.2.15.21 when a new version is released.
https://i.snag.gy/9eYAUT.jpg
hi chrrox The game has been upgraded and the link is 404 error.
new version is 1.2.6.2
After the version number is modified, the link is normal.
## Post #125
- Username: Unari
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2019 12:53 pm
- Post datetime: 2019-01-31T12:48:51+00:00
- Post Title: Re: Mobile Game Asset Download

How you move the certificate to the sdcard is unclear, could you please elaborate?
## Post #126
- Username: Unari
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jan 31, 2019 12:53 pm
- Post datetime: 2019-01-31T13:13:08+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone have the files for Idolm@ster million live? i can't get this to work for that game, even though someone on deviantart is posting the models
## Post #127
- Username: squirrelisnut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Feb 26, 2019 6:15 pm
- Post datetime: 2019-02-27T03:05:02+00:00
- Post Title: Re: Mobile Game Asset Download

thank you so much for sharing sir. i have always wanted to make something different or some kind of impact into the game i play. though i couldnot download it which is strange. i used to download game from apknite to get apk file of the game when changing some codes and other to modify it. but dont really know how to make a full version of mod for the game
## Post #128
- Username: priatnaadnyana
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Dec 09, 2018 2:13 am
- Post datetime: 2019-03-05T15:56:16+00:00
- Post Title: Re: Mobile Game Asset Download

Need Help for this game please : [https://apps.qoo-app.com/en/app/6630](https://apps.qoo-app.com/en/app/6630)

i want to get the audio files too
## Post #129
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2019-03-06T13:20:31+00:00
- Post Title: Re: Mobile Game Asset Download

I can't get any of the methods in this thread for getting millionlive files to work so i was wondering if it was a problem on my end or if these methods arent working anymore
## Post #130
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-03-16T14:36:03+00:00
- Post Title: Re: Mobile Game Asset Download

For help with games I need more info on where you are stuck.

Here are the assets (unity 3d) of this game.
LYN: THE LIGHTBRINGER
[https://pastebin.com/raw/SrAwcRya](https://pastebin.com/raw/SrAwcRya)
[](https://ibb.co/xs0yhmS)

The game reaches out to these url's
[https://mlynglobal.dn.nexoncdn.co.kr/Pa ... isions.txt](https://mlynglobal.dn.nexoncdn.co.kr/PatchFiles/live/revisions.txt)
[https://mlynglobal.dn.nexoncdn.co.kr/Pa ... 0.6403.txt](https://mlynglobal.dn.nexoncdn.co.kr/PatchFiles/live/patch/p0.6403.txt)
[https://mlynglobal.dn.nexoncdn.co.kr/Pa ... 0.6403.zip](https://mlynglobal.dn.nexoncdn.co.kr/PatchFiles/live/patch/p0.6403.zip)
to get the game config
then here for the file list
[https://mlynglobal.dn.nexoncdn.co.kr/co ... -data.json](https://mlynglobal.dn.nexoncdn.co.kr/com.nexon.lyn.global/980ce504de22461d/resource-data.json)
## Post #131
- Username: Cornalito
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 19, 2018 5:52 am
- Post datetime: 2019-04-01T03:11:11+00:00
- Post Title: Re: Mobile Game Asset Download

Hi, the Cinderella Girls Starlight Stage script doesn't work, I open the script but it doesn't download nothing
## Post #132
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-04-08T16:25:12+00:00
- Post Title: Re: Mobile Game Asset Download

[https://play.google.com/store/apps/deta ... apro&hl=ja](https://play.google.com/store/apps/details?id=jp.colopl.drapro&hl=ja)

This is a monster hunter like game created by a Japanese mobile gaming company.
The service will be terminated soon, but the file can not be downloaded because it is newbie registration is suspended.

I tried to get the list, but due to the router limitation I could not open the port.
This game has a lot of great assets. I'm glad if someone helps me.

It has some pieces, but these are normal unity3d, which can be loaded with AssetStudio.
## Post #133
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-04-11T00:48:51+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from einherjar007 ↑Tue Apr 09, 2019 12:25 am at Tue Apr 09, 2019 12:25 am
>
> 
https://play.google.com/store/apps/deta ... apro&hl=ja

This is a monster hunter like game created by a Japanese mobile gaming company.
The service will be terminated soon, but the file can not be downloaded because it is newbie registration is suspended.

I tried to get the list, but due to the router limitation I could not open the port.
This game has a lot of great assets. I'm glad if someone helps me.

It has some pieces, but these are normal unity3d, which can be loaded with AssetStudio.

I managed to use process hackers to finally get the list itself.
Perhaps you can download the asset by specifying the appropriate URL. 
However, in my environment, I can not get the URL of the asset because I can not open the port and can not use Fiddler.

The list is also downloaded as an asset and stored in assetbundleinfo.dat in the storage folder.
I'm glad to if tell how to guide the download URL. Thank you.

-----

It seems that I can find the answer a little bit. Process Hacker is useful.

-----

finally, I got them.
## Post #134
- Username: Mkaimaki
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 18, 2019 4:40 pm
- Post datetime: 2019-04-20T04:40:15+00:00
- Post Title: Re: Mobile Game Asset Download

Hello, I'm trying to download the assets for Life After by Netease (CN Version)
And following the steps, I've found a JSON file but I'm stuck on how to interpret this (Im a helpless newbie)
[http://nos.gameyw.netease.com/gameyw-gb ... 9aafb.json](http://nos.gameyw.netease.com/gameyw-gbox/regular_encode_g66_1555728555_c9b16cf46d3cecca35d49b9574b9aafb.json)
## Post #135
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-20T12:07:35+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Mkaimaki ↑Sat Apr 20, 2019 12:40 pm at Sat Apr 20, 2019 12:40 pm
>
> 
Hello, I'm trying to download the assets for Life After by Netease (CN Version)
And following the steps, I've found a JSON file but I'm stuck on how to interpret this (Im a helpless newbie)
http://nos.gameyw.netease.com/gameyw-gb ... 9aafb.json

Its encrypted you need to decrypt it first.
## Post #136
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-04-21T05:17:00+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Mkaimaki ↑Sat Apr 20, 2019 12:40 pm at Sat Apr 20, 2019 12:40 pm
>
> 
Hello, I'm trying to download the assets for Life After by Netease (CN Version)
And following the steps, I've found a JSON file but I'm stuck on how to interpret this (Im a helpless newbie)
http://nos.gameyw.netease.com/gameyw-gb ... 9aafb.json

For Natease Game have you tried this tutorial
[https://forum.xentax.com/viewtopic.php?f=16&t=17982](https://forum.xentax.com/viewtopic.php?f=16&t=17982)

But most Netease Game encrypted
## Post #137
- Username: a503503
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 25, 2019 9:42 pm
- Post datetime: 2019-04-25T13:47:25+00:00
- Post Title: Re: Mobile Game Asset Download

Hello, I wonder what I can do with an Unity manifest file.
I figured out partly the url of the asset but have no idea the filename(in form of hash).
Do anyone have idea on this?
[Assetbundlemanifest.rar](https://xentaxbackup.github.io/file/16118_Assetbundlemanifest.rar)
## Post #138
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-25T15:44:44+00:00
- Post Title: Re: Mobile Game Asset Download

What game?
## Post #139
- Username: a503503
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Apr 25, 2019 9:42 pm
- Post datetime: 2019-04-25T15:51:28+00:00
- Post Title: Re: Mobile Game Asset Download

JEWEL PRINCESS from DMM
## Post #140
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2019-04-25T16:13:22+00:00
- Post Title: Re: Mobile Game Asset Download

Dear chrrox, can you make a script download for Puchiguru LoveLive!? Thanks you. This is the game's manifest url:

```
https://puchiguru-prod-static-files.pokelabo.jp/v3.0.1.0/Android/v0?__gda__=st=1556208000~exp=1556211600~acl=%2F%2A~hmac=9ecf0a29062f87fd6e27ea0b4f63bc2cda67fa46c9a0864b1223a38ee73a68b1
```

Some game assets's url:

```
https://puchiguru-prod-static-files.pokelabo.jp/v3.0.1.0/Android/puzzlesdchara/08204343063d06273305374135785346486c0b095976112224?__gda__=st=1556208000~exp=1556211600~acl=%2F%2A~hmac=9ecf0a29062f87fd6e27ea0b4f63bc2cda67fa46c9a0864b1223a38ee73a68b1
```
## Post #141
- Username: wanglata
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-27T14:38:08+00:00
- Post Title: Re: Mobile Game Asset Download

Here are all the files seems like it goes offline in a few days.
[https://gofile.io/?c=voTowb](https://gofile.io/?c=voTowb)
@wanglata
## Post #142
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2019-04-28T01:33:43+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Apr 27, 2019 10:38 pm at Sat Apr 27, 2019 10:38 pm
>
> 
Here are all the files seems like it goes offline in a few days.
https://gofile.io/?c=voTowb
@wanglata

ah they change the url every week, btw, you're always awesome, thank you
## Post #143
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-04-28T03:59:44+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wanglata ↑Sun Apr 28, 2019 9:33 am at Sun Apr 28, 2019 9:33 am
>
> 
chrrox wrote: ↑Sat Apr 27, 2019 10:38 pm
Here are all the files seems like it goes offline in a few days.
https://gofile.io/?c=voTowb
@wanglata


ah they change the url every week, btw, you're always awesome, thank you

the game closes at the end of the month I don't think there will be any more updates.
[https://www.crunchyroll.com/anime-news/ ... next-month](https://www.crunchyroll.com/anime-news/2019/03/28-1/puchiguru-love-live-app-closes-up-shop-next-month)
## Post #144
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-05-13T09:33:15+00:00
- Post Title: Re: Mobile Game Asset Download

Shinobi Master Senran Kagura: New Link


[https://apps.qoo-app.com/en/app/5451](https://apps.qoo-app.com/en/app/5451)

Model Assets:
[https://www.itextpad.com/senran](https://www.itextpad.com/senran)

Tutorials
[https://forum.xentax.com/viewtopic.php?t=16027](https://forum.xentax.com/viewtopic.php?t=16027) (decompress .lzs)
[https://forum.xentax.com/viewtopic.php?t=17608](https://forum.xentax.com/viewtopic.php?t=17608) (noesis script .bum *not to work properly)

There are some problem on UV and weight. I hope someone can fix it
[Untitled - Copy.png](https://xentaxbackup.github.io/file/16237_Untitled - Copy.png)
## Post #145
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2019-05-22T13:55:55+00:00
- Post Title: Re: Mobile Game Asset Download

I was wondering if it would be possible to write a script to get the files from the game UtaMacross: Smartphone Deculture? I've never had any luck with the fiddler+nox method for grabbing manifests and such :/ 

also i cant get the game to run on any emulators? ive heard it works on bluestacks but i cant get it to go past the main menu
## Post #146
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-05-23T20:03:47+00:00
- Post Title: Re: Mobile Game Asset Download

UtaMacross: Smartphone Deculture assets are encrypted.
## Post #147
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2019-05-29T03:08:45+00:00
- Post Title: Re: Mobile Game Asset Download

ah, damn. thanks for letting me know
## Post #148
- Username: mitty
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 03, 2018 12:59 am
- Post datetime: 2019-06-04T04:55:28+00:00
- Post Title: Re: Mobile Game Asset Download

Hello! I've been trying to extract models from the game Project Tokyo Dolls (プロジェクト東京ドールズ). Thing is is that all of the model files seem to be .abap and I can't figure out how to extract (would that even be the right word for it? Decompress? Unpack? decrypt??) from the file. I noticed that both on here and zenhax someone previously asked the same thing, and chrrox had replied on both threads with

> The first 0x400 of each file is encrypted.
>
> I am not sure how its encrypted.
>
> once you get the real file start the files are normal compressed unity3d files that work in all tools.

and an image of one of the models from it, so I assume that despite it being encrypted it is definitely possible to get the models from these files.

I apologize for my ignorance, but since it is apparently possible to get the models anyways, how would one decrypt the .abap files? I've searched far and wide on the internet and those two threads are the only ones I've ever seen anyone discuss ripping the PTD models on, and after doing research on .abap files themselves I haven't had much help, so this thread is my last chance lol

If anyone wants to try to decrypt the files themselves, [here is the zenhax thread with a zip including .abap files from the game.](https://zenhax.com/viewtopic.php?t=4366) [here is the old xentax thread too (the mega link to download the zip is dead on this one).](https://forum.xentax.com/viewtopic.php?t=16498) thanks!
## Post #149
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2019-07-26T08:34:50+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Nov 03, 2018 6:16 am at Sat Nov 03, 2018 6:16 am
>
> 
Here is a script to download all the costumes from ブレイド2 X指定 Honey x Blade 2.
Here is a list of all the costumes http://honeyxicons.yolasite.com/Costumes.php.
Edit the line 
Code: Select allpool = ThreadPool(100) 
if your pc can't handle that much and just lower the number.
if you only want one costume un comment line 276
Code: Select alltext_files = ['100001']
 and place in the id from the site i linked.

I'm having the same problem as alictzelt had, do you think you could re-upload that version of python you linked before? Sorry. I can't seem to get it to work.
## Post #150
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2019-08-03T20:54:08+00:00
- Post Title: Re: Mobile Game Asset Download

hey there i tried to grab the latest manifest from imas starlight stage today but during the part where you use fiddler to get the csv i noticed saving the response gave me a file like this:
[https://sta.sh/0wshgljkela](https://sta.sh/0wshgljkela)
i did manage to get a file like this with a different link in the composer
[https://sta.sh/0odh2rjy7j0](https://sta.sh/0odh2rjy7j0)
but the quickbms script that im supposed to use on it doesnt seem to work? the one that makes it an sqlite file

so idk what to do :/ if anyone has the latest manifest already in the csv format ready for that script that auto-downloads the files, id appreciate it if you could send it my way
## Post #151
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2019-08-06T00:28:28+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Thu Jan 03, 2019 9:51 am at Thu Jan 03, 2019 9:51 am
>
> 
Downloads for this game
刀使ノ巫女 刻みし一閃の燈火 - Toji No Miko Tomoshibi
https://justpaste.it/7bo5f
files are plain unity3d files.
https://play.google.com/store/apps/deta ... oTomoshibi

game updates are listed in these url's
http://cache.tojinomiko-tomoshibi.jp/we ... _LIST.json
http://cache.tojinomiko-tomoshibi.jp/we ... _LIST.json
http://cache.tojinomiko-tomoshibi.jp/we ... /androidex
you will most likely need to change the 1.2.15.21 when a new version is released.
https://i.snag.gy/9eYAUT.jpg

Hi, the links don't work for me and where are the models and textures, I would really appreciate it.
## Post #152
- Username: otchi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 13, 2019 11:02 pm
- Post datetime: 2019-08-13T15:11:17+00:00
- Post Title: Re: Mobile Game Asset Download

For some reason neither Fiddler nor Process Hacker seem to capture the assets.
I got the API URLs from ProcessHacker, but it doesn't give me the Assets URLs. I can't seen to find the matching URLs on Fiddler.
Any help? The game is called Ikemen Vampire.
## Post #153
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2019-08-21T05:37:36+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone own the asset of the Android game "Project Tokyo Dolls" latest update   
   PLEASE!!!!
## Post #154
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-08-25T18:49:02+00:00
- Post Title: Re: Mobile Game Asset Download

Updated idolmaster download script.
[http://asset-starlight-stage.akamaized. ... dbmanifest](http://asset-starlight-stage.akamaized.net/dl/10058700/manifests/all_dbmanifest)
[http://asset-starlight-stage.akamaized. ... High_SHigh](http://asset-starlight-stage.akamaized.net/dl/10058700/manifests/Android_AHigh_SHigh)
[http://asset-starlight-stage.akamaized. ... High_SHigh](http://asset-starlight-stage.akamaized.net/dl/10058700/manifests/iOS_AHigh_SHigh)
[imas.7z](https://xentaxbackup.github.io/file/16653_imas.7z)
## Post #155
- Username: LammyQ
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Jul 20, 2019 12:28 am
- Post datetime: 2019-08-26T01:14:28+00:00
- Post Title: Re: Mobile Game Asset Download

Hi folks,
I'm trying to acquire assets for the PC version of Ryu Ga Gotoku Online and would really appreciate some help, please. I know this is a mobile game thread but the method seems to be close enough and there are both Android and iOS versions.

Following the tutorial I got these URLs:
http://dl.ryu-ga-gotoku-online.jp/FWTie ... t_list.csv
http://dl.ryu-ga-gotoku-online.jp/FWTie ... i_list.csv
http://dl.ryu-ga-gotoku-online.jp/FWTie ... _02_02.csv
http://dl.ryu-ga-gotoku-online.jp/FWTie ... _01_02.csv

Trying to access them got me nowhere so I tried what was explained [here](https://forum.xentax.com/viewtopic.php?f=16&t=15582&start=30) using 

```
http://dl.ryu-ga-gotoku-online.jp/FWTieefXTwDJ5Gej.v10900.88783/Assets/Pc/asset_list.csv
```


```
User-Agent: UnityPlayer/2018.2.14f1 (UnityWebRequest/1.0,libcurl/7.52.0-DEV)
Host: dl.ryu-ga-gotoku-online.jp
Connection: Keep-Alive
Accept-Encoding: gzip
```


I saved a .txt file with a list of stuff like this:
adv_bg_mob_pack_set,f7363f46c14ff47684d1cb32592cb8bd,110636
adv_bg_title_00_pack_set,704417eaefb7031fafba38899dad01b9,288483
adv_ch_ef_pack_set,9c03ec22aeb3ab4d35e002ca047a2939,149742
adv_ef_bg_0000301_pack_set,f3177fe00513894fd5ce67a57cdcde29,211499
adv_ef_bg_0000302_pack_set,0100e48e43647d8252b5db153b9506a3,225375


From here, I have no idea what to do, or even if I'm on the right track. Is there anything else needed for someone to work out what's next?
Thanks.
## Post #156
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-08-27T04:53:55+00:00
- Post Title: Re: Mobile Game Asset Download

the files of the latest version of this game will not download with the millionlive script [https://drive.google.com/open?id=1JPRP3 ... OSfc78pR6O](https://drive.google.com/open?id=1JPRP3rrnTf0fnk8q6xZKEAOSfc78pR6O)
## Post #157
- Username: TakutoD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 01, 2019 7:34 pm
- Post datetime: 2019-09-01T11:56:42+00:00
- Post Title: Re: Mobile Game Asset Download

Hello I am trying to rip the files from Capcoms MHRX ( [https://play.google.com/store/apps/deta ... droid.mhxr](https://play.google.com/store/apps/details?id=tw.com.capcom.android.mhxr) )

Here is the game list or csv(?) that the game uses to download things: [http://mhxrres.capcom.com.tw/download/c ... nload.list](http://mhxrres.capcom.com.tw/download/cht/android/v0112/stdDL/download.list)
(Its just a simple text file)
However the game doesn't use unity or anything I've seen before, instead it uses .fpk files that contain .arc files according to HxD


I've looked up a bit on google and apparently Capcom uses the .arc file format for some of their games however I cannot even extract the FPK file that contains the ARC files so I was wondering if anyone has experience in extracting FPK files or ARC files.

Here is a sample file:  [http://mhxrres.capcom.com.tw/download/c ... yer.03.fpk](http://mhxrres.capcom.com.tw/download/cht/android/v0112/stdDL/cmn/player.03.fpk)

Help is much appreciated,

Thanks in advance.
## Post #158
- Username: NegimaSonic
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-09-07T11:55:34+00:00
- Post Title: Re: Mobile Game Asset Download

マジカミ DX
[http://games.dmm.com/detail/magicami/](http://games.dmm.com/detail/magicami/)
[https://asset.magicami.jp/v1/list/14/0](https://asset.magicami.jp/v1/list/14/0)
Save This download as magicami.bundle along with the python script
into the same directory then it will download all the files.
Game uses unity.
Added bundle


 magicami.zip
(639.4 KiB) Downloaded 182 times


[magicami.7z](https://xentaxbackup.github.io/file/16694_magicami.7z)

[episode_engine--cg--main120601.png](https://xentaxbackup.github.io/file/16693_episode_engine--cg--main120601.png)
## Post #159
- Username: TakutoD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 01, 2019 7:34 pm
- Post datetime: 2019-09-12T02:48:19+00:00
- Post Title: Re: Mobile Game Asset Download

Can someone please help me? I ran across a game that encrypts asset bundles and I have no idea how to decrypt it,
[filesample.7z](https://xentaxbackup.github.io/file/16727_filesample.7z)
## Post #160
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-09-12T04:14:47+00:00
- Post Title: Re: Mobile Game Asset Download

What game?
## Post #161
- Username: TakutoD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 01, 2019 7:34 pm
- Post datetime: 2019-09-12T04:28:55+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Thu Sep 12, 2019 12:14 pm at Thu Sep 12, 2019 12:14 pm
>
> What game?

Rockman X Dive
## Post #162
- Username: otchi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Aug 13, 2019 11:02 pm
- Post datetime: 2019-09-23T10:23:20+00:00
- Post Title: Re: Mobile Game Asset Download

So... maybe this is because the game had a different format and such, but I tried Process hacker and the only stuff it spits out is a bunch of Unity garble. I wasn't able to find any URLs even though the assets are clearly hosted on some sort of network and not bundled in the APK. 



I used a Unity disassembler and managed to unpack a bunch of the local files, but the other resources URLs can't be seen. 
The game is called Ikemen Vampire, by the way:

[https://www.modapkdown.com/jp.co.cybird ... -game-mod/](https://www.modapkdown.com/jp.co.cybird.appli.android.vas.en/ikemen-vampire-otome-game-mod/)

Any help?
## Post #163
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2019-09-24T14:23:12+00:00
- Post Title: Re: Mobile Game Asset Download

Kemono Friend 3
[https://play.google.com/store/apps/deta ... noFriends3](https://play.google.com/store/apps/details?id=com.sega.KemonoFriends3)

Assests list :
[https://parade-mobile-prod-cdn.kemono-f ... b_list.txt](https://parade-mobile-prod-cdn.kemono-friends-sega.jp/AssetBundles/1.0/95d7251e77fdd8e8fdf2210b6439d166/1.0/Android/1.0.0/ja/ab_list.txt)

Here some sample:
[https://parade-mobile-prod-cdn.kemono-f ... 2_a.prefab](https://parade-mobile-prod-cdn.kemono-friends-sega.jp/AssetBundles/1.0/95d7251e77fdd8e8fdf2210b6439d166/1.0/Android/1.0.0/ja/assets/ch_0322_a.prefab)
[Screenshot (18).jpg](https://xentaxbackup.github.io/file/16804_Screenshot (18).jpg)
## Post #164
- Username: argkendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 22, 2019 7:50 am
- Post datetime: 2019-09-24T23:54:20+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from ChaoticFusion40 ↑Tue Aug 27, 2019 12:53 pm at Tue Aug 27, 2019 12:53 pm
>
> 
the files of the latest version of this game will not download with the millionlive script https://drive.google.com/open?id=1JPRP3 ... OSfc78pR6O

How can I extract the assets with the manifest you shared in the link? Do you have the script? Could you make a step by step tutorial?
## Post #165
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-09-25T01:01:23+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from argkendo ↑Wed Sep 25, 2019 7:54 am at Wed Sep 25, 2019 7:54 am
>
> 
ChaoticFusion40 wrote: ↑Tue Aug 27, 2019 12:53 pm
the files of the latest version of this game will not download with the millionlive script https://drive.google.com/open?id=1JPRP3 ... OSfc78pR6O


How can I extract the assets with the manifest you shared in the link? Do you have the script? Could you make a step by step tutorial?

i have the manifest and the game is updated, go to your android emulator and look for the manifest.
## Post #166
- Username: argkendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 22, 2019 7:50 am
- Post datetime: 2019-09-25T12:08:50+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from ChaoticFusion40 ↑Wed Sep 25, 2019 9:01 am at Wed Sep 25, 2019 9:01 am
>
> 
argkendo wrote: ↑Wed Sep 25, 2019 7:54 am
ChaoticFusion40 wrote: ↑Tue Aug 27, 2019 12:53 pm
the files of the latest version of this game will not download with the millionlive script https://drive.google.com/open?id=1JPRP3 ... OSfc78pR6O


How can I extract the assets with the manifest you shared in the link? Do you have the script? Could you make a step by step tutorial?


i have the manifest and the game is updated, go to your android emulator and look for the manifest.

How do I extract the assets from the manifest? I need a script right? Last time I followed a step-by-step tutorial shared by a user who also shared the manifest and script to download all assets
## Post #167
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2019-09-25T19:02:10+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from argkendo ↑Wed Sep 25, 2019 8:08 pm at Wed Sep 25, 2019 8:08 pm
>
> 
ChaoticFusion40 wrote: ↑Wed Sep 25, 2019 9:01 am
argkendo wrote: ↑Wed Sep 25, 2019 7:54 am


How can I extract the assets with the manifest you shared in the link? Do you have the script? Could you make a step by step tutorial?


i have the manifest and the game is updated, go to your android emulator and look for the manifest.


How do I extract the assets from the manifest? I need a script right? Last time I followed a step-by-step tutorial shared by a user who also shared the manifest and script to download all assets

i used the script to download them, but no files were downloading.
## Post #168
- Username: argkendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 22, 2019 7:50 am
- Post datetime: 2019-09-26T02:53:43+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from ChaoticFusion40 ↑Thu Sep 26, 2019 3:02 am at Thu Sep 26, 2019 3:02 am
>
> 
argkendo wrote: ↑Wed Sep 25, 2019 8:08 pm
ChaoticFusion40 wrote: ↑Wed Sep 25, 2019 9:01 am


i have the manifest and the game is updated, go to your android emulator and look for the manifest.


How do I extract the assets from the manifest? I need a script right? Last time I followed a step-by-step tutorial shared by a user who also shared the manifest and script to download all assets


i used the script to download them, but no files were downloading.

In that case, did you find any way to download the assets from that manifest?
## Post #169
- Username: argkendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 22, 2019 7:50 am
- Post datetime: 2019-09-26T12:01:04+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Mon Aug 26, 2019 2:49 am at Mon Aug 26, 2019 2:49 am
>
> 
Updated idolmaster download script.
http://asset-starlight-stage.akamaized. ... dbmanifest
http://asset-starlight-stage.akamaized. ... High_SHigh
http://asset-starlight-stage.akamaized. ... High_SHigh

Do you have the latest idolmaster million live manifest and script file?
## Post #170
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2019-09-26T15:54:34+00:00
- Post Title: Re: Mobile Game Asset Download

For anyone want find mirishita's manifest file, you should install the game on any android device, and find it in Android/data/com.bandainamcoent.imas_millionlive_theaterdays/files/e821415207bf0601ed040cb438d526c478a22873 and rename to manifest.data.
In the past, I used to use MLTDTools [https://github.com/OpenMLTD/MLTDTools](https://github.com/OpenMLTD/MLTDTools) to read the manifest.data file and download the raw file, and used fiddler to find the game's version, but currently the game has blocked the use of proxies when playing game. F**k Scamco
## Post #171
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2019-09-26T16:08:58+00:00
- Post Title: Re: Mobile Game Asset Download

Dear chrrox, sorry to bother you, but can you help me? These are all the urls I captured by using the fiddler for Love Live All Star. Can you check it?
https://jp-real-prod-v4tadlicuqeeumke.a ... rdata_a_ja
https://jp-real-prod-v4tadlicuqeeumke.a ... terdata.db
https://jp-real-prod-v4tadlicuqeeumke.a ... ry_ja_k.db
https://jp-real-prod-v4tadlicuqeeumke.a ... e_image.db
https://jp-real-prod-v4tadlicuqeeumke.a ... android.db
https://jp-real-prod-v4tadlicuqeeumke.a ... ry_ja_s.db
https://jp-real-prod-v4tadlicuqeeumke.a ... ry_ja_m.db
https://jp-real-prod-v4tadlicuqeeumke.a ... a_petag.db
https://jp-real-prod-v4tadlicuqeeumke.a ... _a_ja_0.db
The game is made of Unity, but it seems that the file is encrypted
## Post #172
- Username: oreki48
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon May 14, 2018 2:10 am
- Post datetime: 2019-09-26T16:20:12+00:00
- Post Title: Re: Mobile Game Asset Download

i have love live all stars data 
but i still confuse find the 3d models
## Post #173
- Username: Rias
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 27, 2019 8:04 pm
- Post datetime: 2019-09-27T12:31:17+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone have any experience with '[Dragalia Lost](https://play.google.com/store/apps/details?id=com.nintendo.zaga)' ? 

The files all work in AssetStudio with the exception of audio files, which can be extracted with vgmstream. Copying them from my phone or using a proxy to download them is fine too. My problem is that all the filenames look encrypted. I've seen some files floating around the net with proper names, and I've seen people talking about "the manifest has all the filenames" but I have little experience and have no idea how to view the contents of the assetbundle.manifest. I'm not asking for a complete answer, just any advice to learn how to find the filenames so I can organize a lot of these audio clips. 

Thanks.
## Post #174
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2019-09-28T09:59:38+00:00
- Post Title: Re: Mobile Game Asset Download

I found some files from love live all stars use AFS2 and @UTF header.
## Post #175
- Username: azbycx
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-03T09:25:42+00:00
- Post Title: Re: Mobile Game Asset Download

Here is a python download script for 魔法科高校の劣等生 LOST ZERO
The Irregular at Magic High School



unknown.png (262.82 KiB) Viewed 345 times


[MagicHS.zip](https://xentaxbackup.github.io/file/16853_MagicHS.zip)
## Post #176
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2019-10-06T04:45:57+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Thu Oct 03, 2019 5:25 pm at Thu Oct 03, 2019 5:25 pm
>
> 
Here is a python download script for 魔法科高校の劣等生 LOST ZERO
The Irregular at Magic High School
unknown.png

thks chrrox.but I find the script can only  download the 3D modules assets,and whitout the card image assets in it.can u help me with the images assets urls ?thks
## Post #177
- Username: azbycx
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-07T21:57:06+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from azbycx ↑Sun Oct 06, 2019 12:45 pm at Sun Oct 06, 2019 12:45 pm
>
> 
chrrox wrote: ↑Thu Oct 03, 2019 5:25 pm
Here is a python download script for 魔法科高校の劣等生 LOST ZERO
The Irregular at Magic High School
unknown.png


thks chrrox.but I find the script can only  download the 3D modules assets,and whitout the card image assets in it.can u help me with the images assets urls ?thks
[https://photos.app.goo.gl/S19vCsUoM5kiyx6U6](https://photos.app.goo.gl/S19vCsUoM5kiyx6U6)
## Post #178
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2019-10-08T20:53:08+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Tue Oct 08, 2019 5:57 am at Tue Oct 08, 2019 5:57 am
>
> 
azbycx wrote: ↑Sun Oct 06, 2019 12:45 pm
chrrox wrote: ↑Thu Oct 03, 2019 5:25 pm
Here is a python download script for 魔法科高校の劣等生 LOST ZERO
The Irregular at Magic High School
unknown.png


thks chrrox.but I find the script can only  download the 3D modules assets,and whitout the card image assets in it.can u help me with the images assets urls ?thks

https://photos.app.goo.gl/S19vCsUoM5kiyx6U6
Thks,u r so nice
## Post #179
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2019-10-09T00:35:26+00:00
- Post Title: Re: Mobile Game Asset Download

someone to pass me the assets of GIRLS UND PANZER GAME AND TOKYO DOLLS PROJECT please!
## Post #180
- Username: douchi
- Rank: beginner
- Number of posts: 21
- Joined date: Sun Sep 29, 2019 10:24 pm
- Post datetime: 2019-10-09T04:55:58+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Wed Jul 05, 2017 8:15 am at Wed Jul 05, 2017 8:15 am
>
> 
Here is a script that will auto decompress the files for you.
you need to do pip install lz4 for this script to work.

I need your help. This is its uasset and uexp files. Can you help extract its OBJ model? I'm in a hurry. Thank you for your help..
DragonRaja Sample file:[https://mega.nz/#!224GAAha!CMlOzdWZqu8r ... xBXqStogSE](https://mega.nz/#!224GAAha!CMlOzdWZqu8rvHqCXyDiCN17vARsLSy8wxBXqStogSE)
I hope I can get your help.
## Post #181
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2019-10-09T18:22:21+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Tue Oct 08, 2019 5:57 am at Tue Oct 08, 2019 5:57 am
>
> 
azbycx wrote: ↑Sun Oct 06, 2019 12:45 pm
chrrox wrote: ↑Thu Oct 03, 2019 5:25 pm
Here is a python download script for 魔法科高校の劣等生 LOST ZERO
The Irregular at Magic High School
unknown.png


thks chrrox.but I find the script can only  download the 3D modules assets,and whitout the card image assets in it.can u help me with the images assets urls ?thks

https://photos.app.goo.gl/S19vCsUoM5kiyx6U6
I find there are some characters  missing in the photograh,just like the "fumiya"&"ayako"\
and some sub card image like "maya"、"hanzo" ard also not include in it .may i trouble u to check the script out once more?
## Post #182
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2019-10-09T18:24:33+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from zerotaku5123 ↑Wed Oct 09, 2019 8:35 am at Wed Oct 09, 2019 8:35 am
>
> 
someone to pass me the assets of GIRLS UND PANZER GAME AND TOKYO DOLLS PROJECT please!

the two GIRLS UND PANZER GAME mobile game all can be download now ..
## Post #183
- Username: azbycx
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-10T03:59:50+00:00
- Post Title: Re: Mobile Game Asset Download

Ah found newer file
[http://cache.lostzeromagichs.jp/assets/ ... files.json](http://cache.lostzeromagichs.jp/assets/7/android/assetfiles.json)
## Post #184
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2019-10-10T08:52:04+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Thu Oct 10, 2019 11:59 am at Thu Oct 10, 2019 11:59 am
>
> 
Ah found newer file
http://cache.lostzeromagichs.jp/assets/ ... files.json

THKS，and can u tell me how to find this url? in fact  i have try to  capture the network traffic while lunch the app,but i have not seen this file at all  
i can  only find a encrypted json file in the app data folder
## Post #185
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-10-10T12:02:35+00:00
- Post Title: Re: Mobile Game Asset Download

here.

```
using System.Text;
using System.Security.Cryptography;
					
public class Program
{
	public static void Main()
	{
		MD5CryptoServiceProvider md5CryptoServiceProvider = new MD5CryptoServiceProvider();
		string[] urllist = {"miyuki0283_l.unity3d1600150520"};
		for (int x = 0; x < urllist.Length; x++)
		{
			string hashname = urllist[x];
			byte[] array3 = md5CryptoServiceProvider.ComputeHash(Encoding.Unicode.GetBytes(hashname));
			StringBuilder stringBuilder = new StringBuilder();
			for (int i = 0; i < array3.Length; i++)
				{
				stringBuilder.Append(array3[i].ToString("x2"));
			}
			string text = stringBuilder.ToString();
			Console.WriteLine(text);
		}
	}
}

```

This is what I created while checking internet samples.
Enter the file name + .unity3d and the corresponding key in urllist and convert it to md5 to get the URL hash of the asset.
Execution requires C# Compiler.
## Post #186
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2019-10-11T10:26:53+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from einherjar007 ↑Thu Oct 10, 2019 8:02 pm at Thu Oct 10, 2019 8:02 pm
>
> 
here.
Code: Select allusing System;
using System.Text;
using System.Security.Cryptography;
					
public class Program
{
	public static void Main()
	{
		MD5CryptoServiceProvider md5CryptoServiceProvider = new MD5CryptoServiceProvider();
		string[] urllist = {"miyuki0283_l.unity3d1600150520"};
		for (int x = 0; x < urllist.Length; x++)
		{
			string hashname = urllist[x];
			byte[] array3 = md5CryptoServiceProvider.ComputeHash(Encoding.Unicode.GetBytes(hashname));
			StringBuilder stringBuilder = new StringBuilder();
			for (int i = 0; i < array3.Length; i++)
				{
				stringBuilder.Append(array3[i].ToString("x2"));
			}
			string text = stringBuilder.ToString();
			Console.WriteLine(text);
		}
	}
}

This is what I created while checking internet samples.
Enter the file name + .unity3d and the corresponding key in urllist and convert it to md5 to get the URL hash of the asset.
Execution requires C# Compiler.

thks. I have got all the dl links of the 18040 assets about the game  and write them into the txt file:
[https://mega.nz/#!h5NGBKqT!yDLP1B1sHsBL ... m4FQecw_F8](https://mega.nz/#!h5NGBKqT!yDLP1B1sHsBL8JDApiu-cr91uV5G6LeeZm4FQecw_F8)
## Post #187
- Username: reizu
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-12T00:31:36+00:00
- Post Title: Re: Mobile Game Asset Download

Birdie Crush™
バーディークラッシュ
Homepage [https://www.facebook.com/pg/BirdieCrush ... e_internal](https://www.facebook.com/pg/BirdieCrush/posts/?ref=page_internal)


 Birdie Crush.7z
(5.17 KiB) Downloaded 56 times


[https://image-glb.qpyou.cn/g2/Jenkins/A ... chInfo.xml](https://image-glb.qpyou.cn/g2/Jenkins/AssetBundles/rev52831/Android/ResourcePatchInfo.xml)
## Post #188
- Username: garamika
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 09, 2017 4:29 pm
- Post datetime: 2019-10-14T11:23:15+00:00
- Post Title: Re: Mobile Game Asset Download

Regarding LLAS(Love Live School Idol Festival All Stars)
It seems address is getting updated as the assets get updated.
BTW is there any way to decrypt the database?

ex) [https://jp-real-prod-v4tadlicuqeeumke.a ... _a_ja_0.db](https://jp-real-prod-v4tadlicuqeeumke.api.game25.klabgames.net/ep1002/static/f141c313a139e1e6/asset_a_ja_0.db)
[https://jp-real-prod-v4tadlicuqeeumke.a ... 3a139e1e6/](https://jp-real-prod-v4tadlicuqeeumke.api.game25.klabgames.net/ep1002/static/f141c313a139e1e6/) + file name

It seems that
[https://jp-real-prod-v4tadlicuqeeumke.a ... rdata_a_ja](https://jp-real-prod-v4tadlicuqeeumke.api.game25.klabgames.net/ep1002/static/f141c313a139e1e6/masterdata_a_ja)
contains the key but I don't know how to decrypt it.
## Post #189
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-14T14:59:52+00:00
- Post Title: Re: Mobile Game Asset Download

[viewtopic.php?f=10&t=21247](https://forum.xentax.com/viewtopic.php?f=10&t=21247)
## Post #190
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2019-10-16T06:25:23+00:00
- Post Title: Re: Mobile Game Asset Download

Hello, help me please, I am looking for the 3D models of some costumes of the game "Project Tokyo dolls", and I read that they are encrypted but I do not have much knowledge of how to decipher them, 
The models are these:

PLEASE HELP!!!!!
## Post #191
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2019-10-16T10:22:51+00:00
- Post Title: Re: Mobile Game Asset Download

someone helped  grab files from iphone version of  star ocean anamnesis, problem is the files are all .bin. can anyone please tell what to do with the .bin files?
## Post #192
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-10-17T01:55:10+00:00
- Post Title: Re: Mobile Game Asset Download

complete download script for magic HS with file names.
[magicHS.zip](https://xentaxbackup.github.io/file/16911_magicHS.zip)
## Post #193
- Username: nekoknight
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Oct 31, 2018 10:27 am
- Post datetime: 2019-11-03T05:22:05+00:00
- Post Title: Re: Mobile Game Asset Download

I could use some help with locating the asset list for Alice Gear Aegis. 

You have the option to do a "full install" of the game. However, some models do not get downloaded. For example the latest frame arms girl. I tried both fiddler and process hacker with no luck.
## Post #194
- Username: mbugle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 25, 2012 8:18 am
- Post datetime: 2019-11-25T14:25:49+00:00
- Post Title: Re: Mobile Game Asset Download

Hi guys, im trying to get models from idolmaster million live, i have downloaded everything using the python script and an old manifest file that was on the forums but whenever i try the script with a new manifest i get no files, i have uploaded the manifest file here:

[https://drive.google.com/file/d/1_fT6Yn ... sp=sharing](https://drive.google.com/file/d/1_fT6YnEc0h8eue0wxUdX7DMHMCgoX9WI/view?usp=sharing)

Is anyone able to help here because im at a dead end
## Post #195
- Username: SushiiiAnimations
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 02, 2019 7:39 am
- Post datetime: 2019-12-01T23:48:48+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone have the extracted files for the Uta Macross Game? I can't get past the .xab format to port models or motion.
## Post #196
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-12-04T00:43:01+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from otchi ↑Mon Sep 23, 2019 6:23 pm at Mon Sep 23, 2019 6:23 pm
>
> 
Any help?
[https://pastebin.com/qpPEwDEw](https://pastebin.com/qpPEwDEw)
## Post #197
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2019-12-04T20:36:32+00:00
- Post Title: Re: Mobile Game Asset Download

Fairy Quest Online
仙界问情online

[http://cdn1.qyj3d.yyxxgame.com/191114_y ... 31628a6c0f](http://cdn1.qyj3d.yyxxgame.com/191114_yaxd_10//resources/android/assetbundle/assetbundlejsonfile.ab?v=d52dc29d213621bf8e5a1f31628a6c0f)
[assetbundlejsonfile3.zip](https://xentaxbackup.github.io/file/17151_assetbundlejsonfile3.zip)
## Post #198
- Username: MisterPrawn
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Jan 30, 2014 12:36 pm
- Post datetime: 2019-12-09T05:39:25+00:00
- Post Title: Re: Mobile Game Asset Download

I'm trying to download assets and such from King of Fighters All Star, but I can't seem to get a grasp on where to find said assets. If there's a way to get them more proper, let me know! I've seen others be able to rip from it before, but I'd like to personally rip the assets myself.

The Google Play store link: [https://play.google.com/store/apps/deta ... g&hl=en_US](https://play.google.com/store/apps/details?id=com.netmarble.kofg&hl=en_US)

Thanks!
## Post #199
- Username: trytlike1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 05, 2020 6:00 pm
- Post datetime: 2020-01-05T22:39:05+00:00
- Post Title: Re: Mobile Game Asset Download

I can't get to decrypt the game assets for this game. Any help would be appreciated. 

[https://play.google.com/store/apps/deta ... ent.saoars](https://play.google.com/store/apps/details?id=com.bandainamcoent.saoars)
## Post #200
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2020-01-09T23:39:01+00:00
- Post Title: Re: Mobile Game Asset Download

they happen to me the assets of the Love Live All Stars characters please?
## Post #201
- Username: kurokozeref
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Mar 14, 2018 1:56 am
- Post datetime: 2020-01-11T21:02:22+00:00
- Post Title: Re: Mobile Game Asset Download

Need help for Sword Art Online: Integral Factor , I can't find any list i only can get bunch of [https://saoif-com.sslcs.cdngc.net](https://saoif-com.sslcs.cdngc.net) asset
## Post #202
- Username: kitakamikotoha
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 28, 2018 8:59 pm
- Post datetime: 2020-01-12T11:39:15+00:00
- Post Title: Re: Mobile Game Asset Download

I'm trying to follow @shingenseiji and extract models from SideM: Live on Stage, but the tool ended up getting 403 errors for every file it tried to access. Judging from the few early successes on DeviantArt, probably the tool worked early on, but they added 403 responses for everything trying to access pages other than the actual game apps. 
Am I out of luck other than copying from the folder of the game (I don't play)?

EDIT: NVM I found the direct URLs in Resource-urls.txt. It means I can download the models directly from the server.
## Post #203
- Username: kitakamikotoha
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 28, 2018 8:59 pm
- Post datetime: 2020-01-13T07:02:20+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from zerotaku5123 ↑Fri Jan 10, 2020 7:39 am at Fri Jan 10, 2020 7:39 am
>
> 
they happen to me the assets of the Love Live All Stars characters please?

If I remember it right, SIFAS downloads all its assets including models the first time you play the game. I'm almost certain that you can find them in your game files, just dig around until you hit them. The file names should look like this: [https://i0.hdslb.com/bfs/article/356436 ... w_590h.png](https://i0.hdslb.com/bfs/article/356436b34ebb269b8f1dd49f21868837cead2e6e.png@1124w_590h.png)

And then look here: [viewtopic.php?f=10&t=21247](https://forum.xentax.com/viewtopic.php?f=10&t=21247)
## Post #204
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2020-01-15T15:48:26+00:00
- Post Title: Re: Mobile Game Asset Download

Has anyone extracted the models from NND Compass? Opening the extracted apk in asset studio doesnt show any of them under mesh, but the game doesnt seem to download any additional content on first launch so im not really sure where to look for them. I most just want Noho's model
## Post #205
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2020-01-22T07:03:15+00:00
- Post Title: Re: Mobile Game Asset Download

Hello chrrox try to extract some models of the game grimm notes echoes but at the time of extracting them I get files with extension ".prefab" and I have no idea how to open them .... can you please help me?
game:[https://apps.qoo-app.com/en/app/6772](https://apps.qoo-app.com/en/app/6772)
## Post #206
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2020-01-27T18:03:07+00:00
- Post Title: Re: Mobile Game Asset Download

ack, im sorry to post again but could someone help me with ripping from imas side m? ive got the manifest (the file from [https://d2qkdj9w29igl.cloudfront.net/v1 ... id/android](https://d2qkdj9w29igl.cloudfront.net/v1/2020012401-ZwxmviacaxuKTjh6UfHeD0UTOhSerknQ/asset_bundles/android/android)) but its just an extensionless file thats garbled up when i open it in a text editor...im not sure what to do to it to make it into a legible list of files :/
## Post #207
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2020-02-16T14:17:23+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from SushiiiAnimations ↑Mon Dec 02, 2019 7:48 am at Mon Dec 02, 2019 7:48 am
>
> 
Does anyone have the extracted files for the Uta Macross Game? I can't get past the .xab format to port models or motion.

Have the same problem
## Post #208
- Username: cureparfait
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Feb 06, 2020 10:19 pm
- Post datetime: 2020-02-25T14:38:26+00:00
- Post Title: Re: Mobile Game Asset Download

Hi I've been trying to download the manifest/data file from Mirishita specifically for the purpose of exporting things to MMD with Miritores Million Dance but with various roadbumps. td-assets.bn765.com seems to no longer be accessible. Now I have been using MLTD Asset Downloader, but Million Dance will not register the character models as those from the game, so I can't convert either models or motions. I realize I should probably ask the creator of Miritore, considering I'm also having trouble with the "ManifestExport" program, but I'm kinda desperate to just get the .data file, and need general help.
## Post #209
- Username: ChaoticFusion40
- Rank: beginner
- Number of posts: 25
- Joined date: Sat Jun 01, 2019 3:42 pm
- Post datetime: 2020-02-26T01:49:33+00:00
- Post Title: Re: Mobile Game Asset Download

[https://drive.google.com/open?id=1UQDi0 ... Ped2ihM70Q](https://drive.google.com/open?id=1UQDi0YlcJwWU53fwGKxXFxPed2ihM70Q) can someone decrypt this file, this is for star ocean anamnesis 2.12.0
## Post #210
- Username: rmsbsjm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 23, 2020 4:34 pm
- Post datetime: 2020-02-26T07:16:16+00:00
- Post Title: Re: Mobile Game Asset Download

is someone able to help me get links for this game Promise of Wizard [https://apps.qoo-app.com/en/app/8676](https://apps.qoo-app.com/en/app/8676)? I found the links ([https://s4-assets-prod.s4-coly.com/File ... itile_main](https://s4-assets-prod.s4-coly.com/Files/Android/mitile_main)) but it just gives me this when I try to open it in notepad++. tried opening it with assetstudio but it didn't give me any file. tried to look for the link with the list of all files but wasn't able to find that as well.

would be great if someone showed me how to find it as well since I'm kinda new to all this, thanks  

EDIT: I found these, and I'm pretty sure there's a better way to view this than to open it in notepadd++, but I don't know how...
[https://s4-assets-prod.s4-coly.com/Tables/S4MasterData](https://s4-assets-prod.s4-coly.com/Tables/S4MasterData)
[https://s4-assets-prod.s4-coly.com/Tabl ... etFileList](https://s4-assets-prod.s4-coly.com/Tables/S4AssetFileList)
[ghbdrsdgdf.PNG](https://xentaxbackup.github.io/file/17555_ghbdrsdgdf.PNG)
## Post #211
- Username: updl24
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Mar 08, 2020 3:42 pm
- Post datetime: 2020-03-08T08:05:43+00:00
- Post Title: Re: Mobile Game Asset Download

[https://up-dl.net/frp-bypass-apk/](https://up-dl.net/frp-bypass-apk/)
## Post #212
- Username: Cornalito
- Rank: n00b
- Number of posts: 10
- Joined date: Mon Nov 19, 2018 5:52 am
- Post datetime: 2020-03-08T08:20:19+00:00
- Post Title: Re: Mobile Game Asset Download

Is possible get a script for download assets from Princess Connect RE:Dive?
[https://apps.qoo-app.com/es/app/5372](https://apps.qoo-app.com/es/app/5372)
## Post #213
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2020-03-11T03:52:08+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from kitakamikotoha ↑Mon Jan 13, 2020 3:02 pm at Mon Jan 13, 2020 3:02 pm
>
> 
zerotaku5123 wrote: ↑Fri Jan 10, 2020 7:39 am
they happen to me the assets of the Love Live All Stars characters please?


If I remember it right, SIFAS downloads all its assets including models the first time you play the game. I'm almost certain that you can find them in your game files, just dig around until you hit them. The file names should look like this: https://i0.hdslb.com/bfs/article/356436 ... w_590h.png

And then look here: viewtopic.php?f=10&t=21247
I did what you mentioned but it didn't work, I found the models, use the tutorial you sent me and I don't decipher it
## Post #214
- Username: feber13
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 28, 2017 4:54 am
- Post datetime: 2020-04-21T15:05:49+00:00
- Post Title: Re: Mobile Game Asset Download

I tried to do what chrrox said, but it doesn't work? it asks me for a password, I will be doing something wrong, I want to get the csv from mobile legends
[23131312.jpg](https://xentaxbackup.github.io/file/17987_23131312.jpg)
## Post #215
- Username: nosyrbllewe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 23, 2019 4:54 am
- Post datetime: 2020-05-06T04:50:15+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Thu Oct 17, 2019 9:55 am at Thu Oct 17, 2019 9:55 am
>
> 
complete download script for magic HS with file names.

The servers hosting the links are dead as the Magic High School Lost Zero game has shutdown. The post-shutdown offline version of the game seems to have a few of the files, but also seems to lack a significant number of the models (333 ch_* files in the included .obb versus the 2768 ch_* files in this list). Is is possible to retrieve the rest of them somehow? Or am I just out of luck?
## Post #216
- Username: azbycx
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Apr 10, 2018 1:49 am
- Post datetime: 2020-05-07T12:57:43+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from nosyrbllewe ↑Wed May 06, 2020 12:50 pm at Wed May 06, 2020 12:50 pm
>
> 
chrrox wrote: ↑Thu Oct 17, 2019 9:55 am
complete download script for magic HS with file names.


The servers hosting the links are dead as the Magic High School Lost Zero game has shutdown. The post-shutdown offline version of the game seems to have a few of the files, but also seems to lack a significant number of the models (333 ch_* files in the included .obb versus the 2768 ch_* files in this list). Is is possible to retrieve the rest of them somehow? Or am I just out of luck?
[https://mega.nz/file/o99jEB6Q#Z28Mhq_O0 ... 8bjCV-2ufM](https://mega.nz/file/o99jEB6Q#Z28Mhq_O0iuwBB70OKGCUldohpH7DImIk8bjCV-2ufM)
## Post #217
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2020-05-24T01:37:18+00:00
- Post Title: Re: Mobile Game Asset Download

Does this work with Call of Duty Mobile? Interested in some assets from it.
## Post #218
- Username: MrPanda202
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Sep 07, 2019 7:59 pm
- Post datetime: 2020-05-31T23:17:38+00:00
- Post Title: Re: Mobile Game Asset Download

Could you help me get the list from Frozen Adventures A New Match 3 Game?

I have found the structure URL but no luck with finding the manifest/metadata/list

Structure URL is: [https://prod-blackforest.akamaized.net/](https://prod-blackforest.akamaized.net/)

Sample URL for asset: [https://prod-blackforest.akamaized.net/ ... f1f.bundle](https://prod-blackforest.akamaized.net/Android/chapter_greathall_assets_all_a4cbc15b583e6a52b251ab7290bcdf1f.bundle)

That is as far as I could get.

Any help would be greatly appreciated
## Post #219
- Username: Honkasumi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Dec 09, 2018 3:36 pm
- Post datetime: 2020-06-02T23:44:20+00:00
- Post Title: Re: Mobile Game Asset Download

hello there, i have a question, does this extract 3D game models and do i need a specific nox version?
## Post #220
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2020-06-03T12:51:36+00:00
- Post Title: Re: Mobile Game Asset Download

Does someone here still have game files of the game 放課後ガールズトライブ aka Girls Tribe After School ??
This game is called at first time in this Topic.
## Post #221
- Username: HagumiBoi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jun 15, 2020 9:31 pm
- Post datetime: 2020-06-15T13:34:38+00:00
- Post Title: Re: Mobile Game Asset Download

Is there any working sifas decrypt files? like pkg
## Post #222
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-12-18T18:14:31+00:00
- Post Title: Re: Mobile Game Asset Download

Sakura Kakumei Download script for python.


 sakura.zip
(144.04 KiB) Downloaded 97 times


First 0x1000 bytes of xor key for files


 key.zip
(4.11 KiB) Downloaded 92 times



Keys passed to aes stream 3 types.

```
lEnK0pK9akZ9IGcBZiVXT0qLatG3oJQv5135bZsl0D5xPKQC7Gu9pL2R0QVYUkAW6AK38ah7lfgmxYiIn7l4uI7f4d713L6RBy5NE3L1Zbix526WTp3FCkHlWiaE03iXyAEUkXYKSFxaWwHnF5I7E3oIjFT8Km756uprSu071r0vq0yor5PLOprL7QwOIyITp5YPPgiCEKhwBrY5MgXN2X0dKjE16N2mE5X6gTRvNa630bUh1FTyE2

Type 1
Q6BYXbFHZO650Bc/MjgxNjdjNWUtMWI3
f8tmj2yaqhLzQztrMjgxNjdjNWUtMWI3

Type 2
Jr9DW9ksMRv1Lc796mrwv145fXC3L5VcpmKE5VfCuvbrpZGfYwXMpwo9sGkJ54zHse4G7zftpjkhqHHY60O7aQPj4M2ekKMSw094PmXRkN4ftTmDFlYMPmwK8QvhJ20H
```
## Post #223
- Username: infused0doggo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jun 22, 2019 12:19 am
- Post datetime: 2020-12-18T18:39:21+00:00
- Post Title: Re: Mobile Game Asset Download

I got some files from Ensamble Stars but they don't open in Assetstudio and well i tried to see it in binary and i can't get a way to decrypt it, i would apreciate if can someone help me please!

Here an extra file: [https://mega.nz/file/o8Ij0QxJ#i82IS-WHC ... R8tsauZtqs](https://mega.nz/file/o8Ij0QxJ#i82IS-WHCcuik4VsHbXN8xZGp90LxOrQ6R8tsauZtqs)
[Adonis.rar](https://xentaxbackup.github.io/file/19209_Adonis.rar)
## Post #224
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-12-23T13:23:07+00:00
- Post Title: Re: Mobile Game Asset Download

mr.chrrox could u please take a look of this game
[https://lp.gf-music.amebagames.com/?device=pc](https://lp.gf-music.amebagames.com/?device=pc)
[https://play.google.com/store/apps/deta ... ent.gfonpu](https://play.google.com/store/apps/details?id=jp.co.cyberagent.gfonpu)
same company of CGSS and need to gacha to get asset files which is BS
## Post #225
- Username: wansf
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2020-12-24T01:52:06+00:00
- Post Title: Re: Mobile Game Asset Download

I already made a download script for that game.
[viewtopic.php?f=29&t=16055&start=15](https://forum.xentax.com/viewtopic.php?f=29&t=16055&start=15)
## Post #226
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-12-24T02:05:51+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Thu Dec 24, 2020 9:52 am at Thu Dec 24, 2020 9:52 am
>
> 
I already made a download script for that game.
viewtopic.php?f=29&t=16055&start=15
oh i searched with "girl friend" not "girlfriend" xd
it worked well , a big thanks 
but i think they added more cloth and animation since ur script is 3 years ago , could you please make an update?
## Post #227
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2020-12-25T03:20:51+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from infused0doggo ↑Sat Dec 19, 2020 2:39 am at Sat Dec 19, 2020 2:39 am
>
> 
I got some files from Ensamble Stars but they don't open in Assetstudio and well i tried to see it in binary and i can't get a way to decrypt it, i would apreciate if can someone help me please!

Here an extra file: https://mega.nz/file/o8Ij0QxJ#i82IS-WHC ... R8tsauZtqs

Is this the file that it was where?
## Post #228
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2021-01-07T10:00:15+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Dec 19, 2020 2:14 am at Sat Dec 19, 2020 2:14 am
>
> 

First 0x1000 bytes of xor key for files
key.zip

Keys passed to aes stream 3 types.

I tried to xor the file using xor key
the file is here
[https://mega.nz/file/bWxQCDzS#TT8m8svXh ... 5bw8D_CRKY](https://mega.nz/file/bWxQCDzS#TT8m8svXhDHfqEjuhAjZZPfP9O59XKktH5bw8D_CRKY)
it is right?

for the next step what should I do? I don't understant about "Keys passed to aes stream 3 types"
## Post #229
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-02-03T20:41:17+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Oct 12, 2019 8:31 am at Sat Oct 12, 2019 8:31 am
>
> 
Birdie Crush™
バーディークラッシュ
Homepage https://www.facebook.com/pg/BirdieCrush ... e_internal
Birdie Crush.7z
https://image-glb.qpyou.cn/g2/Jenkins/A ... chInfo.xml

The game is officially out and the assets are unencrypted:

[https://play.google.com/store/apps/deta ... oid.common](https://play.google.com/store/apps/details?id=com.com2us.birdiecrush.normal.freefull.google.global.android.common)




birdie.jpg (224.21 KiB) Viewed 497 times
## Post #230
- Username: TheButterDawg
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 8:20 pm
- Post datetime: 2021-02-08T12:55:35+00:00
- Post Title: Re: Mobile Game Asset Download

hi mr. chrrox, can you make a script for decrypting assets from Rockman X DiVE? There some assets files that can accept the key of 10 lengths, but some few or majority might accept keys of either 9, 8 or 7 lengths. Also they mixed up some ACB and ACF formats and also some strange format with a header "s.b...m".
[strange format.PNG](https://xentaxbackup.github.io/file/19493_strange format.PNG)
## Post #231
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2021-02-08T20:39:33+00:00
- Post Title: Re: Mobile Game Asset Download

Hey uh, I've been trying to get this to work with Raid: Shadow Legends, trying to get the three dragon files that only appear during the campaign mode and are only downloaded upon encounter. I can't seem to figure this out. The current version of Nox has a different settings menu and I can't find anywhere within them to install certificates...
## Post #232
- Username: ATFE0123
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Dec 19, 2020 12:03 pm
- Post datetime: 2021-02-18T09:27:42+00:00
- Post Title: Re: Mobile Game Asset Download

I want to decrypt data of Argonavis.
There are a version of Unity and the name of the file, but UnityFS is encrypted.
Is there the person who can find xor key?

Game Files - [https://drive.google.com/file/d/1BeQlgB ... sp=sharing](https://drive.google.com/file/d/1BeQlgBwfme9w0m14_xdD82m66rkuBtZG/view?usp=sharing)
[Arg.png](https://xentaxbackup.github.io/file/19551_Arg.png)
## Post #233
- Username: TheButterDawg
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 8:20 pm
- Post datetime: 2021-02-22T04:32:10+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone know how to use fiddler on Manichi Compile Heart in Nox player? Cause mine can't....

Oh, wait, found the json site here from it's android japanese app: [https://s3-ap-northeast-1.amazonaws.com ... _list.json](https://s3-ap-northeast-1.amazonaws.com/mainichicompileheart/android/download_file_list.json)


P.S: Update files and everything are there in case anyone wants them.
## Post #234
- Username: Monorail
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 23, 2021 11:24 pm
- Post datetime: 2021-02-23T15:43:17+00:00
- Post Title: Re: Mobile Game Asset Download

Can anyone find the assets list/manifest and example urls for Uma Musume? I worked with someone on the Uma Musume Discord to run Uma Musume with HTTP Toolkit, but they can't spot anything like the assets list/manifest in the log. The only thing we got is the base url, prd-storage-umamusume.akamaized.net/dl/resources (need to be verified for typos). 
(All of East Asia outside of Japan is region-locked, but Western IPs can connect to the server in-game. This means East Asian players outside Japan need to use a VPN for the game. Since most network intercepting softwares uses the android VPN function, you can't run both VPN and network interception. Someone in Japan or Western countries should help out)
## Post #235
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-02-24T01:55:53+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Monorail ↑Tue Feb 23, 2021 11:43 pm at Tue Feb 23, 2021 11:43 pm
>
> 
Can anyone find the assets list/manifest and example urls for Uma Musume? I worked with someone on the Uma Musume Discord to run Uma Musume with HTTP Toolkit, but they can't spot anything like the assets list/manifest in the log. The only thing we got is the base url, prd-storage-umamusume.akamaized.net/dl/resources (need to be verified for typos). 
(All of East Asia outside of Japan is region-locked, but Western IPs can connect to the server in-game. This means East Asian players outside Japan need to use a VPN for the game. Since most network intercepting softwares uses the android VPN function, you can't run both VPN and network interception. Someone in Japan or Western countries should help out)

you can dl all asset in game with japan VPN
## Post #236
- Username: Monorail
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 23, 2021 11:24 pm
- Post datetime: 2021-02-24T07:54:42+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wansf ↑Wed Feb 24, 2021 9:55 am at Wed Feb 24, 2021 9:55 am
>
> 
you can dl all asset in game with japan VPN

What's the point if you need the actual game app for the files? 
Anyway someone on Uma Musume Discord located Uma Musume's meta, under root/data/data/jp.co.cygames.umamusume/files/ 
(apply filter "pfb" for model parts, there are 3 types of models, body, head and tail; for texture filter "3d/chara/.../chr*id*_00/materials/")
The format is [https://prd-storage-umamusume.akamaized ... [full_hash](https://prd-storage-umamusume.akamaized.net/dl/resources/Android/assetbundles/%5Bfirst_2_letters_of_hash%5D/%5Bfull_hash)]
example: [https://prd-storage-umamusume.akamaized ... 7DBXZ5UUMF](https://prd-storage-umamusume.akamaized.net/dl/resources/Android/assetbundles/5B/5BXBCEYLUYY5R4LL2ZEZJ57DBXZ5UUMF)
What still has to be done is to get the meta without actually downloading the game and game data, and sadly they can't get into the game after the server opens (their meta is from preload). 

Update: lots of assets have been uploaded to drives and linked to in the Uma Musume Discord.
## Post #237
- Username: leoalan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 02, 2021 8:36 am
- Post datetime: 2021-03-02T04:52:50+00:00
- Post Title: Re: Mobile Game Asset Download

Hello there, i followed the steps for Eiyuu Senki WWX and got the csv: [http://eiyuww.cdn.dmmgames.com/ykFxF45_ ... 1614654255](http://eiyuww.cdn.dmmgames.com/ykFxF45_/z/webgl/Adult_DMM_Mac_Release/StreamingAssets/AssetBundles/WebGL/AssetPath.csv?t=1614654255)
The problem is that i can't read it! I tried with CSVed and this is what appears:
Is the file encrypted? Even changing the unicode in other programs like excel/notepad, is still unreadable gibberish except for few kanjis.
I really appreciate any help.
## Post #238
- Username: leoalan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-03-02T15:27:31+00:00
- Post Title: Re: Mobile Game Asset Download

That is encrypted.
## Post #239
- Username: leoalan
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 02, 2021 8:36 am
- Post datetime: 2021-03-02T18:02:38+00:00
- Post Title: Re: Mobile Game Asset Download

i see. Could you help with the decryption or at least show how to do it? I'm completely clueless about it.
I found about other folks on separated sadpanda galleries that probably used the same Fiddler method to get the .csv, i tried to contact them, but they vanished for months.

(the game have a browser version [http://pc-play.games.dmm.co.jp/play/eiyuwwx/](http://pc-play.games.dmm.co.jp/play/eiyuwwx/), so is easy to get the .csv without emulators.)
I appreaciate your help in any case.

update: i finally got all of the game assets hash. Thanks chrrox for this amazing tutorial.
## Post #240
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-04T23:03:56+00:00
- Post Title: Re: Mobile Game Asset Download

I'm trying to get real racing 3 files but all nothing appears from nox, did I do something wrong??
## Post #241
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-03-05T01:41:36+00:00
- Post Title: Re: Mobile Game Asset Download

Did you try opening the normal browser and see if you see anything.
## Post #242
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-03-05T09:23:48+00:00
- Post Title: Re: Mobile Game Asset Download

mr.chris could you please make a script to dl project sekai asset?
## Post #243
- Username: slivery56789
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Mar 06, 2021 1:36 am
- Post datetime: 2021-03-05T18:13:57+00:00
- Post Title: Re: Mobile Game Asset Download

[edit] im bad, searching for the wrong string
## Post #244
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T19:04:27+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Fri Mar 05, 2021 9:41 am at Fri Mar 05, 2021 9:41 am
>
> 
Did you try opening the normal browser and see if you see anything.
what's the normal browser?
## Post #245
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-03-07T22:32:26+00:00
- Post Title: Re: Mobile Game Asset Download

the built in internet browser in nox.
## Post #246
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-08T21:18:12+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Mon Mar 08, 2021 6:32 am at Mon Mar 08, 2021 6:32 am
>
> 
the built in internet browser in nox.

there's nothing
## Post #247
- Username: dustyegg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 06, 2019 3:37 am
- Post datetime: 2021-03-09T01:09:48+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Sep 07, 2019 7:55 pm at Sat Sep 07, 2019 7:55 pm
>
> 
マジカミ DX
http://games.dmm.com/detail/magicami/
https://asset.magicami.jp/v1/list/14/0
Save This download as magicami.bundle along with the python script
into the same directory then it will download all the files.
Game uses unity.
Added bundle
magicami.zip

So how exactly do I do this?
## Post #248
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-03-09T04:42:56+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from ReVolt ↑Tue Mar 09, 2021 5:18 am at Tue Mar 09, 2021 5:18 am
>
> 
chrrox wrote: ↑Mon Mar 08, 2021 6:32 am
the built in internet browser in nox.


there's nothing

Then he proxy is not setup correctly.
## Post #249
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-03-10T04:58:02+00:00
- Post Title: Re: Mobile Game Asset Download

umamusume launched on DMM now 
it seems to be better quality aseets then mobile 
[https://dmg.umamusume.jp/](https://dmg.umamusume.jp/)
## Post #250
- Username: usernammm
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 17, 2021 6:16 pm
- Post datetime: 2021-03-17T10:17:32+00:00
- Post Title: Re: Mobile Game Asset Download

We can download Uma Musume DMM and discover the assets encrypted with AppData \ LocalLow \ Cygames \ umamusume.
And you can easily see the details of the asset in Asset Studio in the directory where it was installed.
## Post #251
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-03-21T09:11:48+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from usernammm ↑Wed Mar 17, 2021 6:17 pm at Wed Mar 17, 2021 6:17 pm
>
> 
We can download Uma Musume DMM and discover the assets encrypted with AppData \ LocalLow \ Cygames \ umamusume.
And you can easily see the details of the asset in Asset Studio in the directory where it was installed.

they blocked VPN so i cant dl from DMM client
## Post #252
- Username: aidensamuel
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 26, 2021 3:57 am
- Post datetime: 2021-03-25T20:07:04+00:00
- Post Title: Re: Mobile Game Asset Download

[https://dmg.umamusume.jp/](https://dmg.umamusume.jp/) 
I went on this [page](https://dll-file.net/dll_files3.dll.php) but can't download it. I also use a VPN but it won't work.
## Post #253
- Username: omiusoktto
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 31, 2021 8:22 am
- Post datetime: 2021-03-31T00:26:03+00:00
- Post Title: Re: Mobile Game Asset Download

Hi i tried the method with nutaku's project qt but i couldn't find any csv, maybe it's tunneled, but i don't know how to find the address using process hacker :/
## Post #254
- Username: baidon1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2021 1:28 am
- Post datetime: 2021-04-02T17:40:16+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Sep 07, 2019 7:55 pm at Sat Sep 07, 2019 7:55 pm
>
> 
マジカミ DX
http://games.dmm.com/detail/magicami/
https://asset.magicami.jp/v1/list/14/0
Save This download as magicami.bundle along with the python script
into the same directory then it will download all the files.
Game uses unity.
Added bundle
magicami.zip

The link to the assets isn't working.
## Post #255
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-04-02T19:23:47+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from omiusoktto ↑Wed Mar 31, 2021 8:26 am at Wed Mar 31, 2021 8:26 am
>
> 
Hi i tried the method with nutaku's project qt but i couldn't find any csv, maybe it's tunneled, but i don't know how to find the address using process hacker :/

Just use chrome and right click choose inspect and go to network tab.
then reload the page.
## Post #256
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-04-02T19:24:26+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from baidon1 ↑Sat Apr 03, 2021 1:40 am at Sat Apr 03, 2021 1:40 am
>
> 
chrrox wrote: ↑Sat Sep 07, 2019 7:55 pm
マジカミ DX
http://games.dmm.com/detail/magicami/
https://asset.magicami.jp/v1/list/14/0
Save This download as magicami.bundle along with the python script
into the same directory then it will download all the files.
Game uses unity.
Added bundle
magicami.zip


The link to the assets isn't working.

if you use the android app it downloads all files on launch.
## Post #257
- Username: LeonaWest
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 11, 2020 10:59 am
- Post datetime: 2021-04-02T20:03:25+00:00
- Post Title: Re: Mobile Game Asset Download

Decryption of Umamusume is easy with Asset Studio.
However, the facial expression file cannot be applied. There is a file, but the Path of AnimationClip does not match.
Can anyone do it?
## Post #258
- Username: baidon1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2021 1:28 am
- Post datetime: 2021-04-03T12:48:14+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Apr 03, 2021 3:24 am at Sat Apr 03, 2021 3:24 am
>
> 
baidon1 wrote: ↑Sat Apr 03, 2021 1:40 am
chrrox wrote: ↑Sat Sep 07, 2019 7:55 pm
マジカミ DX
http://games.dmm.com/detail/magicami/
https://asset.magicami.jp/v1/list/14/0
Save This download as magicami.bundle along with the python script
into the same directory then it will download all the files.
Game uses unity.
Added bundle
magicami.zip


The link to the assets isn't working.


if you use the android app it downloads all files on launch.
I wish I could, but I could get someone else to do it for me, then that person can send the models to me via download.
## Post #259
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-04-11T03:36:02+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from baidon1 ↑Sat Apr 03, 2021 8:48 pm at Sat Apr 03, 2021 8:48 pm
>
> 
chrrox wrote: ↑Sat Apr 03, 2021 3:24 am
baidon1 wrote: ↑Sat Apr 03, 2021 1:40 am


The link to the assets isn't working.


if you use the android app it downloads all files on launch.

I wish I could, but I could get someone else to do it for me, then that person can send the models to me via download.

u cant export rigged models from that game anyway, just saying
## Post #260
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2021-04-11T08:43:22+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wansf ↑Sun Apr 11, 2021 11:36 am at Sun Apr 11, 2021 11:36 am
>
> 

u cant export rigged models from that game anyway, just saying

yeah I only found cloth accessories was rigged
## Post #261
- Username: Atlus
- Rank: n00b
- Number of posts: 15
- Joined date: Wed Mar 31, 2021 5:52 pm
- Post datetime: 2021-04-14T07:23:27+00:00
- Post Title: Re: Mobile Game Asset Download

I found a manifest file inside a unity asset 


Screenshot 2021-04-13 192220.png (200.1 KiB) Viewed 568 times

and some sort of abconfig file for the reason of the encrypted assets for Rockman X Dive:
manifest

[http://rxdres.capcom.com.tw/174/AssetBu ... 0414150304](http://rxdres.capcom.com.tw/174/AssetBundlesEncrypt/Android/Android?20210414150304)
abconfig

[http://rxdres.capcom.com.tw/174/AssetBu ... 0414150254](http://rxdres.capcom.com.tw/174/AssetBundlesEncrypt/Android/abconfig?20210414150254)

...where do i start from there cause, i found the links on fiddler.
## Post #262
- Username: dustyegg
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 06, 2019 3:37 am
- Post datetime: 2021-05-04T21:38:55+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wansf ↑Sun Apr 11, 2021 11:36 am at Sun Apr 11, 2021 11:36 am
>
> 
baidon1 wrote: ↑Sat Apr 03, 2021 8:48 pm
chrrox wrote: ↑Sat Apr 03, 2021 3:24 am


if you use the android app it downloads all files on launch.

I wish I could, but I could get someone else to do it for me, then that person can send the models to me via download.


u cant export rigged models from that game anyway, just saying

So I'm assming it's not possible to get the character models?
## Post #263
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-05-04T21:47:17+00:00
- Post Title: Re: Mobile Game Asset Download

The character models load fine from the game.
## Post #264
- Username: TakutoD
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 01, 2019 7:34 pm
- Post datetime: 2021-05-08T01:35:47+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from chrrox ↑Sat Apr 03, 2021 3:24 am at Sat Apr 03, 2021 3:24 am
>
> 
baidon1 wrote: ↑Sat Apr 03, 2021 1:40 am
chrrox wrote: ↑Sat Sep 07, 2019 7:55 pm
マジカミ DX
http://games.dmm.com/detail/magicami/
https://asset.magicami.jp/v1/list/14/0
Save This download as magicami.bundle along with the python script
into the same directory then it will download all the files.
Game uses unity.
Added bundle
magicami.zip


The link to the assets isn't working.


if you use the android app it downloads all files on launch.

is the asset list encrypted in the latest versions? I tried downloading the same file you mentioned in your post (the .bundle file) but its nothing like the one you included, I even tried resending the request as list/14/0 like your file but still looks encrypted compared to yours and the python script doesn't work, is it possible for you to upload a newer asset list or do I have to use the android version?
## Post #265
- Username: debukun13
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 29, 2011 7:13 am
- Post datetime: 2021-05-09T01:42:42+00:00
- Post Title: Re: Mobile Game Asset Download

Has the url for Sakura kakumei changed?
I can't seem to download the file...
## Post #266
- Username: doreanh
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 24, 2021 4:43 pm
- Post datetime: 2021-05-24T08:51:33+00:00
- Post Title: Re: Mobile Game Asset Download

I follow your tutorial. It works well until the last stage.
I am trying to get the sprite of the building from Elvenar ([https://downloadapk.net/Elvenar.html](https://downloadapk.net/Elvenar.html))
However, Fiddler shows that the game URL is tunneled 
[](https://ibb.co/N3dfScD)

When I use Process hacker to find the URL as tutorial, it shows nothing (I used elvenar.com in Filter)
Can you please help me?
## Post #267
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2021-05-24T10:31:26+00:00
- Post Title: Re: Mobile Game Asset Download

make sure https inspection is enabled.
Also go to the end of the list as its loaded that could just be the request.
search for 
> GET / in process hacker
its most likely stored on amazon of clodfront o some other cdn.
## Post #268
- Username: baidon1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2021 1:28 am
- Post datetime: 2021-07-07T02:52:04+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from alictzelt ↑Sun Apr 11, 2021 4:43 pm at Sun Apr 11, 2021 4:43 pm
>
> 
wansf wrote: ↑Sun Apr 11, 2021 11:36 am

u cant export rigged models from that game anyway, just saying


yeah I only found cloth accessories was rigged

Changed my mind. I don't need your help for my Magicami movie anyway.
## Post #269
- Username: SushiiiAnimations
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 02, 2019 7:39 am
- Post datetime: 2021-07-17T03:49:39+00:00
- Post Title: Re: Mobile Game Asset Download

Hi, I am fairly new to ripping assets with an xor encryption, so if anyone could help me out in decrypting these assets, that would be amazing of you! 
The game I am trying to decrypt is My Hero Acadamia: The Strongest Hero

I have the assets ripped from my phone, here are the files if anyone is interested!

[https://mega.nz/file/VJ9mjCrC#sNdpodTUI ... xUdOD9kzP4](https://mega.nz/file/VJ9mjCrC#sNdpodTUIMtkfWPz3DsXvSxQ3vrT3QE5PxUdOD9kzP4)

If anyone is willing to help me, that would be awesome!
## Post #270
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-08-01T11:03:50+00:00
- Post Title: Re: Mobile Game Asset Download

@chrrox
could you please create a model downloading script for デタリキZX [http://games.dmm.co.jp/detail/detarikizx/](http://games.dmm.co.jp/detail/detarikizx/)
very similar game to Honeyblade
## Post #271
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-08-31T10:58:23+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone know the final manifest URL of THE IDOLM@STER SideM LIVE ON ST@GE !? It seems to have shutdown today...
## Post #272
- Username: sunnyboy76
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 09, 2021 11:14 am
- Post datetime: 2021-09-14T14:36:34+00:00
- Post Title: Re: Mobile Game Asset Download

Is it possible for mainfes to be encrypted? Because I downloaded all the files when the game was loaded, but except for some obviously not, they are all unreadable code
## Post #273
- Username: NittaMinami
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 11, 2021 8:12 pm
- Post datetime: 2021-09-21T14:30:45+00:00
- Post Title: Re: Mobile Game Asset Download

I m trying every way possible but I cant install the app on Nox,The game is gonna die soon.
It is Project Tokyo Dolls.
What should I do?
## Post #274
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-09-21T16:02:45+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from NittaMinami ↑Tue Sep 21, 2021 10:30 pm at Tue Sep 21, 2021 10:30 pm
>
> 
I m trying every way possible but I cant install the app on Nox,The game is gonna die soon.
It is Project Tokyo Dolls.
What should I do?

that game's models are highly encrypted so better just forget about it
the quality are bad tho
## Post #275
- Username: NittaMinami
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Sep 11, 2021 8:12 pm
- Post datetime: 2021-09-21T16:29:08+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from wansf ↑Wed Sep 22, 2021 12:02 am at Wed Sep 22, 2021 12:02 am
>
> 
NittaMinami wrote: ↑Tue Sep 21, 2021 10:30 pm
I m trying every way possible but I cant install the app on Nox,The game is gonna die soon.
It is Project Tokyo Dolls.
What should I do?


that game's models are highly encrypted so better just forget about it
the quality are bad tho

I understand but at least I wants to keep card art and maybe 3d assets if possible.
I saw someone who seems to have extracted the models.
I really love the game a lot it might be impossible but.
## Post #276
- Username: rosalba
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Apr 24, 2020 8:21 am
- Post datetime: 2021-10-03T02:30:08+00:00
- Post Title: Re: Mobile Game Asset Download

So I uninstalled Nox because I didn't think I would be extracting anymore Game Assets from Mobile Games, but turns out there are other games I'd like to extract assets from.

I re-downloaded the latest version of Nox (7.0.1.6) and followed chroxx's tutorial again to set up the Fiddler-Nox Communication thing, but this time, every time I try to connect to the internet in Nox (by browser), it just keeps displaying the message "There are problems with the security certificate for this site.", followed by "This certificate [the DO_NOT_TRUST Fiddler Cert] isn't from a trusted authority" when clicking the option "View Certificate". When I launch an online game, it's just stuck in the initial loading screen.

Any help about this?

Also:

> Reply from einherjar007 ↑Tue Aug 31, 2021 6:58 pm at Tue Aug 31, 2021 6:58 pm
>
> 
Does anyone know the final manifest URL of THE IDOLM@STER SideM LIVE ON ST@GE !? It seems to have shutdown today...
I just tried the LoS Manifest Links I have, and it still downloads the assets. The URLs I saved are from August 2020.
## Post #277
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-10-03T03:11:44+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from rosalba ↑Sun Oct 03, 2021 10:30 am at Sun Oct 03, 2021 10:30 am
>
> 
I just tried the LoS Manifest Links I have, and it still downloads the assets. The URLs I saved are from August 2020.
Assets other than the model can also be downloaded from the old manifest URL, but it seems that only the model can always be retrieved from the latest manifest URL. A manifest for 2020-December is required.

I have acquired many assets and manifests, but recently, many games have detected communication errors when using a network monitoring proxy. 
Fiddler is almost useless these days. It's best to do a string search with process hacker.
With experience, can usually find the URL of a list file. Of course, some games don't even have a list.

Also, this is a technique taught by chrrox, but sometimes the list file is expanded only in memory.
In particular, json type lists are usually encrypted, so you'll get them from memory.
## Post #278
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-11-02T05:25:29+00:00
- Post Title: Re: Mobile Game Asset Download

[https://gate-of-nightmares.jp/](https://gate-of-nightmares.jp/)

This game came out recently, all the assets are initially contained inside standard CPK files which can be extracted easily but the resulting files seem to be encrypted (maybe), a few sample models here in case someone wants to take a look:

[https://mega.nz/folder/RKACQDxT#AVip8sPn5gyTLMI-ADt9nQ](https://mega.nz/folder/RKACQDxT#AVip8sPn5gyTLMI-ADt9nQ)
## Post #279
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2021-11-02T05:30:51+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from GDL ↑Tue Nov 02, 2021 1:25 pm at Tue Nov 02, 2021 1:25 pm
>
> 
https://gate-of-nightmares.jp/

This game came out recently, all the assets are initially contained inside standard CPK files which can be extracted easily but the resulting files seem to be encrypted (maybe), a few sample models here in case someone wants to take a look:

Just XOR 0x0B
## Post #280
- Username: alictzelt
- Rank: beginner
- Number of posts: 32
- Joined date: Tue Jun 27, 2017 6:02 am
- Post datetime: 2021-11-02T07:05:09+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from GDL ↑Tue Nov 02, 2021 1:25 pm at Tue Nov 02, 2021 1:25 pm
>
> 

https://gate-of-nightmares.jp/

This game came out recently, all the assets are initially contained inside standard CPK files which can be extracted easily but the resulting files seem to be encrypted (maybe), a few sample models here in case someone wants to take a look:

https://mega.nz/folder/RKACQDxT#AVip8sPn5gyTLMI-ADt9nQ

decrypted script is here
[viewtopic.php?f=21&t=24632](https://forum.xentax.com/viewtopic.php?f=21&t=24632)
## Post #281
- Username: bokoboko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 07, 2018 1:11 pm
- Post datetime: 2021-11-08T09:50:02+00:00
- Post Title: Re: Mobile Game Asset Download

Is it just me or does this not work reliably anymore?

I used this solution around 2 years ago for retrieving idolmaster models and it worked fine.

But most games these days seem to detect whether you're using a proxy and refuses the connection, displaying a connection timeout error.

I just tried Blue Archive, it does some initial tunnelling to the api for version info & to send some properties about device you're using and connection information, and then it throws a timeout.

I suppose checking strings in memory is the only viable way to do it now unless the game is packaged with all assets in an xapk/obb file. Just a bother because searching through strings can take a while unless you specifically know what to filter for, and even then some games use hashes to forbid you from directly accessing resource url's.
## Post #282
- Username: kitakamikotoha
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 28, 2018 8:59 pm
- Post datetime: 2021-12-05T08:41:52+00:00
- Post Title: Re: Mobile Game Asset Download

The IM@S thread is pretty much dead at this point, and if anyone that was a regular there is still reading this, maybe go back there and talk about the 2 new games, Starlit Season & SideM GROWING STARS.
## Post #283
- Username: TheLastLantern
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Dec 17, 2021 4:07 pm
- Post datetime: 2021-12-17T08:17:59+00:00
- Post Title: Re: Mobile Game Asset Download

Will it works with DC Comics legends (this is a mobile game on Unity engine)? Because there are so many anime fans on this thread and i can't be sure if this method will be work with this game.
I tried this method with other game, can't remember which (around 4 years ago) but it's was too hard for my brain...
## Post #284
- Username: r195j1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 27, 2021 5:22 pm
- Post datetime: 2021-12-28T03:32:18+00:00
- Post Title: Re: Mobile Game Asset Download

Hi, I'm trying to get the assets from the game alternative girls 2 ([https://play.google.com/store/apps/deta ... .alternajp](https://play.google.com/store/apps/details?id=jp.co.cyberagent.alternajp) Or [https://apkpure.com/%E3%82%AA%E3%83%AB% ... .alternajp](https://apkpure.com/%E3%82%AA%E3%83%AB%E3%82%BF%E3%83%8A%E3%83%86%E3%82%A3%E3%83%96%E3%82%AC%E3%83%BC%E3%83%AB%E3%82%BA2%EF%BC%9Cvr%E5%AF%BE%E5%BF%9C-%E7%BE%8E%E5%B0%91%E5%A5%B3-rpg%E3%82%B2%E3%83%BC%E3%83%A0%EF%BC%9E/jp.co.cyberagent.alternajp)), 

This game will be shutdown soon, while there will be an offline version of the game available, quite a few of the function will be removed.
If possible, I would like to have a backup of the entire game.

I tried to follow the tutorial, but some of the steps cannot be use for this game.

Firstly the with https inspection on, the game wont go past the main screen.

With it off, the Fiddler only shows that the game URL is tunneled.

Using Process hacker as the tutorial, and using the url that was listed in the Fiddler as the filter (amebagames.com and ameba.jp), I'm unable to find links that might contain the csv file.

However when I use the keyword cloudfront as the filter it does provide me with some link, example ([https://d27zeb5uofrx7i.cloudfront.net/m ... dle/bnJx32](https://d27zeb5uofrx7i.cloudfront.net/melo-stg-116-assetbundle/bnJx32)). Those link are able to download some files, but they doesn't seems to be in CSV format.



sample.JPG (127.79 KiB) Viewed 166 times



If I open those file in notepad, they all started with the words UnityFS and is follow by a series of symbol, I can't find a way to convert these file into an CSV.

Can anyone give me some advice on how should I proceed with this? At the moment, I'm not even sure that the link I got from Process hacker is correct.
## Post #285
- Username: r195j1
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-12-28T16:22:21+00:00
- Post Title: Re: Mobile Game Asset Download

> If I open those file in notepad, they all started with the words UnityFS and is follow by a series of symbol

Those are unity3d files and they contain assets. Check this article [http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS](http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS)
You can use AssetStudio for extraction.
## Post #286
- Username: r195j1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 27, 2021 5:22 pm
- Post datetime: 2021-12-29T03:31:14+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from ikskoks ↑Wed Dec 29, 2021 12:22 am at Wed Dec 29, 2021 12:22 am
>
> 
If I open those file in notepad, they all started with the words UnityFS and is follow by a series of symbol

Those are unity3d files and they contain assets. Check this article http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS
You can use AssetStudio for extraction.

I see, so these are the assets files, thanks for the info. Seems like I would need to find another way to find the csv file if I want to get the links to all the assets.
## Post #287
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2022-01-02T04:49:09+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from r195j1 ↑Wed Dec 29, 2021 11:31 am at Wed Dec 29, 2021 11:31 am
>
> 
ikskoks wrote: ↑Wed Dec 29, 2021 12:22 am
If I open those file in notepad, they all started with the words UnityFS and is follow by a series of symbol

Those are unity3d files and they contain assets. Check this article http://wiki.xentax.com/index.php/Unity_Unity3d_UnityFS
You can use AssetStudio for extraction.


I see, so these are the assets files, thanks for the info. Seems like I would need to find another way to find the csv file if I want to get the links to all the assets.
What version do you need files from? PC / iOS / AOS?
## Post #288
- Username: garamika
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 09, 2017 4:29 pm
- Post datetime: 2022-01-03T08:40:47+00:00
- Post Title: Re: Mobile Game Asset Download

PC version is dead already.
If available, I would like the file for Android version
## Post #289
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2022-01-03T21:40:24+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from garamika ↑Mon Jan 03, 2022 4:40 pm at Mon Jan 03, 2022 4:40 pm
>
> 
PC version is dead already.
If available, I would like the file for Android version
[https://disk.yandex.ru/d/HPShZ73mjMm9fw](https://disk.yandex.ru/d/HPShZ73mjMm9fw)
Those files that are not downloaded are audio data, for them you will need to replace the link to melo-stg-106-resources
## Post #290
- Username: garamika
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 09, 2017 4:29 pm
- Post datetime: 2022-01-04T18:37:55+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Mrtest ↑Tue Jan 04, 2022 5:40 am at Tue Jan 04, 2022 5:40 am
>
> 
garamika wrote: ↑Mon Jan 03, 2022 4:40 pm
PC version is dead already.
If available, I would like the file for Android version

https://disk.yandex.ru/d/HPShZ73mjMm9fw
Those files that are not downloaded are audio data, for them you will need to replace the link to melo-stg-106-resources

Thanks a lot!
## Post #291
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2022-01-08T00:30:01+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Mrtest ↑Tue Jan 04, 2022 5:40 am at Tue Jan 04, 2022 5:40 am
>
> 
garamika wrote: ↑Mon Jan 03, 2022 4:40 pm
PC version is dead already.
If available, I would like the file for Android version

https://disk.yandex.ru/d/HPShZ73mjMm9fw
Those files that are not downloaded are audio data, for them you will need to replace the link to melo-stg-106-resources

hello sir , could you please list the assets like that for the game Honey Blade 2X and Detariki Z?
they are both dl on demand bs so please
## Post #292
- Username: SusCX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 05, 2021 8:19 pm
- Post datetime: 2022-01-08T09:47:50+00:00
- Post Title: Re: Mobile Game Asset Download

Is there a way to retrieve a manifest file from Lapis: ReLights?
## Post #293
- Username: r195j1
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 27, 2021 5:22 pm
- Post datetime: 2022-01-08T17:29:50+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Mrtest ↑Tue Jan 04, 2022 5:40 am at Tue Jan 04, 2022 5:40 am
>
> 
garamika wrote: ↑Mon Jan 03, 2022 4:40 pm
PC version is dead already.
If available, I would like the file for Android version

https://disk.yandex.ru/d/HPShZ73mjMm9fw
Those files that are not downloaded are audio data, for them you will need to replace the link to melo-stg-106-resources

Hi, Thanks for helping out, sorry that I missed the notification.

Actually I manage to figure out how to get the fiddler to work.
Because the default android version of NOX is now using android 7, in order to get the fiddler to work with user generated certificate, we'll need to switch NOX to use android 5.
## Post #294
- Username: sunnyboy76
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Sep 09, 2021 11:14 am
- Post datetime: 2022-02-16T19:33:36+00:00
- Post Title: Re: Mobile Game Asset Download

I have encountered some problems. 
I tried to get the resources using your method and I did get some, but when I finished extracting them and comparing them with the game I found that the resources in this list were not complete.
I think there must be another list out there, but I have tried everything and can't get it.
APP namd:com.superhippo.crystalmaidens
## Post #295
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2022-03-20T04:40:54+00:00
- Post Title: Re: Mobile Game Asset Download

Hello Chorrox, I have a question, do all games have a Csv file? 
I made some real progress on my own, but not really efficiently.
I still can't find the CSv files in unity games, 
but I have been able to find them in other games. 
so far its a 50% success rate. 

I have to use charels proxy since fiddler doesn't work for me, would you be able to do a tutorial for that one Chorrox?
## Post #296
- Username: Tectonic
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 29, 2022 12:28 pm
- Post datetime: 2022-04-29T04:33:57+00:00
- Post Title: Re: Mobile Game Asset Download

Hi all,
I have been using Asset Studio to view assets for a mobile game called Slime Isekai Memories and using it to help the community with content. I was hoping for some help to see if there was an easier way to identify any new assets once a new update is live in game other than browsing all the files for the game one at a time and identifying anything new manually. I was hoping there might be some sort of date or time stamp available to make things easier. Any suggestions or help would be much appreciated. Tec
## Post #297
- Username: domamaypa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 29, 2022 7:34 pm
- Post datetime: 2022-04-29T11:44:19+00:00
- Post Title: Re: Mobile Game Asset Download

Hello, I want to view assets (such as CGs and sprite) in a DMM game called Iris Mysteria. Does anyone have any experience on how to do it? I'm pretty new to this.
## Post #298
- Username: JohnyBoi
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun May 01, 2022 2:42 pm
- Post datetime: 2022-08-30T22:01:55+00:00
- Post Title: Re: Mobile Game Asset Download

Hey, does League of Legends Wild Rift work with this method?
I've tried almost anything, including this method, but I must've done something wrong during the process or my knowledge is not enough for it. 
Please, does anyone know?
## Post #299
- Username: abedy
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Aug 29, 2015 3:03 am
- Post datetime: 2022-10-04T15:23:32+00:00
- Post Title: Re: Mobile Game Asset Download

this tut is from 2017 so lot of thigs are not working as used to but you can try to setup Charles and it has Mirror function in menu or press ctrl+alt+I.still need to enable support for ssl whch is easier to use on android 5
## Post #300
- Username: willylbj23
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 30, 2022 2:10 am
- Post datetime: 2022-12-04T21:02:21+00:00
- Post Title: Re: Mobile Game Asset Download

Solved
## Post #301
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2022-12-05T04:24:36+00:00
- Post Title: Re: Mobile Game Asset Download

are they also encrypted, and also runs unity?
## Post #302
- Username: kinobi
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 18, 2022 3:05 pm
- Post datetime: 2023-02-11T05:08:02+00:00
- Post Title: Re: Mobile Game Asset Download

can anyone help me with this game:
[https://apps.qoo-app.com/en/app/4630](https://apps.qoo-app.com/en/app/4630)

i've followed the the tutorial exactly and as it said if the urls dont show up in fiddler, i have to use process hacker. i do see the game assets but the urls aren't working

it just says that dns lookup failed
## Post #303
- Username: gardener
- Rank: n00b
- Number of posts: 13
- Joined date: Mon Apr 03, 2023 11:24 am
- Post datetime: 2023-06-03T19:29:54+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from einherjar007 ↑Thu Apr 11, 2019 8:48 am at Thu Apr 11, 2019 8:48 am
>
> 

hello, how did you get the list with process hacker? i'm having trouble with setting up the port and proxy but would like some assets, thank you
## Post #304
- Username: baidon1
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 03, 2021 1:28 am
- Post datetime: 2023-07-25T18:31:03+00:00
- Post Title: Re: Mobile Game Asset Download

Does anyone know where the character models for Cafe Maid are located?
## Post #305
- Username: send02
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2023 7:58 pm
- Post datetime: 2023-09-24T12:05:02+00:00
- Post Title: Re: Mobile Game Asset Download

Do you know how to open the "Atelier Resleriana" data?
I used AssetStudio and could only see some of the data.
I want to extract audio data.
## Post #306
- Username: Yuune
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 10, 2023 9:59 pm
- Post datetime: 2023-10-10T14:04:03+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from send02 ↑Sun Sep 24, 2023 8:05 pm at Sun Sep 24, 2023 8:05 pm
>
> 
Do you know how to open the "Atelier Resleriana" data?
I used AssetStudio and could only see some of the data.
I want to extract audio data.
I coded this tool to decrypt it's proprietary AB encryption format [https://github.com/hax0r31337/resleriana_tools](https://github.com/hax0r31337/resleriana_tools)
Hope my post helps
## Post #307
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2023-10-11T04:30:48+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Yuune ↑Tue Oct 10, 2023 10:04 pm at Tue Oct 10, 2023 10:04 pm
>
> 

or these from unitypy:  [https://github.com/LukeFZ/AtelierTool](https://github.com/LukeFZ/AtelierTool) [https://github.com/Razmoth/AtelierManager](https://github.com/Razmoth/AtelierManager)

they also made a database to automatically download and decrypt for you [https://gacha.lukefz.xyz/atelier/version](https://gacha.lukefz.xyz/atelier/version)
## Post #308
- Username: send02
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2023 7:58 pm
- Post datetime: 2023-10-12T01:55:14+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from Yuune ↑Tue Oct 10, 2023 10:04 pm at Tue Oct 10, 2023 10:04 pm
>
> 

Thank you for creating the tool.
I was able to decrypt the assets in the Embed folder in the xapk using this tool. However, only the initial data is in that folder.
When I extracted the "catalog.json" and assets from the current latest data and placed the data in the same way, it could not be extracted. Sorry I'm not familiar with "Go", but is there anything else I need to do besides running main.go?
## Post #309
- Username: send02
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Sep 24, 2023 7:58 pm
- Post datetime: 2023-10-12T03:25:22+00:00
- Post Title: Re: Mobile Game Asset Download

> Reply from MrYouKnowItAll ↑Wed Oct 11, 2023 12:30 pm at Wed Oct 11, 2023 12:30 pm
>
> 

Sorry. I was able to extract all data by using this "AtelierTool". Thank you very much!

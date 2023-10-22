## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-21T13:20:51+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Probably most might regard this topic as dead so I guess it'd be better to start a new thread, for tools specially. This is my own version of PIG2FBX, named as A8Tool, 
which supports the latest version(approximately v3.3 above) of Asphalt 8: Airborne for Android, iOS & Win32. 
Compatible also with the lastest version of Asphalt Xtreme(tested on v1.7.0g).

Usage of A8Tool:
Drag and drop one or multiple pig files onto the exe;
Use the following batch commands:

```
for %%f in (*.pig) do A8Tool.exe "%%f"
```

Files from vary platforms have no difference in data. The only difference between Android/iOS and Win32 version is that the files are packed in different ways.

About Textures:
In the attachment, there're 3 respective BMS scripts for each platform in separate folders. For Win32, just run QuickBMS with BinUnpacker.bms, and select any .bin files to
unpack the archives.
But make sure to keep the .bin and their .hdr files in the same folder. To decompress the resulting .tga textures, use the decompressor in their corresponding folder.
Textures from iOS version needs the same decompressor for Android.

Note:
I. You'll need the lastest version of QuickBMS to get those scripts to work.

II. To load ASTC-compressed pvr images in PVRTexTool, you'll need to download astcenc.exe, place the corresponding executables in your preferred location,
then place the location in the environment variable PATH.

III. Beware that A8Tool is NOT compatible with older versions of the game. So use PIG2FBX instead if you game version is lower than v3.3. But it provides a few version checks
so it's still safe to try on that. 

Tested on all bike and car models only but you're welcome to report any issues.


 Asphalt8.rar
(195.33 KiB) Downloaded 454 times



A lightweight edition for Rival Wheels can be found [here](http://forum.xentax.com/viewtopic.php?p=147984#p147984).
## Post #2
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2018-01-22T16:40:26+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Thank you so much! Going to test it right now, will update you regarding eventual bugs.
## Post #3
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2018-01-22T19:15:46+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

This tool didn't work with Asphalt Xtreme .pig
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-23T01:41:14+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from zimex25
>
> This tool didn't work with Asphalt Xtreme .pig
I havn't looked into that game yet. This is mean for Asphalt 8:Airborne only.
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-23T10:31:58+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Well, had a rough look at it's files. There is a difference of only a single byte that specifies which compression it uses. 

Update: It's compatible with Asphalt Xtreme now.(Tested on v1.7.0g)
You'll have to correct the positions of some mesh groups for some models manually.
## Post #6
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2018-01-28T12:20:25+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Perfectly works with the latest Asphalt 8 format.
Didn't try it yet with Xtreme.   
Just wondering, do you think you could make it support also Asphalt Overdrive format?
## Post #7
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-01-29T00:39:57+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Hey guys, quick question, I have Win10 installed on a second partition, yet not very familiar with it, so here goes, forgive my ignorance, how does one gain access to the game files? lol
Looking on goggle, lots of weird websites and lots of fake stuff, anyone can tell me what to do?

thanks
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-29T07:49:05+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from AMG
>
> 
Just wondering, do you think you could make it support also Asphalt Overdrive format?
So I assume you could access to the pig files without any difficulties, then what's your problems?  The data is not compressed at all, as their extesion(dcmp) indicate, and PIG2FBX works totally fine.
Didn't find the game on Google Play & iTunes. I tested on v1.3.1b instead, which is what I can find. Is that the lastest version of the game?
## Post #9
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-29T07:58:17+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from mono24
>
> how does one gain access to the game files?
The apps are by default located in a hidden folder called WindowsApps in the "Program Files" folder of your system drive.
## Post #10
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2018-01-29T10:21:07+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from Bigchillghost
>
> AMG wrote:
Just wondering, do you think you could make it support also Asphalt Overdrive format?  
So I assume you could access to the pig files without any difficulties, then what's your problems?  The data is not compressed at all, as their extesion(dcmp) indicate, and PIG2FBX works totally fine.
Here you can see why I was wondering, about Overdrive   
[blog/?p=1239](http://forum.xentax.com/blog/?p=1239)

"Known issues:
- no support for Asphalt Overdrive; I believe AO pig files need further decompression"

So it worked for you, instead?
It crashes for me.

> Reply from Bigchillghost
>
> AMG wrote:Didn't find the game on Google Play & iTunes. I tested on v1.3.1b instead, which is what I can find. Is that the lastest version of the game?
Yes, I think v1.3.1b is the latest.
## Post #11
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-29T11:30:41+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from AMG
>
> So it worked for you, instead?

Yeah their format is exactly the same as the rather old version of Asphalt 8 where Chipicao's Gameloft Pig Importer can still come in handy.
Um it's more like a mixed version where the dcmp files in the main data folder are uncompressed, while those in the dlcs folder are LZ4-compressed. 
Tested also with these files and PIG2FBX works with no problems either.
So here comes the question: what do you use for extracting the pig files?
## Post #12
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2018-01-29T11:43:19+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from Bigchillghost
>
> AMG wrote:Bigchillghost wrote:So it worked for you, instead?

Yeah their format is exactly the same as the rather old version of Asphalt 8 where Chipicao's Gameloft Pig Importer can still come in handy.
Um it's more like a mixed version where the dcmp files in the main data folder are uncompressed, while those in the dlcs folder are LZ4-compressed. 
Tested also with these files and PIG2FBX works with no problems either.
So here comes the question: what do you use for extracting the pig files?

I didn't, that's why I have issues with those, I guess.
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-29T12:15:39+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from AMG
>
> I didn't, that's why I have issues with those, I guess.
What files did you use the tool on? The dcmp archives directly?
## Post #14
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2018-01-29T12:19:55+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from Bigchillghost
>
> AMG wrote:I didn't, that's why I have issues with those, I guess.
What files did you use the tool on? The dcmp archives directly?
Tried to drag and drop the full .dcmp archive, yes
Then later, (sort of) unpacked the .dcmp archive with 7-zip, and done the same thing with the single .pig files

With both procedures, PIG2FBX crashes.
## Post #15
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-01-29T12:52:54+00:00
- Post Title: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from AMG
>
> 
Tried to drag and drop the full .dcmp archive, yes
Then later, (sort of) unpacked the .dcmp archive with 7-zip, and done the same thing with the single .pig files

With both procedures, PIG2FBX crashes.
The dcmp archives start with 5 zero bytes, not the typical "PK\x03\x04" identifier. I didn't expect WinRar would work though. But even so, there're no issues in my case since all the files are extracted correctly. You're supposed to use it on the pig files from model.dcmp in the folder files\data\ where there're only 4 cars only, but not those from the dlcs folder.
## Post #16
- Username: autobotlongarm
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 25, 2015 7:38 am
- Post datetime: 2018-02-02T21:49:33+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

How do I extract the textures to a correct format?
BTW my Asphalt 8 IPA version is 3.3.1
## Post #17
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-03T02:31:32+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from autobotlongarm
>
> How do I extract the textures to a correct format?
BTW my Asphalt 8 IPA version is 3.3.1
Did you actually read the first post?

> Reply from Bigchillghost
>
> To decompress the resulting .tga textures, use the decompressor in their corresponding folder.
Textures from iOS version needs the same decompressor for Android.
You'll need the lastest version of QuickBMS to get those scripts to work.
## Post #18
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-02-04T10:50:56+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Thank you so much for this tool.    It's working nicely till now...will report if I will face any bug.
I managed to rip models and textures from Asphalt Xtreme using Ninja Ripper and Bluestacks...but after an update the game stopped working on my bluestacks so was unable rip further.
here is the one I have done: [http://gamemodels.ru/files/file/7212-fo ... s-mkii-09/](http://gamemodels.ru/files/file/7212-ford-focus-rs-mkii-09/)

[EDIT]Unable to rip the textures from Asphalt Xtreme.Gettng ths error:
## Post #19
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-04T13:50:55+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from taruncreation
>
> Unable to rip the textures from Asphalt Xtreme.Gettng ths error:
Please read carefully the entire first post.

> Reply from Bigchillghost
>
> 
You'll need the lastest version of QuickBMS to get those scripts to work.
## Post #20
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-02-04T17:51:31+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Is Quick BMS version 0.8.3 the latest version? If not where can I find the latest version?
## Post #21
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2018-02-04T20:09:32+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from taruncreation
>
> Is Quick BMS version 0.8.3 the latest version? If not where can I find the latest version?

It is. Seems like you used v0.7.7
## Post #22
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-05T01:29:06+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Technically it requires at least v0.8.2, but there's no harm in keeping your tools up to date.
## Post #23
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-02-05T10:17:07+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Have used the latest version but still can't  get the texture file.
Here is the file I was trying to decompress: [https://app.box.com/s/4vrssovvtrnkm6potpw37op062psimrn](https://app.box.com/s/4vrssovvtrnkm6potpw37op062psimrn)
## Post #24
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-05T11:43:06+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from taruncreation
>
> Have used the latest version but still can't  get the texture file.
You should describe your problem more specifically.
No issue with mine.
## Post #25
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-05T15:34:47+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Bigchillghost
>
> mono24 wrote:how does one gain access to the game files?
The apps are by default located in a hidden folder called WindowsApps in the "Program Files" folder of your system drive.
That is not what I meant, the location is NOT the problem, gaining access to the folder IS though, access is denied, changing owner of the folder and such wont help, access is restricted, like its encrypted as well.
## Post #26
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-05T15:53:30+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from mono24
>
> That is not what I meant, the location is NOT the problem
Then why not say it early?

> Reply from mono24
>
> gaining access to the folder IS though, access is denied, changing owner of the folder and such wont help, access is restricted, like its encrypted as well.
Same problem happened to me when I was trying to load one of the files directly into the hex editor. The solution is rather easy.
You simply just copy those files to another path and that's all.
## Post #27
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2018-02-05T15:59:12+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Bigchillghost
>
> You simply just copy those files to another path and that's all.
Not at all, still cant gain access, no matter what I try to do I am forbidden, very strange.
## Post #28
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-05T16:08:50+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

I can delete or copy the files within the folder, however restoring, namely any modifications to the folder will be denied.
## Post #29
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-08T08:37:51+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Tip on loading ASTC-compressed pvr images from Asphalt Xtreme. See the notes in the first post.
## Post #30
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-02-16T21:48:10+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

wow, thanks!
## Post #31
- Username: autobotlongarm
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Tue Aug 25, 2015 7:38 am
- Post datetime: 2018-02-17T01:49:52+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

I ran into a problem, and that's Asphalt Nitro pig file not extracting for some reason. The only model I see worth extracting from it is the Dodge Challenger SRT8 and the Ford Shelby GT500 since they look different to their Asphalt 8 counterpart.
## Post #32
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-02-17T13:10:54+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from autobotlongarm
>
> I ran into a problem, and that's Asphalt Nitro pig file not extracting for some reason.
The error message has already pointed you the solution:
"Wrong game version! Try PIG2FBX instead!"

Of course you won't see this message if you're not running the tool through command line.
## Post #33
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-10-15T10:04:34+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

cant import the textures from Aspalt Xtreme. And i unfortunatelly dont understand what the author means in the main post.. "To load ASTC-compressed pvr images in PVRTexTool, you'll need to download astcenc.exe, place the corresponding executables in your preferred location,
then place the location in the environment variable PATH." What are the "corresponding executables"? What is the "environment variable PATH"? Where is this location?
## Post #34
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-15T12:29:00+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Gta5KoRn
>
> cant import the textures from Aspalt Xtreme. And i unfortunatelly dont understand what the author means in the main post.. "To load ASTC-compressed pvr images in PVRTexTool, you'll need to download astcenc.exe, place the corresponding executables in your preferred location, then place the location in the environment variable PATH."
Alright, think I'm gonna explain you "patiently".

> Reply from Gta5KoRn
>
> What are the "corresponding executables"?
If you'd already downloaded the astc-encoder you should probably notice that there're binary executables for different computer architectures. So, pick the CORRESPONDING one for your system.

> Reply from Gta5KoRn
>
> What is the "environment variable PATH"?
Refer to the wiki: [https://en.wikipedia.org/wiki/PATH_(variable)](https://en.wikipedia.org/wiki/PATH_%28variable%29). Don't know how to add a new location into the PATH? Google it!

> Reply from Gta5KoRn
>
> Where is this location?
It reads "your preferred location", so any location where you prefer the astcenc.exe to be. As simple as that.
## Post #35
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-10-15T16:58:18+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

ok, everything solved. But another question. The textures look weird. Its not how it supposed to be i guess: [https://imgur.com/a/GcBUuHT](https://imgur.com/a/GcBUuHT) 
Any fix on this?
------------------
EDIT: solved too. pvrtextool cant handle the android version textures. but works with ios version. 
Thanks for the help
## Post #36
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-16T01:42:01+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Gta5KoRn
>
> The textures look weird. Its not how it supposed to be i guess: https://imgur.com/a/GcBUuHT 
Any fix on this?
I specially downloaded the Android version game again (v1.7.3) and they still work fine:



car_suv_mercedes-benz_g500_livery02_occ_mk.jpg (122.28 KiB) Viewed 268 times


But in your screenshot it shows your image format is astc 8x8 which doesn't make sense.
## Post #37
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2018-10-16T09:01:36+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Gta5KoRn
>
> ok, everything solved. But another question. The textures look weird. Its not how it supposed to be i guess: https://imgur.com/a/GcBUuHT 
Any fix on this?
------------------
EDIT: solved too. pvrtextool cant handle the android version textures. but works with ios version. 
Thanks for the help

PVRTexTool is working fine with android and IOS both...You haven't figured that astc encoder perfectly...
## Post #38
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-10-16T09:09:12+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Bigchillghost
>
> Gta5KoRn wrote:The textures look weird. Its not how it supposed to be i guess: https://imgur.com/a/GcBUuHT 
Any fix on this?
I specially downloaded the Android version game again (v1.7.3) and they still work fine:
car_suv_mercedes-benz_g500_livery02_occ_mk.jpg
But in your screenshot it shows your image format is astc 8x8 which doesn't make sense.
no idea... thats how it is. Pvrtextool v4.20, Asphalt Xtreme 1.7.3b build 17325 (OpenGL ES 3.1). I see there is another build Asphalt Xtreme 1.7.3b build 17324 (OpenGL ES 2.0)
here the downloadlink of 17325: [https://cloud.mail.ru/public/5Je2/LD9NWzMnc](https://cloud.mail.ru/public/5Je2/LD9NWzMnc)
## Post #39
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-16T09:12:47+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Just upload your tga file so I can have a check.
## Post #40
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-10-16T11:04:56+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

[https://www.mediafire.com/file/lzwvw0sg ... ga.7z/file](https://www.mediafire.com/file/lzwvw0sg6wcuued/android_tga.7z/file) 
only "car_suv_mercedes-benz_g500_rfx.tga" can be imported bug free
## Post #41
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-16T12:03:12+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Bigchillghost
>
> 
But in your screenshot it shows your image format is astc 8x8 which doesn't make sense.
My bad. Your image was indeed in astc 8x8 format. 



car_suv_mercedes-benz_g500_occ_mk.jpg (118.11 KiB) Viewed 260 times



> Reply from Gta5KoRn
>
> 
only "car_suv_mercedes-benz_g500_rfx.tga" can be imported bug free
They all work fine:

car_suv_mercedes-benz_g500_rfx.tga is also astc 8x8 compressed, no idea why you can open it correctly but failed with the others.
## Post #42
- Username: Gta5KoRn
- Rank: beginner
- Number of posts: 23
- Joined date: Fri Jul 28, 2017 11:12 pm
- Post datetime: 2018-10-16T19:30:18+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

well, pvrtextool is sometimes weird. i had another error by import, it said the texture doesnt exist in the location where it is, or something like this.  
Just tried again to import android textures and they are pink. Anyway they work fine with the ios version.
## Post #43
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-10-17T09:14:52+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Gta5KoRn
>
> well, pvrtextool is sometimes weird.
If it works well on everyone else's PC but not yours, then it must be you doing something wrong.
So what did you do exactly to solve the astc-encoding issue?

> Reply from Gta5KoRn
>
> i had another error by import, it said the texture doesnt exist in the location where it is, or something like this.
If you encounter an error like this:



PathIssue.jpg (9.64 KiB) Viewed 247 times


then your path must contain illegal characters.

> Reply from Gta5KoRn
>
> Anyway they work fine with the ios version.
Does it work with the astc-encoded images?
## Post #44
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2018-12-17T21:20:44+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

> Reply from Bigchillghost
>
> Files from vary platforms have no difference in data. The only difference between Android/iOS and Win32 version is that the files are packed in different ways.
There are difference in texture compression, iOS version have less compession artifacts.
I uploaded my testing samples [here](https://www.mediafire.com/file/iy78t4au954e8db/A8_Textures_test.zip/file), if anyone's curious.
## Post #45
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-01-26T15:54:46+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win3

Here's a forked edition specially modified for the game Rival Wheels.


 A8ToolRW.zip
A8Tool RW Edition (10.73 KiB) Downloaded 101 times


Textures from this game are legacy PVR images, so just change the ext form tga to pvr.

Note that the security checks are removed in this ver so it'll definitely crash with files from other games.
## Post #46
- Username: st2davo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 25, 2019 8:20 pm
- Post datetime: 2019-11-25T13:51:06+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Hi guys, im trying to get textures from Six-Guns. Could this tutorial work? Because after I tried to decompress some TGAs in QuickBMS it says "unhandled compression 0, 0files found in 0 seconds"
## Post #47
- Username: n53lab1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Sep 19, 2019 12:17 pm
- Post datetime: 2019-12-01T13:28:48+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

every time i try A8 tools it crashes.... i am using A8 v 3.3.1.... and how to extract texture from it?
## Post #48
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2019-12-09T15:10:13+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> and how to extract texture from it?

For the models just Drag&Drop the .pig files in A8Tool and for textures use the AndroidTexturesDecompressor.bms to convert the tga files to pvr if you're ripping from Android version of game else use the TextureDecompressor.bms from Win32 folder.
## Post #49
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-06-16T02:24:37+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

I tried to get textures but they are corrupted when I load them in pvrtextool
## Post #50
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2020-06-16T05:26:16+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from LetMeDownloadPervert ↑Tue Jun 16, 2020 10:24 am at Tue Jun 16, 2020 10:24 am
>
> 
I tried to get textures but they are corrupted when I load them in pvrtextool

I think you will have to download the whole PVRTexTool SDK.
## Post #51
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-06-16T12:22:11+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Eh, there is a problem. I already have the SDK.
## Post #52
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-06-16T12:50:29+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from taruncreation ↑Tue Oct 16, 2018 5:01 pm at Tue Oct 16, 2018 5:01 pm
>
> 
Gta5KoRn wrote:ok, everything solved. But another question. The textures look weird. Its not how it supposed to be i guess: https://imgur.com/a/GcBUuHT 
Any fix on this?
------------------
EDIT: solved too. pvrtextool cant handle the android version textures. but works with ios version. 
Thanks for the help

PVRTexTool is working fine with android and IOS both...You haven't figured that astc encoder perfectly...

Eh, I am having the same problem too. What do you mean by "figured that astc encoder perfectly..."
## Post #53
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-06-16T13:01:35+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

help, when I rip textures from windows version, I get these errors

```
- open input file E:\twinmill\textures_win32.bin.hdr

- error in src\file.c line 557: fdnum_open()
Error: No such file or directory

Last script line before the error or that produced the error:
  14  open . IdxName 1

Press ENTER or close the window to quit
```
## Post #54
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-06-16T16:52:39+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from LetMeDownloadPervert ↑Tue Jun 16, 2020 10:24 am at Tue Jun 16, 2020 10:24 am
>
> 
I tried to get textures but they are corrupted when I load them in pvrtextool
Upload the source ".tga" files so that you don't waste anybody's time.

> Reply from LetMeDownloadPervert ↑Tue Jun 16, 2020 9:01 pm at Tue Jun 16, 2020 9:01 pm
>
> 
I get these errors
Code: Select all- enter in folder .
- open input file E:\twinmill\textures_win32.bin.hdr

- error in src\file.c line 557: fdnum_open()
Error: No such file or directory
Two possibilities:
1. You didn't copy the correspinding hdr files to the folder;
2. They changed the archive structure so the script no longer works.
## Post #55
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-06-24T12:41:27+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Later I have fixed this. I did not decompress the textures correctly.
## Post #56
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-09-09T13:41:36+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

new game BRIO Virtual Drift Challenge I got textures but a8tool isn't working for this
## Post #57
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-09-09T13:43:41+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

nvm I used the rival wheels version and it worked woohoo
## Post #58
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-09-09T13:45:04+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

nope all I get is just a mess of vertices
## Post #59
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2020-10-17T06:45:12+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from ReVolt ↑Wed Sep 09, 2020 9:45 pm at Wed Sep 09, 2020 9:45 pm
>
> 
nope all I get is just a mess of vertices

Hi , use PIG2FBX for the models
## Post #60
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-17T15:08:55+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Where do I find PIG2FBX? I googled it and all I could find was the source code.
## Post #61
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-17T15:15:49+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

nvm I found it, but when I use it the car is cut in half and there is corrupted faces that are flying around the vehicle.
## Post #62
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2020-10-17T15:16:34+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

here's the brio's file:
[http://www.mediafire.com/file/epn5x48nj ... t.pig/file](http://www.mediafire.com/file/epn5x48njip5ziq/car_brio_rs_opt.pig/file)
## Post #63
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2020-10-17T16:41:09+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from ReVolt ↑Sat Oct 17, 2020 11:16 pm at Sat Oct 17, 2020 11:16 pm
>
> 
here's the brio's file:
http://www.mediafire.com/file/epn5x48nj ... t.pig/file

No bro actually this game was made in partnership of Gameloft and Honda...if u notice it is similar to Asphalt Nitro...u just need to mirror the half part and join both the parts together that's it.
## Post #64
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2020-11-15T07:19:56+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Hi , 
The .pig files from latest version are not rippable using A8Tool now. Or is it something wrong with my system?



[Sample File](https://app.box.com/s/iae0pfwh6yuttn4qde2rojanenbslwmt)
## Post #65
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-11-16T12:07:54+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from taruncreation ↑Sun Nov 15, 2020 3:19 pm at Sun Nov 15, 2020 3:19 pm
>
> Or is it something wrong with my system?
Apparently. You can tell that by running the tool without any params specified.
The format is still identical.



car_aston_martin_valhalla.png (232.14 KiB) Viewed 231 times
## Post #66
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2020-11-23T14:48:20+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

it's working now , It was missing vcruntime140.dll
## Post #67
- Username: tempaccount555
- Rank: beginner
- Number of posts: 27
- Joined date: Sun May 12, 2019 8:14 pm
- Post datetime: 2021-03-27T07:14:39+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

anyone know how to extract the A8 textures? Pls?
## Post #68
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-05-27T16:03:10+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

im sorry but if i import it has nothing
## Post #69
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-06-29T11:12:43+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

like i mean there are no vertices created
## Post #70
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-24T11:22:47+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

how about the asphalt nitro 2 .cpig files, while not released yet, please make support
## Post #71
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-07-27T08:05:36+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

on my pc it doesn't work but in the other pc it works
## Post #72
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2021-07-29T15:02:01+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from fajNYgosciu1234 ↑Sat Jul 24, 2021 7:22 pm at Sat Jul 24, 2021 7:22 pm
>
> 
how about the asphalt nitro 2 .cpig files, while not released yet, please make support

The Rival Wheels converter works fine with Asphalt Nitro 2. Check the bottom of very first post of this thread to find the converter.
## Post #73
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-02T18:04:01+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

does it have the issues from asphalt nitro original where vehicle is in half
## Post #74
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2021-08-05T11:16:35+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from fajNYgosciu1234 ↑Tue Aug 03, 2021 2:04 am at Tue Aug 03, 2021 2:04 am
>
> 
does it have the issues from asphalt nitro original where vehicle is in half

Yes , that one of the way Gameloft has tried to cut down on the game's size. also no MP , low res. textures etc.
## Post #75
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-15T16:15:59+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

for some reason, when i use this converter, i get empty models, no vertices, just empty [https://www.mediafire.com/file/8cgno5rp ... shapes.fbx](https://www.mediafire.com/file/8cgno5rpchap8w6/alp_area_02_levelshapes.fbx)
## Post #76
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2021-08-18T15:16:56+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from fajNYgosciu1234 ↑Mon Aug 16, 2021 12:15 am at Mon Aug 16, 2021 12:15 am
>
> 
for some reason, when i use this converter, i get empty models, no vertices, just empty https://www.mediafire.com/file/8cgno5rp ... shapes.fbx

Yeah there seems to be something wrong with this .fbx file...maybe post the original .pig file?
## Post #77
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-08-18T15:54:45+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

i think it's an issue with my pc, but idk which one
## Post #78
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-08-29T23:14:06+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

How will we extract the game's data now? Using Android version. Normally the Android/data/com.gameloft.android.ANMP.GloftA8HM and Android/obb/com.gameloft.android.ANMP.GloftA8HM  would contain all of the games data. But now, the data folder only contains cache and misc content. And the obb folder doesn't even contain the game !
## Post #79
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-09-21T17:09:35+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

does this work for sonic runners adventure, this uses a similar format
## Post #80
- Username: xersey789
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Sep 24, 2021 4:12 pm
- Post datetime: 2021-09-25T15:25:16+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Hey can you give me alink so to download the a8tool pls
## Post #81
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2021-11-03T11:38:52+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from Bigchillghost ↑Sat Jan 26, 2019 11:54 pm at Sat Jan 26, 2019 11:54 pm
>
> 
Here's a forked edition specially modified for the game Rival Wheels.
A8ToolRW.zip
Textures from this game are legacy PVR images, so just change the ext form tga to pvr.

Note that the security checks are removed in this ver so it'll definitely crash with files from other games.
Some models appear to be broken upon conversion tho:



I could get away with just mirroring the model and all, but I've also noticed a few details missing as well, apart from Rapunzel which I tried to reproduce what you demonstrated.
## Post #82
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-11-03T16:45:18+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from huckleberrypie ↑Wed Nov 03, 2021 7:38 pm at Wed Nov 03, 2021 7:38 pm
>
> 
Some models appear to be broken upon conversion tho
Um, it's indeed a bit different than the RW format. Here's the modified version for this game:


 DisneyPrincessMajesticQuest.zip
(11.15 KiB) Downloaded 31 times



You'll still have to create a mirrored clone of the half mesh though.
## Post #83
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2021-11-04T01:16:41+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from Bigchillghost ↑Thu Nov 04, 2021 12:45 am at Thu Nov 04, 2021 12:45 am
>
> 
huckleberrypie wrote: ↑Wed Nov 03, 2021 7:38 pm
Some models appear to be broken upon conversion tho

Um, it's indeed a bit different than the RW format. Here's the modified version for this game:
DisneyPrincessMajesticQuest.zip

You'll still have to create a mirrored clone of the half mesh though.
Alright, thanks!
## Post #84
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-19T17:42:00+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from ReVolt ↑Mon Aug 30, 2021 7:14 am at Mon Aug 30, 2021 7:14 am
>
> 
How will we extract the game's data now? Using Android version. Normally the Android/data/com.gameloft.android.ANMP.GloftA8HM and Android/obb/com.gameloft.android.ANMP.GloftA8HM  would contain all of the games data. But now, the data folder only contains cache and misc content. And the obb folder doesn't even contain the game !

did you try getting some models from models folder
## Post #85
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2021-12-19T18:58:02+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

how to extract dlcs .jpk
## Post #86
- Username: farfocl3
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Apr 29, 2022 12:12 pm
- Post datetime: 2022-04-30T04:34:47+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Hi, Bigchillghost. Would you mind take a look at the .pig files from [an android game I'm trying to convert](https://forum.xentax.com/viewtopic.php?f=16&t=25300). I have tried using the different tools in this thread, but all of them don't even produce a .fbx - I just get nothing.

After having another person taking a look at it, it seems that the vertices are unknown - maybe encrypted?

Anyway, I'm attaching an example file (the player character), so you don't have to grab the whole 700mb pack linked in the topic above. Maybe you can crack it?

Thanks in advance.
[ch_tintin.zip](https://xentaxbackup.github.io/file/22170_ch_tintin.zip)
## Post #87
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2022-07-07T12:21:05+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from farfocl3 ↑Sat Apr 30, 2022 12:34 pm at Sat Apr 30, 2022 12:34 pm
>
> 
Hi, Bigchillghost. Would you mind take a look at the .pig files from an android game I'm trying to convert. I have tried using the different tools in this thread, but all of them don't even produce a .fbx - I just get nothing.

After having another person taking a look at it, it seems that the vertices are unknown - maybe encrypted?

Anyway, I'm attaching an example file (the player character), so you don't have to grab the whole 700mb pack linked in the topic above. Maybe you can crack it?

Thanks in advance.

I am looking forward to this as well.
## Post #88
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-07-21T19:59:51+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

i'm trying to convert the track models, however when i drag and drop multiple of them there is only 1 pig file converted
## Post #89
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2022-07-22T06:17:08+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

i made a batch and it worked
> Reply from fajNYgosciu1234 ↑Fri Jul 22, 2022 3:59 am at Fri Jul 22, 2022 3:59 am
>
> 
i'm trying to convert the track models, however when i drag and drop multiple of them there is only 1 pig file converted
## Post #90
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2022-07-22T07:04:52+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from fajNYgosciu1234 ↑Fri Jul 22, 2022 2:17 pm at Fri Jul 22, 2022 2:17 pm
>
> 
Would it kill you to click the thank button and actually show your gratitude to the creator of the tool you're using? And for Gods' sake when will you ever learn to edit your post and avoid double-posting?
## Post #91
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-08-10T14:18:14+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

im trying to convert the a8 textures (windows version) but all it does is output corrupt pvrs I can't open...help???
## Post #92
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-10T14:20:05+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from ReVolt ↑Wed Aug 10, 2022 10:18 pm at Wed Aug 10, 2022 10:18 pm
>
> 
im trying to convert the a8 textures (windows version) but all it does is output corrupt pvrs I can't open...help???

Use the AndroidTexturesDecompressor.bms for the textures from Windows version...
## Post #93
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-08-10T14:22:18+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from taruncreation ↑Wed Aug 10, 2022 10:20 pm at Wed Aug 10, 2022 10:20 pm
>
> 
ReVolt wrote: ↑Wed Aug 10, 2022 10:18 pm
im trying to convert the a8 textures (windows version) but all it does is output corrupt pvrs I can't open...help???


Use the AndroidTexturesDecompressor.bms for the textures from Windows version...
this is what appears for me:

file used: car_9ff_gt9_df.pvr
## Post #94
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2022-08-10T14:26:03+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

You seem to be using an old version of PVRTexTool then...maybe download the latest SDK.
I've been easily converting these textures in mine..
## Post #95
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-08-10T14:28:53+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

ok I'll use that   I've been using the old version because some textures didn't load correctly for me in the newer versions before
## Post #96
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-08-10T14:32:52+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

now it just gives me this 


(fixed) used android decrompressor
## Post #97
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-02-28T22:40:17+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from fajNYgosciu1234 ↑Fri Jul 22, 2022 2:17 pm at Fri Jul 22, 2022 2:17 pm
>
> 
i made a batch and it workedfajNYgosciu1234 wrote: ↑Fri Jul 22, 2022 3:59 am
i'm trying to convert the track models, however when i drag and drop multiple of them there is only 1 pig file converted
 How did you "made a batch" I am having the same issue
## Post #98
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-02-28T23:32:34+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from antr ↑Wed Mar 01, 2023 6:40 am at Wed Mar 01, 2023 6:40 am
>
> 
fajNYgosciu1234 wrote: ↑Fri Jul 22, 2022 2:17 pm
i made a batch and it workedfajNYgosciu1234 wrote: ↑Fri Jul 22, 2022 3:59 am
i'm trying to convert the track models, however when i drag and drop multiple of them there is only 1 pig file converted


 How did you "made a batch" I am having the same issue
nevermind I found out how to create this batch 
(if anyone is interested): 

@echo off
for %%f in (*.pig) do (
    A8Tool.exe "%%f"
)
echo All files converted successfully.
pause
## Post #99
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T00:06:10+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

so I converted the alps track to fbx now I have the 3d model but how do I apply the texture to each 3d model (I can't find away to convert the tga files)
## Post #100
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2023-03-01T02:31:24+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from antr ↑Wed Mar 01, 2023 8:06 am at Wed Mar 01, 2023 8:06 am
>
> 
so I converted the alps track to fbx now I have the 3d model but how do I apply the texture to each 3d model (I can't find away to convert the tga files)

The BMS script to convert textures don't work for you?
## Post #101
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T12:14:09+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from taruncreation ↑Wed Mar 01, 2023 10:31 am at Wed Mar 01, 2023 10:31 am
>
> 
antr wrote: ↑Wed Mar 01, 2023 8:06 am
so I converted the alps track to fbx now I have the 3d model but how do I apply the texture to each 3d model (I can't find away to convert the tga files)


The BMS script to convert textures don't work for you?

it worked (I found a way to convert tga) but blender can't read the pvr textures it just shows them as pink
## Post #102
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2023-03-01T12:16:31+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

Can you post the .pvr file here?
## Post #103
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T12:46:03+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

ok , I found a way to convert pvr to jpg but texture are over pixelated so unusable how do you do something like that [https://www.youtube.com/watch?v=hmsqVRcp-cs](https://www.youtube.com/watch?v=hmsqVRcp-cs) 
here the texture are not pixelated how did he do that ?
## Post #104
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T12:57:20+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

I can't post the texture apparently a 432 Ko file is to much
## Post #105
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2023-03-01T12:59:48+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

You can upload it to some file hosting site and share the link here... 
Sites like Mediafire, Box etc.
## Post #106
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T13:23:14+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from taruncreation ↑Wed Mar 01, 2023 8:59 pm at Wed Mar 01, 2023 8:59 pm
>
> 
You can upload it to some file hosting site and share the link here... 
Sites like Mediafire, Box etc.
example of overpixelated unusable texture (they are all like this)
[https://www.mediafire.com/view/xafpy45v ... r.jpg/file](https://www.mediafire.com/view/xafpy45vg57xdwp/alp_lm_area_07_levelshapesmonfeur.jpg/file)
## Post #107
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T13:24:27+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

and just to know have you already converted an asphalt 8 track in blender with the texture I can't find anything online about this
## Post #108
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2023-03-01T13:41:39+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from antr ↑Wed Mar 01, 2023 9:24 pm at Wed Mar 01, 2023 9:24 pm
>
> 
and just to know have you already converted an asphalt 8 track in blender with the texture I can't find anything online about this

For example I just converted the textures from the track "Alps" and yes there are textures similar to the ones you posted above. I don't know how the game uses those textures but there are other textures as well for the buildings , asphalt , grass , scenery etc. You can try checking all the textures for the track.
Alps textures : [https://app.box.com/s/7q5f365lfwunq3m2y5s9pgxtsncawpt9](https://app.box.com/s/7q5f365lfwunq3m2y5s9pgxtsncawpt9)
## Post #109
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T13:53:43+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

thanks a lot for the folder what format do you recommend  for me to convert them into does it changes anything ? I was thinking jpg
## Post #110
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2023-03-01T13:59:10+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from antr ↑Wed Mar 01, 2023 9:53 pm at Wed Mar 01, 2023 9:53 pm
>
> 
thanks a lot for the folder what format do you recommend  for me to convert them into does it changes anything ? I was thinking jpg

Tbh that depends on the game you're porting the track to...jpg is not the best format for quality and also it doesn't handle transparency well...
I'd suggest maybe .png or .tga but that depends on your game as well if it supports those formats.
## Post #111
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T14:11:38+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

I want to do something for beamng as it is really easy for a first project
## Post #112
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T14:38:18+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

I converted all file to png I will now try to apply the textures to the 3d model in blender, any tips to do that ?
## Post #113
- Username: taruncreation
- Rank: advanced
- Number of posts: 72
- Joined date: Fri Aug 26, 2016 6:17 pm
- Post datetime: 2023-03-01T14:41:39+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from antr ↑Wed Mar 01, 2023 10:38 pm at Wed Mar 01, 2023 10:38 pm
>
> 
I converted all file to png I will now try to apply the textures to the 3d model in blender, any tips to do that ?

Search YouTube , there are loads of tutorials. I don't think anyone here is going to write down a whole tutorial
## Post #114
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T14:47:40+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

thanks for the answer I am going to check right now
## Post #115
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T16:08:24+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

on which website could I find that tutorial can't find anything on youtube beside this [https://www.youtube.com/watch?v=hmsqVRcp-cs](https://www.youtube.com/watch?v=hmsqVRcp-cs) which isnt a tutorial but it prove me that this is possible
## Post #116
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-01T16:45:48+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

could it work with ninja ripper ?
## Post #117
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-03T01:29:04+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

I wasn't able to make it work yet, don't know If I will I can't find ANYTHING that could help with the problems I have
## Post #118
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-03-03T17:11:47+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

the textures are zstd compressed now
## Post #119
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-03-03T18:47:39+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

i noticed that some track meshes when exported have model glitches, their uv's are also wrong, the track i tested is barcelona and the screenshot is down below
[https://i.imgur.com/vLg8dcw.png](https://i.imgur.com/vLg8dcw.png)
## Post #120
- Username: antr
- Rank: n00b
- Number of posts: 16
- Joined date: Fri Jan 14, 2022 3:03 pm
- Post datetime: 2023-03-04T20:14:32+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

> Reply from fajNYgosciu1234 ↑Sat Mar 04, 2023 2:47 am at Sat Mar 04, 2023 2:47 am
>
> 
i noticed that some track meshes when exported have model glitches, their uv's are also wrong, the track i tested is barcelona and the screenshot is down below
https://i.imgur.com/vLg8dcw.png

Yeah I have sthe same issues with the alps, and also the texture I have are in a too tiny resolution so not usable
## Post #121
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-05-27T11:29:50+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

bugatti bolide (the base version with decals) has model and uv glitches, most notably on the carpaint, it also affects parts like the details
[https://i.imgur.com/YD7pWaY.png](https://i.imgur.com/YD7pWaY.png)
[https://i.imgur.com/cE4hIVU.png](https://i.imgur.com/cE4hIVU.png)
## Post #122
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-07-24T14:16:26+00:00
- Post Title: Re: A8Tool - Asphalt 8 FBX Converter for Android, iOS & Win32

i managed to convert the textures properly, but the uv mapping in the tracks and a few models are broken still, i would also try to wait for vertex color support that would have multiple layers but i think it's controlled by the game and not the models

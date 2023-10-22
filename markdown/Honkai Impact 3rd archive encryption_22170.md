## Post #1
- Username: toastyengineer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 01, 2017 12:10 am
- Post datetime: 2020-05-18T19:02:29+00:00
- Post Title: Honkai Impact 3rd archive encryption

Hey everyone,
So more or less recently, MiHoyo started to encrypt the unity 3d assets and textures for Honkai Imapct.
For some reason they have a ".wmv" extension. They come in 186 "blocks" about 50 mb each, and there is also a "BlockMeta.xmf" and "Blocks.xmf" file contained in the Asb folder (probably for indexing?).

Of course i already tried the basic programs like AssedStudio to try and extract these, but without success

I included 1 of the blocks and the 2 index files (probably?).
[https://mega.nz/file/P0ZnDY6b#TIFRgD9B- ... HDNA4ap280](https://mega.nz/file/P0ZnDY6b#TIFRgD9B-C6RmMWUKV2ao-a_FQf35EdLLHDNA4ap280)

I would really appreciate it if someone could have a look an check if there is a way to extract these 3d models or textures.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-19T05:26:44+00:00
- Post Title: Honkai Impact 3rd archive encryption

Can't help with the encryption but you can use this BMS script to unpack the unity3d assets from the wmf container.


 wmfUnpack.zip
(584 Bytes) Downloaded 303 times



Pick the "Blocks.xmf" file or anything as input as the script'll open it automatically. Just make sure the wmv files reside in the same path.
## Post #3
- Username: toastyengineer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 01, 2017 12:10 am
- Post datetime: 2020-05-19T18:36:02+00:00
- Post Title: Honkai Impact 3rd archive encryption

Hello

Thanks alot for your help!
Unfortounately i get an error when using the script, i attached the screenshot. I will see if i can solve it myself.



QfXpbMMSX5.png (31.07 KiB) Viewed 1242 times


I will edit if i manage to fix it.
## Post #4
- Username: toastyengineer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 01, 2017 12:10 am
- Post datetime: 2020-05-19T18:47:24+00:00
- Post Title: Honkai Impact 3rd archive encryption

Figured it out, it was probably just some reference error, i deleted the open "block.xmf" part and selected it manually and it worked
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-20T01:17:17+00:00
- Post Title: Honkai Impact 3rd archive encryption

> Reply from toastyengineer ↑Wed May 20, 2020 2:36 am at Wed May 20, 2020 2:36 am
>
> 
Unfortounately i get an error when using the script, i attached the screenshot.
I see. Was misplacing the parameters of "open" at final step but without testing. Sorry about that.  
Script updated at the same post.
## Post #6
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2020-05-24T22:25:35+00:00
- Post Title: Honkai Impact 3rd archive encryption

> Reply from toastyengineer ↑Wed May 20, 2020 2:47 am at Wed May 20, 2020 2:47 am
>
> 
Figured it out, it was probably just some reference error, i deleted the open "block.xmf" part and selected it manually and it worked

Anything on the decyption though?. I got no luck finding anything about that.
## Post #7
- Username: toastyengineer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 01, 2017 12:10 am
- Post datetime: 2020-05-27T14:05:10+00:00
- Post Title: Honkai Impact 3rd archive encryption

It seems to be a UnityFS archive. Tried to use different tools but, but it did not work. That's all i found out so far
## Post #8
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2020-06-10T11:49:01+00:00
- Post Title: Honkai Impact 3rd archive encryption

I have here a file example , perhaps some with more knowledge can help.
Link [https://mega.nz/file/RoNwnARD#6mDO_0138 ... vlMt3k3vdk](https://mega.nz/file/RoNwnARD#6mDO_0138ertP9viH8_pddvqsNnSEGIaxvlMt3k3vdk)
## Post #9
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2020-06-24T21:32:34+00:00
- Post Title: Honkai Impact 3rd archive encryption

If anyone can give a hand with the unity FSachive thing would be highly apreciated. Google seems to not be of use since it gives me only the wrong results of what i search .
## Post #10
- Username: BuIlDaLiBlE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 30, 2018 3:29 am
- Post datetime: 2020-06-25T09:14:00+00:00
- Post Title: Honkai Impact 3rd archive encryption

There was an anonymous reply that linked a certain chinese blog about this, but the reply was removed for unknown reason.
Since I'm not sure if it was directly related to the blog I'll post the link to it again: [https://blog.palug.cn/](https://blog.palug.cn/). I don't understand what's going on in his "analysis", but it's at least something.
## Post #11
- Username: toastyengineer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Jun 01, 2017 12:10 am
- Post datetime: 2020-07-21T07:28:46+00:00
- Post Title: Honkai Impact 3rd archive encryption

Thanks for the link to the Forum, it has quite a bit of information and decryption keys. 
If you go to the post about Honkai impact 3.8.0 you can find a download link to a Honkai Impact  3.5.0 Archive from the PC version.
I think he also said he will maybe upload 4.0.0 archive when 4.1.0 is released.
## Post #12
- Username: BuIlDaLiBlE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 30, 2018 3:29 am
- Post datetime: 2020-07-21T10:18:11+00:00
- Post Title: Honkai Impact 3rd archive encryption

Yes I know that, and he has already posted 4.0 a while ago. The problem stands tho: how to decrypt those files ourselves? I want to get some data from files that are not part of the game bundle but downloaded from the CDN, for example.
## Post #13
- Username: blueevangelion
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Dec 12, 2020 9:18 pm
- Post datetime: 2020-12-12T13:30:01+00:00
- Post Title: Honkai Impact 3rd archive encryption

4.0 (and any up to 4.3) still use a block.xmf file, they are decrypted into unity3d files, there should be a unity3d extractor for quickbms
## Post #14
- Username: BuIlDaLiBlE
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 30, 2018 3:29 am
- Post datetime: 2020-12-15T21:25:01+00:00
- Post Title: Honkai Impact 3rd archive encryption

Didn't want to start a new thread, but I have a different file from the same game that uses a different encryption (uploaded: [https://bpnet.work/files/RandomDialogData_en.bytes](https://bpnet.work/files/RandomDialogData_en.bytes)). I'm certain it contains game dialogue text data, but how it was encrypted is a total mystery (I even asked the author of the aforementioned blog, he has no idea either). If the file makes you ring any bell, please don't hesitate to share your ideas.
## Post #15
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2021-01-24T01:32:42+00:00
- Post Title: Honkai Impact 3rd archive encryption

The link from the Chinese blog actually works, it can decrypt both the Android and PC versions (up to date):



asuka.png (239.67 KiB) Viewed 781 times



That image above is the model of Asuka from the current collaboration of Honkai with Evangelion:



the blog actually has some info on how the decryption was found but I can't read code or Chinese for that matter  

Btw, the official Honkai website has an interactive 3D model of Asuka it seems:

[https://honkaiimpact3.mihoyo.com/global/en-us/fab](https://honkaiimpact3.mihoyo.com/global/en-us/fab)

I wonder if it can be grabbed and converted
## Post #16
- Username: quang23021998
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jun 22, 2020 4:53 am
- Post datetime: 2021-01-31T17:13:08+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from GDL ↑Sun Jan 24, 2021 9:32 am at Sun Jan 24, 2021 9:32 am
>
> 
The link from the Chinese blog actually works, it can decrypt both the Android and PC versions (up to date):

asuka.png


That image above is the model of Asuka from the current collaboration of Honkai with Evangelion:



the blog actually has some info on how the decryption was found but I can't read code or Chinese for that matter  

Btw, the official Honkai website has an interactive 3D model of Asuka it seems:

https://honkaiimpact3.mihoyo.com/global/en-us/fab

I wonder if it can be grabbed and converted

Can you share the decryption tool from this [https://blog.palug.cn/](https://blog.palug.cn/) Chinese blog? Seem like it was deleted, I couldn't access the site. Would really appreciate it if you can post it here!

Edit: I manage to access the blog and get the decryption tool now.
## Post #17
- Username: X3D
- Rank: advanced
- Number of posts: 50
- Joined date: Thu Jan 21, 2016 5:44 am
- Post datetime: 2021-01-31T18:34:55+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

Hi quang23021998, if you require some of the models there are 28 in XPS format to download here:

[Scroll down about halfway]

[https://www.deviantart.com/l1x3r/gallery](https://www.deviantart.com/l1x3r/gallery)
## Post #18
- Username: korea0799
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jun 22, 2016 3:44 pm
- Post datetime: 2021-02-04T06:02:59+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

You can find some mmd format models in [www.aplaybox.com](http://www.aplaybox.com)
## Post #19
- Username: tim7666
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 13, 2018 4:01 am
- Post datetime: 2021-02-09T16:10:29+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

Does anyone succes in the decryption of these files now ? it would be wonderful to have an something understandable or a tutorial on how to do that.
## Post #20
- Username: delialala
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 04, 2021 8:29 pm
- Post datetime: 2021-03-04T12:58:43+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

alright, after messing around with it for a couple of hours I finally figured it out. this is what worked for me in 4.6, it may not work in later versions if kekhoyo decides to up their decryption game again
what you'll need:
- the decryption tool from here: [https://www.mediafire.com/file/8oz3xlik ... 0.exe/file](https://www.mediafire.com/file/8oz3xlikez93e2q/HonKai3BundleDecryptor.1.3.0.exe/file)
- assetstudio: [https://github.com/Perfare/AssetStudio](https://github.com/Perfare/AssetStudio)

1. run the decryption tool then type 1 and enter
2. right click on the honkai launcher then open file location. then go Games -> BH3_Data -> StreamingAssets -> Asb -> pc. you should see a bunch of .wmv files
3. drag and drop the Blocks.xmf file from the pc folder inside the window of the decrypter. you should see that the file path has been written. then press enter
note: at this point, if the program crashes that means you need administrator permission to modify the folder where you have the wmv files. either just move the files or remove the administrator permission on that folder
4. at this point the program should show you all the files you can decrypt. you can choose which one to decrypt or just type in 0 to decrypt all of them. this is going to take a while. after it finishes, the "Decrypted" folder should now appear in the one where you have the .wmv files
6. extract the assetStudio zip file and run AssetStudioGUI
7. go to file -> load folder and choose one of the folders from the "Decrypted" one
8. after it finishes loading, go to asset list and grab whatever you want by selecting them then export -> selected assets. 

note: some folders crash assetStudio. I've no idea why that happens, just force close the program and move on to the next folder
I also tried to rip the models by selecting stuff in scene hierarchy then exporting them through the model tab, but the fxd files always turn out empty lol. if anyone has any ideas how to do that then pls share
## Post #21
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2021-03-05T00:33:32+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

same problem as magikami , they use a specific way to build their model in-game thus we cant export from scene hierarchy nor Animator export , which is bad
## Post #22
- Username: YeetCraig
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Mar 09, 2021 3:01 pm
- Post datetime: 2021-03-09T07:08:46+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

Would it be possible to reencrypt the files, to modify skins/asset models in game?
## Post #23
- Username: delialala
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 04, 2021 8:29 pm
- Post datetime: 2021-03-09T07:59:59+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from YeetCraig ↑Tue Mar 09, 2021 3:08 pm at Tue Mar 09, 2021 3:08 pm
>
> 
Would it be possible to reencrypt the files, to modify skins/asset models in game?

I'm pretty sure the game checks at the launch the integrity of the files, but I might be wrong. theoretically, super super theoretically, ig it could be possible to delete the scripts relating to connecting with mihoyo servers and have the game run on your computer only.
the other problem is all the data that is server side, you'd have to figure out how to tell the game to store it on your pc instead. and that is if we figure out how to extract all the models from the game and plug all the assets into unity ourselves
it's a lot of work and personally I'm a complete newbie when it comes to unity and c# coding so someone else might have a better idea of what we can or can't do
## Post #24
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-25T21:51:41+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption


## Post #25
- Username: delialala
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 04, 2021 8:29 pm
- Post datetime: 2021-03-26T17:49:15+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from Durik256 ↑Fri Mar 26, 2021 5:51 am at Fri Mar 26, 2021 5:51 am
>
> 
delialala wrote: ↑Thu Mar 04, 2021 8:58 pm
the decryption tool from this guy's blog 

could you post the tool? (there is no link on the site anymore)

edited the post, I hope it works now
## Post #26
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-26T19:02:49+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption


## Post #27
- Username: RustyNova
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 22, 2021 9:06 pm
- Post datetime: 2021-04-22T13:09:54+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

But now in 4.7, the decryptor broke and we can't extract it anymore. The author doesn't seem to get interested in fixing it either. So... Does anyone got a plan B?
## Post #28
- Username: VadimKarpov
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 02, 2021 8:09 pm
- Post datetime: 2021-05-02T15:19:31+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from delialala ↑Sat Mar 27, 2021 1:49 am at Sat Mar 27, 2021 1:49 am
>
> 
Durik256 wrote: ↑Fri Mar 26, 2021 5:51 am
delialala wrote: ↑Thu Mar 04, 2021 8:58 pm
the decryption tool from this guy's blog 

could you post the tool? (there is no link on the site anymore)


edited the post, I hope it works now
Hey, can you update it for 4.7?
## Post #29
- Username: Monarch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2021 3:50 am
- Post datetime: 2021-05-25T19:52:22+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from delialala ↑Thu Mar 04, 2021 8:58 pm at Thu Mar 04, 2021 8:58 pm
>
> 
alright, after messing around with it for a couple of hours I finally figured it out. this is what worked for me in 4.6, it may not work in later versions if kekhoyo decides to up their decryption game again
what you'll need:
- the decryption tool from here: https://www.mediafire.com/file/8oz3xlik ... 0.exe/file
- assetstudio: https://github.com/Perfare/AssetStudio

1. run the decryption tool then type 1 and enter
2. right click on the honkai launcher then open file location. then go Games -> BH3_Data -> StreamingAssets -> Asb -> pc. you should see a bunch of .wmv files
3. drag and drop the Blocks.xmf file from the pc folder inside the window of the decrypter. you should see that the file path has been written. then press enter
note: at this point, if the program crashes that means you need administrator permission to modify the folder where you have the wmv files. either just move the files or remove the administrator permission on that folder
4. at this point the program should show you all the files you can decrypt. you can choose which one to decrypt or just type in 0 to decrypt all of them. this is going to take a while. after it finishes, the "Decrypted" folder should now appear in the one where you have the .wmv files
6. extract the assetStudio zip file and run AssetStudioGUI
7. go to file -> load folder and choose one of the folders from the "Decrypted" one
8. after it finishes loading, go to asset list and grab whatever you want by selecting them then export -> selected assets. 

note: some folders crash assetStudio. I've no idea why that happens, just force close the program and move on to the next folder
I also tried to rip the models by selecting stuff in scene hierarchy then exporting them through the model tab, but the fxd files always turn out empty lol. if anyone has any ideas how to do that then pls share

Any update on this for 4.7? Or at least the extracted models before the new encryption?
## Post #30
- Username: Monarch
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed May 26, 2021 3:50 am
- Post datetime: 2021-05-27T14:35:43+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from Monarch ↑Wed May 26, 2021 3:52 am at Wed May 26, 2021 3:52 am
>
> Any update on this for 4.7? Or at least the extracted models before the new encryption?

Correction 4.8 PC client
## Post #31
- Username: SixtyONE
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon May 31, 2021 5:18 pm
- Post datetime: 2021-05-31T10:25:35+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

I really hope that this tools can update to ver.4.8,
or offer a source file of the decryption tool for everybody
## Post #32
- Username: Flash21
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jul 09, 2021 10:49 pm
- Post datetime: 2021-07-11T11:27:21+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from GDL ↑Sun Jan 24, 2021 9:32 am at Sun Jan 24, 2021 9:32 am
>
> 
The link from the Chinese blog actually works, it can decrypt both the Android and PC versions (up to date):

asuka.png


That image above is the model of Asuka from the current collaboration of Honkai with Evangelion:



the blog actually has some info on how the decryption was found but I can't read code or Chinese for that matter  

Btw, the official Honkai website has an interactive 3D model of Asuka it seems:

https://honkaiimpact3.mihoyo.com/global/en-us/fab

I wonder if it can be grabbed and converted

did you get the Asuka model? can you send me please?
## Post #33
- Username: pgw00k
- Rank: beginner
- Number of posts: 25
- Joined date: Fri Nov 28, 2014 7:42 am
- Post datetime: 2021-10-14T07:58:07+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

Is anyone work for this on v5.2?
## Post #34
- Username: TokiChan
- Rank: mega-veteran
- Number of posts: 223
- Joined date: Thu May 19, 2016 2:38 am
- Post datetime: 2022-02-20T16:52:41+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

I see that decryptor work with PC game. How about Android vesion 5.4?
## Post #35
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2022-04-16T12:29:21+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from TokiChan ↑Mon Feb 21, 2022 12:52 am at Mon Feb 21, 2022 12:52 am
>
> 
I see that decryptor work with PC game. How about Android vesion 5.4?
Does it work with latest pc game ? It should not work from somewhere like V4.8.
## Post #36
- Username: linsaberlove
- Rank: n00b
- Number of posts: 17
- Joined date: Fri May 22, 2020 10:33 pm
- Post datetime: 2022-04-16T12:31:36+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

Does anyone have full game file between V3.5 and V4.1 ? Newer versions won't export animation clip.
## Post #37
- Username: NeferneferOttom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 07, 2022 11:42 am
- Post datetime: 2022-04-17T15:00:05+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

There isn't any way since 4.8，fk mihoyo，Now only available for download on “[www.aplaybox.com](http://www.aplaybox.com)”，search 神帝宇，or ninjaripper
## Post #38
- Username: soynim
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 08, 2022 10:28 pm
- Post datetime: 2022-05-08T14:41:57+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from linsaberlove ↑Sat Apr 16, 2022 8:31 pm at Sat Apr 16, 2022 8:31 pm
>
> 
Does anyone have full game file between V3.5 and V4.1 ? Newer versions won't export animation clip.

I have some V3.7 files, Can u tell me how to export animation data...
I can share these results with U
## Post #39
- Username: takemi nakura
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Jul 17, 2021 10:47 am
- Post datetime: 2022-07-07T22:09:44+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from delialala ↑Thu Mar 04, 2021 8:58 pm at Thu Mar 04, 2021 8:58 pm
>
> 
alright, after messing around with it for a couple of hours I finally figured it out. this is what worked for me in 4.6, it may not work in later versions if kekhoyo decides to up their decryption game again
what you'll need:
- the decryption tool from here: https://www.mediafire.com/file/8oz3xlik ... 0.exe/file
- assetstudio: https://github.com/Perfare/AssetStudio

1. run the decryption tool then type 1 and enter
2. right click on the honkai launcher then open file location. then go Games -> BH3_Data -> StreamingAssets -> Asb -> pc. you should see a bunch of .wmv files
3. drag and drop the Blocks.xmf file from the pc folder inside the window of the decrypter. you should see that the file path has been written. then press enter
note: at this point, if the program crashes that means you need administrator permission to modify the folder where you have the wmv files. either just move the files or remove the administrator permission on that folder
4. at this point the program should show you all the files you can decrypt. you can choose which one to decrypt or just type in 0 to decrypt all of them. this is going to take a while. after it finishes, the "Decrypted" folder should now appear in the one where you have the .wmv files
6. extract the assetStudio zip file and run AssetStudioGUI
7. go to file -> load folder and choose one of the folders from the "Decrypted" one
8. after it finishes loading, go to asset list and grab whatever you want by selecting them then export -> selected assets. 

note: some folders crash assetStudio. I've no idea why that happens, just force close the program and move on to the next folder
I also tried to rip the models by selecting stuff in scene hierarchy then exporting them through the model tab, but the fxd files always turn out empty lol. if anyone has any ideas how to do that then pls share
is there any source code on this decrypt tool? doesnt work for 5.8
## Post #40
- Username: NeferneferOttom
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Jan 07, 2022 11:42 am
- Post datetime: 2022-09-29T13:52:24+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

Github search "Razmoth",His tools work in 6.0 JP PC
## Post #41
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-09-29T15:58:30+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

> Reply from NeferneferOttom ↑Thu Sep 29, 2022 9:52 pm at Thu Sep 29, 2022 9:52 pm
>
> 
Github search "Razmoth",His tools work in 6.0 JP PC

his tool was DMCAd,thankfully he has a Discord channel
## Post #42
- Username: Persivan
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Feb 26, 2023 7:17 am
- Post datetime: 2023-02-26T01:12:38+00:00
- Post Title: Re: Honkai Impact 3rd archive encryption

worked for 6.4
[https://github.com/TomyJan/HoYoStudio](https://github.com/TomyJan/HoYoStudio)

Another question is. How can i save my changes? (I want to change dialogues)

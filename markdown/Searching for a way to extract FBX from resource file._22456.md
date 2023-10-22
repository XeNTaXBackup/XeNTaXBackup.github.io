## Post #1
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2020-07-27T19:44:15+00:00
- Post Title: Searching for a way to extract FBX from resource file.

Game uses custom engine and is still in closed beta. Since it's not even released yet, there is no tools that would natively recognize their resource pack file format. But!

it looks kinda simple (though still above my level) - at the start of pack file there is always a list of files with relative paths and after this something that looks like all textures, models, scripts etc are copy-pasted inside that file.
 i can read scripts as I would in plain-text format and I can see standard FBX headers. Tried copypasting stuff from one "Kaydara FBX Binary" until next one into another file and changing extension to FBX, but it doesn't work. I see two possible reasons - asset files inside pack don't have end of file thingies and another one is that there might be animation for this model or any other file's content after model info.

Wasn't able to use NinjaRipper and RenderDoc. Game is started through launcher and uses anticheat which, I guess, prevents them from capturing.
Not experienced enough to use Advanced Mesh Reaper. Have no idea how to get info about models polycount, indices and other required values before ripping it.
Was able to extract textures with Dragon Unpacker, but alas it doesn't work with FBX. Is there any other tool like it that can recognize FBX file and extract it? Or maybe there is a way to teach Dragon Unpacker new FBX trick?

 I'm not trying to make a hack/cheat so not interested in packing it back. Just want to extract player meshes to see how it's done.
Thanks in advance.

[https://www.dropbox.com/s/qarvex1yqxoxs ... e.zip?dl=0](https://www.dropbox.com/s/qarvex1yqxoxsx4/sample.zip?dl=0)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-28T13:23:58+00:00
- Post Title: Searching for a way to extract FBX from resource file.

> Reply from dimwalker ↑Tue Jul 28, 2020 3:44 am at Tue Jul 28, 2020 3:44 am
>
> Have no idea how to get info about models polycount, indices and other required values before ripping it.
Uploading some sample files is alway a good start for such requests, coz not everyone has the time or desire to remind you of that.
## Post #3
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2020-07-28T14:20:26+00:00
- Post Title: Searching for a way to extract FBX from resource file.

> Reply from Bigchillghost ↑Tue Jul 28, 2020 9:23 pm at Tue Jul 28, 2020 9:23 pm
>
> 
Uploading some sample files is alway a good start for such requests, coz not everyone has the time or desire to remind you of that.

I was afraid of breaking forum rules.
Is it allowed to post a link to a file uploaded to other site?
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-28T14:39:53+00:00
- Post Title: Searching for a way to extract FBX from resource file.

> Reply from dimwalker ↑Tue Jul 28, 2020 10:20 pm at Tue Jul 28, 2020 10:20 pm
>
> 
Is it allowed to post a link to a file uploaded to other site?
Refer to the numerous other similar posts.
## Post #5
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2020-07-28T15:10:15+00:00
- Post Title: Searching for a way to extract FBX from resource file.

> Reply from Bigchillghost ↑Tue Jul 28, 2020 10:39 pm at Tue Jul 28, 2020 10:39 pm
>
> 
Refer to the numerous other similar posts.
[Done.](https://www.dropbox.com/s/qarvex1yqxoxsx4/sample.zip?dl=0) Also updated original post.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-29T12:19:01+00:00
- Post Title: Searching for a way to extract FBX from resource file.

Simple enough. Use this BMS script.


 dbpUnpacker.zip
(396 Bytes) Downloaded 23 times
## Post #7
- Username: dimwalker
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Mar 18, 2009 6:06 am
- Post datetime: 2020-07-29T12:39:39+00:00
- Post Title: Searching for a way to extract FBX from resource file.

> Reply from Bigchillghost ↑Wed Jul 29, 2020 8:19 pm at Wed Jul 29, 2020 8:19 pm
>
> 
Simple enough. Use this BMS script.

Much appreciated!

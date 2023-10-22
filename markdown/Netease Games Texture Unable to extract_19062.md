## Post #1
- Username: 237616546
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Oct 24, 2018 7:19 pm
- Post datetime: 2018-11-12T01:43:00+00:00
- Post Title: Netease Games Texture Unable to extract

[http://stzb.163.com/](http://stzb.163.com/)
I can extract the model, but I can't extract the texture.
Later I saw this script.

```

get SIZE asize
get NAME basename
string NAME + .ktx
math SIZE - 0x80
filexor "\x7A\x7B\x7C\x7D\x7E\x7F\x80\x81\x82\x83\x84\x85\x86\x87\x88\x89\x8A\x8B\x8C\x8D\x8E\x8F\x90\x91\x92\x93\x94\x95\x96\x97\x98\x99\x9A\x9B\x9C\x9D\x9E\x9F\xA0\xA1\xA2\xA3\xA4\xA5\xA6\xA7\xA8\xA9\xAA\xAB\xAC\xAD\xAE\xAF\xB0\xB1\xB2\xB3\xB4\xB5\xB6\xB7\xB8\xB9\xBA\xBB\xBC\xBD\xBE\xBF\xC0\xC1\xC2\xC3\xC4\xC5\xC6\xC7\xC8\xC9\xCA\xCB\xCC\xCD\xCE\xCF\xD0\xD1\xD2\xD3\xD4\xD5\xD6\xD7\xD8\xD9\xDA\xDB\xDC\xDD\xDE\xDF\xE0\xE1\xE2\xE3\xE4\xE5\xE6\xE7\xE8\xE9\xEA\xEB\xEC\xED\xEE\xEF\xF0\xF1\xF2\xF3\xF4\xF5\xF6\xF7\xF8\xF9"
log NAME 0x0 0x80
append
filexor ""
log NAME 0x80 SIZE
```


Thank you,  @Acewell

However, I can not open this texture.
## Post #2
- Username: lxxxk
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Jul 02, 2014 1:33 pm
- Post datetime: 2018-11-13T02:00:47+00:00
- Post Title: Netease Games Texture Unable to extract

please help me [https://n.163.com/](https://n.163.com/) Netease Games DAT model to fbx or obj

Scripthttps://zenhax.com/viewtopic.php?f=9&t=7235&hilit=against+cold

DAT
[test.rar](https://xentaxbackup.github.io/file/15168_test.rar)
## Post #3
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-13T18:30:00+00:00
- Post Title: Netease Games Texture Unable to extract

@237616546 That script is for decrypting Rebellious Million Arthur files. Other Netease games are usually not encrypted like that. If you find a file with the "KTX" header, try opening it directly with Mali Texture Compression Tool or PVRTexTool.

@lxxxk I have seen your comment in my thread. This is a different format than what is supported by my tool. Probably a different engine by Netease.
## Post #4
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-14T10:11:21+00:00
- Post Title: Netease Games Texture Unable to extract

Thank you. I try to use these two tools to open and read KTX files, but I can't read them. I don't know whether the extracted format is wrong or the read tool is wrong. Can you download the game and try to extract the texture and extract the correct PNG?
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-14T10:29:19+00:00
- Post Title: Netease Games Texture Unable to extract

I don't want to download the whole game. I can take a look if you post 1 - 2 KTX samples.
## Post #6
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-14T10:48:46+00:00
- Post Title: Netease Games Texture Unable to extract

This is the sample extracted from the game. There are models and textures. Thank you.

[https://www49.zippyshare.com/v/xKzfyZND/file.html](https://www49.zippyshare.com/v/xKzfyZND/file.html)

or

[https://www113.zippyshare.com/v/MjRJwqWy/file.html](https://www113.zippyshare.com/v/MjRJwqWy/file.html)
## Post #7
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-14T10:55:21+00:00
- Post Title: Netease Games Texture Unable to extract

I also want to extract another game, but I don't know what engine it is.
This is the official website of its game: [http://www.dawnoftitans.com/](http://www.dawnoftitans.com/)
You can download the sample at this website link: [https://www.zenhax.com/viewtopic.php?F= ... 813#p39813](https://www.zenhax.com/viewtopic.php?F=5&t=8786&p=39813#p39813)

or

[https://www113.zippyshare.com/v/CaxFkksE/file.html](https://www113.zippyshare.com/v/CaxFkksE/file.html)


I uploaded some samples.
Thank you very much!
## Post #8
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-14T11:01:31+00:00
- Post Title: Netease Games Texture Unable to extract

> Reply from lxxxk
>
> please help me https://n.163.com/ Netease Games DAT model to fbx or obj

Scripthttps://zenhax.com/viewtopic.php?f=9&t=7235&hilit=against+cold

DAT

Sorry, neither do I.
## Post #9
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-14T11:29:47+00:00
- Post Title: Netease Games Texture Unable to extract

> Reply from xtiger
>
> This is the sample extracted from the game. There are models and textures. Thank you.

https://www49.zippyshare.com/v/xKzfyZND/file.html
Textures use ASTC compression. They can be opened with PVRTexTool using "astcenc.exe".



> Reply from xtiger
>
> 
You can download the sample at this website link: https://www.zenhax.com/viewtopic.php?F= ... 813#p39813
Interesting game. I will take a look when I have the time. Those bof files are compressed with zstd. Judging from your last sample you will get an ATC compressed DDS texture when you decompress the bof files. They can be loaded with existing tools. I am more interested in the models.
## Post #10
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-14T12:48:15+00:00
- Post Title: Netease Games Texture Unable to extract

Thank you. I prefer its model. Do you have any idea?
## Post #11
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-14T13:00:34+00:00
- Post Title: Netease Games Texture Unable to extract

> Reply from xtiger
>
> Thank you. I prefer its model. Do you have any idea?
The model format doesn't look too complicated. I will make a tool for loading the models.
## Post #12
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-15T02:10:05+00:00
- Post Title: Netease Games Texture Unable to extract

Sorry, I download PVRTexTool, but I can't find this "astcenc.exe". Can you download the address for me?
## Post #13
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-15T07:12:18+00:00
- Post Title: Netease Games Texture Unable to extract

> Reply from akderebur
>
> xtiger wrote:This is the sample extracted from the game. There are models and textures. Thank you.

https://www49.zippyshare.com/v/xKzfyZND/file.html

Textures use ASTC compression. They can be opened with PVRTexTool using "astcenc.exe".


xtiger wrote:
You can download the sample at this website link: https://www.zenhax.com/viewtopic.php?F= ... 813#p39813

Interesting game. I will take a look when I have the time. Those bof files are compressed with zstd. Judging from your last sample you will get an ATC compressed DDS texture when you decompress the bof files. They can be loaded with existing tools. I am more interested in the models.
Can you send all the extracted texture to SkyDrive? Or tell me the way, please!
## Post #14
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-15T07:15:28+00:00
- Post Title: Netease Games Texture Unable to extract

> Reply from akderebur
>
> xtiger wrote:This is the sample extracted from the game. There are models and textures. Thank you.

https://www49.zippyshare.com/v/xKzfyZND/file.html

Textures use ASTC compression. They can be opened with PVRTexTool using "astcenc.exe".


xtiger wrote:
You can download the sample at this website link: https://www.zenhax.com/viewtopic.php?F= ... 813#p39813

Interesting game. I will take a look when I have the time. Those bof files are compressed with zstd. Judging from your last sample you will get an ATC compressed DDS texture when you decompress the bof files. They can be loaded with existing tools. I am more interested in the models.

I used "astcenc.exe" of Mali Texture Compression Tool v4.3.0, but I could not extract it.
## Post #15
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-16T01:42:25+00:00
- Post Title: Netease Games Texture Unable to extract

> Reply from xtiger
>
> 
I used "astcenc.exe" of Mali Texture Compression Tool v4.3.0, but I could not extract it.
Make sure you add "astcenc.exe" to the environment variable PATH. Then just load the KTX file with PVRTexTool.

Btw I am done with the models. I will release the tool tomorrow.
## Post #16
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-16T05:13:29+00:00
- Post Title: Re: Netease Games Texture Unable to extract

> Reply from akderebur
>
> xtiger wrote:
I used "astcenc.exe" of Mali Texture Compression Tool v4.3.0, but I could not extract it.
Make sure you add "astcenc.exe" to the environment variable PATH. Then just load the KTX file with PVRTexTool.

Btw I am done with the models. I will release the tool tomorrow.
I think there is something wrong with the KTX file I extracted from the initial code, and I can't read the texture. Can you give me the extracted files or tools? Thank you

You are a genius!
[20181116130846.png](https://xentaxbackup.github.io/file/15182_20181116130846.png)
## Post #17
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-16T10:57:03+00:00
- Post Title: Re: Netease Games Texture Unable to extract

Upload the KTX file that you are having this problem with.
## Post #18
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-16T11:54:04+00:00
- Post Title: Re: Netease Games Texture Unable to extract

> Reply from akderebur
>
> Upload the KTX file that you are having this problem with.

NPK
[https://www49.zippyshare.com/v/xKzfyZND/file.html](https://www49.zippyshare.com/v/xKzfyZND/file.html)

or
KTX
[https://www113.zippyshare.com/v/MjRJwqWy/file.html](https://www113.zippyshare.com/v/MjRJwqWy/file.html)

I feel this KTX file is wrong.

Thank you.
## Post #19
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-16T12:20:18+00:00
- Post Title: Re: Netease Games Texture Unable to extract

> Reply from xtiger
>
> 
I feel this KTX file is wrong.
Yes, it is not a ktx file.

Model tool : [viewtopic.php?f=16&t=19078](http://forum.xentax.com/viewtopic.php?f=16&t=19078)
## Post #20
- Username: xtiger
- Rank: advanced
- Number of posts: 49
- Joined date: Tue Nov 13, 2018 1:56 pm
- Post datetime: 2018-11-17T02:19:49+00:00
- Post Title: Re: Netease Games Texture Unable to extract

> Reply from akderebur
>
> xtiger wrote:
I feel this KTX file is wrong.

Yes, it is not a ktx file.

Model tool : viewtopic.php?f=16&t=19078
How do I export these textures from the NPK file? Thank you.
## Post #21
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-11-17T14:50:37+00:00
- Post Title: Re: Netease Games Texture Unable to extract

> Reply from xtiger
>
> 
How do I export these textures from the NPK file? Thank you.
Use the "nxpk.bms" quickbms script on the npk file and it will extract all the files. It is up to you to find which files are textures.
## Post #22
- Username: usabdt
- Rank: advanced
- Number of posts: 47
- Joined date: Fri Sep 21, 2018 4:28 am
- Post datetime: 2018-12-26T09:12:54+00:00
- Post Title: Re: Netease Games Texture Unable to extract

> Reply from lxxxk
>
> please help me https://n.163.com/ Netease Games DAT model to fbx or obj

Scripthttps://zenhax.com/viewtopic.php?f=9&t=7235&hilit=against+cold

DAT

Did you extract the model? I also need this game model. If you can, show me

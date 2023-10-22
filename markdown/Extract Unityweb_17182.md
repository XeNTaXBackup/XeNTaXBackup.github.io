## Post #1
- Username: Rua
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 13, 2017 5:49 pm
- Post datetime: 2017-10-23T23:34:26+00:00
- Post Title: Extract Unityweb

Hello,
I find this model from this pre-releasing DMM game.
[http://www.dmm.co.jp/netgame/social/-/g ... id=463002/](http://www.dmm.co.jp/netgame/social/-/gadgets/=/app_id=463002/)
GO down and click the green button once you log in:

Through inspect element, I was able to find a .unityweb file that somewhat have a reasonable size of 29.15 mb.
How would I obtain the model including the texture and the armature?
Here is the .unityweb file I got:
[http://www58.zippyshare.com/v/U6kPZCn5/file.html](http://www58.zippyshare.com/v/U6kPZCn5/file.html)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-10-24T10:07:07+00:00
- Post Title: Extract Unityweb

its possible to get an obj out of it.
## Post #3
- Username: Rua
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 13, 2017 5:49 pm
- Post datetime: 2017-10-24T12:19:08+00:00
- Post Title: Extract Unityweb

> Reply from chrrox
>
> its possible to get an obj out of it.
What is the process you done to extract that?
Did you have to capture something else from the game or is it just the .unityweb file I uploaded here?
## Post #4
- Username: Rua
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-10-24T20:41:39+00:00
- Post Title: Extract Unityweb

Use offzip on the unity web file
offzip.exe -a -z -15 c:\file.unityweb c:\extract 0x0
you might also be able to just rename it to .gz and extract it with 7zip
then you need to extract the unity file from the unityweb file.
then uncompress the unity3d file with unity asset bundle extractor
then use that tool to export the textures and mesh.
I had to manually convert textures and use noesis to open the obj file.
## Post #5
- Username: Rua
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 13, 2017 5:49 pm
- Post datetime: 2017-10-24T21:41:24+00:00
- Post Title: Extract Unityweb

> Reply from chrrox
>
> Use offzip on the unity web file
offzip.exe -a -z -15 c:\file.unityweb c:\extract 0x0
you might also be able to just rename it to .gz and extract it with 7zip
then you need to extract the unity file from the unityweb file.
then uncompress the unity3d file with unity asset bundle extractor
then use that tool to export the textures and mesh.
I had to manually convert textures and use noesis to open the obj file.
Thanks for the instruction. Quite a chunky file. Still running the script to extract it.
## Post #6
- Username: Rua
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 13, 2017 5:49 pm
- Post datetime: 2017-10-24T21:50:06+00:00
- Post Title: Extract Unityweb

> Reply from chrrox
>
> Use offzip on the unity web file
offzip.exe -a -z -15 c:\file.unityweb c:\extract 0x0
you might also be able to just rename it to .gz and extract it with 7zip
then you need to extract the unity file from the unityweb file.
then uncompress the unity3d file with unity asset bundle extractor
then use that tool to export the textures and mesh.
I had to manually convert textures and use noesis to open the obj file.

After renaming it and extracting it, I got a file of the same name "build_171020_prod_12.data.unityweb".
It is 37.8 MB
I ran offzip with the file I extracted after renaming it and got the following messages at the end.
- 2119 valid compressed streams found
- 0x008f0b01 -> 0x0092fa29 bytes covering the 23% of the file
I was not able to find the unity3d file.
I used the offzip from here: [http://aluigi.altervista.org/mytoolz/offzip.zip](http://aluigi.altervista.org/mytoolz/offzip.zip)
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-24T22:57:50+00:00
- Post Title: Extract Unityweb

the original sample is just gzip compressed and you can just right click on it and Extract to with 7-zip, 
it doesn't care about extensions since it identifies from file headers.
the next step you should be on and questioning is this one  

> then you need to extract the unity file from the unityweb file.
## Post #8
- Username: Rua
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 13, 2017 5:49 pm
- Post datetime: 2017-10-25T00:12:25+00:00
- Post Title: Extract Unityweb

> Reply from AceWell
>
> the original sample is just gzip compressed and you can just right click on it and Extract to with 7-zip, 
it doesn't care about extensions since it identifies from file headers.
the next step you should be on and questioning is this one  
then you need to extract the unity file from the unityweb file.
Yeah, I figured offset is just decompressing the zip file. It is the same as me renaming it to .gz.
I am not sure how to extract the unity file from this decompressed unityweb file.
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-26T07:23:10+00:00
- Post Title: Extract Unityweb

okay to extract the unity3d file use this bms script on the extracted sample, only works with the one in this thread

```

idstring "UnityWeb"
goto 0xb6
get OFFSET long
get SIZE long
get NAME_SZ long
getdstring NAME NAME_SZ
log NAME OFFSET SIZE

```

after you run the bms script on the extracted sample you will have a data.unity3d file,
open it in UnityAssetsBundleExtractor and let it unpack then select sharedassets1.assets,
that is where that character model is by the name Chr_01_Model
then select the last type package when prompted from the list,
then find and select the model and export it via "Plugins" > "Export to .obj".

trying to export the textures crash, i will get back to that later maybe.
## Post #10
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-10-26T09:07:40+00:00
- Post Title: Extract Unityweb

Just use [https://codeload.github.com/Perfare/Uni ... zip/v0.8.0](https://codeload.github.com/Perfare/UnityStudio/zip/v0.8.0)
The textures were just dds files with a slightly altered header.
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-10-27T01:51:14+00:00
- Post Title: Extract Unityweb

ooh we're up to 8.0 now!   
link to releases
[https://github.com/Perfare/UnityStudio/releases](https://github.com/Perfare/UnityStudio/releases)

yeah you can open the data.unity3d file with Unity Studio and extract the contents
File > Extract Bundle...
then open up the sharedassets1.assets file
File > Load file...
and select the textures and export
## Post #12
- Username: binlv
- Rank: advanced
- Number of posts: 65
- Joined date: Wed Apr 12, 2017 8:36 am
- Post datetime: 2017-12-09T06:36:12+00:00
- Post Title: Extract Unityweb

I changed the .gz file and extract the build_171020_prod_12.data.unityweb file. And how to extract .unity3d file?
## Post #13
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-12-12T12:29:06+00:00
- Post Title: Extract Unityweb

> Reply from binlv
>
> I changed the .gz file and extract the build_171020_prod_12.data.unityweb file. And how to extract .unity3d file?

with unityStudio you open it with 
than export

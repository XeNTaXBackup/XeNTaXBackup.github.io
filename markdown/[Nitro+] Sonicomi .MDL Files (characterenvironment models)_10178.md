## Post #1
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2013-02-27T02:03:30+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

I've managed to open the Sonicomi game assets and extract the game data. I have also got the header of the .MDL files that are inside the 3d.npa file. They are not in Source, Half-Life or Quake format as far as I'm aware of (judging from the extension I thought they were). Here's the dump:

```
42494E5652534E7B0D0A2020202020202020310D0A7D0D0A4D455348686561645F6D6F757468007B565254587BDC0E00 | BINVRSN{..        1..}..MESHhead_mouth.{VRTX{...

```


To me, it looks like a binary mesh file. Looking at the files, towards the end of the file there is a lot of extra data with words like "FRME" "TRNS" and others.  The middle "beef" is vertex data, I believe.
I can upload these files if you like.

Does anyone have experience with any of the Nitro+ games? Is there a converter or reader plugin I need to use?

Cheers,
Cubeburner.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-27T03:43:18+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

What did you use to unpack it? asmodean's exnpa?
## Post #3
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2013-02-27T04:13:10+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

> Reply from finale00
>
> What did you use to unpack it? asmodean's exnpa?
I used the tool called "nipa". The .npa files were encrypted but I ran the EXE like so:

```

```


And it went to work decrypting the archives.

Originally from some Visual Novel forum. Here's a link: [http://forums.novelnews.net/showthread.php?t=35621](http://forums.novelnews.net/showthread.php?t=35621) .

Like I said, I can upload the .mdl files for you to examine.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-27T22:20:19+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

Uploads would be nice I don't know where I put the game.
## Post #5
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2013-02-27T22:25:26+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

[Uploaded here on my server.](http://dandere.net/czneedsabeer/boobies.7z)

Cheers!
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-02-28T00:15:37+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

Oh right this format. I never liked it cause they have text data mixed in with binary data.
## Post #7
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-03-02T09:23:30+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

> Reply from Cubeburner
>
> Uploaded here on my server.
Cheers!

It is a nice 3d format.

You can download the converted files in Wavefront .obj/mtl format using this link:
[http://3dconverter.webege.com/converted](http://3dconverter.webege.com/converted)

I must down my PC now, but I will release my developer version of 3D Object Converter as soon as possible.
## Post #8
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-03-03T20:26:36+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

> Reply from Cubeburner
>
> And it went to work decrypting the archives.

Can you tell me how did you decode the .mdl and the .png files ?
(I downloaded the SoniComi Trial version and I extracted the files from the 3d.npa already.)
## Post #9
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2013-03-03T23:19:12+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

I will edit this post when I get back to my desk.

Also, there is an issue with the converted models. The .MDL files have multiple meshes, while you only converted the base face mesh. Maybe we need a scan function that will look for additional meshes. Then there are bones, which can be seen at the bottom of the file in a hex editor. If you open the source file in a hex editor and search for VRTX (I think...) Then you will see the other meshes.
Thanks again for your efforts.
## Post #10
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-04T03:43:39+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

Ah ha, I just kept reading lines until I was past that annoying plain-text material section.
Let's see where I can get now.

EDIT: nvm I really don't like the nested structure. If this was just plain text I wouldn't mind as much (like how the .x format is done), but I've never really had a good idea how to deal with parentheses matching. Maybe I should be parsing it recursively or something. Good luck karpati lol maybe I'll visit this thing when I am up for some recursive programming.
## Post #11
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2013-03-04T06:14:27+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

On the topic of the encryption, when I ran the tool I linked in a post that I used to decrypt the .npa files, it automatically decrypted the model .mdl files. I don't know if the archive itself is only encrypted and the data actually isn't inside the archive, or if both are encrypted and the tool uses the same key to decrypt them.

When I first saw the extension I thought "hey, Source/HL2 models!" but nope, I was wrong.
## Post #12
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-03-05T21:07:20+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

> Reply from Cubeburner
>
> Also, there is an issue with the converted models. The .MDL files have multiple meshes, while you only converted the base face mesh. Maybe we need a scan function that will look for additional meshes.

I did find  3 MESH, VRTX, TXUV, FACE data blocks in your sample files, so these files have 3 meshes only.
The other parts of the models are in the \media\3d\st\sonico\coordinate\   directories!

I modified the .mdl loader module:
- I flipped the UC datas vertically
- I changed the face ordering
- I added the materials.

You can download the new converted (+ studio.obj/mtl file) files in Wavefront .obj/mtl format using this link:
[http://3dconverter.webege.com/converted](http://3dconverter.webege.com/converted)

You can download the latest version of 3D O.C. using this link:
[http://3dconverter.webege.com/develop_x86](http://3dconverter.webege.com/develop_x86)
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2013-03-05T21:10:56+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

> Reply from Cubeburner
>
> On the topic of the encryption, when I ran the tool I linked in a post that I used to decrypt the .npa files, it automatically decrypted the model .mdl files.

Thank you for your information, I ran into a little stupid situation.

I used the following command:
nipa.exe -xg 3d.npa Sonicomi
and it did not work fine.

If I used the following command on the DEMO version I got the correct files:
nipa.exe -xg 3d.npa SonicomiTr2
## Post #14
- Username: Cubeburner
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Oct 11, 2011 2:53 pm
- Post datetime: 2013-03-05T21:42:30+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

> Reply from Karpati
>
> Cubeburner wrote:On the topic of the encryption, when I ran the tool I linked in a post that I used to decrypt the .npa files, it automatically decrypted the model .mdl files.

Thank you for your information, I ran into a little stupid situation.

I used the following command:
nipa.exe -xg 3d.npa Sonicomi
and it did not work fine.

If I used the following command on the DEMO version I got the correct files:
nipa.exe -xg 3d.npa SonicomiTr2
Sonicomi decrypt option is for the full game, while SonicomiTr2 is for the trial. I should have been more clear.
## Post #15
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2013-03-15T14:32:04+00:00
- Post Title: [Nitro+] Sonicomi .MDL Files (character/environment models)

Only for Blender249:  animation importer for anm files.
First run script (alt+p)for import meshes and bones from mdl file.
For autotexturing go to correct line in script and write your path to folder with images.

On stage model script crash.

link for blend file and examples.
[http://www.mediafire.com/?alg5b845et33s60](http://www.mediafire.com/?alg5b845et33s60)
## Post #16
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-16T18:51:28+00:00
- Post Title: Re: [Nitro+] Sonicomi .MDL Files (character/environment mode

awesome. thanks mariusz! imma have a good look at how you got those animations in your blender script now . i was looking all over for some of your script examples but during the purging of all sample files from xentax, all of your old scripts were deleted as well!
## Post #17
- Username: raykingnihong
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Mon Apr 07, 2014 3:06 am
- Post datetime: 2014-12-16T10:58:29+00:00
- Post Title: Re: [Nitro+] Sonicomi .MDL Files (character/environment mode

> Reply from Szkaradek123
>
> Only for Blender249:  animation importer for anm files.
First run script (alt+p)for import meshes and bones from mdl file.
For autotexturing go to correct line in script and write your path to folder with images.

On stage model script crash.

link for blend file and examples.
http://www.mediafire.com/?alg5b845et33s60Hi, Szkaradek123, I tested the script error, my game version is Motto! SoniComi PS3 files and SoniComi 2.0 pc files, here is a sample file：[https://onedrive.live.com/redir?resid=6 ... 1236%21155](https://onedrive.live.com/redir?resid=6A28B826BE5F1236%21155)
[jp.png](https://xentaxbackup.github.io/file/8285_jp.png)

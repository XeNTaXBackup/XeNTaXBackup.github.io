## Post #1
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-12-08T15:26:37+00:00
- Post Title: Idolmaster (DereSte) 3d site

[https://deresute.info/3d](https://deresute.info/3d)



[https://deresute.info/3d/100153](https://deresute.info/3d/100153)


You can view the 3d object model on this site
I wonder if I can extract it.
(Chrome is recommended)
[aa.jpg](https://xentaxbackup.github.io/file/11994_aa.jpg)
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-12-08T20:18:18+00:00
- Post Title: Idolmaster (DereSte) 3d site

Have a look at the page source:

```
<html>
	<head>
		<meta charset="utf-8"><meta http-equiv="X-UA-Compatible" content="IE=edge">
		<meta name="viewport" content="width=device-width, user-scalable=no, minimum-scale=1.0, maximum-scale=1.0">
		<title>DERESUTE.INFO 3D VIEWER (仮)</title>
		<style>*{margin:0;padding:0}body{overflow:hidden}</style>
	</head>
	<body>
		<div id="container"></div>
		<script>
			window.headModel = "3d_chara_head_0126_1008_M_Head";
			window.headTexture = "3d_chara_head_0126_1008_tx_chr0126_1008";
			window.headBone = "3d_chara_head_0126_1008_bone";
			window.bodyModel = "3d_md_body1008_M_Body";
			window.bodyTexture = "3d_tx_body1008_tx_body1008";
			window.bodyBone = "3d_md_body1008_bone";
			window.headHasObject = true;
			window.resourceVersion = "10021570";
		</script>
		<script src="https://files.deresute.info/model_10021570/model/3d_chara_head_0126_1008_M_Head.js"></script>
		<script src="https://files.deresute.info/model_10021570/bone/3d_chara_head_0126_1008_bone.js"></script>
		<script src="https://files.deresute.info/model_10021570/model/3d_md_body1008_M_Body.js"></script>
		<script src="https://files.deresute.info/model_10021570/bone/3d_md_body1008_bone.js"></script>
		<script src="/static/viewer/bundle.js"></script>
	</body>
</html>
```

To get the textures, insert resourceVersion and texture name into this url:

```
https://files.deresute.info/model_" + resourceVersion + "/texture/" + t + ".png
```
In this case:

```
https://files.deresute.info/model_10021570/texture/3d_tx_body1008_tx_body1008.png
```

To get the OBJ and bone data:
The files are zlib compressed and base64 encoded.
So open the 4 scripts (not /static/viewer/bundle.js).
Base64 decode the text between the quotation marks.
Extract the zlib compressed data, you can drag & drop a compressed file (extension must be ".zlib) onto this application:
[http://www.mediafire.com/file/1adckp30kk3btdb/zdrop.zip](http://www.mediafire.com/file/1adckp30kk3btdb/zdrop.zip)
I think you'll have to manually create the .mtl files.

Edit: Save this as "materials.mtl":

```
Ka 1.000 1.000 1.000
Kd 1.000 1.000 1.000
illum 0
map_Kd 3d_tx_body1008_tx_body1008.png

newmtl M_Head_0
Ka 1.000 1.000 1.000
Kd 1.000 1.000 1.000
illum 0
map_Kd 3d_chara_head_0126_1008_tx_chr0126_1008.png
```

Add this line at the top of each .obj: 
```
mtllib materials.mtl
```

Result:



screenshot.jpg (115.38 KiB) Viewed 2242 times
## Post #3
- Username: Shine
- Rank: beginner
- Number of posts: 21
- Joined date: Tue Sep 23, 2014 1:15 am
- Post datetime: 2016-12-09T20:40:18+00:00
- Post Title: Idolmaster (DereSte) 3d site

how to decode with base64?
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-12-09T21:22:38+00:00
- Post Title: Idolmaster (DereSte) 3d site

> Reply from Shine
>
> how to decode with base64?
You could use Notepad++ and decode the selected text with this command:
Plugins > MIME Tools > Base64 Decode
## Post #5
- Username: ophy111
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Dec 08, 2016 3:39 pm
- Post datetime: 2016-12-10T05:06:47+00:00
- Post Title: Idolmaster (DereSte) 3d site

How do I get the decoded text as a .zlib? And are you saying as soon as I extract the .zlib I'll be able to turn it into a .obj or...? Sorry, I'm new to this and your steps kind of confuse me. x:
## Post #6
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-12-10T08:18:26+00:00
- Post Title: Idolmaster (DereSte) 3d site

> Reply from ophy111
>
> How do I get the decoded text as a .zlib? And are you saying as soon as I extract the .zlib I'll be able to turn it into a .obj or...? Sorry, I'm new to this and your steps kind of confuse me. x:
It actually is kind of confusing 
Ok, for example save the file 3d_chara_head_0126_1008_M_Head.js on your computer.

1) Open the file with Notepad++ and delete this text from the beginning:
/* DON'T LOOK AT THIS */ window.data_3d_chara_head_0126_1008_M_Head="
and this from the end of the file:
";

2) Press CTRL+A to select everything, click on Plugins > MIME Tools > Base64 Decode
3) Save the file as head.obj.zlib
4) Drag and drop the zlib file onto zdrop.exe (link is in my first post)

Now you should have your head.obj



ins.png (231.89 KiB) Viewed 2209 times
## Post #7
- Username: ophy111
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Dec 08, 2016 3:39 pm
- Post datetime: 2016-12-10T09:05:01+00:00
- Post Title: Idolmaster (DereSte) 3d site

> Reply from herbert3000
>
> ophy111 wrote:How do I get the decoded text as a .zlib? And are you saying as soon as I extract the .zlib I'll be able to turn it into a .obj or...? Sorry, I'm new to this and your steps kind of confuse me. x:
It actually is kind of confusing 
Ok, for example save the file 3d_chara_head_0126_1008_M_Head.js on your computer.

1) Open the file with Notepad++ and delete this text from the beginning:
/* DON'T LOOK AT THIS */ window.data_3d_chara_head_0126_1008_M_Head="
and this from the end of the file:
";

2) Press CTRL+A to select everything, click on Plugins > MIME Tools > Base64 Decode
3) Save the file as head.obj.zlib
4) Drag and drop the zlib file onto zdrop.exe (link is in my first post)

Now you should have your head.obj
ins.png

omg!!! thank you so much!! :'D
## Post #8
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-12-10T10:31:59+00:00
- Post Title: Idolmaster (DereSte) 3d site

There is a third material existed
Image is verified in Chrome
How do I get it?
and thanks very much to herbert3000
[cc.png](https://xentaxbackup.github.io/file/12012_cc.png)
## Post #9
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-12-10T14:02:32+00:00
- Post Title: Idolmaster (DereSte) 3d site

Capture and use the third texture
[karen.jpg](https://xentaxbackup.github.io/file/12015_karen.jpg)
## Post #10
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2016-12-11T03:32:28+00:00
- Post Title: Idolmaster (DereSte) 3d site

Ok, I'll give you one easy tip.
Initialize Chrome cache then go to
C:\Users\(My Account)\AppData\Local\Google\Chrome\User Data\Default\Cache
and replace all files to png 
then you will be able to see the texture
With your image browser
## Post #11
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2016-12-27T17:56:03+00:00
- Post Title: Idolmaster (DereSte) 3d site

How to get the bones?
## Post #12
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2016-12-29T18:41:12+00:00
- Post Title: Idolmaster (DereSte) 3d site

> Reply from Fina
>
> How to get the bones?

The models are in static pose so i doubt there are any bones there, they are simple t-pose static meshes.
## Post #13
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2016-12-30T07:25:00+00:00
- Post Title: Idolmaster (DereSte) 3d site

But someone already managed to rip the bones
## Post #14
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-01-04T12:15:34+00:00
- Post Title: Idolmaster (DereSte) 3d site

> Reply from Fina
>
> But someone already managed to rip the bones
You can get the model files from the Bandai Namco server
You can use the Unity Studio to decrypt
## Post #15
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2017-01-07T14:51:46+00:00
- Post Title: Idolmaster (DereSte) 3d site

> Reply from oamio
>
> Fina wrote:But someone already managed to rip the bones
You can get the model files from the Bandai Namco server
You can use the Unity Studio to decrypt

The model is not in the "BNEI0242" File?
If so which files it is?
## Post #16
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2017-02-19T05:46:25+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from herbert3000
>
> Shine wrote:how to decode with base64?
You could use Notepad++ and decode the selected text with this command:
Plugins > MIME Tools > Base64 Decode

Can u make script for this site too,please?
[http://imas.gamedbs.jp/cgss/chara/index3d/90?q=SSR](http://imas.gamedbs.jp/cgss/chara/index3d/90?q=SSR)
## Post #17
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-02-24T05:33:20+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Fina
>
> herbert3000 wrote:Shine wrote:how to decode with base64?
You could use Notepad++ and decode the selected text with this command:
Plugins > MIME Tools > Base64 Decode

Can u make script for this site too,please?
http://imas.gamedbs.jp/cgss/chara/index3d/90?q=SSR

This is the model script file
[three.bundle.min.zip](https://xentaxbackup.github.io/file/12510_three.bundle.min.zip)
## Post #18
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2017-02-28T08:27:04+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

But when I  Open the model file (not the script) with Notepad++ the words are different and I can't find these words in the beginning (/* DON'T LOOK AT THIS */ window.data_)
## Post #19
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2017-03-02T23:05:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Getting the models from imas.gamedbs.jp/cgss/chara/index3d is a little bit harder, but here's what I did:

Open any 3d model, for example:
http://imas.gamedbs.jp/cgss/chara/viewer3d/101/1001

Change /viewer3d/ in the url to /mesh/b/ for the body (or /mesh/h/ for the head) and press enter:
http://imas.gamedbs.jp/cgss/chara/mesh/b/101/1001
http://imas.gamedbs.jp/cgss/chara/mesh/h/101/1001

Save the file and open it in a text editor (for example the body file)
Delete window.imb=" from the start and " from the end
Search for:
u-ZyJgrBw5
and delete it
Cut everything from the current cursor position to the end and paste is as a new document. Base64 decode the file and save it as mat.mtl.zlib



screenshots.png (36.97 KiB) Viewed 868 times


Also Base64 decode the other file where you cut the string and save it as body1001.obj.zlib (or whatever the id of the 3d model is)

Drag & drop the files onto zdrop.exe

Open mat.mtl with a text editor and copy all filenames after map_Kd into this url:
http://imas.gamedbs.jp/cgss/images_tx/

For example:
newmtl mt_body1308
map_Kd tx_body1308.png
becomes:
http://imas.gamedbs.jp/cgss/images_tx/tx_body1308.png

Download the files into the directory where the obj and mtl files are

Open body.obj with a text editor
Copy the name after mtllib and rename the file mat.mtl to the new filename

For example:
mtllib md_body1308_25_42_4419.mtl
-> mat.mtl becomes md_body1308_25_42_4419.mtl

I'm sure there must be an easier way but that'a all I've got for now. I also didn't have the time yet to illustrate the instructions with screenshots.
## Post #20
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2017-03-03T07:11:54+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Thank u! It's worked!! btw can u rip the bones too as well?
## Post #21
- Username: xbcdr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu May 18, 2017 7:44 pm
- Post datetime: 2017-05-23T07:27:14+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from herbert3000
>
> Getting the models from imas.gamedbs.jp/cgss/chara/index3d is a little bit harder, but here's what I did...
Thx, it really helps
And I tried to find something more...

For any page of imas.gamedbs.jp/cgss/chara/viewer3d/*
model data were loaded from folder ../mesh/b/ and ../mesh/h/
as '<script>' labels tell it
(for example <script src="imas.gamedbs.jp/cgss/chara/mesh/b/xxx"></script> )
which are NOT static DOM elements

So I traced the scripts and found the global variable "a"
defined in "<script>a=blablablabla</script>",
and a decoder js file following it
"<script src="[http://imas.gamedbs.jp/cgss/js/three.bu ... "></script](http://imas.gamedbs.jp/cgss/js/three.bundle.min.js?1486798735%22%3E%3C/script)>"
(no idea what "1486798735" means)

Variable "a" is decoded at line 975:

```
var e=a.substring(a.length-7),k=a.split(e),b=JSON.parse(function(b,e){for(var f=window.atob(e).split("").map(function(b){return b.charCodeAt(0)}),k=0,r=0;f[r]^=b.charCodeAt(k),k=(k+1)%b.length,r=(r+1)%f.length,0!==k||0!==r;);return f.map(function(b){return String.fromCharCode(b)}).join("")}(e+k[1],k[0]));
```


No idea and no matter what it does,
you can get an array like:

```
 md:{
  imh:{
    u:"http:\/\/imas.gamedbs.jp\/cgss\/chara\/mesh\/h\/257\/3017",
    x:"0",
    y:"131",
    z:"-3",
    rx:"0",
    ry:"0",
    rz:"0",
    sx:"100",
    sy:"100",
    sz:"100"},
   imb:{
    u:"http:\/\/imas.gamedbs.jp\/cgss\/chara\/mesh\/b\/257\/3017",
    x:"0",
    y:"0",
    z:"0",
    rx:"0",
    ry:"0",
    rz:"0"}
  },
 p:"http:\/\/imas.gamedbs.jp\/cgss\/images_tx\/",
 sk:"u-ZyJgrBw5"}
```


Obviously it contains the url that we want,
position of model, (and some what?)
url prefix of textures,
and the split string(reversed) for the next decoding.

Follow herbert3000's step,
download this two "mesh" file,
cut their header(window.imx=") and footer("),
split them by that string(reverse(b.sk)), (you'll get two parts each file)
base64 decode this two parts,
save the first part as xxx.obj.zlib and the second part as xxx.mtl.zlib,
decode zlib files by zdrop.exe,
and you get the obj file containing model point set and the mtl file listing textures.

Obj file may look like:

```
# Wavefront OBJ file
# Created with Kaydara FBX
# 
mtllib md_chr0266_18_21_5940.mtl

g M_Head
v -0.012692 0.075740 0.102601
v -0.006363 0.068618 0.099454
```

Rename the mtl file when it defines label "mtllib".

Mtl file looks like:

```
map_Kd tx_chr0106.png
newmtl mt_chr0106_mayu
map_Kd tx_chr0106.png
```

Download all the image files in b.p(imas.gamedbs.jp/cgss/images_tx/)
For example imas.gamedbs.jp/cgss/images_tx/tx_chr0106.png

And then you get all files about the models. (I hope so...)

No any motion in the preview page, so I guess that it has no bone data.

All the steps can be done mechanically, though they are not easier.
An simple js+php script can get them automatically, if you want to own them all.
## Post #22
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-05-24T07:52:20+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Models extracted from game include bones, animations are downloaded apart, but there's no way to convert it in a useful format.

[](http://www.imagebam.com/image/6bc510550110769) 

[](http://www.imagebam.com/image/7076e3550110779) 

[](http://www.imagebam.com/image/cc8f36550110785)
## Post #23
- Username: oamio
- Rank: veteran
- Number of posts: 98
- Joined date: Sun Mar 06, 2011 9:52 pm
- Post datetime: 2017-05-30T18:20:58+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from cornal
>
> Models extracted from game include bones, animations are downloaded apart, but there's no way to convert it in a useful format.

How did you extract models?
If you have extracted animation files, you can render it in 3ds max
It is useful enough because it can also make video
## Post #24
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-05-31T05:12:15+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from oamio
>
> cornal wrote:Models extracted from game include bones, animations are downloaded apart, but there's no way to convert it in a useful format.

How did you extract models?
If you have extracted animation files, you can render it in 3ds max
It is useful enough because it can also make video

I extract the models from game directory: Storage Card\Android\Data\Files, then you must use this Script created by Aluigi 

 Cinderella Script.rar
(224 Bytes) Downloaded 509 times



Once unpacked the files, you can use Assets Bundle Extractor to extract the textures and then export the files as .Assets, the .assets files import them in Unity Studio and extract the models in .FBX, this includes bones and skins.

About the animations, I don't know how convert them in a useful format, the only tool capable of extract the animations is Unity Ex.

The models need a file that arranges the head and body position as well , but I don't know how make this works with the models, so I arrange manually.
## Post #25
- Username: jpnvrh
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Dec 14, 2016 12:38 pm
- Post datetime: 2017-06-08T12:39:25+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from cornal
>
> oamio wrote:cornal wrote:Models extracted from game include bones, animations are downloaded apart, but there's no way to convert it in a useful format.

How did you extract models?
If you have extracted animation files, you can render it in 3ds max
It is useful enough because it can also make video

I extract the models from game directory: Storage Card\Android\Data\Files, then you must use this Script created by Aluigi Cinderella Script.rar

Once unpacked the files, you can use Assets Bundle Extractor to extract the textures and then export the files as .Assets, the .assets files import them in Unity Studio and extract the models in .FBX, this includes bones and skins.

About the animations, I don't know how convert them in a useful format, the only tool capable of extract the animations is Unity Ex.

The models need a file that arranges the head and body position as well , but I don't know how make this works with the models, so I arrange manually.
Can you give us detailed step by step instruction?
## Post #26
- Username: Letty
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 18, 2017 9:14 am
- Post datetime: 2017-06-18T02:18:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Tried extracting using QuickBMS, but I'm getting the following:

- error in src\extra\xalloc.c line 704: xdbg_realloc()

Error: memory allocation problem
       Access is denied.


press ENTER to quit
## Post #27
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-06-18T05:17:35+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Letty
>
> Tried extracting using QuickBMS, but I'm getting the following:

- error in src\extra\xalloc.c line 704: xdbg_realloc()

Error: memory allocation problem
       Access is denied.


press ENTER to quit

When this message appears, means that file is audio or system files, just ignore it, big files are audio, small files until 2mbs are graphic files, (3d models, GUI, and texture files).







Caso Dificil.png (12.07 KiB) Viewed 691 times
## Post #28
- Username: peepeeanne
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed May 24, 2017 5:21 am
- Post datetime: 2017-06-24T10:38:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

can u only rip SSR that you own,or can you find any in the game directory?
## Post #29
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-06-24T16:18:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from peepeeanne
>
> can u only rip SSR that you own,or can you find any in the game directory?

Exist a way, opening the file inside the manifest folder in SD card/android/data/starlight/files/manifest, this file contains all data information and can be opened with a SQL Editor (Firefox have one) open the file and save as .csv file, this can be opened with Excel.

But sadly the files can't be downloaded to PC, because this files need a key to download
[http://storage.game.starlight-stage.jp/ ... a7dcffbd49](http://storage.game.starlight-stage.jp/dl/resources/High/AssetBundles/Android/13ff6c39da98103c3d3933a7dcffbd49)

Always show Access Denied.
## Post #30
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-06-25T15:07:35+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Could not believe it when scamco block access storage page. there wasn't time to download aki model
## Post #31
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-06-28T05:50:29+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

So what do we do now that the 3D viewer page is gone?
## Post #32
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2017-07-03T22:40:02+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I can confirm models can still be extracted, only issue are texture maps which have to be reconverted from PNG to PVR in order to mantain the UVW maps


Source:Twitter
## Post #33
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-07-04T04:54:57+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> I can confirm models can still be extracted, only issue are texture maps which have to be reconverted from PNG to PVR in order to mantain the UVW maps


Source:Twitter
Of course we can, but everything we need now is bypass "[http://storage.game.starlight-stage.jp/](http://storage.game.starlight-stage.jp/)"
## Post #34
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-07-04T05:35:59+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> I can confirm models can still be extracted, only issue are texture maps which have to be reconverted from PNG to PVR in order to mantain the UVW maps


Source:Twitter

how the heck are you doing that? are you getting them from the game? i never could figure that one out
## Post #35
- Username: oamio
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-04T12:16:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Download any file you want.
tools needed 
1. telerik fiddler
2. quickbms
3. (optional) android emulator to get the latest character database.
4. sqlite browser (I used SQLiteDatabaseBrowserPortable)

grab the latest database using fiddler


```
http://storage.game.starlight-stage.jp/dl/10027505/manifests/Android_AHigh_SHigh
```

put this in the get request under composer

```
User-Agent: Dalvik/1.6.0 (Linux; U; Android 4.4.4; GT-P5210 Build/KTU84P)
Host: storage.game.starlight-stage.jp
Connection: Keep-Alive
Accept-Encoding: gzip

```

now you can right click on it and choose save response
Now run this quickbms script on it

```
get ctype long
get size long
get zsize long
get comp long
savepos offset
clog imas.sqlite offset zsize size

```

Now open imas.sqlite in the sqlite tool
and choose export table as csv
use the windows newline character
now you can open the csv in any editor you want and search for the file you want to download.
example 3d_chara_data.unity3d with hash 64ba487fcc99f86bdc38a3b029620c7e
so the url is 

```
http://storage.game.starlight-stage.jp/dl/resources/High/AssetBundles/Android/64ba487fcc99f86bdc38a3b029620c7e
```

just issue that request with fiddler and save the response as 3d_chara_data.unity3d
or if you want ios assets use
3d_chara_data.unity3d c86c359ba92e6e99f360b027204551be

```
http://storage.game.starlight-stage.jp/dl/10027505/manifests/iOS_AHigh_SHigh
```

and for the url use

```
http://storage.game.starlight-stage.jp/dl/resources/High/AssetBundles/iOS/c86c359ba92e6e99f360b027204551be
```
## Post #36
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-07-04T15:55:26+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Oh yess, i love u chrrox, can we married?
## Post #37
- Username: mono24
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-07-04T23:33:25+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Here you go you will love this.
[viewtopic.php?f=29&t=16055&p=131909#p131909](http://forum.xentax.com/viewtopic.php?f=29&t=16055&p=131909#p131909)
## Post #38
- Username: Rua
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 13, 2017 5:49 pm
- Post datetime: 2017-07-13T09:55:15+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

how may I separate the model into parts such as hair, dress, boot, and gloves?
## Post #39
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-07-23T14:09:37+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Rua
>
> how may I separate the model into parts such as hair, dress, boot, and gloves?
 Use blender or 3Ds max to do that
## Post #40
- Username: Letty
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 18, 2017 9:14 am
- Post datetime: 2017-08-01T07:03:42+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Getting "rebuilding library because the asset database could not be found" errors when I try to open the project. Am I missing an archive file?
## Post #41
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-12T19:12:05+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I was able to get the animation clips extracted, but can't provide a tool for it because I used some Unity Editor functionality. I can share the animations as fbx if anyone is interested.

Preview (appears slow because of recording) :
## Post #42
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-08-13T04:21:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Do you extracted the animations using UnityEx ? How do you process it in Unity?
## Post #43
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-13T09:28:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from cornal
>
> Do you extracted the animations using UnityEx ? How do you process it in Unity?
No, I didn't use any third party tool, just the Unity itself. Loaded the asset bundle containing the clip using [AssetBundle](https://docs.unity3d.com/ScriptReference/AssetBundle.html) class, and got the animation clip. It can be saved to disk with the [AssetDatabase](https://docs.unity3d.com/ScriptReference/AssetDatabase.html) class but it doesn't help very much, so not needed.

I already had a script for exporting mesh/skeleton from Unity scene, I developed it further to include animations. Just selected a random body for mesh/skeleton from one of the body bundles.
## Post #44
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2017-08-13T12:28:43+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

That would be cool to have the animations too, that would leave platinum stars ps4 being the only idolm@ster game not rippable.
## Post #45
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2017-08-16T06:45:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> cornal wrote:Do you extracted the animations using UnityEx ? How do you process it in Unity?
No, I didn't use any third party tool, just the Unity itself. Loaded the asset bundle containing the clip using AssetBundle class, and got the animation clip. It can be saved to disk with the AssetDatabase class but it doesn't help very much, so not needed.

I already had a script for exporting mesh/skeleton from Unity scene, I developed it further to include animations. Just selected a random body for mesh/skeleton from one of the body bundles.
Did you get the animations bundle from the manifest? How is it named, also does it include head/face animations? It's a bit of a chore to redo the entire face animation in 3dmax
## Post #46
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-16T18:15:38+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> Did you get the animations bundle from the manifest? How is it named, also does it include head/face animations? It's a bit of a chore to redo the entire face animation in 3dmax

Bundles that contain animation clips are named like this : "3d_cutt_an_chr_son9006_01_legacy". Head animations are included but I didn't notice any face animations. I didn't check all of the files though.
## Post #47
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-17T07:08:19+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> Lumine wrote:Did you get the animations bundle from the manifest? How is it named, also does it include head/face animations? It's a bit of a chore to redo the entire face animation in 3dmax

Bundles that contain animation clips are named like this : "3d_cutt_an_chr_son9006_01_legacy". Head animations are included but I didn't notice any face animations. I didn't check all of the files though.
Nice work. Is this a common way to output the bone animation for Unity3d games? (like MLTD)

Or maybe... can you make a small movie on youtube? I want to know how you do this.
It is OK if you don't want to make a movie, i know it is difficult and boring.
But can you post a song animation named '桜の頃', i really like this song. Sorry i dont know the English name.
## Post #48
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-17T09:34:34+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from z22901206
>
> 
Nice work. Is this a common way to output the bone animation for Unity3d games? (like MLTD)

Or maybe... can you make a small movie on youtube? I want to know how you do this.
It is OK if you don't want to make a movie, i know it is difficult and boring.
But can you post a song animation named '桜の頃', i really like this song. Sorry i dont know the English name.

From what I understand extracting animations from Unity games isn't that common. I am planning to release a tool for it soon, it just needs a bit more work.

I don't have any info about the song names, only different ids for different animation clips. Can you send me a video showing the beginning of the song animation? I can understand which one it is that way.
## Post #49
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-17T10:11:40+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> z22901206 wrote:
Nice work. Is this a common way to output the bone animation for Unity3d games? (like MLTD)

Or maybe... can you make a small movie on youtube? I want to know how you do this.
It is OK if you don't want to make a movie, i know it is difficult and boring.
But can you post a song animation named '桜の頃', i really like this song. Sorry i dont know the English name.

From what I understand extracting animations from Unity games isn't that common. I am planning to release a tool for it soon, it just needs a bit more work.

I don't have any info about the song names, only different ids for different animation clips. Can you send me a video showing the beginning of the song animation? I can understand which one it is that way.

A tool ? I can image how difficult it is. Good luck, no bugs  

Uh..I find this video, "sakura no koro" may be the english name.
[https://www.youtube.com/watch?v=Q7t6R8RM_ZM](https://www.youtube.com/watch?v=Q7t6R8RM_ZM)
## Post #50
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-17T19:23:37+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I managed to make a somewhat working program for extracting the animations but can't say for sure if it will work for other Unity games. That is why I am not posting this in a new thread.

How to use

The program looks like this : 


Use  File->Open to load the assetbundles. If the program finds a gameobject with skinned mesh (character most likely) it will add it to the left list. If it finds an animation clip, it will add the clip to the right list.

Select the character and animation combination that you want. The animation will start to play if everything is fine. Select Export-> IQE to export the skeleton and animation. Meshes won't be exported. Exported file will have the name of the animation, so be careful not to overwrite when exporting multiple characters.

Here comes the pipeline. Once the export is complete you will see an iqe file in the export folder. You can view it and export it as iqm with the [IqeBrowser](http://www.moddb.com/mods/r-reinhard/addons/iqebrowser-v217). It will look like this : 


There is a dummy triangle mesh which is kind of required for some importers to load the iqe file properly. Don't worry about it, you can delete it later. 

So after exporting the model as iqm, you can load it with [Noesis](http://richwhitehouse.com/index.php?content=inc_projects.php). After that you can pretty much export it to any format you like but dae seems to work the best. When I exported it as fbx, the animation played faster than the original version but maybe it was my mistake.

Download : [https://www.mediafire.com/file/dcn16jfj ... rt_New.rar](https://www.mediafire.com/file/dcn16jfj0oq7i9u/AnimExport_New.rar)

Note : Noesis should include iqe importing
## Post #51
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-17T19:26:36+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from z22901206
>
> 
Uh..I find this video, "sakura no koro" may be the english name.
https://www.youtube.com/watch?v=Q7t6R8RM_ZM

The bundle file for that animation is "3d_cutt_an_chr_son9012_01_legacy". You can extract the animation yourself with any character you want, using the method I posted above.
## Post #52
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-18T07:48:01+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> z22901206 wrote:
Uh..I find this video, "sakura no koro" may be the english name.
https://www.youtube.com/watch?v=Q7t6R8RM_ZM

The bundle file for that animation is "3d_cutt_an_chr_son9012_01_legacy". You can extract the animation yourself with any character you want, using the method I posted above.

There is some mistake on my pc...
Here is my feedback, including CGSS, i post some games model and animation in it.
I hope it can be useful...
[https://drive.google.com/file/d/0B_EOJK ... sp=sharing](https://drive.google.com/file/d/0B_EOJKLZ9WswejNROEhmbldObzQ/view?usp=sharing)
## Post #53
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-18T10:47:39+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from z22901206
>
> 
There is some mistake on my pc...
Here is my feedback, including CGSS, i post some games model and animation in it.
I hope it can be useful...
https://drive.google.com/file/d/0B_EOJK ... sp=sharing
Ok, I was able to fix some stuff. When loading the bundles the program changes the bytes indicating the build platform, so that it will appear as a pc bundle and get loaded. Looks like the offset was wrong for some files. It is fixed now.

Cgss samples should load fine now.

Models will load fine for mltd but there seems to be a problem with the animation. Are you sure that the animation file is not corrupted? I also got an error trying to open it with the asset bundle extractor.

The alter files are a bit problematic. First of all you need to unpack them using the [Asset Bundle Extractor](https://7daystodie.com/forums/showthread.php?22675-Unity-Assets-Bundle-Extractor). After unpacking, the models load fine but animation bundles are not. I need to investigate that further to understand the problem.

Thanks for the samples.
## Post #54
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-18T15:06:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> z22901206 wrote:
There is some mistake on my pc...
Here is my feedback, including CGSS, i post some games model and animation in it.
I hope it can be useful...
https://drive.google.com/file/d/0B_EOJK ... sp=sharing
Ok, I was able to fix some stuff. When loading the bundles the program changes the bytes indicating the build platform, so that it will appear as a pc bundle and get loaded. Looks like the offset was wrong for some files. It is fixed now.

New download : http://www.mediafire.com/file/iau71x8b2 ... porter.rar

Cgss samples should load fine now.

Models will load fine for mltd but there seems to be a problem with the animation. Are you sure that the animation file is not corrupted? I also got an error trying to open it with the asset bundle extractor.

The alter files are a bit problematic. First of all you need to unpack them using the Asset Bundle Extractor. After unpacking, the models load fine but animation bundles are not. I need to investigate that further to understand the problem.

Thanks for the samples.

CGSS samples can load.  

The ML animation file i uploaded before is corrupted, it is my mistake...
I upload other files, these should be complete. 
[https://drive.google.com/open?id=0B_EOJ ... 1lVRFdLdVE](https://drive.google.com/open?id=0B_EOJKLZ9WswTTZhY1lVRFdLdVE)
## Post #55
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-18T16:07:52+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> z22901206 wrote:
There is some mistake on my pc...
Here is my feedback, including CGSS, i post some games model and animation in it.
I hope it can be useful...
https://drive.google.com/file/d/0B_EOJK ... sp=sharing
Ok, I was able to fix some stuff. When loading the bundles the program changes the bytes indicating the build platform, so that it will appear as a pc bundle and get loaded. Looks like the offset was wrong for some files. It is fixed now.

New download : http://www.mediafire.com/file/iau71x8b2 ... porter.rar

Cgss samples should load fine now.

Models will load fine for mltd but there seems to be a problem with the animation. Are you sure that the animation file is not corrupted? I also got an error trying to open it with the asset bundle extractor.

The alter files are a bit problematic. First of all you need to unpack them using the Asset Bundle Extractor. After unpacking, the models load fine but animation bundles are not. I need to investigate that further to understand the problem.

Thanks for the samples.
Tks for yr work, and how to load head/face animation? I try some head model but not work.
## Post #56
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-18T18:41:47+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from z22901206
>
> 

CGSS samples can load.  

The ML animation file i uploaded before is corrupted, it is my mistake...
I upload other files, these should be complete. 
https://drive.google.com/open?id=0B_EOJ ... 1lVRFdLdVE
Unlike cgss, mltd seems to use mecanim for rig/animation. That is why the animations are not being played. The program tries to load them as legacy animation but they are not. 

I am working on a way to make mecanim work but those animations that you uploaded don't seem to be character animations, or at least not body animations. Can you send me more animation files to test? You can upload them somewhere and pm me. Thanks.

> Reply from wanglata
>
> 
Tks for yr work, and how to load head/face animation? I try some head model but not work.
I didn't notice any face animations. All those "3d_cutt_an_chr" files have clips for body animation. Did you find a bundle/file for face animation?
## Post #57
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-08-19T13:36:04+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

i wonder! if there is a way to get the facialMorphs("BlendShapes") from MilionLive?
## Post #58
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-19T15:29:43+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> 
I didn't notice any face animations. All those "3d_cutt_an_chr" files have clips for body animation. Did you find a bundle/file for face animation?
I try download new game data, and dont find any animation bundle, except "3d_cutt_an_chr". So I think face anim in  "3d_cutt_an_chr" too, or head bundle. And tool doesnt work with head mesh, right? Body work perfect, but head not load anim.
[Screenshot (72).jpg](https://xentaxbackup.github.io/file/13218_Screenshot (72).jpg)
## Post #59
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-19T15:59:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from wanglata
>
> 
I try download new game data, and dont find any animation bundle, except "3d_cutt_an_chr". So I think face anim in  "3d_cutt_an_chr" too, or head bundle. And tool doesnt work with head mesh, right? Body work perfect, but head not load anim.

Face anim is very likely in the body animation. But it doesn't seem to be bone anim, maybe there is more work to do.
Ps: After i checked, the code "about" face animation is poor little, now i am not sure whether the face animation is in body animation.
[666666666666.jpg](https://xentaxbackup.github.io/file/13221_666666666666.jpg)
## Post #60
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-19T16:34:01+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Looks like face animations were in the same bundle as face meshes. The thing is that, they aren't legacy animations, so the program wasn't able to load them. 

I managed to get them to work but they are more like face poses than animations :


Anyway I will update the program tomorrow, after I make sure everything works fine. I have other stuff to do today
## Post #61
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2017-08-20T02:58:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> Looks like face animations were in the same bundle as face meshes. The thing is that, they aren't legacy animations, so the program wasn't able to load them. 

I managed to get them to work but they are more like face poses than animations :


Anyway I will update the program tomorrow, after I make sure everything works fine. I have other stuff to do today
These information is according to c4d and mmd.

These are called facial expression(as for human). They are parts of a model. Usually the base model is take0. When you want to add facial expression, just change the model and make a new take, like take1.
Usually it will be named, like "smile". Take a bridge from base to take1, the facial expression is finished. Now you can use ExpressionController to control the facial expression, it is likely a slider. It will record the x% of the facial expression(Unlike bone animation). And it will be a frame of an animation if you register it. The player will play the animation, according to the x% changing. Usually, you can register multiple facial expression in a same frame, just like "eye_smile 70%" "mouth_smile 85%".

PS: i don't know how it works in Unity3d
## Post #62
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-20T08:18:26+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I hope we can re-use head and face amin like body. Still waiting
## Post #63
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-20T11:01:53+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from wanglata
>
> I hope we can re-use head and face amin like body. Still waiting
I will try to implement the sliders that z22901206 mentioned. 

Also got the mltd animations working too :


Still it will take some time to add this stuff. It might be slow, because I will be busy for couple of days. I am going to finish it when I have time.
## Post #64
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2017-08-21T08:33:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Which assets have the face expression files? 3d_chara_head or 3d_md_body files?
Edit: Nvm there, just found out, animation assets for facial expressions are located in the 3d_chara_headXXXX files



Some feedback: 
-When trying to open a any file (Example: 3d_chara_head_0250_hq.unity3d) I get the error "Array index is out of range."

Is there a way to download the Cinderella Girls Starlight Stage entire manifest? I'll be traveling for a few days and want to keep experimenting with the assets

Thanks a lot for your hard work everyone!
## Post #65
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-21T20:33:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> Which assets have the face expression files? 3d_chara_head or 3d_md_body files?
Edit: Nvm there, just found out, animation assets for facial expressions are located in the 3d_chara_headXXXX files



Some feedback: 
-When trying to open a any file (Example: 3d_chara_head_0250_hq.unity3d) I get the error "Array index is out of range."

Is there a way to download the Cinderella Girls Starlight Stage entire manifest? I'll be traveling for a few days and want to keep experimenting with the assets

Thanks a lot for your hard work everyone!

The current version that I posted does not handle head/face animations but it should have at least loaded the mesh correctly. Can you pm me the file that has this problem?

chrrox release a python script that downloads the manifest and the files automatically. You can find it here : [viewtopic.php?f=29&t=16055](http://forum.xentax.com/viewtopic.php?f=29&t=16055)
## Post #66
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-22T01:50:13+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Oh boi, I do not notice that the head can load animation with the body. Now just need facial animation. Hope your tool can release soon @akderebur
## Post #67
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-22T08:47:24+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from wanglata
>
> Oh boi, I do not notice that the head can load animation with the body. Now just need facial animation. Hope your tool can release soon @akderebur
I haven't seen full face animations though. There are bunch of takes with 1 keyframe each, so they are more like expressions than animations. I will add a way to blend the expressions but after blending you will end up with a still face expression.

I think they might be using scripting to blend the expressions to match the songs ingame, or maybe some other method. It looks like there are no fully animated face clips for each song.
## Post #68
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-22T16:26:23+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> 
I haven't seen full face animations though. There are bunch of takes with 1 keyframe each, so they are more like expressions than animations. I will add a way to blend the expressions but after blending you will end up with a still face expression.

I think they might be using scripting to blend the expressions to match the songs ingame, or maybe some other method. It looks like there are no fully animated face clips for each song.
Do you check file "3d_cutt_namesong"? I redownload some song in 3d mode, and only get some file "3d_uvm_uv_movie", "3d_stage", "3d_cyalume", "3d_cutt_an_chr_son", "3d_cutt_namesong" and 1 file sqlite music scores
Sample onegai [Mega](https://mega.nz/#!ydpniLJb!IaMBxyoDOkjrBoVtXYdpZBiNPj6bjfgludTWdmAWZBg)
## Post #69
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2017-08-23T01:18:55+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> The current version that I posted does not handle head/face animations but it should have at least loaded the mesh correctly. Can you pm me the file that has this problem?
>
> 
>
> chrrox release a python script that downloads the manifest and the files automatically. You can find it here : viewtopic.php?f=29&t=16055

Thanks a lot for the link and script akderebur , the program worked perfectly this time. Will use this time abroad to categorize some of the dance animation assets in case people are looking for some specific song (still looking for Radio Happy one).

I see face animation is still an issue, I've noticed they are attached to the 3_chara_headXXX assets but still need to be linked to each dance animation assets for the lips sync to work I supose


*I just noticed the tiara obj was lost during the process lol
## Post #70
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-08-23T04:59:04+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Kinda stupid question, but is there a way to tell which body goes to what character instead of tryna guess? Like for the general outfits, not the SSR outfits.
## Post #71
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-08-23T05:18:23+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Is possible open the Room Chars, would be nice for make some GIFS
## Post #72
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2017-08-23T05:58:33+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from anime663
>
> Kinda stupid question, but is there a way to tell which body goes to what character instead of tryna guess? Like for the general outfits, not the SSR outfits.
[https://starlight.kirara.ca/](https://starlight.kirara.ca/) -> Pick a character -> click on Raw Data Table 

It should give you all the information of that specific character starting with Chara_id
## Post #73
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2017-08-23T06:00:24+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> 
https://starlight.kirara.ca/ -> Pick a character -> click on Raw Data Table 

It should give you all the information of that specific character starting with Chara_id

Sweet thanks!
## Post #74
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-23T11:10:01+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> 

Thanks a lot for the link and script akderebur , the program worked perfectly this time. Will use this time abroad to categorize some of the dance animation assets in case people are looking for some specific song (still looking for Radio Happy one).

I see face animation is still an issue, I've noticed they are attached to the 3_chara_headXXX assets but still need to be linked to each dance animation assets for the lips sync to work I supose
The problem in the head bundle doesnt store face animation, which is face pose. I suppose, as z22901206 said it's like morph system of MMD , CGSS use a blend of face pose in each frame to create a face animation. So now need to find a way to use this blend.

P/s: Radio Happy animation is 3d_cutt_an_chr_son3041_01_legacy.unity3d
## Post #75
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-24T04:38:16+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> cornal wrote:Do you extracted the animations using UnityEx ? How do you process it in Unity?
No, I didn't use any third party tool, just the Unity itself. Loaded the asset bundle containing the clip using AssetBundle class, and got the animation clip. It can be saved to disk with the AssetDatabase class but it doesn't help very much, so not needed.

I already had a script for exporting mesh/skeleton from Unity scene, I developed it further to include animations. Just selected a random body for mesh/skeleton from one of the body bundles.
Sorry for offtopic,but will this method work with other game on Unity engine? (DC legends in my case) i can't check this by myself cuz i have no access to my laptop,so i hope you can help me
Samples: [https://www.vg-resource.com/thread-31030.html](https://www.vg-resource.com/thread-31030.html) 
Thanka in advance! 
P.S .TEMP files should be decompressed in Unity Studio before opening
## Post #76
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-25T22:31:20+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I finally had time to update the tool. It should be able to load mecanim animations now, so mltd animations should work. Sometimes animation clips are in the model bundles and they will be added to the clips list after you select the object from the left list (faces for example).

Also added the option to blend facial expressions, you need to check the "Face" box to enable blending. Still no full facial animations, I honestly think they aren't any, but I might be wrong.

New download : [https://www.mediafire.com/file/dcn16jfj ... rt_New.rar](https://www.mediafire.com/file/dcn16jfj0oq7i9u/AnimExport_New.rar)

Btw I didn't mention the controls before, here they are : 

Controls
Right-click and move mouse : Orbit around model
Ctrl + Mouse Wheel Scroll : Zoom
Mouse Wheel Click and move mouse : Pan

> Reply from Rutabaga
>
> 
Sorry for offtopic,but will this method work with other game on Unity engine? (DC legends in my case) i can't check this by myself cuz i have no access to my laptop,so i hope you can help me
Samples: https://www.vg-resource.com/thread-31030.html 
Thanka in advance! 
P.S .TEMP files should be decompressed in Unity Studio before opening

I tried loading some models and they seemed to work fine :

Make sure to select the correct root bone. It should be "Base_Reference".
## Post #77
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-26T09:57:58+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> I finally had time to update the tool. It should be able to load mecanim animations now, so mltd animations should work. Sometimes animation clips are in the model bundles and they will be added to the clips list after you select the object from the left list (faces for example).

Also added the option to blend facial expressions, you need to check the "Face" box to enable blending. Still no full facial animations, I honestly think they aren't any, but I might be wrong.

New download : https://www.mediafire.com/file/dcn16jfj ... rt_New.rar
I still waiting for your tool update , and I was wrong to think facial script in "3d_cutt_songname", or not? Because I see something like position and I dont think that is camera anim bundle  
[Screenshot (75).jpg](https://xentaxbackup.github.io/file/13252_Screenshot (75).jpg)
## Post #78
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2017-08-27T01:29:17+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> I finally had time to update the tool. It should be able to load mecanim animations now, so mltd animations should work. Sometimes animation clips are in the model bundles and they will be added to the clips list after you select the object from the left list (faces for example).

Also added the option to blend facial expressions, you need to check the "Face" box to enable blending. Still no full facial animations, I honestly think they aren't any, but I might be wrong.

New download : https://www.mediafire.com/file/dcn16jfj ... rt_New.rar

Btw I didn't mention the controls before, here they are : 

Controls
Right-click and move mouse : Orbit around model
Ctrl + Mouse Wheel Scroll : Zoom
Mouse Wheel Click and move mouse : Pan

Thanks a lot for your work akderebur,your program looks promising; When exporting the face poses would you recommend .dae or .fbx for exporting purposes? 

> Reply from wanglata
>
> P/s: Radio Happy animation is 3d_cutt_an_chr_son3041_01_legacy.unity3d
Hehe.. thanks for that, saved me a lot of time, how did you know it, is there a data table for the game songs?

[https://manifestproxy-starlight.kirara.ca/](https://manifestproxy-starlight.kirara.ca/) is dead again, good thing I started downloading the entire game assets before it happened


*Just noticed the head decorations for all generic idols are in a different asset
## Post #79
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-08-27T05:20:48+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> 
I tried loading some models and they seemed to work fine :

Make sure to select the correct root bone. It should be "Base_Reference". 
Amazing! Thanks a lot!! This anim extracted manually or by using AnimExport tool?
Tnx.
## Post #80
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-08-27T08:20:26+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> 
When exporting the face poses would you recommend .dae or .fbx for exporting purposes?
I find dae to be better overall but I guess fbx will also work.

> Reply from Rutabaga
>
> 
Amazing! Thanks a lot!! This anim extracted manually or by using AnimExport tool?
Tnx.
I used the tool to extract the animations. You can download it and try it yourself.
## Post #81
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-08-27T10:38:32+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Lumine
>
> Hehe.. thanks for that, saved me a lot of time, how did you know it, is there a data table for the game songs?
I redownload the song, check md5 hash and find in sqlite data base
## Post #82
- Username: cornal
- Rank: beginner
- Number of posts: 39
- Joined date: Sat Oct 25, 2014 10:31 am
- Post datetime: 2017-08-27T17:19:38+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I made a thread on Zenhax for the audio files, some time ago, here is all the tools for extract the audio files
## Post #83
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2017-08-31T18:32:21+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

nvm
## Post #84
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2017-09-02T16:43:28+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Manifest for SideM

```
https://d2qkdj9w29igl.cloudfront.net/v1/2017082901-GQDAMNLZMRK3VrYGkTGgHt20zxIb16Z9/asset_bundles/ios/ios
```
## Post #85
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-09-08T19:03:29+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hello, do you think it would be possible to get the program updated to work with SideM assets?
## Post #86
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-09-08T22:11:48+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I can`t get any of the unity3d files ot open in unity studio :/ i`m on version 0.8 and it has worked before so i`m not sure why im having trouble all of the sudden
## Post #87
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2017-09-09T10:25:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

@akderebur excuse me bro, can u add something like "export all" option for facial in your tool?
## Post #88
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2017-10-20T05:31:22+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

So A problem that i am having is when i try to load the animation file in animexport it says array index is out of range so what do i do???
## Post #89
- Username: kayaha
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Thu Mar 09, 2017 11:15 pm
- Post datetime: 2017-10-25T15:32:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Amazing work! akderebur
Your tool is perfectly working about body animation,
But there seems to be data that can not be loaded for face animation.
For example, I can load 3d_chara_head_0250 and 3d_chara_head_0237 perfectly.
I tried 3d_chara_head_0267_3008 but I could not load (array index is out of range).
Would it be too much trouble for you to help?
## Post #90
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2017-10-25T15:40:14+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from kayaha
>
> Amazing work! akderebur
Your tool is perfectly working about body animation,
But there seems to be data that can not be loaded for face animation.
For example, I can load 3d_chara_head_0250 and 3d_chara_head_0237 perfectly.
I tried 3d_chara_head_0267_3008 but I could not load (array index is out of range).
Would it be too much trouble for you to help?
Are you sure that the files are unpacked? That error message usually pops when trying to load packed files. Use the script that coral posted on page 2 to unpack the file first.
## Post #91
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2017-10-31T06:26:04+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Oh ya I was able to rip the animation to MMD

[https://www.youtube.com/watch?v=6ruNJHPYK-k](https://www.youtube.com/watch?v=6ruNJHPYK-k)
## Post #92
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2017-11-06T05:38:31+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Ohlamy
>
> Oh ya I was able to rip the animation to MMD

https://www.youtube.com/watch?v=6ruNJHPYK-k

Lol LiveAnimation doesnt event convert real anims it interprets them like mocap data so they will always look very wrong
## Post #93
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2017-11-10T17:41:07+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I didn't use LiveAnimation
## Post #94
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2017-11-11T07:41:03+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Does anyone know this animation file name or if they have it [https://www.youtube.com/watch?v=cS8QHKwiD-g](https://www.youtube.com/watch?v=cS8QHKwiD-g)
## Post #95
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2017-11-12T12:10:19+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

FBX Exporter (beta)    [https://www.assetstore.unity3d.com/en/#!/content/101408](https://www.assetstore.unity3d.com/en/#!/content/101408)   you can use this to export from unity if you know how to import the unity files(assetbundles or other stuff) in the Unity Editor version: 2017.2  . ATM it only works for Maya
## Post #96
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2017-11-14T00:17:38+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Deleted
## Post #97
- Username: SeriousNorbo
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 27, 2016 6:24 am
- Post datetime: 2017-11-15T16:04:54+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hey, Akderebur, is there any chance you'll update the program to work with new Unity 2017.1 and .2.

Loading resources always throws "Array Index is out of range".
## Post #98
- Username: ghostx2015
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jun 11, 2015 12:32 am
- Post datetime: 2017-11-16T04:20:22+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> wanglata wrote:Oh boi, I do not notice that the head can load animation with the body. Now just need facial animation. Hope your tool can release soon @akderebur   

I haven't seen full face animations though. There are bunch of takes with 1 keyframe each, so they are more like expressions than animations. I will add a way to blend the expressions but after blending you will end up with a still face expression.

I think they might be using scripting to blend the expressions to match the songs ingame, or maybe some other method. It looks like there are no fully animated face clips for each song.
HI,How to import animation in 3Ds Max？
## Post #99
- Username: garamika
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 09, 2017 4:29 pm
- Post datetime: 2017-12-20T17:00:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Looking at the file named 3d_cutt_{SONGNAME}.unity3d,
I found out what seems to be the lipsync and facials.

The lipsync and facials are in the same file (MonoBehaviour) as the camera data.
(Beware of the spelling : they do not seem to distinguish "l" and "r")

It seems that for facials, they seem to switch between facials on the frame indicated.
For "ripSyncKeys", they seem to switch between vowels in set speed on the frame.
So looking at the data may give us the key for the facial animations.
[lip.PNG](https://xentaxbackup.github.io/file/13718_lip.PNG)
## Post #100
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-01-02T03:35:40+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Please does anyone know how to extract or open the .unity3d files?? Everyone goes over that like nothing, a guy even asked like 10 times in this thread and no one gave him an answer. Guess my question will get the same ignoring treatment.
## Post #101
- Username: mircea
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Sep 28, 2016 6:36 am
- Post datetime: 2018-01-02T11:38:55+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from 47no
>
> Please does anyone know how to extract or open the .unity3d files?? Everyone goes over that like nothing, a guy even asked like 10 times in this thread and no one gave him an answer. Guess my question will get the same ignoring treatment.

Use unityStudio 0.8.0 (you can export to fbx with this if your too mind closed to read the damn thread pages) and look on the thread for the link!  I did not even ask about that and i still have 10GB of models extracted from .unity3d files
## Post #102
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-01-03T02:05:03+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from mircea
>
> 47no wrote:Please does anyone know how to extract or open the .unity3d files?? Everyone goes over that like nothing, a guy even asked like 10 times in this thread and no one gave him an answer. Guess my question will get the same ignoring treatment.

Use unityStudio 0.8.0 (you can export to fbx with this if your too mind closed to read the damn thread pages) and look on the thread for the link!  I did not even ask about that and i still have 10GB of models extracted from .unity3d files

I did look around and searched for answers before asking, and I already tried unity studio 0.8.0 but every .unity3d file I opened showed nothing. Am I missing something? Thank you for answering by the way.
## Post #103
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2018-01-10T15:48:47+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Anybody still alive??

Since October or November 2017, I think deresute has many things changed... as the sql table was protected(?).

I posted the problem in >>[chrrox's topic - Mobile Game Asset Download](http://forum.xentax.com/viewtopic.php?f=29&t=16055&p=135130#p135130)<< about 2 months ago.
But no one answer that question and still no response.

I decided to ask it again in this topic.
1. How to get csv file? (Maybe all tutorials before in this and that topics didn't work out....)
2. How can I view (and extract) assets? (As my Unity Studio 0.8.0 didn't show anything for all assets I transferred from my android device)
May I need some decompression?? How??
3. (After assets can be extracted) How to convert model and animations into FBX or usable unity data?

Extra Question (Unity Game Development).
How can I manage AssetBundle to download everything except card data on startup and load card data when user tapping the card (like deresute)?

Hopefully someone will answer my questions. 
Best regard, Axess.
## Post #104
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-01-10T16:32:16+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Axess
>
> Anybody still alive??

Since October or November 2017, I think deresute has many things changed... as the sql table was protected(?).

I posted the problem in >>chrrox's topic - Mobile Game Asset Download<< about 2 months ago.
But no one answer that question and still no response.

I decided to ask it again in this topic.
1. How to get csv file? (Maybe all tutorials before in this and that topics didn't work out....)
2. How can I view (and extract) assets? (As my Unity Studio 0.8.0 didn't show anything for all assets I transferred from my android device)
May I need some decompression?? How??
3. (After assets can be extracted) How to convert model and animations into FBX or usable unity data?

Extra Question (Unity Game Development).
How can I manage AssetBundle to download everything except card data on startup and load card data when user tapping the card (like deresute)?

Hopefully someone will answer my questions. 
Best regard, Axess.

I'll try to type up a tutorial on the weekend to question (1) and (2).
## Post #105
- Username: Paul Wang
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jan 10, 2018 10:34 pm
- Post datetime: 2018-01-12T04:35:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Axess
>
> Anybody still alive??

Since October or November 2017, I think deresute has many things changed... as the sql table was protected(?).

I posted the problem in >>chrrox's topic - Mobile Game Asset Download<< about 2 months ago.
But no one answer that question and still no response.

I decided to ask it again in this topic.
1. How to get csv file? (Maybe all tutorials before in this and that topics didn't work out....)
2. How can I view (and extract) assets? (As my Unity Studio 0.8.0 didn't show anything for all assets I transferred from my android device)
May I need some decompression?? How??
3. (After assets can be extracted) How to convert model and animations into FBX or usable unity data?

Extra Question (Unity Game Development).
How can I manage AssetBundle to download everything except card data on startup and load card data when user tapping the card (like deresute)?

Hopefully someone will answer my questions. :)
Best regard, Axess.

SQL table is "protected" by LZ4. Just inflate it.
## Post #106
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-15T04:41:16+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

good day im@s cgss game researchers, i was kinda hoping if i could request fumika sagisawa's bright memories model? (including bones) that i can use to learn fiddling with blender/3ds? thank you

EDIT found it... now, my concern is how to import the FBX on blender then export it out for use in MMD any pro advice to a noob like me?

EDIT 2: manage to import the head and body part plus bones to blender... now how to export everything for use in MMD.
## Post #107
- Username: MTCicero
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jan 16, 2018 6:33 pm
- Post datetime: 2018-01-18T21:12:03+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Where did you find it? I've been looking for bones for these models for weeks.
## Post #108
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-19T12:16:41+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

[](https://ibb.co/gnXiDb)
> Reply from MTCicero
>
> Where did you find it? I've been looking for bones for these models for weeks.
well self learning pays off (and instructions how to extract the model+bones are already posted by early deresute researchers)...  in case you missed it, its included on the file when you export the model. just use unitystudio latest, extract ALL 3d objects (to fbx). and that always includes the bones... of course the texture needs to be set manually... (this is assuming you know how to decompress the unity3d file)

my only problem is how to import those bones in MMD because re-rigging an entire model + physics is a pain. and there's the face expressions sigh.. and i hope pros will answer me if i need the "cheek" part when exporting the model to MMD... such a long way to mastery of modeling
## Post #109
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2018-01-19T14:29:22+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> 
my only problem is how to import those bones in MMD because re-rigging an entire model + physics is a pain. and there's the face expressions sigh.. and i hope pros will answer me if i need the "cheek" part when exporting the model to MMD... such a long way to mastery of modeling

Once you get the fbx, you can use [MMDtools_Blender](https://github.com/powroupi/blender_mmd_tools) or [Metaseq](http://www.metaseq.net/en/) to export it as pmx/pmd.

As for Metaseq:
You will get Mesh/Texture/UV/Bones/Weight.
You should do renaming/rebuilding/physics/facial expression yourself.

As for Blender, try it yourself.
## Post #110
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-19T17:12:43+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from z22901206
>
> 
Once you get the fbx, you can use MMDtools_Blender or Metaseq to export it as pmx/pmd.

As for Metaseq:
You will get Mesh/Texture/UV/Bones/Weight.
You should do renaming/rebuilding/physics/facial expression yourself.

As for Blender, try it yourself.

thanks for the advice master... i use blender (since my newbie skills started with and has grown using blender) but i cant seem to export it correctly to PMD/PMX correctly so that i can use it to MMD or PMXe (for stuffs). so i kinda hit some "learning" wall.... anyway will try those now...
## Post #111
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-19T18:45:56+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

finally got PMXe and MMD to load the body + bones and they work great (can pose)... really thanks z22901206!!!

now i need to attach the head + bones to the body and that's the end of "step 1" which i understand will be the same with the body.. then apply the physics and stuffs.

now question again, 

1. how to convert the dance anims to MMD readable format

2. do i need to include the cheek part in the head model when joining to head main part via ctrl J? [https://ibb.co/gnXiDb](https://ibb.co/gnXiDb) --- boxed red (m_cheek)
because it looks ridiculous when combined with the main head part as seen here [](https://ibb.co/gtCRib)

3. finally has anyone manage to convert the expressions used in the game during the dance (eye blinks, brows etc etc) into MMD usable format since this game has been around like 3 yrs or more already?
## Post #112
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2018-01-20T04:31:48+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Paul Wang
>
> SQL table is "protected" by LZ4. Just inflate it.
Still no hope. orz
>> [viewtopic.php?f=29&t=16055&p=137256#p137256](http://forum.xentax.com/viewtopic.php?f=29&t=16055&p=137256#p137256)

/Still waiting tutorial from samsonyu
or someone else can help me ?
## Post #113
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-01-20T05:22:56+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

i literally just did it 2 seconds ago and it works fine.
make sure you click
save > response > response body
it should save a file called 39_.txt
you just need to remove the lz4 compression on that file I use quickbms with no problem.
## Post #114
- Username: wanglata
- Rank: beginner
- Number of posts: 36
- Joined date: Sun Jan 22, 2017 9:41 pm
- Post datetime: 2018-01-20T06:41:33+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Axess
>
> Paul Wang wrote:SQL table is "protected" by LZ4. Just inflate it.
Still no hope. orz
>> viewtopic.php?f=29&t=16055&p=137256#p137256

/Still waiting tutorial from samsonyu
or someone else can help me ?
Actually you can find SQL table in Android/data/jp.co.bandainamcoent.BNEI02/file/manifest and download any assets with fiddler
## Post #115
- Username: xion14blade
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 15, 2018 6:29 am
- Post datetime: 2018-01-20T07:59:31+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Is the manifest table up to date? Can't seem to find any of the models/songs from the past 2-3 months
## Post #116
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-20T14:51:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from xion14blade
>
> Is the manifest table up to date? Can't seem to find any of the models/songs from the past 2-3 months

try using the manifest table in the android folder of deresute.
## Post #117
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-21T13:58:28+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

kinda hit some learning wall again... i dont know why but i always either lose the head part or the body part when exporting FBX to MMD using MMD tools. LOL

i know how to extract the models (head and body) from the unity3d files and export those to 2 FBX files but i kinda hit the problem when  im combining the head and body part and the bones from both parts then exporting it for use in MMD using MMD tools. 

so i was kinda hoping if the good community of deresute researchers can teach me how to export those FBX correctly using MMD tools so i can use it to PMXe or MMD

EDIT: scratch that... managed to combine the head/body part and the bones into one and is finally usable in mmd after a bit of trial and error... wew. now i need to apply textures then fix and rebuild the bones. Then apply physics. Then play
## Post #118
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-01-22T06:34:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Can anybody give me a tip of what I am doing wrong? I get to download all the .unity3d files but when I try to open any of them with the latest unity studio it seems they are all empty.
## Post #119
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-22T09:52:36+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from 47no
>
> Can anybody give me a tip of what I am doing wrong? I get to download all the .unity3d files but when I try to open any of them with the latest unity studio it seems they are all empty.

You will have to uncompress those unity3d files first using quickbms (read back in this thread... I think it was in page 3 or 4) before you can load it in unity
## Post #120
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-01-24T05:10:34+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> 47no wrote:Can anybody give me a tip of what I am doing wrong? I get to download all the .unity3d files but when I try to open any of them with the latest unity studio it seems they are all empty.

You will have to uncompress those unity3d files first using quickbms (read back in this thread... I think it was in page 3 or 4) before you can load it in unity

Thanks for your answer. So that would be 2 times that I need to use quickbms? I used the quickbms script posted in page 3 to convert the response from fiddler into the sql table. Do I need to use it again on each .unity3d file??
## Post #121
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-24T05:30:37+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from 47no
>
> 
Thanks for your answer. So that would be 2 times that I need to use quickbms? I used the quickbms script posted in page 3 to convert the response from fiddler into the sql table. Do I need to use it again on each .unity3d file??

well yeah... after you get your unity3d files after downloading everything, you will need to use again quickbms using the cinderella script ([download/file.php?id=12952](http://forum.xentax.com/download/file.php?id=12952)) to convert a unity3d file then load that in unity studio to export the models to FBX. there's a much faster one, by using CGSS_lz4 ([download/file.php?id=13088](http://forum.xentax.com/download/file.php?id=13088)) just drag the unity3d files to the cgss_lz4 exe and it will do the extraction itself (no need to select script and stuffs, a very friendly program) and you will end up with a filename.unity3d.unity3d (yep that is no typo) load that to unity studio and export the models.
## Post #122
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-01-24T09:36:54+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> 47no wrote:
Thanks for your answer. So that would be 2 times that I need to use quickbms? I used the quickbms script posted in page 3 to convert the response from fiddler into the sql table. Do I need to use it again on each .unity3d file??

well yeah... after you get your unity3d files after downloading everything, you will need to use again quickbms using the cinderella script (download/file.php?id=12952) to convert a unity3d file then load that in unity studio to export the models to FBX. there's a much faster one, by using CGSS_lz4 (download/file.php?id=13088) just drag the unity3d files to the cgss_lz4 exe and it will do the extraction itself (no need to select script and stuffs, a very friendly program) and you will end up with a filename.unity3d.unity3d (yep that is no typo) load that to unity studio and export the models.

Well that worked! Thank you! Now I just gotta figure out how to attach the textures to the model, but I'll manage haha
## Post #123
- Username: nut
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 26, 2018 5:57 am
- Post datetime: 2018-01-26T02:08:33+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I got my model files all loaded in unity studio just fine, and exported as .fbx, but I can't seem to import them into blender. The error says it doesn't support ASCII fbx files. Has anyone gotten around this? I tried several methods already to convert them to binary fbx files but none of them load in blender.
## Post #124
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-01-26T11:40:08+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from nut
>
> I got my model files all loaded in unity studio just fine, and exported as .fbx, but I can't seem to import them into blender. The error says it doesn't support ASCII fbx files. Has anyone gotten around this? I tried several methods already to convert them to binary fbx files but none of them load in blender.

you will need the bos fbx importer/exporter ([http://blenderfbx.render.jp/](http://blenderfbx.render.jp/)) follow the instructions here ([http://blenderfbx.render.jp/install](http://blenderfbx.render.jp/install)) to open the ascii fbx files. i believe this doesnt work in latest blender (2.79) due to code changes (python 3.5 > 3.6) but is guaranteed to work fin in blender 2.72 (which i use)
## Post #125
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-01-31T05:36:08+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Was anybody able to import the face poses to blender and apply them as blend shapes? Or to unity and use them as animations?
## Post #126
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-02-01T17:11:52+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from 47no
>
> Was anybody able to import the face poses to blender and apply them as blend shapes? Or to unity and use them as animations?

been trying that as well because its a pain to redo every face poses and expression in MMD but seeing how earlier "researchers" didnt post about that means, the way to import the faces is yet to be discovered or maybe there's no way to import at all.
## Post #127
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-02-02T01:21:51+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> 47no wrote:Was anybody able to import the face poses to blender and apply them as blend shapes? Or to unity and use them as animations?

been trying that as well because its a pain to redo every face poses and expression in MMD but seeing how earlier "researchers" didnt post about that means, the way to import the faces is yet to be discovered or maybe there's no way to import at all.

Yeah, I gave up some days ago and realized it had been quicker if I just recreated the face animations myself, I am onto that now
## Post #128
- Username: LiteCheese
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 27, 2017 2:54 am
- Post datetime: 2018-02-06T23:48:59+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Probably not the most efficient way, but here is how I imported facial animations into MMD: [https://imgur.com/a/XQZnV](https://imgur.com/a/XQZnV)
Note when importing into blender, the model was scaled to the original tiny size to get it to work for me.

Thanks to akderebur for the original work.

PS: I named the shape key as right eye based on my right and not the model's right.
## Post #129
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2018-02-07T00:07:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

here is most recent update download link.
[http://storage.game.starlight-stage.jp/ ... High_SHigh](http://storage.game.starlight-stage.jp/dl/10033600/manifests/Android_AHigh_SHigh)
[http://storage.game.starlight-stage.jp/ ... dbmanifest](http://storage.game.starlight-stage.jp/dl/10033600/manifests/all_dbmanifest)
## Post #130
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-02-07T02:06:37+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from LiteCheese
>
> Probably not the most efficient way, but here is how I imported facial animations into MMD: https://imgur.com/a/XQZnV
Note when importing into blender, the model was scaled to the original tiny size to get it to work for me.

Thanks to akderebur for the original work.

PS: I named the shape key as right eye based on my right and not the model's right.

Thank you! I've been using akderebur's tool too but was trying to apply the exported face pose as .dae to blender. Will try your method!

EDIT: Tried it but seem to have problems when importing the smd into blender, I get the pose upside down, backwards and at chest height, did you encounter this problem?

[https://imgur.com/z8bhe1r](https://imgur.com/z8bhe1r)
## Post #131
- Username: LoveLynx
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Feb 08, 2018 8:30 am
- Post datetime: 2018-02-08T00:33:21+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from chrrox
>
> here is most recent update download link.
http://storage.game.starlight-stage.jp/ ... High_SHigh
http://storage.game.starlight-stage.jp/ ... dbmanifest

I'm getting an  "Access denied" response, why is that? ;;
(Also hello! I'm new. : D)
## Post #132
- Username: LiteCheese
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 27, 2017 2:54 am
- Post datetime: 2018-02-08T01:18:20+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from 47no
>
> 

Thank you! I've been using akderebur's tool too but was trying to apply the exported face pose as .dae to blender. Will try your method!

EDIT: Tried it but seem to have problems when importing the smd into blender, I get the pose upside down, backwards and at chest height, did you encounter this problem?

https://imgur.com/z8bhe1r

I had that problem too but it worked out fine for me when I scaled mine back to its original size then imported the pose. It might have to do with scaling or some rotation. Not exactly sure.
## Post #133
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-02-08T04:37:07+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from LoveLynx
>
> chrrox wrote:here is most recent update download link.
http://storage.game.starlight-stage.jp/ ... High_SHigh
http://storage.game.starlight-stage.jp/ ... dbmanifest

I'm getting an  "Access denied" response, why is that? ;;
(Also hello! I'm new. : D)

You gotta make a request through fiddler, check page 3 of this thread
## Post #134
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-02-08T08:06:56+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from LiteCheese
>
> 47no wrote:

Thank you! I've been using akderebur's tool too but was trying to apply the exported face pose as .dae to blender. Will try your method!

EDIT: Tried it but seem to have problems when importing the smd into blender, I get the pose upside down, backwards and at chest height, did you encounter this problem?

https://imgur.com/z8bhe1r

I had that problem too but it worked out fine for me when I scaled mine back to its original size then imported the pose. It might have to do with scaling or some rotation. Not exactly sure.

What would be the 'original size'? I imported both the head and body into blender directly from the .fbx exported by unity studio, didn't ever resize it.
## Post #135
- Username: bokoboko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 07, 2018 1:11 pm
- Post datetime: 2018-02-08T23:20:23+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hello everyone, I'm having trouble with this.

I'm able to download the manifest with Fiddler, and then download a specific asset from the manifest list using a url like:
[http://storage.game.starlight-stage.jp/ ... ee562df73f](http://storage.game.starlight-stage.jp/dl/resources/High/AssetBundles/Android/d3497f01fd3539be1912d8ee562df73f) for 3d_chara_body_3010.unity3d
(I right click > Save > Response > Response body)

And then I use the bms script to decompress it, found here: [download/file.php?id=12952](http://forum.xentax.com/download/file.php?id=12952)
But then when loading it into Unity Studio, it appears empty with "Finished loading 0 files with 0 exportable assets"

Anything I'm doing wrong?
## Post #136
- Username: 47no
- Rank: n00b
- Number of posts: 11
- Joined date: Tue Jan 02, 2018 9:32 am
- Post datetime: 2018-02-09T00:52:11+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from bokoboko
>
> Hello everyone, I'm having trouble with this.

I'm able to download the manifest with Fiddler, and then download a specific asset from the manifest list using a url like:
http://storage.game.starlight-stage.jp/ ... ee562df73f for 3d_chara_body_3010.unity3d
(I right click > Save > Response > Response body)

And then I use the bms script to decompress it, found here: download/file.php?id=12952
But then when loading it into Unity Studio, it appears empty with "Finished loading 0 files with 0 exportable assets"

Anything I'm doing wrong?

Try this:

> Reply from Aegis
>
> By using CGSS_lz4 (download/file.php?id=13088) just drag the unity3d files to the cgss_lz4 exe and it will do the extraction itself (no need to select script and stuffs, a very friendly program) and you will end up with a filename.unity3d.unity3d (yep that is no typo) load that to unity studio and export the models.
## Post #137
- Username: bokoboko
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Feb 07, 2018 1:11 pm
- Post datetime: 2018-02-09T01:09:34+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Already tried it, it produces same decompressed file which produces same result in Unity Studio
and I've tried with many different files in the manifest, all produce empty result.

Edit:
It appears I'm using an older version of Unity Studio (v0.5.0.0) which doesn't work but the newer version apparently should.

Edit:
To those facing this issue too, the newest version of Unity Studio is from a different fork you can find here: [https://github.com/Perfare/UnityStudio/releases](https://github.com/Perfare/UnityStudio/releases)


I also made a tool in c# to automatically download and decompress manifest/asset files, though dunno if I can post here (and not too useful in its current state because it's just for this game, I was just too lazy to download individually through fiddler)
## Post #138
- Username: LiteCheese
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 27, 2017 2:54 am
- Post datetime: 2018-02-09T02:26:04+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from 47no
>
> LiteCheese wrote:47no wrote:

Thank you! I've been using akderebur's tool too but was trying to apply the exported face pose as .dae to blender. Will try your method!

EDIT: Tried it but seem to have problems when importing the smd into blender, I get the pose upside down, backwards and at chest height, did you encounter this problem?

https://imgur.com/z8bhe1r

I had that problem too but it worked out fine for me when I scaled mine back to its original size then imported the pose. It might have to do with scaling or some rotation. Not exactly sure.

What would be the 'original size'? I imported both the head and body into blender directly from the .fbx exported by unity studio, didn't ever resize it.

I also directly exported the head and body fbx using unity studio. Then I imported to blender and then into mmd, where I rescaled it for mmd editing without face poses (this was before akderebur develop the animexport program). Some time along the way, akderebur made the program and I started experimenting it. This is when I found that when I imported my model back to blender (from pmx using mmd tools) scaled to its "original size", the imported facial poses worked. So to be honest, I'm still figuring out how to directly import face poses from the fbx exported from unity studio. I got a hunch that it has to do with the armature but I'm no expert with 3d modelling etc.

EDIT: Okay I figured it out. Just rename the Head and Neck bones to something else other than Head and Neck. Then import your pose and it should look correct.

EDIT #2: Figured out more things. Had to rename the Head, Neck AND Position bones. Here's some more pictures of how I get things to work. [https://imgur.com/a/XOxnt](https://imgur.com/a/XOxnt)
## Post #139
- Username: z22901206
- Rank: advanced
- Number of posts: 40
- Joined date: Thu Dec 24, 2015 8:50 pm
- Post datetime: 2018-02-09T12:20:56+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from LiteCheese
>
> 
I also directly exported the head and body fbx using unity studio. Then I imported to blender and then into mmd, where I rescaled it for mmd editing without face poses (this was before akderebur develop the animexport program). Some time along the way, akderebur made the program and I started experimenting it. This is when I found that when I imported my model back to blender (from pmx using mmd tools) scaled to its "original size", the imported facial poses worked. So to be honest, I'm still figuring out how to directly import face poses from the fbx exported from unity studio. I got a hunch that it has to do with the armature but I'm no expert with 3d modelling etc.

US doesn't support any animation export, neither bone-based nor Morph, till now.
The author said that he is working on it, but still in an early stage.
## Post #140
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-02-21T14:18:55+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

so uh i tried the expression importing and followed the instructions here [https://imgur.com/a/XQZnV](https://imgur.com/a/XQZnV) (like exporting the iqe using the animexporter, convert to sqm using iqebrowser, convert to smd using noesis then import to blender). followed the instruction of litecheese of renaming the head and neck bone to something else and what i get is a ridiculous "looks like mutated" long necked mess as seen here: [https://imgur.com/a/rzGUw](https://imgur.com/a/rzGUw) i know i might be doing wrong somewhere but i cant seem to find it so seeking the help of litecheese to point out where it looks like i am doing wrong.
## Post #141
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-02-21T22:05:19+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

A user contacted me saying that the animation exporter is not working for some newer files. I tested it, and it looks the clips inside the new bundles are not recognized. I don't know what the reason is atm.

Unity Studio is able to load and export the clips, but exported clips aren't really okay. There is probably a problem with keyframe interpolation, and I don't want to write a new exporter for it.

So I modified the US a bit, to dump the data of the animation clips. The dumped data can be loaded into the AnimExport afterwards. So here is how to do it.

- Download this US : [http://www.mediafire.com/file/c5e1c64v0 ... USDump.rar](http://www.mediafire.com/file/c5e1c64v0c6os9c/USDump.rar)

- Load the bundle in US, go to Assets List, select the animation clip and click Export -> Curve data in upper menu : 


- A file with the ".cdata" extension will be created.

- Download the new AnimExport : [http://www.mediafire.com/file/w8nf1q4id ... Export.rar](http://www.mediafire.com/file/w8nf1q4idzwt4vy/NewAnimExport.rar)

- Load that cdata file in AnimExport. The animation clip will be created and added to the list.

- The rest is the same. Select your character, select the clip and export.

Hope this helps some people who wants to get the newer animations.
## Post #142
- Username: Lumine
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat May 08, 2010 11:43 pm
- Post datetime: 2018-02-28T21:44:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

With the release of DragonBallZFigthers for PC I really hope someone manages to mod it to add the Idolmaster girls, we got almost every tool at our disposal, thanks for your work akderebur.
## Post #143
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-03-02T17:12:39+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

aaaaaah i dont know anymore... followed all of the instruction litecheese posted like to the smallest details, but the expressions didnt work. all i get is that that each bones are inverted, and reversed like the back hair is on the front instead of back and the mouth-eye bones are at the back instead in front (screenshot provided). i didnt apply armature modifier anymore since i already know the mesh will become a mess in such bone positions once i add the armature modifier. it did fix the posture though...

i think its either i am doing something wrong during conversion from iqe-iqm-smd or there's a version difference with the blender plugins litecheese and i use (like mmd tools)

though i am pretty sure i use the latest though. and for details,
i use mmd tools that are from here powroupi/blender_mmd_tools, i used 2.76 blender, i also used the latest blender source tool plugin (for smd import), and noesis and iqe browser are also latest. i would really appreciate any PROFESSIONAL advice on how to fix this.
[New Bitmap Image.jpg](https://xentaxbackup.github.io/file/13990_New Bitmap Image.jpg)
## Post #144
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2018-03-13T21:49:53+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

i'm having a weird issue with the new version of animation exporter
the old one without facial animation support worked fine for me, but when i export legacy starlight stage body animations instead of the base skeleton being in T-pose i get it in the first animation frame's pose, making it impossible to use anywhere at all...
do you think you could reupload the older version of the program @akderebur?
## Post #145
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-13T22:51:13+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from MarieRose1301
>
> i'm having a weird issue with the new version of animation exporter
the old one without facial animation support worked fine for me, but when i export legacy starlight stage body animations instead of the base skeleton being in T-pose i get it in the first animation frame's pose, making it impossible to use anywhere at all...
do you think you could reupload the older version of the program @akderebur?

You can find the old versions in my previous posts : [viewtopic.php?p=133129#p133129](http://forum.xentax.com/viewtopic.php?p=133129#p133129)

I don't think I have changed anything regarding the animation export though. I doubt you will get a different result with the old version.
## Post #146
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2018-03-14T12:44:13+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> MarieRose1301 wrote:i'm having a weird issue with the new version of animation exporter
the old one without facial animation support worked fine for me, but when i export legacy starlight stage body animations instead of the base skeleton being in T-pose i get it in the first animation frame's pose, making it impossible to use anywhere at all...
do you think you could reupload the older version of the program @akderebur?

You can find the old versions in my previous posts : viewtopic.php?p=133129#p133129

I don't think I have changed anything regarding the animation export though. I doubt you will get a different result with the old version.

The program in the post you linked me is the newer version than the one i used before. This one has the facial animations working already, and the one i was stupid enough to overwrite was made a while ago...
This one didn't work out as expected indeed though
It exports the animations just fine, but the issue is that instead of the T pose the rest pose becomes the animation's first frame, i'm not sure why
## Post #147
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-14T12:56:06+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from MarieRose1301
>
> 
It exports the animations just fine, but the issue is that instead of the T pose the rest pose becomes the animation's first frame, i'm not sure why

That seems to be right. The tool starts sampling the animation starting from the first frame, and exports it.

Are you having a problem after you apply the exported animation to your model? If that is the case, I think it is more related to your 3d software.
## Post #148
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2018-03-14T17:01:08+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> MarieRose1301 wrote:
It exports the animations just fine, but the issue is that instead of the T pose the rest pose becomes the animation's first frame, i'm not sure why

That seems to be right. The tool starts sampling the animation starting from the first frame, and exports it.

Are you having a problem after you apply the exported animation to your model? If that is the case, I think it is more related to your 3d software.

It wasn't like this before I swear
It used to be like this when you reset the animation: 
It's very important the rest pose is the T pose for me like it used to be at first
## Post #149
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-03-14T17:16:59+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from MarieRose1301
>
> 
It's very important the rest pose is the T pose for me like it used to be at first

I am not sure why you would need that, but here is a link to an older version : [http://www.mediafire.com/file/iau71x8b2 ... porter.rar](http://www.mediafire.com/file/iau71x8b2p2jp18/AnimExporter.rar)
## Post #150
- Username: MarieRose1301
- Rank: veteran
- Number of posts: 97
- Joined date: Sun Oct 12, 2014 5:29 am
- Post datetime: 2018-03-14T19:01:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> MarieRose1301 wrote:
It's very important the rest pose is the T pose for me like it used to be at first

I am not sure why you would need that, but here is a link to an older version : http://www.mediafire.com/file/iau71x8b2 ... porter.rar

omg thank you so much, this is working the way i need it to now C:
## Post #151
- Username: xion14blade
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 15, 2018 6:29 am
- Post datetime: 2018-04-02T20:00:23+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I managed to get the fbx files and all onto blender following LiteCheese's guide, however I've encountered and issue where exporting to pmx with mmd_tools, doesn't actually export anything, am doing something wrong?
## Post #152
- Username: kitayume
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 27, 2017 10:14 am
- Post datetime: 2018-04-03T12:06:15+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I can't export IQM file with this motions(7740frames) , can somebody help me please?;u;
[QQ截图20180403200503.png](https://xentaxbackup.github.io/file/14161_QQ截图20180403200503.png)
## Post #153
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-03T15:55:39+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from kitayume
>
> I can't export IQM file with this motions(7740frames) , can somebody help me please?;u;
Can you post some sample files?
## Post #154
- Username: kitayume
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 27, 2017 10:14 am
- Post datetime: 2018-04-03T23:43:01+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> 
Can you post some sample files?
[http://www.mediafire.com/folder/t63v411 ... 2ze/shared](http://www.mediafire.com/folder/t63v4119qdvdtqv,s45qy2s95yhe2ze/shared)
here are sample files

Animation was called "l_chmot_00_wam050_0001_c01_common_001_ani"

Thank you!!
## Post #155
- Username: kitayume
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 27, 2017 10:14 am
- Post datetime: 2018-04-05T04:55:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> kitayume wrote:I can't export IQM file with this motions(7740frames) , can somebody help me please?;u;
Can you post some sample files?

When I try to rip another motion it just normally exported,
But when I’m trying to rip this motion it doesn’t have any response for me;u;
## Post #156
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-05T06:34:26+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from kitayume
>
> 
But when I’m trying to rip this motion it doesn’t have any response for me;u;
I was able to export the animation fine. Are you using the latest version I posted : [viewtopic.php?p=138105#p138105](http://forum.xentax.com/viewtopic.php?p=138105#p138105)?
## Post #157
- Username: kitayume
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 27, 2017 10:14 am
- Post datetime: 2018-04-05T07:06:40+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> kitayume wrote:
But when I’m trying to rip this motion it doesn’t have any response for me;u;
I was able to export the animation fine. Are you using the latest version I posted : viewtopic.php?p=138105#p138105?

Yes I’m using this version, I’ll try it again.
Thank you!
## Post #158
- Username: kitayume
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Tue Jun 27, 2017 10:14 am
- Post datetime: 2018-04-06T00:06:06+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> kitayume wrote:
But when I’m trying to rip this motion it doesn’t have any response for me;u;
I was able to export the animation fine. Are you using the latest version I posted : viewtopic.php?p=138105#p138105?

its work when I change path for file. but the bvh file I convert is large,is that correct?
## Post #159
- Username: xion14blade
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 15, 2018 6:29 am
- Post datetime: 2018-04-22T12:40:19+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from xion14blade
>
> I managed to get the fbx files and all onto blender following LiteCheese's guide, however I've encountered and issue where exporting to pmx with mmd_tools, doesn't actually export anything, am doing something wrong?
Get past a roadblock, run into another :/ anyone know what I'm doing wrong?
## Post #160
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-04-23T23:59:41+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Anyone has the newest manifest of the SideM app? There’s been a lot of new models released since the last one posted by chrrox.
## Post #161
- Username: sdxsdxsdx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 23, 2017 7:16 pm
- Post datetime: 2018-04-24T00:53:15+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> kitayume wrote:
But when I’m trying to rip this motion it doesn’t have any response for me;u;
I was able to export the animation fine. Are you using the latest version I posted : viewtopic.php?p=138105#p138105?
Can you public "AnimExport" source code with full Unity project,
I want to extract other game(Hatsune Miku VR) animation by this tool,
but some games not pack character model and animation together,
or not use assetbundle format.
## Post #162
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-24T07:01:11+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from sdxsdxsdx
>
> 
I want to extract other game(Hatsune Miku VR) animation by this tool,
but some games not pack character model and animation together,
or not use assetbundle format.
My script depends on Unity and it basically reads the animation data that is loaded/played in the scene. If your game doesn't use assetbundles, you won't be able to import the assets into a Unity game anyway. So this method won't help you.

Your best option is to use a third-party tool like UnityStudio. It recently added support for animations. You can give it a try.
## Post #163
- Username: sdxsdxsdx
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Oct 23, 2017 7:16 pm
- Post datetime: 2018-04-24T13:07:55+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> sdxsdxsdx wrote:
I want to extract other game(Hatsune Miku VR) animation by this tool,
but some games not pack character model and animation together,
or not use assetbundle format.
My script depends on Unity and it basically reads the animation data that is loaded/played in the scene. If your game doesn't use assetbundles, you won't be able to import the assets into a Unity game anyway. So this method won't help you.

Your best option is to use a third-party tool like UnityStudio. It recently added support for animations. You can give it a try.
Ok,thanks for your advice
Your tool is amazing,I like it so much.
## Post #164
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-04-28T16:03:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> I finally had time to update the tool. It should be able to load mecanim animations now, so mltd animations should work. Sometimes animation clips are in the model bundles and they will be added to the clips list after you select the object from the left list (faces for example).

Also added the option to blend facial expressions, you need to check the "Face" box to enable blending. Still no full facial animations, I honestly think they aren't any, but I might be wrong.

New download : https://www.mediafire.com/file/dcn16jfj ... rt_New.rar

Make sure to select the correct root bone. It should be "Base Reference".

Hello akderebur,

When I launch your tool by double clicking AnimExport.exe, the application opens the "AnimeExport Configuration" window.
There's no File menu. 
There's a tab called "Graphics" and "Input".
And buttons for "Play!" and "Quit".

Can you tell me what I'm doing wrong?
Much appreciated.

P.S. I'm tried to get the animations for one of the songs, so I can practice performing the dance : )
## Post #165
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-04-28T16:24:22+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from samsonyu
>
> 
Can you tell me what I'm doing wrong?
Much appreciated.
Click "Play"  . I made it as a Unity game, so it asks for graphics options at the start.
## Post #166
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-04-28T16:36:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from akderebur
>
> 
Click "Play"  . I made it as a Unity game, so it asks for graphics options at the start.

Hello akderebur,
Thank you for your reply!
For some reason, I had to launch it twice in a row before it worked properly.
But thanks a lot!
I will try it out.
## Post #167
- Username: xion14blade
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jan 15, 2018 6:29 am
- Post datetime: 2018-04-30T20:45:21+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

The quickbms script doesn't seem to be working anymore for the latest manifest file. Anyone know a fix for it?
## Post #168
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-05-04T04:38:11+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from xion14blade
>
> The quickbms script doesn't seem to be working anymore for the latest manifest file. Anyone know a fix for it?

there's a manifest (that have no filename extension) file in the "manifest" folder inside the deresute folder in your android. well of course you will need to install the deresute app first
## Post #169
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2018-05-11T21:44:25+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

@akderebur 

Hello again are you able to get back on to discord i found another problem with animexport again 

-andno
## Post #170
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2018-05-11T23:05:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Ohlamy
>
> 
Hello again are you able to get back on to discord i found another problem with animexport again
I am currently not willing to work further on this project. Isn't Unity Studio able to load the animations from this game? I think animation support was added not long ago.
## Post #171
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-05-11T23:33:37+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Ohlamy
>
> @akderebur 

Hello again are you able to get back on to discord i found another problem with animexport again 

-andno

@Ohlamy
Maybe I can help.
What is the problem?
## Post #172
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2018-05-11T23:36:15+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

it's the newer mltd animation not loading in the exporter
## Post #173
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2018-05-11T23:43:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

@akderebur 

No the animation doesn't load because they changed the format of the animation
## Post #174
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-05-11T23:50:34+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Ohlamy
>
> @akderebur 

No the animation doesn't load because they changed the format of the animation

I have not tried looking at the latest IDOLMASTER game files, but when did you download the files? This week? Are you using the tool to load the unity asset bundle files directly or are you extracting the animation files from the asset bundles?
## Post #175
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2018-05-11T23:52:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I got the newest files and usually im able to just load the animation into the program just fine
## Post #176
- Username: samsonyu
- Rank: n00b
- Number of posts: 11
- Joined date: Wed Sep 27, 2017 6:24 am
- Post datetime: 2018-05-11T23:58:07+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Ohlamy
>
> I got the newest files and usually im able to just load the animation into the program just fine

If what you say is true, then we will just have to wait and see who’s willing to step up to the plate to come up with a new solution. In the mean time, hope you still have the old files to play around with : )
## Post #177
- Username: Ohlamy
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Mon Jul 03, 2017 2:01 pm
- Post datetime: 2018-05-11T23:58:49+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I do luckily XD
## Post #178
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-05-18T02:20:02+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

What's the new manifest for Million Live Theater Days and SideM LIVE ON ST@GE?
## Post #179
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-05-18T15:04:36+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

just found this on youtube
[https://www.youtube.com/watch?v=VjsFBl-82wA](https://www.youtube.com/watch?v=VjsFBl-82wA)
[https://www.youtube.com/watch?v=vunSgFNdjJk](https://www.youtube.com/watch?v=vunSgFNdjJk)

the interesting thing is that it says in description that this was created by a certain "starlight dance simulator" we all know that this is what we want why we rip the models. just hoping that someone could help me dig the internet for this.
## Post #180
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-12T11:54:36+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I decrypted The Idolm@ster Platinum stars PS4 files. 



Examples of polycount:
## Post #181
- Username: shingenseiji
- Rank: advanced
- Number of posts: 42
- Joined date: Tue Feb 20, 2018 12:57 am
- Post datetime: 2018-06-12T14:04:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from daemon1
>
> I decrypted The Idolm@ster Platinum stars PS4 files. 



Examples of polycount:
OH MY GOD YES!!!! Amazing job Daemon!!! Were you able to extract the textures too or did you only extract the models?
## Post #182
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-12T14:12:38+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

This on the image above is a texture 2048x2048 in size, in BC7 format

(imgur scaled down the image)
## Post #183
- Username: love8destiny
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 22, 2017 1:24 pm
- Post datetime: 2018-06-14T01:34:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Edit: Deleted (figured out the solution)
## Post #184
- Username: Mrtest
- Rank: advanced
- Number of posts: 43
- Joined date: Wed Aug 24, 2011 3:11 am
- Post datetime: 2018-06-19T10:13:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from daemon1
>
> This on the image above is a texture 2048x2048 in size, in BC7 format

(imgur scaled down the image)
Will the script be uploaded for .jxk files?
## Post #185
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2018-06-19T10:45:05+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Mrtest
>
> daemon1 wrote:This on the image above is a texture 2048x2048 in size, in BC7 format

(imgur scaled down the image)

Will the script be uploaded for .jxk files?
да
## Post #186
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2018-07-05T16:17:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from LiteCheese
>
> Probably not the most efficient way, but here is how I imported facial animations into MMD: https://imgur.com/a/XQZnV
Note when importing into blender, the model was scaled to the original tiny size to get it to work for me.

Thanks to akderebur for the original work.

PS: I named the shape key as right eye based on my right and not the model's right.

how to load fbx to blender using Bos Fbx script without error? (mine is blender v2.77)
since i can't use it, i converted it to FBX through Noesis (using the "-fbxnewexport -fbxsmoothgroups") and used the fbx script instead Bos Fbx script for model
i tried to use dae ,pmx (model was resize little big in pmx ed) & fbx (fbx make the model way to small so i don't use it because i can only see black thing ) for model and load the smd 
but nothing happened when i load the smd...only triangle mesh and more bones show instead
the face doesn't change ( i tried to load wink eye)

i hope someone can help mehh ;v;
## Post #187
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-07-09T14:18:53+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Fina
>
> LiteCheese wrote:Probably not the most efficient way, but here is how I imported facial animations into MMD: https://imgur.com/a/XQZnV
Note when importing into blender, the model was scaled to the original tiny size to get it to work for me.

Thanks to akderebur for the original work.

PS: I named the shape key as right eye based on my right and not the model's right.

how to load fbx to blender using Bos Fbx script without error? (mine is blender v2.77)
since i can't use it, i converted it to FBX through Noesis (using the "-fbxnewexport -fbxsmoothgroups") and used the fbx script instead Bos Fbx script for model
i tried to use dae ,pmx (model was resize little big in pmx ed) & fbx (fbx make the model way to small so i don't use it because i can only see black thing ) for model and load the smd 
but nothing happened when i load the smd...only triangle mesh and more bones show instead
the face doesn't change ( i tried to load wink eye)

i hope someone can help mehh ;v;

the only thing i do so that i can use BOS FBX, is to use an old ver of blender 2.72 to be exact then, once i converted it to PMX load it again to blender 2.77 (with mmd tools)
## Post #188
- Username: LiteCheese
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 27, 2017 2:54 am
- Post datetime: 2018-07-09T16:10:21+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> Fina wrote:LiteCheese wrote:Probably not the most efficient way, but here is how I imported facial animations into MMD: https://imgur.com/a/XQZnV
Note when importing into blender, the model was scaled to the original tiny size to get it to work for me.

Thanks to akderebur for the original work.

PS: I named the shape key as right eye based on my right and not the model's right.

how to load fbx to blender using Bos Fbx script without error? (mine is blender v2.77)
since i can't use it, i converted it to FBX through Noesis (using the "-fbxnewexport -fbxsmoothgroups") and used the fbx script instead Bos Fbx script for model
i tried to use dae ,pmx (model was resize little big in pmx ed) & fbx (fbx make the model way to small so i don't use it because i can only see black thing ) for model and load the smd 
but nothing happened when i load the smd...only triangle mesh and more bones show instead
the face doesn't change ( i tried to load wink eye)

i hope someone can help mehh ;v;

the only thing i do so that i can use BOS FBX, is to use an old ver of blender 2.72 to be exact then, once i converted it to PMX load it again to blender 2.77 (with mmd tools)

Maybe? [https://blender.stackexchange.com/quest ... named-umio](https://blender.stackexchange.com/questions/51848/using-bos-fbx-error-no-module-named-umio)
## Post #189
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2018-07-15T04:53:52+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> xion14blade wrote:The quickbms script doesn't seem to be working anymore for the latest manifest file. Anyone know a fix for it?


there's a manifest (that have no filename extension) file in the "manifest" folder inside the deresute folder in your android. well of course you will need to install the deresute app first

really? i havent seen anything like that

if thats true then thatd be a huge life saver since i cant get the fiddler method to work at all
## Post #190
- Username: piaze
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 11, 2018 6:23 am
- Post datetime: 2018-07-23T06:54:43+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Help..

I'm having problem importing facial animations

Is it the Blender Source  Tool the problem?

When Importing SMD, Making a new Armature shows well on the program with bones in the right place, but if I choose either two of the other options, the model just faces down with distortion.

Am I doing something wrong here?
## Post #191
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-07-25T12:47:55+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from piaze
>
> Help..

I'm having problem importing facial animations

Is it the Blender Source  Tool the problem?

When Importing SMD, Making a new Armature shows well on the program with bones in the right place, but if I choose either two of the other options, the model just faces down with distortion.

Am I doing something wrong here?

renaming the neck and head bone to something else corrects the position as per instructions of litecheese. but i expect you will experience the same gibberish face when loading a facial animation
## Post #192
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-07-25T12:49:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Supurreme
>
> Aegis wrote:xion14blade wrote:The quickbms script doesn't seem to be working anymore for the latest manifest file. Anyone know a fix for it?


there's a manifest (that have no filename extension) file in the "manifest" folder inside the deresute folder in your android. well of course you will need to install the deresute app first

really? i havent seen anything like that

if thats true then thatd be a huge life saver since i cant get the fiddler method to work at all

see that manifest folder? there's a file inside that. rename that to imas.sqlite and do the rest of the step as usual. no need for fiddler stuffs. the good thing in this is that it is a guaranteed updated database for models and stuffs
[37775437_2210196065676694_389895224165400576_n.jpg](https://xentaxbackup.github.io/file/14658_37775437_2210196065676694_389895224165400576_n.jpg)
## Post #193
- Username: piaze
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 11, 2018 6:23 am
- Post datetime: 2018-07-26T16:23:32+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis
>
> 
renaming the neck and head bone to something else corrects the position as per instructions of litecheese. but i expect you will experience the same gibberish face when loading a facial animation

I also renamed Position too following litecheese's guide ([https://imgur.com/a/XOxnt](https://imgur.com/a/XOxnt)).  I've miss that part about renaming them, and after that It seems to work a bit not facing bottom, but the face bone still gets distorted 180 deg facing backwards.

Is there a solution to this also? Many thanks in advance
## Post #194
- Username: Axess
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sat Nov 04, 2017 11:09 pm
- Post datetime: 2018-07-27T18:48:09+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I managed to get body and head(+cheek) model.
When I export head into fbx, the face is hidden by cheek(?).
*Using AssetStudio.x64.v0.10.0.52
[](https://imgur.com/BjcaTyU)

1. How to solve this? ↑
2. How to join the head and body perfectly?
-> Solved (Only in UnityEditor)

3. How to export apply bone and animation and use it in 3dmax/maya/etc...
For the bone & animation, I used akderebur's program. And successfully exported IQE.
-> Convert to IQM -> ...

4. In 1 set of character, which files are needed?
Here's my list
- 3d_chara_body_XXXX.unity3d
>> Cloth & Collision ScriptableObject
- 3d_chara_head_YYYY_XXXX.unity3d
>> Head part. Contains model data, animation controller, avatar, animation clip, head & cheek's texture, cloth & collision ScriptableObject
- 3d_md_bodyXXXX.unity3d
>> Body model data
- 3d_tx_bodyXXXX.unity3d
>> Body texture

5. For 1 song, which files are needed?
(I use [wanglata's onegai](http://forum.xentax.com/viewtopic.php?p=133248#p133248) as reference)
- 3d_cutt_ac_camera_XXXX.unity3d
- 3d_cutt_an_chr_sonXXXX_YY_legacy.unity3d
- 3d_cyalume_mZZZ.unity3d
- 3d_uvm_uv_movie_AAAA_BBB_low.unity3d
- 3d_uvm_uv_movie_free_CCC_low.unity3d
- 3d_uvm_uv_movie_musicXXXX_001_low.unity3d
- 3d_uvm_uv_movie_music1XXXX_002_low.unity3d
- sqlite << Where? I can't find it!!

Thank you.

------------

**Edited**

6. Joining model can be done in unity.
(Using gameObject.transform.position/rotation of Head/Neck = Body/Neck & Head/Head = Body/Head)
But how to export the different model data into one?

[](https://imgur.com/RtOLQX4)

7. Animation can be applied in unity too.
The body was done perfectly, but I don't know how to apply head's animation.

[](https://imgur.com/VddNIfx)

8. Writing your own custom shader for cheek (w/ alpha texture) is not too hard, but the problem is lighting.
How to solve this?

[](https://imgur.com/BAnx3mn)
[](https://imgur.com/kYYeaYP)
## Post #195
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-07-28T15:23:03+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from piaze
>
> Aegis wrote:
renaming the neck and head bone to something else corrects the position as per instructions of litecheese. but i expect you will experience the same gibberish face when loading a facial animation

I also renamed Position too following litecheese's guide (https://imgur.com/a/XOxnt).  I've miss that part about renaming them, and after that It seems to work a bit not facing bottom, but the face bone still gets distorted 180 deg facing backwards.

Is there a solution to this also? Many thanks in advance

sorry mate. i cant help you there. that also is my problem ever since i started learning exporting unity models for use in MMD and the guide of litecheese?, i literally followed the step accurately A-Z without any jumps but it doesn't fix the model getting twisted once you apply the facial expression/animation other than getting correct standing pose (which i guess because you renamed the head, neck and position bones, the bone coordinates did not apply)

i theorized that during IQE>IQM>SMD export (then import), there's some jumbling of data or perhaps even bone coordinates which thus resulted to SMD import plug in of blender reading it wrong which then resulted to as we know it, distorted, twisted head model every time we apply the facial expression/anim.
## Post #196
- Username: MarioSonicU
- Rank: advanced
- Number of posts: 75
- Joined date: Fri Jun 26, 2015 6:26 am
- Post datetime: 2018-08-03T20:58:44+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Does anyone still have IQE Browser? ModDB Doesnot have the file
## Post #197
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2018-08-07T05:31:23+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from MarioSonicU
>
> Does anyone still have IQE Browser? ModDB Doesnot have the file

really? [https://www.moddb.com/mods/r-reinhard/a ... owser-v215](https://www.moddb.com/mods/r-reinhard/addons/iqebrowser-v215) you dont google well.
## Post #198
- Username: love8destiny
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 22, 2017 1:24 pm
- Post datetime: 2018-08-20T20:53:40+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

need help. using the script that cornal posted on page 2 to unpack legacy files, but it's throwing me back errors... none of the legacy files in the newest deresute update work in animexporter, they just give me a bundle null or index out of range. this is the error it gives me... anyone know how to fix? or another way to unpack/decompress the files so i can use them in animexporter? P.S. cgss_lz4 doesn't seem to work for me.   

EDIT: 
there doesn't seem to be a way to rip any usable deresute animations at the moment. the new unity studio update doesn't support the deresute animations, and neither does animexporter. if anyone knows a new method of ripping legacy files, please post it here
EDIT #2: the newest version of assetstudio supports animation ripping. i also found out a method of identifying motions of the solo songs; each solo song is listed in the 3000's and the last two digits correspond to the respective MASTER album (ex. 3d_cutt_an_chr_son3038_1.unity3d = himitsu no toilette animation, master 38)
## Post #199
- Username: Punzer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 08, 2018 12:19 pm
- Post datetime: 2018-10-09T10:24:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Damn I've got a long read ahead of me, hope the methods used still work, 'cause i've been looking to get a hold of these models (Especially Koume and Rina) for months and If I can get them myself that'd be the tops.
## Post #200
- Username: Sunochan17
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2018 11:06 am
- Post datetime: 2018-10-13T07:49:17+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I followed chrrox step by step for maintaining what I believe was the csv or the manifest through the emulator and fiddler with no luck. For some reason I can't get fiddler to pick up whats running on the emulator so I could get the latest manifest. I'm not too sure on what I'm doing wrong, I made sure to have the certificate downloaded and placed into the emulator as well. I've tried three separate times already with no luck. If anyone would be willing to help me and get me past the first step of extracting the models I would greatly appreciate it! (also I wouldn't mind some pointers on manifests and what to look for as well as efficient ways to maintain them. I'm more use to having the data and meshes readily available to just run in asset studio and then be done with it. So, this has definitely been quite the challenge to understand since it's relatively new to me. I would like to apologize if I come of as a bit annoying due to my complete lack of knowledge! with the proper guidance I'm sure ill get the hang of it!) Anyways back to what I was saying if you can help in any way even if its just a little bit of advice I would be very thankful!
## Post #201
- Username: Sunochan17
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2018 11:06 am
- Post datetime: 2018-10-13T21:36:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Sunochan17
>
> I followed chrrox step by step for maintaining what I believe was the csv or the manifest through the emulator and fiddler with no luck. For some reason I can't get fiddler to pick up whats running on the emulator so I could get the latest manifest. I'm not too sure on what I'm doing wrong, I made sure to have the certificate downloaded and placed into the emulator as well. I've tried three separate times already with no luck. If anyone would be willing to help me and get me past the first step of extracting the models I would greatly appreciate it! (also I wouldn't mind some pointers on manifests and what to look for as well as efficient ways to maintain them. I'm more use to having the data and meshes readily available to just run in asset studio and then be done with it. So, this has definitely been quite the challenge to understand since it's relatively new to me. I would like to apologize if I come of as a bit annoying due to my complete lack of knowledge! with the proper guidance I'm sure ill get the hang of it!) Anyways back to what I was saying if you can help in any way even if its just a little bit of advice I would be very thankful!
Okay so I've managed to get the manifest through the emulator instead of using fiddler to get it, although I'm not sure if I use the same url that was used as the code? I've tired exporting the response to run through asset studio and I even ran it in unity studio but it states 0 files are preset.
## Post #202
- Username: kotori 0912
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 26, 2018 10:10 am
- Post datetime: 2018-10-17T15:28:33+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

If you want get the resources of this game,maybe you can try 
CGSSAssetsDownloader
Github
[https://github.com/toyobayashi/CGSSAsse ... r/releases](https://github.com/toyobayashi/CGSSAssetsDownloader/releases)
You can download resources by name with this.
[20181017232456.jpg](https://xentaxbackup.github.io/file/15041_20181017232456.jpg)
## Post #203
- Username: kotori 0912
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 26, 2018 10:10 am
- Post datetime: 2018-10-17T15:33:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from kotori 0912
>
> If you want get the resources of this game,maybe you can try 
CGSSAssetsDownloader
Github
https://github.com/toyobayashi/CGSSAsse ... r/releases
You can download resources by name with this.

And could anyone tell me how to combine the head and the body.
I'm not good at deal with models.(only have unity and blender)
## Post #204
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2018-10-19T07:24:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from kotori 0912
>
> If you want get the resources of this game,maybe you can try 
CGSSAssetsDownloader
Github
https://github.com/toyobayashi/CGSSAsse ... r/releases
You can download resources by name with this.

umm how to use it? 
btw i tried to find background video (play on live game) here
did u know wut the file name?
## Post #205
- Username: kotori 0912
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 26, 2018 10:10 am
- Post datetime: 2018-10-19T13:21:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi
>
> kotori 0912 wrote:If you want get the resources of this game,maybe you can try 
CGSSAssetsDownloader
Github
https://github.com/toyobayashi/CGSSAsse ... r/releases
You can download resources by name with this.

umm how to use it? 
btw i tried to find background video (play on live game) here
did u know wut the file name?

you can open the manifest_10045900.db with SQliteDatabaseBrowser ,and export a .csv.
maybe like live_bg2d_bg_live_03.unity3d.
I'm not sure.
## Post #206
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2018-10-20T17:25:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from kotori 0912
>
> 
you can open the manifest_10045900.db with SQliteDatabaseBrowser ,and export a .csv.
maybe like live_bg2d_bg_live_03.unity3d.
I'm not sure.
i already knew how to use the sq method
i just wondering how to export using that unique method u show bcause it's seem like it's can export mp3
when i used the sq method i tried to export acb files but i got 404 when requesting from fiddler

btw "live_bg2d_bg_live_03.unity3d" is normal 2d pic
## Post #207
- Username: love8destiny
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 22, 2017 1:24 pm
- Post datetime: 2018-10-20T20:13:16+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

now than animexporter no longer works and assetstudio makes the animations look like crap, if anyone knows how to convert the unity3d legacy animations, please tell us
## Post #208
- Username: love8destiny
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 22, 2017 1:24 pm
- Post datetime: 2018-10-20T20:15:53+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi
>
> kotori 0912 wrote:
you can open the manifest_10045900.db with SQliteDatabaseBrowser ,and export a .csv.
maybe like live_bg2d_bg_live_03.unity3d.
I'm not sure.
i already knew how to use the sq method
i just wondering how to export using that unique method u show bcause it's seem like it's can export mp3
when i used the sq method i tried to export acb files but i got 404 when requesting from fiddler

btw "live_bg2d_bg_live_03.unity3d" is normal 2d pic

when downloading anything from the "live" tab it will show up in your mishiro folder mishiro\resources\assets\live
## Post #209
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2018-10-21T15:41:38+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from love8destiny
>
> 

when downloading anything from the "live" tab it will show up in your mishiro folder mishiro\resources\assets\live

i mean i don't know how to use the mishiro thing
how to open it? did i have to play/load game too?
## Post #210
- Username: grancia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 03, 2018 8:01 pm
- Post datetime: 2018-12-26T13:52:55+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I used animExport but the things that I can see is only a pink face in the all of clips.

How can I fix this?
[2018-12-26_03-22-37.png](https://xentaxbackup.github.io/file/15380_2018-12-26_03-22-37.png)
## Post #211
- Username: LiteCheese
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Tue Jun 27, 2017 2:54 am
- Post datetime: 2019-01-09T17:40:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from grancia
>
> I used animExport but the things that I can see is only a pink face in the all of clips.

How can I fix this?

Try opening the non-hq version vs the hq one. 
[https://imgur.com/a/xTc62yc](https://imgur.com/a/xTc62yc)
## Post #212
- Username: grancia
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 03, 2018 8:01 pm
- Post datetime: 2019-01-09T19:06:21+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from LiteCheese
>
> grancia wrote:I used animExport but the things that I can see is only a pink face in the all of clips.

How can I fix this?

Try opening the non-hq version vs the hq one. 
https://imgur.com/a/xTc62yc
It doesn't help me, hq version has same problem

[https://imgur.com/a/CZM6Cd5](https://imgur.com/a/CZM6Cd5)
## Post #213
- Username: banckiers
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 11, 2019 4:39 am
- Post datetime: 2019-01-13T02:46:28+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hi guys, help me, please ... could you send me a zip file of Kanzaki Ranko to work on a MMD video?
## Post #214
- Username: Sunochan17
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2018 11:06 am
- Post datetime: 2019-02-09T01:27:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hello everyone! I was wondering if anyone knew if the textures for the customizable outfit are in the files? I've been looking around for awhile with no luck, and I'm just not sure so I figured I would ask in case someone else had information on it.
## Post #215
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-04-15T16:49:14+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

i forgot to ask, to the pros here, how do you convert CGSS motion (like the dance movements) to something that is readable by MMD? was it the same with the face morphs?
## Post #216
- Username: digitalboyz
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Jun 18, 2012 3:58 am
- Post datetime: 2019-04-21T08:21:43+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I have try to import latest data file using AnimExport but seem program cant read file.

[](https://imgbb.com/)
## Post #217
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-22T09:54:17+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

it's seem like the sq lite ask for key when load manifest
i can't rip anymore
i try to download old file in fiddler but it was key too
any solution?
[Screenshot (31).png](https://xentaxbackup.github.io/file/16275_Screenshot (31).png)
## Post #218
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T02:33:02+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi ↑Wed May 22, 2019 5:54 pm at Wed May 22, 2019 5:54 pm
>
> 
it's seem like the sq lite ask for key when load manifest
i can't rip anymore
i try to download old file in fiddler but it was key too
any solution?

i dont know if i understand you correctly but if you are trying to rip the manifest file to obtain that table to download the models, you can easily get it in your deresute folder assuming you installed the game on  your phone. rename it to imas.sqlite then load it to sqlite browser, export the manifest table to csv. and you are good to go.

that said, it seems like bamco also changed the location of the 3d models too because i cant download any models  using the automated imas model downloader phyton script that can be downloaded somewhere here in this thread.
## Post #219
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-26T06:19:01+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> i dont know if i understand you correctly but if you are trying to rip the manifest file to obtain that table to download the models, you can easily get it in your deresute folder assuming you installed the game on  your phone. rename it to imas.sqlite then load it to sqlite browser, export the manifest table to csv. and you are good to go.
>
> 
>
> that said, it seems like bamco also changed the location of the 3d models too because i cant download any models  using the automated imas model downloader phyton script that can be downloaded somewhere here in this thread.

Yeah that's wut i done b4
Which one is deresute folder? The "d" folder? If so, in the "d" folder has "LocalData.db", I view it in sqlite and then csv ed, it's seem like no hash to look at... Just weird random character/word
## Post #220
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T06:45:25+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi ↑Sun May 26, 2019 2:19 pm at Sun May 26, 2019 2:19 pm
>
> 

Yeah that's wut i done b4
Which one is deresute folder? The "d" folder? If so, in the "d" folder has "LocalData.db", I view it in sqlite and then csv ed, it's seem like no hash to look at... Just weird random character/word

look for the [manifest] folder. it contain a file that has a name of jumbled letters and numbers that would be the file you want.
## Post #221
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-26T07:23:10+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> look for the [manifest] folder. it contain a file that has a name of jumbled letters and numbers that would be the file you want.

The manifest? Well that was the method i used b4 ;v;
The manifest won't work anymore   
It asked for password
## Post #222
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T08:06:46+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi ↑Sun May 26, 2019 3:23 pm at Sun May 26, 2019 3:23 pm
>
> 

look for the [manifest] folder. it contain a file that has a name of jumbled letters and numbers that would be the file you want.


The manifest? Well that was the method i used b4 ;v;
The manifest won't work anymore   
It asked for password

Huh really? It is working for me today since i am ripping the new SSR models 

. 1 rename file to imas.sqlite - 2 load the file to SQLite DBrowser - 3 export manifest to csv.

If that still doesnt work download - mishiro in github the rest is easy ifyou know what you are doing
## Post #223
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-26T08:58:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Huh really? It is working for me today since i am ripping the new SSR models 
>
> 
>
> . 1 rename file to imas.sqlite - 2 load the file to SQLite DBrowser - 3 export manifest to csv.
>
> 
>
> If that still doesnt work download - mishiro in github the rest is easy ifyou know what you are doing

May i know what ver ur sq lite?
Do u  have any tutorial link for mishiro btw?
## Post #224
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T09:20:06+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi ↑Sun May 26, 2019 4:58 pm at Sun May 26, 2019 4:58 pm
>
> 
 
Huh really? It is working for me today since i am ripping the new SSR models 

. 1 rename file to imas.sqlite - 2 load the file to SQLite DBrowser - 3 export manifest to csv.

If that still doesnt work download - mishiro in github the rest is easy ifyou know what you are doing


May i know what ver ur sq lite?
Do u  have any tutorial link for mishiro btw?

1. ver 3.11.2 or the latest one downloaded from their official site

2. none mate but it is really easy that you dont really need a tutorial. all you need is the open_dress_id from the raw data tablefrom starlight kirara and search that number in mishiro.
## Post #225
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-26T09:27:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> 1. ver 3.11.2 or the latest one downloaded from their official site
>
> 
>
> 2. none mate but it is really easy that you dont really need a tutorial. all you need is the open_dress_id from the raw data tablefrom starlight kirara and search that number in mishiro.

When i open mishiro
It give me error ;v;
[Screenshot (34).png](https://xentaxbackup.github.io/file/16285_Screenshot (34).png)
## Post #226
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T09:58:04+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

sorry mate cant help you there... i didnt see that error when i run mishiro. all i can do is maybe send you the manifest.csv (updated as of today)
[https://megaupload.nz/Scd4Tdsan5/manifests_csv](https://megaupload.nz/Scd4Tdsan5/manifests_csv)
## Post #227
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-26T10:37:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

really thanks for the csv!
but do u have problem when request the file in fiddler? that's my problem from the beginning ;v;
it's show key instead of download the file
[Screenshot (35).png](https://xentaxbackup.github.io/file/16286_Screenshot (35).png)
## Post #228
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T11:10:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Hoshi ↑Sun May 26, 2019 6:37 pm at Sun May 26, 2019 6:37 pm
>
> 
really thanks for the csv!
but do u have problem when request the file in fiddler? that's my problem from the beginning ;v;
it's show key instead of download the file

well i dont know mate... i have been using that file in manifest folder since fiddling in fiddler is tedious and a lot needs to be done before getting to the good stuff. but anyway, enjoy ripping.
## Post #229
- Username: BlackCandleMass
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 25, 2019 10:14 am
- Post datetime: 2019-05-26T18:44:35+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hey I'm in need of help but my knowledge is limited, I've used mishiro to download some assets, like 3d_chara_head_0243_hq.unity3d however I'm not sure what to do from there. I'm not sure if I'm missing something or misusing the tools I've tried, I've tried using quick BMS with and without the Cinderella script but I always get errors, CGSS LZ4 also gives me errors then CTD. The only tool I've been able use to extract files the .unity3d files I've got is asset studio, when finished I get alot of folders with .dat files a .file, a .ress and no .assets (is this normal) I did manage to extract a .fbx and 2 .obj One more thing UBAE doesn't crash but I'm not sure how use it, I'm assuming you need a asset bundle. Which I don't have.

Also a quick question should the head model have bones? I've imported the .fbx it contained three meshes I was able to get into blender, however it has no bones or weight. I can post screenshots of anything if needed.
## Post #230
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-26T23:59:54+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from BlackCandleMass ↑Mon May 27, 2019 2:44 am at Mon May 27, 2019 2:44 am
>
> 
Hey I'm in need of help but my knowledge is limited, I've used mishiro to download some assets, like 3d_chara_head_0243_hq.unity3d however I'm not sure what to do from there. I'm not sure if I'm missing something or misusing the tools I've tried, I've tried using quick BMS with and without the Cinderella script but I always get errors, CGSS LZ4 also gives me errors then CTD. The only tool I've been able use to extract files the .unity3d files I've got is asset studio, when finished I get alot of folders with .dat files a .file, a .ress and no .assets (is this normal) I did manage to extract a .fbx and 2 .obj One more thing UBAE doesn't crash but I'm not sure how use it, I'm assuming you need a asset bundle. Which I don't have.

Also a quick question should the head model have bones? I've imported the .fbx it contained three meshes I was able to get into blender, however it has no bones or weight. I can post screenshots of anything if needed.

after downloading the model files from mishiro, load it to asset studio(file>load folder), export all ojects (in model tab in file menu) and you will get an FBX.... import the fbx to your 3d software of your choice (in my case blender). do the same to head part (if you export the body part first and vice versa). the tedious part is recombining the head and body part by aligning the bones and joining them to one, adding the texture for the body (head file already have its texture). if you plan to use it on MMD, you will need MMD tools though.

and yep, head model do have bones the same with body. i think the weight and other stuffs needs to be "reprogrammed" back since assets studio dont export those to the FBX

anyway my knowledge is limited too and my answers are mostly based from my current level of experience.
## Post #231
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-27T15:03:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

EDIT: looks like asset studio can do the work that animexport does. i can easily apply morphs now... now will try to convert the dance anims
## Post #232
- Username: BlackCandleMass
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat May 25, 2019 10:14 am
- Post datetime: 2019-05-28T06:22:03+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hey Aegis did you select the animator and an animation clip in asset studio? That appears to be the only way I extract them, which seems like it'll be fine for what I had in mind however it is time consuming, so if you find another way please let us know.

Good luck with extracting the dance animations
## Post #233
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-28T09:59:57+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from BlackCandleMass ↑Tue May 28, 2019 2:22 pm at Tue May 28, 2019 2:22 pm
>
> 
Hey Aegis did you select the animator and an animation clip in asset studio? That appears to be the only way I extract them, which seems like it'll be fine for what I had in mind however it is time consuming, so if you find another way please let us know.

Good luck with extracting the dance animations

yes i did that. [and to extract all anim clips, it seems like you can select all of it and extract them together with the animator and you will end up with, in my case with miria akagi cinfest, 4.1-ish MB fbx file. load that in blender and do the steps in adding the morphs. <<<< scratch this... still finding how to batch add anim clips other than doing it one by one]

as to the dance anims, load the md_body model file of the SSR you want, and the an_chr_son of the dance you want then in aasset list, select the animator of the md_body and the animation clip of the an_chr_son and extract it.  and  you will get a fbx file containing the body model with the dance anim. once you got the fbx, you know what to do.
## Post #234
- Username: Hoshi
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Dec 28, 2016 1:40 am
- Post datetime: 2019-05-29T10:49:42+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

nvm find the fix already=edit=
## Post #235
- Username: Aegis
- Rank: beginner
- Number of posts: 30
- Joined date: Mon Jan 15, 2018 12:08 pm
- Post datetime: 2019-05-29T16:21:48+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

damn a brick wall... tried exporting the dance anim to MMD but when played it looks ridiculous. reloaded it back to blender, and the anim is really wrong. there must be sort of issue in mmd_tools during export but i dont know i must be doing it wrong.

FIXED --- steps how to fix the dance anim, can be found here [https://github.com/powroupi/blender_mmd ... -497182752](https://github.com/powroupi/blender_mmd_tools/issues/223#issuecomment-497182752)
## Post #236
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2019-07-31T23:26:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Aegis ↑Sun May 26, 2019 5:58 pm at Sun May 26, 2019 5:58 pm
>
> 
sorry mate cant help you there... i didnt see that error when i run mishiro. all i can do is maybe send you the manifest.csv (updated as of today)
https://megaupload.nz/Scd4Tdsan5/manifests_csv

could someone upload this csv on a site other than megaupload? i cant access this site as of 7/31/19 ;;
## Post #237
- Username: mbugle
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 25, 2012 8:18 am
- Post datetime: 2019-09-10T15:07:28+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hey, i have been downloading assets with mishiro and have had success in getting models into 3dsmax. Is there a tool to download models from Idolmaster million live as i would love models from this game. i see there are ways to download the files with python if you have a manifest file but I'm not familiar with using python scripts and I'm struggling to find a step by step guide. Any help would be much appreciated,
mbugle
## Post #238
- Username: argkendo
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed May 22, 2019 7:50 am
- Post datetime: 2019-09-21T15:21:12+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Hello everyone, I obtained the assets following a step-by-step tutorial published in a post made by the user "chroxx" ([viewtopic.php?f=29&t=16055](https://forum.xentax.com/viewtopic.php?f=29&t=16055)).

Then I used the AssetStudio application (v0.13.24) to extract the assets.

Then I exported all the assets obtaining several folders, one of them called "Animators" in which all the models were in ".fbx" format.

I have used Blender to see the models, but the morphs did not load or do not work (I use to mention that my knowledge in 3D editing programs is very basic). Does anyone have any idea why this happens or if it is an error?



Blender.png (234.14 KiB) Viewed 321 times



I read in this post that the user "akderebur" created an application (AnimExporter) with which it is possible to create morphs with facial expressions that is basically what interests me. Unfortunately I did not understand how to make it work with the assets I obtained. Could someone do a step-by-step tutorial?

I know that a user "Lite Chesse" made a small tutorial on how to extract facials using the application AnimExporter ([https://imgur.com/a/XQZnV](https://imgur.com/a/XQZnV)), unfortunately I did not understand it since it is not specific in some matters.
## Post #239
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2019-09-22T23:40:50+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

How to make face expressions work on model. (Blender only.) When you finish face expressions will be writed as shape keys and you can you they in every prog.

1.Download Utiny ripper, extract all assets from model.unity3d file.
2.Open Unity load your face model with avatar, load animation clips on avatar.
3.Use Unity exporter addon to export your model with animation clips and export it.
4.Download Blender and CATS BLENDER TOOLS for blender.
5.Import model exported from Unity to Blender.
6.Transfer bone pose into shape keys with CATS BLENDER feature. Caution: Animation does not work properly, bones are just do face pose on the 1-st frame or it can be 0 frame (random for me).
So you just, transfer bone pose into the shape key or whatever you need and do rest position and rotation on 0 frame of animation.
And you you with all animation clips which you need.
Technically that is all what you need to do to make FaceExpressions to work.

You can add me in discord if you have a question. "Cyan Blue#9804"
## Post #240
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2019-09-22T23:45:46+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Here is an example of some facial poses made using this method:
## Post #241
- Username: Shineruze
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 01, 2019 2:32 pm
- Post datetime: 2019-10-06T05:00:53+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

How to import animations with the assetstudio to extract a useful file? in order that I can manipulate it in blender, because there is a file with the extension .dat.
I already read this post, but they have already changed the version of unity that the game uses and also the tools have changed
## Post #242
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2019-10-06T22:08:20+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from Shineruze ↑Sun Oct 06, 2019 1:00 pm at Sun Oct 06, 2019 1:00 pm
>
> 
How to import animations with the assetstudio to extract a useful file? in order that I can manipulate it in blender, because there is a file with the extension .dat.
I already read this post, but they have already changed the version of unity that the game uses and also the tools have changed

Use Mishiro to download models, textures, animations. 
And Unity Asset Studio can't export animations as fbx.
## Post #243
- Username: gloomymood
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 18, 2019 2:27 pm
- Post datetime: 2019-11-30T21:59:59+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Pretty new to this, just throwing it out there in case anyone knows.

I have seen a few videos of a seemingly modded Deresute, like having all 5 idols being the same (might have been a clever edit) or having an entirely different body mesh (seemed legit). Is it possible to identify the DATA files, let alone repack your own in a way that is compatible? That seems like a brick wall for me.
## Post #244
- Username: kitakamikotoha
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 28, 2018 8:59 pm
- Post datetime: 2020-01-12T11:40:15+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from pechenuxa ↑Mon Oct 07, 2019 6:08 am at Mon Oct 07, 2019 6:08 am
>
> 
Shineruze wrote: ↑Sun Oct 06, 2019 1:00 pm
How to import animations with the assetstudio to extract a useful file? in order that I can manipulate it in blender, because there is a file with the extension .dat.
I already read this post, but they have already changed the version of unity that the game uses and also the tools have changed


Use Mishiro to download models, textures, animations. 
And Unity Asset Studio can't export animations as fbx.

Asset Studio can export animations, open the FBX file in noesis and check. 

Anyone has ways to extract Msute models other than this: [https://github.com/starjet/Msute_Cst](https://github.com/starjet/Msute_Cst) or copying files from the game directly (I don't play that game)? That tool doesn't seem to be updated for over a year and all I get from it are 403 errors even though I have the right baseURL.

EDIT: NVM I found the direct URLs in Resource-urls.txt. It means I can download the models directly from the server.
## Post #245
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2020-01-15T14:34:56+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

For me asset studio is not exporting animations with model, do not download the newer version of utinyripper, cause it breaking models, download older builds estimated on june-august of 2019.
## Post #246
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2020-01-15T15:28:37+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Also how to find animations for dances on mishiro? 
I mean which id for which song?
If someone has have animations link for them will be appreciated.
## Post #247
- Username: bd6761
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Oct 24, 2017 2:53 pm
- Post datetime: 2020-01-24T05:15:30+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from pechenuxa ↑Mon Sep 23, 2019 7:40 am at Mon Sep 23, 2019 7:40 am
>
> 
How to make face expressions work on model. (Blender only.) When you finish face expressions will be writed as shape keys and you can you they in every prog.

1.Download Utiny ripper, extract all assets from model.unity3d file.
2.Open Unity load your face model with avatar, load animation clips on avatar.
3.Use Unity exporter addon to export your model with animation clips and export it.
4.Download Blender and CATS BLENDER TOOLS for blender.
5.Import model exported from Unity to Blender.
6.Transfer bone pose into shape keys with CATS BLENDER feature. Caution: Animation does not work properly, bones are just do face pose on the 1-st frame or it can be 0 frame (random for me).
So you just, transfer bone pose into the shape key or whatever you need and do rest position and rotation on 0 frame of animation.
And you you with all animation clips which you need.
Technically that is all what you need to do to make FaceExpressions to work.

You can add me in discord if you have a question. "Cyan Blue#9804"

>2.Open Unity load your face model with avatar, load animation clips on avatar.
>3.Use Unity exporter addon to export your model with animation clips and export it.

Please describe this 2 steps with pictures,I'm not really understand.
I didn't use Unity before.
## Post #248
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2020-01-25T06:02:14+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from bd6761 ↑Fri Jan 24, 2020 1:15 pm at Fri Jan 24, 2020 1:15 pm
>
> 
pechenuxa wrote: ↑Mon Sep 23, 2019 7:40 am
How to make face expressions work on model. (Blender only.) When you finish face expressions will be writed as shape keys and you can you they in every prog.

1.Download Utiny ripper, extract all assets from model.unity3d file.
2.Open Unity load your face model with avatar, load animation clips on avatar.
3.Use Unity exporter addon to export your model with animation clips and export it.
4.Download Blender and CATS BLENDER TOOLS for blender.
5.Import model exported from Unity to Blender.
6.Transfer bone pose into shape keys with CATS BLENDER feature. Caution: Animation does not work properly, bones are just do face pose on the 1-st frame or it can be 0 frame (random for me).
So you just, transfer bone pose into the shape key or whatever you need and do rest position and rotation on 0 frame of animation.
And you you with all animation clips which you need.
Technically that is all what you need to do to make FaceExpressions to work.

You can add me in discord if you have a question. "Cyan Blue#9804"


>2.Open Unity load your face model with avatar, load animation clips on avatar.
>3.Use Unity exporter addon to export your model with animation clips and export it.

Please describe this 2 steps with pictures,I'm not really understand.
I didn't use Unity before.

I don’t want to explain how to import assets into Unity, I don’t have to teach you how to use Unity.
## Post #249
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-04-02T13:04:30+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from pechenuxa ↑Mon Sep 23, 2019 7:40 am at Mon Sep 23, 2019 7:40 am
>
> 
How to make face expressions work on model. (Blender only.) When you finish face expressions will be writed as shape keys and you can you they in every prog.

1.Download Utiny ripper, extract all assets from model.unity3d file.
2.Open Unity load your face model with avatar, load animation clips on avatar.
3.Use Unity exporter addon to export your model with animation clips and export it.
4.Download Blender and CATS BLENDER TOOLS for blender.
5.Import model exported from Unity to Blender.
6.Transfer bone pose into shape keys with CATS BLENDER feature. Caution: Animation does not work properly, bones are just do face pose on the 1-st frame or it can be 0 frame (random for me).
So you just, transfer bone pose into the shape key or whatever you need and do rest position and rotation on 0 frame of animation.
And you you with all animation clips which you need.
Technically that is all what you need to do to make FaceExpressions to work.

You can add me in discord if you have a question. "Cyan Blue#9804"

will animation exported from "3d_cutt_an~" work on their face after these process? or still need some other works? thx
## Post #250
- Username: pechenuxa
- Rank: beginner
- Number of posts: 27
- Joined date: Tue Dec 11, 2018 2:47 am
- Post datetime: 2020-04-02T16:44:00+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I think it will work only if you didn't change something in model skeleton.
## Post #251
- Username: wansf
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Mar 11, 2018 5:56 pm
- Post datetime: 2020-04-02T16:55:38+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

wow thats great to hear thx for ur quick reply 
gonna try it right now

edit : meh seems 3d_cutt dun store any face animation
## Post #252
- Username: Pokegirlsky
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Apr 17, 2020 10:52 am
- Post datetime: 2020-04-17T18:03:01+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

So I've been spending the past few days trying to learn everything I can from this thread. I want to get the dance animations from the game into MMD as a VMD file. At this point I am able to export models into MMD as a PMX but any animation that seem to be with them in noesis never shows up once i load the FBX version of the model into Blender. So I can't export the animation as a VMD if there's no animation showing. 

I'm fairly new to a lot of this, so simple step by step instructions would be nice. Thank you ^^
## Post #253
- Username: chibbers
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Apr 27, 2020 11:32 am
- Post datetime: 2020-04-27T03:36:32+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I have run into an issue. I exported the fbx file into blender just fine but it has no bones or any such other then the model itself and texture for me to port it to mmd/pmd editor if anyone can say what i possibly did wrong or a way to fix this it would help! im a kinda newbie to this stuff and am trying my best to learn as i go!.
## Post #254
- Username: Bapho
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Mar 01, 2020 3:05 am
- Post datetime: 2020-06-24T13:41:48+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from pechenuxa ↑Mon Sep 23, 2019 7:40 am at Mon Sep 23, 2019 7:40 am
>
> 
How to make face expressions work on model. (Blender only.) When you finish face expressions will be writed as shape keys and you can you they in every prog.

1.Download Utiny ripper, extract all assets from model.unity3d file.
2.Open Unity load your face model with avatar, load animation clips on avatar.
3.Use Unity exporter addon to export your model with animation clips and export it.
4.Download Blender and CATS BLENDER TOOLS for blender.
5.Import model exported from Unity to Blender.
6.Transfer bone pose into shape keys with CATS BLENDER feature. Caution: Animation does not work properly, bones are just do face pose on the 1-st frame or it can be 0 frame (random for me).
So you just, transfer bone pose into the shape key or whatever you need and do rest position and rotation on 0 frame of animation.
And you you with all animation clips which you need.
Technically that is all what you need to do to make FaceExpressions to work.

You can add me in discord if you have a question. "Cyan Blue#9804"

I could get one animation as a shapekey, but i don't understand how you got multiple to work
## Post #255
- Username: LeonaWest
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 11, 2020 10:59 am
- Post datetime: 2020-07-11T03:16:05+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

I got the motion of the body, but I can't get the motion of the face.
The motion of the face when singing.
In what file is it stored?
## Post #256
- Username: garamika
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue May 09, 2017 4:29 pm
- Post datetime: 2020-07-14T13:46:45+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

It seems that not the "3d_an_cutt_~~~" file stores the facials but the unity3d file with the name of the song stores the  facials, cameras, and stage light informations - like the ones in scrobj file in MLTD. Yet theres a long way to parse the file so that can be translated into vmd file.
## Post #257
- Username: LeonaWest
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Jul 11, 2020 10:59 am
- Post datetime: 2020-07-16T14:31:39+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Do you know how to do that? I would appreciate it if you could share the method.
## Post #258
- Username: duckhime
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 03, 2020 9:30 am
- Post datetime: 2020-08-04T04:27:57+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

> Reply from pechenuxa ↑Mon Sep 23, 2019 7:40 am at Mon Sep 23, 2019 7:40 am
>
> 
How to make face expressions work on model. (Blender only.) When you finish face expressions will be writed as shape keys and you can you they in every prog.

1.Download Utiny ripper, extract all assets from model.unity3d file.
2.Open Unity load your face model with avatar, load animation clips on avatar.
3.Use Unity exporter addon to export your model with animation clips and export it.
4.Download Blender and CATS BLENDER TOOLS for blender.
5.Import model exported from Unity to Blender.
6.Transfer bone pose into shape keys with CATS BLENDER feature. Caution: Animation does not work properly, bones are just do face pose on the 1-st frame or it can be 0 frame (random for me).
So you just, transfer bone pose into the shape key or whatever you need and do rest position and rotation on 0 frame of animation.
And you you with all animation clips which you need.
Technically that is all what you need to do to make FaceExpressions to work.

You can add me in discord if you have a question. "Cyan Blue#9804"

for those having trouble with steps 2-3:

my alternate method for steps 2-3 is very tedious but should work with CATS' shape key creator

1) open 3d_chara_head_xxxx_xxxx_hq.unity3d in AssetStudio
2) under Asset List, ctrl click the AnimationClip (shape key, face expression) you wish to export and the Animator (md_chrxxxx_xxxx_hq)
3) Export > Animator + selected AnimationClips
4) rename .fbx whatever you want (i did the clip names, so mouth_e, eyeL_close, etc)
5) delete remaining files (textures) and repeat with each AnimationClip you want exported

then you can import into blender and copy the bone pose to your main model and save as a shape key with CATS
## Post #259
- Username: SHIBAJA
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Jan 08, 2021 10:58 pm
- Post datetime: 2021-01-08T15:39:18+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

new guy here, been browsing the forum for a while.

I found this site that sells deresute accs with a 3d model viewer, but sadly it only works for pre-2018 SSRs. 
using F12 you can see the textures and the site fetching everything from a database.



chrome_g4Tlxua1p2.png (183.96 KiB) Viewed 381 times


wonder if its possible to import them, though i dont think they'll serve much use since no animation data exists.

note the website is in thai
[https://deresute.4th.in/#cardTable](https://deresute.4th.in/#cardTable)
## Post #260
- Username: kitakamikotoha
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Wed Mar 28, 2018 8:59 pm
- Post datetime: 2021-12-05T08:38:23+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Thread's dead. Necro-ing it for the new games Starlit Season & SideM GROWING STARS.
## Post #261
- Username: Dinoguy1000
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2021-12-12T09:09:27+00:00
- Post Title: Re: Idolmaster (DereSte) 3d site

Topic locked; we don't support ripping from websites (see the rules). This thread may disappear at some point too.

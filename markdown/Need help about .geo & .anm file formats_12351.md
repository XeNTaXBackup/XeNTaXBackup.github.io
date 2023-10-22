## Post #1
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2014-12-08T11:47:04+00:00
- Post Title: Need help about .geo & .anm file formats

Hi All,

Congrats to Xentax for completing 25 years, here's to 50 more years  
Thanks a lot Mr. Mouse for letting to join Xentax for free & for giving MultiEx Commander for free.  

I don't have knowledge like a lot of the guys, but I'm learning from here.

I would request for some help in understanding & possibly converting the .geo & .anm file formats. The tools 
available on internet for these files are not of any help. 
The files can be found here 
[http://www.4shared.com/archive/x4mtHrAk ... urity.html](http://www.4shared.com/archive/x4mtHrAkba/tocado_security.html)

Any help will be highly appreciated.

Regards,
Saurav
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-08T13:00:29+00:00
- Post Title: Need help about .geo & .anm file formats

hi,
I won't download from 4shared, sry.

There are many other uploaders ([http://www.uploadmb.com/](http://www.uploadmb.com/) for example)
who don't require providing personal data.
## Post #3
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2014-12-08T17:02:59+00:00
- Post Title: Need help about .geo & .anm file formats

Hi shakotay2,

I've uploaded the files here 
[http://www.uploadmb.com/dw.php?id=1418057750](http://www.uploadmb.com/dw.php?id=1418057750)

Shame I didn't know about it.   

Regards,
Saurav
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-08T20:35:05+00:00
- Post Title: Need help about .geo & .anm file formats

thx, not a problem.  

I tried out 2 Noesis plugins from finale00 but they were not suiting for this game's .geo files.

This is the result using hex2obj (view link in my sig):



npc_tocado_sec.jpg (157.33 KiB) Viewed 303 times


I handled the first submesh only.
Not sure about the uv data.
---------------

The second submesh (body) has other parameters (vertex block size=44), uvs o.k.
Copy the following 6 lines into an empty textfile and save it as body.H2O or similar. Then load it into hex2obj.
0x4FAF 2484
Vb1
44 36
0x635B 670
020000
0x0 255
## Post #5
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-09T10:23:17+00:00
- Post Title: Need help about .geo & .anm file formats

Hi 

Here is model and animation in fbx format.
Models are low poly and use LODs and maybe shadow meshes.

Animations use quaternions for rotation. Each animation bone key is relativ to its parent.

What name is game?
[model.zip](https://xentaxbackup.github.io/file/8228_model.zip)
## Post #6
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2014-12-14T17:32:12+00:00
- Post Title: Need help about .geo & .anm file formats

Hi Szkaradek123 & shakotay2,

Sorry i couldn't reply earlier as I was busy with job   
Thanks for your help guys   

@shakotay2
I downloaded Hex2obj v0.2x, followed your steps, but got an error "Error : more than 4 numerals in H2O's codestring!"
How did u load the model in hex2obj ?

@Szkaradek123
The fbx files run fine in 3ds max 2012, but I need to understand the .geo & .anm file formats first.
What did u use to convert the models ?
The sample files are from a long dead MMO Auto assault.Another dead MMO Tabula Rasa also uses the same formats.

Thanks again for your help guys.

Regards,
Saurav
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-14T18:39:19+00:00
- Post Title: Need help about .geo & .anm file formats

check your H2O file for typos (not required if you copyPasted from my previous post)
(The 'b' of 'Vb' has to be lower case)

Load npc_m_f_tocado-security.geo into hex2obj (v0.23)
copy H2O to model folder
then File Open H2O
press mesh button
## Post #8
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2014-12-15T07:45:16+00:00
- Post Title: Need help about .geo & .anm file formats

Hi shakotay2,

Success man!!   Here's the proof



tocado security.bmp (192.12 KiB) Viewed 247 times



The model is damn low poly!! 

This brings up two questions.
1st, there are 2 models in the .geo file. How to separate them ? Is it required ?
2nd, do I need to create .h2o file for every .geo file ? If yes, that's a hell lot of work for 28307 .geo files !!

Regards,
Saurav
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-15T10:30:35+00:00
- Post Title: Need help about .geo & .anm file formats

> Reply from saurav
>
> The model is damn low poly!!Hi saurav, how does it look ingame?
If it's much better there you'd to search for a high poly .geo.
There's a LOD with 1963 vertices:
0x19206 8373
Vb1
36 99
0x1D3B0 1963
020000
0x0 255

At offset 24 of the vertex block there are normals.
The uvs are in the LOD of my post of Dec. 8th:



npc_m_f_tocado-security_uvs.jpg (116.03 KiB) Viewed 233 times



> This brings up two questions.
>
> 1st, there are 2 models in the .geo file. How to separate them ? Is it required ?
I found 
0x2EA05 4185
Vb1
36 99
0x30AF7 1000
020000
0x0 255

and

0x399E5 2082
Vb1
36 99
0x3AA69 500
020000
0x0 255

There might be even more. Search for LODLevel to find more LOD models.
The model should start some bytes after XDNI.

> 2nd, do I need to create .h2o file for every .geo file ? If yes, that's a hell lot of work for 28307 .geo files !!
You'll have to change startaddresses and counts for go1 and go3, yes.
Also there seem to exist three vertex block sizes: 32, 36 and 44 bytes

hex2obj is a helper tool only for a quick start.

Once you know the format it makes sense to create a maxscript for example.

edit: well, seems Mariusz saved that problem while I was editing this post.
## Post #10
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-15T11:04:14+00:00
- Post Title: Need help about .geo & .anm file formats

Hi
This format is complex.

I use game Auto Assault .

trial: [http://www.gamershell.com/search/?q=Auto+Assault](http://www.gamershell.com/search/?q=Auto+Assault)
unpacker for glm : [http://int0thegame.blogspot.com/2007/12 ... l-v10.html](http://int0thegame.blogspot.com/2007/12/tabula-rasa-ncsoft-glm-tool-v10.html)

Here is a importer for geometry and animation.
It don't works with all files .

It requires Blender 249 and Python 26.

Steps:
1.unpack importer
2.run Blender249.blend
3.in Blender Text Window press alt+p
3.select geo files for model and skeleton 
4.select anm files for animation
[Blender249[AutoAssault][geo][anm][2014-12-15].zip](https://xentaxbackup.github.io/file/8272_Blender249[AutoAssault][geo][anm][2014-12-15].zip)
## Post #11
- Username: saurav
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Nov 22, 2014 12:19 am
- Post datetime: 2014-12-21T11:47:31+00:00
- Post Title: Need help about .geo & .anm file formats

Hi shakotay2 & Szkaradek123,
Thanks a lot for your help.Lots of bear hugs & beers to u guys !!  

@ shakotay2 
Sorry I don't have a way to check that since the game is long dead.The models look low poly even in blender. 
I tried to compare the ,geo file format with .bip since the .geo files contains words like bip,leg,neck etc but failed to make any progress.I'm looking into it more closely. 
What do the different vertex block sizes mean ?

@ Szkaradek123
Thanks for the links but I already have the client & unpacker before joining. 
The scripts work fine for biped models, but gives errors for some vehicle models, like "memoryError" or "bone_<name> not found".
And what to do with the log files generated by blender for the models ?

I have attached the files that can't be opened in blender. Request you to please have a look at them/

Regards,
Saurav
[AAprobmodel.rar](https://xentaxbackup.github.io/file/8321_AAprobmodel.rar)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-22T22:26:03+00:00
- Post Title: Need help about .geo & .anm file formats

> Reply from saurav
>
> What do the different vertex block sizes mean ?different sizes just mean different data to be contained. Main aspect for me is that the position of the uv data might be different.

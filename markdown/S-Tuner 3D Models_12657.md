## Post #1
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2015-03-02T06:43:51+00:00
- Post Title: S-Tuner 3D Models

Hi all! I've exported the 3d model from S-Tuner Car Builder, but I can't import or open it in any editor.
Model file having a extension .3dm and a header "3dmv002lb". I tried convert the model with Hex2Obj, but I can't understand how this tool works. I used Google, but I can't receive any result. In older versions of this car builder 3dm files having a another format (obj file crypted with base64), but in new versions format has changed.
Please help me, some models from this car builder very exclusive.
I will publish the link to the exported model there (I can't attach the file, his size bigger than 256 KiB). 3dt file this is just a zip archive with 3dm file (model), mtl file (materials tab), con file (coordinates of some parts), and screenshot of the model. I also attach the Builder application, may be forum programmers can decompile this and take the code... I don't know.
Sorry for my mistakes in text, I'll still learning English.

Builder: [https://drive.google.com/file/d/0B41fB9 ... sp=sharing](https://drive.google.com/file/d/0B41fB90jbip1SkdqQWNWYjAzNlk/view?usp=sharing)
Example 3D Model: [https://drive.google.com/file/d/0B41fB9 ... sp=sharing](https://drive.google.com/file/d/0B41fB90jbip1VTBlYlZMXzRCYXc/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-03-02T10:06:43+00:00
- Post Title: S-Tuner 3D Models

> Reply from NFSModDev
>
> I tried convert the model with Hex2Obj, but I can't understand how this tool works.You can't use hex2obj on an encoded/encrypted/whatever file!

There are ten thousands of "XNS" (for example) in the export.3dm

Search for model data in your browsers cache. That's how I would do it.

> Please help me, some models from this car builder very exclusive.yeah! That's the reason why they try to protect their intellectual property. (Guess you'll have to pay some bucks to get a model, don't you?)
## Post #3
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-03-02T18:47:57+00:00
- Post Title: S-Tuner 3D Models

I researched this format on ZenHAX a while ago. It's just a Wavefront OBJ file with some basic encryption. here's the QuickBMS script I made for unpacking it:

```

encryption math "-= 10"
comtype base64

get NAME basename
string NAME += ".obj"

get ZSIZE asize
math ZSIZE -= 7

idstring "3dmv002"

clog NAME 7 ZSIZE ZSIZE
```
## Post #4
- Username: Mike Oxmaul
- Rank: n00b
- Number of posts: 15
- Joined date: Fri Dec 05, 2014 9:54 pm
- Post datetime: 2015-03-02T20:04:05+00:00
- Post Title: S-Tuner 3D Models

> Reply from shakotay2
>
> Search for model data in your browsers cache
The cache contains some files, and I successfully copied and imported models. But search a single model file into a cache dir with 4500+ files = suicide 
barti, i have the error...

```
Error: unsupported encryption/hashing type (math)
```
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2015-03-02T20:19:31+00:00
- Post Title: S-Tuner 3D Models

> Reply from NFSModDev
>
> 
barti, i have the error...
Code: Select allError: unsupported encryption/hashing type (math)

Update your QuickBMS.
## Post #6
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2016-05-26T02:55:45+00:00
- Post Title: S-Tuner 3D Models

> Reply from barti
>
> NFSModDev wrote:
barti, i have the error...
Code: Select allError: unsupported encryption/hashing type (math)

Update your QuickBMS.
## Post #7
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2016-05-26T10:20:34+00:00
- Post Title: S-Tuner 3D Models

How get models from S-Tuner:
1.Download and install URL Snooper 2
2.Go to page [http://3dtuning.stuner.net/](http://3dtuning.stuner.net/)
3.Run URL Snooper 2 and click Sniff Network
4.Chose car and parts
5.Find in URL Snooper 2 files .obj and .mtl 
6.Click right button mouse and copy link 
7.Download and IMPORT IN ZMODELER (mesh in 3ds max is broken...)
8.Enjoy 
[Bez tytułu.png](https://xentaxbackup.github.io/file/10973_Bez tytułu.png)
## Post #8
- Username: MacedoSTI
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Aug 11, 2014 11:57 pm
- Post datetime: 2016-05-27T15:35:57+00:00
- Post Title: S-Tuner 3D Models

zimex25
the principal part of Stuner car is a ".3ds" format i can't open it on my 3ds max "invalid file" and have 40kb

i found a XML file
[http://3dtuning.stuner.net/assets/asset ... 4362809568](http://3dtuning.stuner.net/assets/assets.xml?time=1464362809568)
## Post #9
- Username: zimex25
- Rank: veteran
- Number of posts: 143
- Joined date: Fri Feb 05, 2016 4:20 am
- Post datetime: 2016-05-28T14:04:34+00:00
- Post Title: S-Tuner 3D Models

> Reply from MacedoSTI
>
> zimex25
the principal part of Stuner car is a ".3ds" format i can't open it on my 3ds max "invalid file" and have 40kb

i found a XML file
http://3dtuning.stuner.net/assets/asset ... 4362809568
I don't know why i think is other 3ds format...
## Post #10
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2016-05-30T19:44:51+00:00
- Post Title: S-Tuner 3D Models

Just unpack the .3ds with 7zip and a .obj will pop out.
## Post #11
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2016-07-01T12:03:00+00:00
- Post Title: S-Tuner 3D Models

Didn't Have Much luck getting access to the Main Car Body 3D Models...

I Happily Got All the .Obj files i wanted for all the other parts but obviously as with some of the older posts above, i realise the .3dt / .3dm .con .mtl files are a bit more complicated to decrypt/Convert...

ideally i'd love to have the Rest of the car model availiable in 3DS Max...

Planning to Use the Model as a Base (want to fix improve upon it. Fix Bonnet, Rear Bumper etc... perhaps model interior based on real car) 
for my Upcoming Assetto Corsa Car Mod 
- so Keen To Finally Get The NISSAN PULSAR GTiR / RNN14 (4WD SR20DET Hatch) into a Modern Day Game...

It's a Car i Bought in Real Life after discovering it in Gran Turismo 1 & 2...



Example :) GTIR export .jpg (134.16 KiB) Viewed 152 times


Basically it seems the Decrypting Script i tried out from above was fine for .3DM Version 2 files.... and now they are hosting version 3 files...
I'm New to this & Script/Programming is not my Forte at all... i did try running the same script on the RoofHatch.3ds instead with no luck so far...
Any advice is appreciated 

PS: just joined the forum... Hello all 

"QuickBMS generic files extractor and reimporter 0.7.4a
by Luigi Auriemma
e-mail: [me@aluigi.org](mailto:me@aluigi.org)
web:    aluigi.org
        (Apr 29 2016 - 16:57:25)

                   quickbms.aluigi.org  Homepage
                            zenhax.com  ZenHAX Forum
                               @zenhax  Twitter & Scripts

- GUI mode activated, remember that the tool works also from command-line
  where are available various options like folder scanning, filters and so on

- select the BMS script or plugin to use
- select the input archives/files to extract, type * or "" for whole folder and subfolders
- select the output folder where extracting the files
- open input file C:\Users\Windows 10\Desktop\AC - Track 3D TESTS\NISSAN GTi-R\quickbms\INPUT\export.3dm
- open script C:\Users\Windows 10\Desktop\AC - Track 3D TESTS\NISSAN GTi-R\quickbms\S Tuner.txt
- set output folder C:\Users\Windows 10\Desktop\AC - Track 3D TESTS\NISSAN GTi-R\quickbms\OUTPUT

  offset   filesize   filename
--------------------------------------

- signature of 7 bytes at offset 0x00000000 doesn't match the one
  expected by the script:

  this one: "3dmv003"
  33 64 6d 76 30 30 33                              3dmv003

  expected: "3dmv002"
  33 64 6d 76 30 30 32                              3dmv002

- 0 files found in 0 seconds
  coverage file 0     0%   7          524867

Press ENTER or close the window to quit
## Post #12
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2016-07-01T12:06:27+00:00
- Post Title: S-Tuner 3D Models

> Reply from barreiros
>
> Just unpack the .3ds with 7zip and a .obj will pop out.

UM NO, This might of worked in the past but it does not at this point in time...

i think we need an updated QuickBMS Script by one of you Genii (a plural form of genie) / geniuses...
## Post #13
- Username: AMG
- Rank: advanced
- Number of posts: 61
- Joined date: Sun Aug 10, 2014 10:55 pm
- Post datetime: 2016-07-01T13:42:38+00:00
- Post Title: S-Tuner 3D Models

Contact the S-Tuner guy. As far as I know he doesn't mind you using his content unless you ask him first. He will probably send you the stuff personally if you ask him kindly.

[http://3dtuning.stuner.net/legal.html](http://3dtuning.stuner.net/legal.html)
## Post #14
- Username: QOTSANINSOADKORN
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Fri Jul 01, 2016 7:26 pm
- Post datetime: 2016-07-01T13:49:06+00:00
- Post Title: S-Tuner 3D Models

Have high Percentage of NISSAN GTiR 3D Model (4WD WRC "Homologation Model" SR20DET 1998cc TURBO Hatchback) from S-Tuner but missing Main Body as it's a newer version of the Encrypted .3dm file... Version 3 not 2 which I did find a script on here for QuickBMS...

WRC Versions had a few upgrades 6-Speed + Rollcage + Boost increased from 10.5 PSI to 15-16PSI for 300+ HP @ all 4 Wheels:
Same Engine + Turbo + TMIC + 440CC (GTR Yellow) Injectors.... "Mini-Godzilla"





[http://www.nissan-global.com/EN/HERITAG ... gti-r.html](http://www.nissan-global.com/EN/HERITAGE/pulsargti-r.html)
[http://www.nissan-global.com/EN/HERITAG ... ti-r2.html](http://www.nissan-global.com/EN/HERITAGE/pulsargti-r2.html)
[GTiR 3D Model - Progress_2.png](https://xentaxbackup.github.io/file/11226_GTiR 3D Model - Progress_2.png)
## Post #15
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2016-07-01T23:14:16+00:00
- Post Title: S-Tuner 3D Models

Now, what are we even talking about? Why would one want a script if you can simply download the files?

Is this the part you want?



Unbenannt.jpg (41.48 KiB) Viewed 134 times



Use the network analysis tool of you browser to download the 3ds, then simply unpack it with 7zip. You'll end up with an .obj just like the other parts. I just tried it again, it works fine for me, as you can see above (7zip 9.22 beta).
## Post #16
- Username: barreiros
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Tue Apr 28, 2015 6:34 am
- Post datetime: 2016-07-01T23:48:18+00:00
- Post Title: Re: Assetto Corsa - NISSAN GTiR 3D Model from S-Tuner - 4WD

There is also a RBR mod of this car:

[http://kazumaro133.blog100.fc2.com/blog-entry-289.html](http://kazumaro133.blog100.fc2.com/blog-entry-289.html)

But please ask for permissions before converting mods or models to another game to release them in public. Mod Edit: Offensive language removed. content creators is a bad idea if you still want them to release models in the future.

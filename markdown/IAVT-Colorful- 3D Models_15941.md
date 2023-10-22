## Post #1
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-03T13:24:40+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Hi there!
(I didn´t know if this was the right forum to post in, but I give it a go though!)
Has anybody ripped 3D Models from IA/VT-Colorful- on PS Vita?
(A Vocaloid Rhythm game just like the Project Diva Series.)
If so, is someone able to provide 3D models in Wavefront OBJ file extension to let me import it into Blender?
(Or PMD or PMX Models too)
If not, how can I do this process by myself?
Which tools do I need?
Someone who knows how to do this?
I have been heard of Henkaku, but because my firmware is on 3.63 on PS Vita I can´t do this do they say...
I don´t want the whole game to just play, I mainly want the 3D models featured in the game!
Thank you in advanced!
## Post #2
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2017-03-03T13:43:28+00:00
- Post Title: IA/VT-Colorful- 3D Models?

can you provide sample file?
## Post #3
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-03T14:27:23+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Well, I don´t have any sample file for the moment, as my Profile title suggests, I´m a ultra-noob when it comes to this. 
I had played the game to the end and unlocked all the songs and I had more modules then, but stupid as I was, I deleted the saved game and started a new game...
But I do have some saved data on my PC called PSVITA, there is my game IA/VT-Colorful- saves somewhere.
Can I send you that so you can look at it? 
If that´s to some help the file extensions is: param.sfo, icon.png, psvmd, psvinf, psvimg.
What I think is that param.sfo is the main file here that possible contains the models, Am I right?
And again, I don´t think I can use Henkaku cause of my firmware, maybe there´s other options.
And good to know: My game is not digital.
Thank you for your fast answer and your willing to help!
## Post #4
- Username: ProjectDiva
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-03T22:05:40+00:00
- Post Title: IA/VT-Colorful- 3D Models?

> Reply from ProjectDiva
>
> Well, I don´t have any sample file for the moment, as my Profile title suggests, I´m a ultra-noob when it comes to this. 
I had played the game to the end and unlocked all the songs and I had more modules then, but stupid as I was, I deleted the saved game and started a new game...
But I do have some saved data on my PC called PSVITA, there is my game IA/VT-Colorful- saves somewhere.
Can I send you that so you can look at it? 
If that´s to some help the file extensions is: param.sfo, icon.png, psvmd, psvinf, psvimg.
What I think is that param.sfo is the main file here that possible contains the models, Am I right?
And again, I don´t think I can use Henkaku cause of my firmware, maybe there´s other options.
And good to know: My game is not digital.
Thank you for your fast answer and your willing to help!

you need to do this
[viewtopic.php?f=29&t=15909](http://forum.xentax.com/viewtopic.php?f=29&t=15909)
then you will see folders with the model files in it.
## Post #5
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-04T11:03:16+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Oh, it´s chrrox! 
What a honor! 
I thought it was much harder!
Thank you so much!
I´m gonna try it right away!
## Post #6
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-13T21:17:10+00:00
- Post Title: IA/VT-Colorful- 3D Models?

I should not have said that it was easy...(yeah stupid noob here.  )
I have been following your directions chrrox, but it seems i cannot understand it.
I think I have been done it correctly in the first parts, but the last parts though, I´m really lost...
I can say that I´m a very new PS Vita owner(I have been owning it in two months and haven´t played it very much)and knows very little about this, but really wants to learn how to do this!
Maybe I´m very slow at learning new stuff.  
Plus I´m not a native english speaker(I´m from Sweden.) 
By the way, the thing I can´t understand is when you talk about PSN ID, what I think you mean is a folder with those numbers. 
But I´m not 100% sure...
And then you say "run from command prompt" do you mean the pure cmd or one of the tools I have been downloading, because what I saw there was a command prompt in psvimg extract etc. And then the very last part: when you explain how to use it, that´s where I´m stuck...! 
Please, I really hope you are reading this and are willing to help me. 
I feel very hopeless and worthless when I can´t understand when everybody else does.
And last thing to say, I was very afraid to write this stupid help message. 
Thank you in advanced!
## Post #7
- Username: Acewell
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-13T22:27:07+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Download QCMA [https://codestation.github.io/qcma/](https://codestation.github.io/qcma/)
launch qcma and take a look at its settings
take note of the applications / backups folder
in my case its "C:\Users\chrrox\PS Vita"
Backup your game (IA/VT-Colorful) to your pc now
after the backup go to C:\Users\chrrox\PS Vita\APP
you should see a folder with a long string this is your ID
inside that folder you should see your backed up games in this case PCSG00355
inside that folder you will find a game folder containing
game.psvimg
game.psvmd

APP\XXXXXXXXXXXXXXXX\PCSG00355
goto [http://cma.henkaku.xyz/](http://cma.henkaku.xyz/) and put in that long string to get your decryption key.

download and extract
[https://github.com/yifanlu/psvimgtools/ ... s/tag/v0.1](https://github.com/yifanlu/psvimgtools/releases/tag/v0.1)

hold shift and right click on an empty space in that folder and choose to open a command prompt in this folder.


now type psvimg-extract -K "Key From Website Here Without Quotes" "Full Path to game.psvimg" "Directory Where you want Files Extracted To"

and press enter.
## Post #8
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-15T13:33:51+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Weird, the command prompt says that psvimg-extract isn´t a intern command, extern command, program or command file(translated from swedish). I don´t know how to fix that problem though, sadly.
## Post #9
- Username: ProjectDiva
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-15T17:09:42+00:00
- Post Title: IA/VT-Colorful- 3D Models?

> Reply from ProjectDiva
>
> Weird, the command prompt says that psvimg-extract isn´t a intern command, extern command, program or command file(translated from swedish). I don´t know how to fix that problem though, sadly.

psvimg-extract is the exe name.

type dir in the command prompt and you should see
psvimg-extract.exe

if not you need to change to the directory that it is located at.
type cd "Path to psvimg-extract.exe" example cd c:\mytools\vita\
## Post #10
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-17T09:49:59+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Argh! What am I doing wrong?
Now it says "no such file or directory"!
I don´t know if it matters that my computer version is Windows 7?
Anyway, I will post the CMD info here to see if you can help me!
(You very kind and patient to me!  )
[no such file or directory.png](https://xentaxbackup.github.io/file/12645_no such file or directory.png)
## Post #11
- Username: ProjectDiva
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-17T10:22:34+00:00
- Post Title: IA/VT-Colorful- 3D Models?

you have spaces in your directories so you need to use "" around the path.
c:\ ps vita\app will not work you need to do
"c:\ ps vita\app"
Also you need to point directly to the game.psvimg 
so like
"c:\ ps vita\app\game.psvimg"
## Post #12
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-03-17T11:21:50+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Ah! I got it now!
Thank you very much!    
Can I ask you a thing more? 
If we say I want the 3D model files to Blender in Wavefront OBJ. extension, how can I convert the files to either Wavefront OBJ. or PMX/PMD?
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2017-03-17T11:48:47+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Post some sample files hosted somewhere like google drive or zippy share and people will most likely look at the format.
## Post #14
- Username: Supurreme
- Rank: advanced
- Number of posts: 43
- Joined date: Mon Jun 05, 2017 5:50 pm
- Post datetime: 2017-06-29T08:36:12+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Hey did you ever figure this out? I`m pretty interested in those models myself but can`t seem to figure out how to get them
## Post #15
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2017-06-29T16:25:45+00:00
- Post Title: IA/VT-Colorful- 3D Models?

Samples from this game if anyone wants to check:
[http://www98.zippyshare.com/v/180MEVEK/file.html](http://www98.zippyshare.com/v/180MEVEK/file.html)
Textures are .gxt and can be viewed in Noesis
## Post #16
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-06-29T17:04:13+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

strange vertex stride (31 bytes):



cos_001-mdl.jpg (160.27 KiB) Viewed 183 times


(first submesh (of 5?) only, as always)
## Post #17
- Username: mikulover39
- Rank: advanced
- Number of posts: 61
- Joined date: Tue Nov 22, 2011 5:55 pm
- Post datetime: 2017-06-29T17:17:21+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

The games models are made by mqdl with a few texture differences for the games engine.
He has some publicly available models available for MMD and other programs.
Texture comparison Vita left MMD right
## Post #18
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-08-11T17:27:01+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

Hi!
I saw today on Deviantart someone had uploaded pictures off IA/VT-Colorful- model(It was not downloadable though)!
How did he/she do that?
Are there any explainations, because I'm clueless how to open up the model.
Which programs do I need, or could someone provide a link to the model(s)???
Please?
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-11T18:59:11+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

> Reply from ProjectDiva
>
> Hi!
I saw today on Deviantart someone had uploaded pictures off IA/VT-Colorful- model(It was not downloadable though)!
How did he/she do that?dunno. Maybe he/she used hex2obj? 

(cos_001_clothes01_a.mxt.gxt converted to jpg using Noesis.)



cos_001_tex.jpg (247.82 KiB) Viewed 150 times



H2O file for cloth:

0x10C00 13023
Vb1
31 15
0x171C0 2332
020100
0x0 255
## Post #20
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-10-03T11:29:29+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

Hi again! 
I have been used this method again, but when I did it this time, I get no files, why?
It seems it´s successful at command prompt but I get zero files!
Do this tool needs to be updated or does the files end up in a diffferent location on the computer?
Help please.
## Post #21
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-10-04T16:25:28+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

Look at this:
When I look in the folder there´s no directory nor files!
[CMD.png](https://xentaxbackup.github.io/file/13387_CMD.png)
## Post #22
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2017-10-07T20:17:55+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

Arggh! I´m so stupid! But I fixed it by myself! 
Between, do you guys know what I can do with the files?
I want to convert them to a file extension Blender and/or Milkshape likes. 
(Wavefront OBJ. or PMX/PMD for example).
Where and to who can I upload them to let them have a look at the files?
## Post #23
- Username: ProjectDiva
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Jan 21, 2017 1:10 am
- Post datetime: 2018-02-19T20:44:01+00:00
- Post Title: Re: IA/VT-Colorful- 3D Models?

Hello!
Any news on how to extract the files from psvimg-extract???
ux0_temp_game_PCSG00355_appmeta_PCSG00355 and ux0_temp_game_PCSG00355_savedata_PCSG00355 is what I get from psvimg-extract, 
because there were two types of psvimg files in APP folder. 
My files is this types: BIN, DB, ICV, file(keystone and sealedkey), DAT, SFO, PNG(Can´t open), XML and so on.
I saw one of the Xentax members uploaded some MDL files to an upload site, but the files is now invalid!
Please, can you help me?

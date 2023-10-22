## Post #1
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-03-27T15:06:11+00:00
- Post Title: granny engine .gr2 question

Hi,

i've got a .gr2 meshes,used in many games.

anyone know how it can be converted back to an editable format?

i speak about the granny radtoolgame o'course.

all help welcome
## Post #2
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-27T16:47:10+00:00
- Post Title: granny engine .gr2 question

Not having too much of an idea about those games in question, I am always afraid to state the obvious. But do you think that this link may be somehow helpfull   :

[http://www.radgametools.com/](http://www.radgametools.com/)
## Post #3
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2006-03-28T14:38:09+00:00
- Post Title: granny engine .gr2 question

well,helpful to spend $10k to get the sdk 

sdk ftp only available to customers..well all links appreciated tough
## Post #4
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-03-28T19:17:17+00:00
- Post Title: granny engine .gr2 question

Mambox, 
obviously youre right. 10K is for the much bigger guns. 
Alternative I hear is reportedly Blitz3D + B3D Pipeline = $100

Anyway here is that thread, its funny in places:
[http://www.blitzbasic.com/Community/pos ... opic=52800](http://www.blitzbasic.com/Community/posts.php?topic=52800)
## Post #5
- Username: Paul Siramy
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Nov 04, 2005 6:31 pm
- Post datetime: 2006-03-31T21:30:22+00:00
- Post Title: granny engine .gr2 question

[Granny 3D SDK Features](http://www.radgametools.com/grasdk.htm)

> File format
>
> 
>
>     * completely transparent and flexible file format
>
>           o all aspects of file format are exposed at the API level, so you can write your own Granny file readers and writers even without using the Granny API utilities for doing so
>
>           o file format is not hard-coded, so you can add your own extensions or even change it completely and use it for files other than your art assets
To me it means that any game that use Granny file version 2.x can use their own variation of the original file format. It also means that all the work you'll done to decode a .gr2 of 1 game won't necessary help you for decoding a .gr2 of another game
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-14T14:15:51+00:00
- Post Title: granny engine .gr2 question

I once wrote a program for another game - can't remember what it was, maybe AoE3 - and I think there was a guy who figured out at least a part of the format.

edit: Yeah it was indeed Age3: This guy could load some gr2 files into 3dsmax:
[http://aoe3.heavengames.com/cgi-bin/for ... =20#post21](http://aoe3.heavengames.com/cgi-bin/forums/display.cgi?action=st&fn=1&tn=23622&st=20#post21)
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-01-14T16:47:06+00:00
- Post Title: granny engine .gr2 question

but i'm afraid it didnt ever shared his script,copyrights probs.

any gr2 converter would be funny
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-14T19:27:36+00:00
- Post Title: granny engine .gr2 question

He didn't do anything with the format, he just used the granny.dll to load the mesh.
[http://aoe3.heavengames.com/cgi-bin/for ... 25313,,all](http://aoe3.heavengames.com/cgi-bin/forums/display.cgi?action=ct&f=14,25313,,all)
## Post #9
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-01-15T15:42:53+00:00
- Post Title: granny engine .gr2 question

you're right!!!

missed it!

i'll try when gmax is installed again.

thanks!!
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-01-16T21:51:15+00:00
- Post Title: granny engine .gr2 question

Did you try it?

So what about a community project to create header/lib files for the granny.dll? It's used in many games...
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-02-07T06:33:03+00:00
- Post Title: granny engine .gr2 question

[out]
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-07T11:36:58+00:00
- Post Title: granny engine .gr2 question

Nice, uses a different approach than the granny reader above. What format do the files decompressed by this one have? Can they be read with 3DS?

I think the biggest problem is to get data back to granny format because there are probably no functions for that in the dll. The good news is that they don't really care about reversing and don't try to protect their stuff.
All functions are exported with their names and C helps us by providing the byte size of the parameters. 
It has to figured out what those functions do and what parameters they want.
## Post #13
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-02-07T11:44:48+00:00
- Post Title: granny engine .gr2 question

> Reply from Rheini
>
> Did you try it?

So what about a community project to create header/lib files for the granny.dll? It's used in many games...

btw sorry to you,i've no time to test the granny in gmax,have a tons of work atm.
## Post #14
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-02-07T14:03:35+00:00
- Post Title: granny engine .gr2 question

[out]
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-02-07T14:28:22+00:00
- Post Title: granny engine .gr2 question

I don't get your point. This function converts a granny file into some raw format, so what do you mean?
## Post #16
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2007-02-07T14:53:01+00:00
- Post Title: 

[out]
## Post #17
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-12T22:59:18+00:00
- Post Title: 

I tested on a file. I think this function just decompresses the gr2 file and returns the raw data.
## Post #18
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-19T11:16:06+00:00
- Post Title: 

I tested Ykkrosh's approach on a Settlers 2: building. works quiet well.
[http://img106.imageshack.us/my.php?image=bildhy8.jpg](http://img106.imageshack.us/my.php?image=bildhy8.jpg)
## Post #19
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-03-19T13:45:43+00:00
- Post Title: 

just tried now with gmax and some 'cars' granny..only a wheel out script,the viewer watch correct cars and textures...

nothing good for me in this.

without sdk nothing is documented..whats about:
GrannyConvertFileInfoToRaw@8 _GrannyConvertFileToRaw@8 _GrannyConvertIndices@20 _GrannyConvertPixelFormat@32 _GrannyConvertSingleObject@16 _GrannyConvertTree@12 _GrannyConvertTreeInPlace@16 _GrannyConvertVertexLayouts@20

etc...
## Post #20
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-19T18:29:32+00:00
- Post Title: 

So I assume that you mean only 1 wheel of the car was imported into gmax.
The cause might be that the program only exports the first mesh in the file.
Here's a slightly modified version that outputs all meshes.
[grnreader.rar](https://xentaxbackup.github.io/file/1095_grnreader.rar)
## Post #21
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-03-20T15:01:45+00:00
- Post Title: 

slightly modified that make it!

dunno where you found it but work like a charm,at least for the granny models i have.

time to render it 

thanks!

what do you suggest to render it?
## Post #22
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-20T15:20:56+00:00
- Post Title: 

Compiled it myself.
## Post #23
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-03-20T16:28:26+00:00
- Post Title: 

thats the secret...you master it!
## Post #24
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-03-21T09:08:00+00:00
- Post Title: 

Still wondering how they save the bones and that stuff.
## Post #25
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2007-03-25T13:03:43+00:00
- Post Title: 

found this...
[granny.zip](https://xentaxbackup.github.io/file/1101_granny.zip)
## Post #26
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-01-20T00:35:09+00:00
- Post Title: 

This guy also coded some Granny supporting stuff:
[http://www.codesuppository.blogspot.com/](http://www.codesuppository.blogspot.com/)
## Post #27
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2008-01-22T16:58:30+00:00
- Post Title: 

This guy just rock!

i had lost the place but played with some kinetik sdk and it's amazing
## Post #28
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-15T12:11:32+00:00
- Post Title: 

I'm not a real programmer, though I have some knowledge about game development.
I'm interested in this topic because I want to create a plugin to grab the gr2 animations. To me the geometry is not interesting (though is useful to have) but the real divide between a professional product and an indie production is the animation quality. I'm much into the adventure genre: find me a moddable game with good talking animation to grab...  

I took the Neverwinter Night importer and I started to modify it. Here' some tings I noticed and some thoughts:

- You can be successfull or not depending by the granny2.dll version. Some files are opened with a version and not another one. I'm using the granny crowd demo dll (2.6.0.10 version). This is a serious limitation, because I won't be able to tell if the plugin would work in every condition. I'm currently working with two adventures "murder on the orient express" and "And there were none" : I'm able to iimport the skeleton from the model file as well as the animation file from of the former but only from the model file of the latter.

- The NW2 importer is used to grab the skeleton data. In the source you can clearly see that the gr2 data are converted to raw data and then composed to be read and useful. I'm not able to dump this code in a standalone program so I'm currently using the dlu plugin to grab the data. Right now I'm able to export the skeleton directly to SMD format (not exporting from 3ds MAX, directly from the gr2 file). The SMD is really easy to understand and it's a blessing. Here's a shot of the skeleton in Milkshape:
[](http://img255.imageshack.us/my.php?image=82642987ha5.png)
this file is a gr2 animation file, containing only animation data. The skeleton is there, so the export is successful and the first frame is taken as reference. 

- I figured out much of he data needed to get the animation working (SMD format as well). I have only problem with the datas of the keyframe coordinates but I'm quite confident I will be able to fix it.

i hope to figure it out. I'll keep you posted...
## Post #29
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-16T14:19:01+00:00
- Post Title: 

I got it. Preparing a video...
## Post #30
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-16T17:15:00+00:00
- Post Title: 

ok Sorry for the third post in a row, but in this forum there's not the modify option.

i post here a little video showing the skeleton and animation importer. I had to swith back in 3dsmax format because the SMD format doesn't support this kind of keyframe manipulation (the rotation and position keyframe are distinct and asymmetrical). The NeverwinterNight2 skeleton importer has done the main part of the job. I only deleted some useless parts that could crash the import process and I found different errors in the animation part. Strange errors that I (an unprofessional) was able to find quite easily. So i think that the importer was working and unreleased to avoid a legal battle with the owners. Do you like this "inside-job" theory? Too conspirational for thew game industry?   
Some gr2 files have a different rotation format for the keyframes (the skeleton is working for all the model I tried). I thinlk I can solve this and release the plugin with the source. Do you think that the old scary Granny would sue me in a court of law for this? no, seriously, in your experence is that illegal?

video:
[http://it.youtube.com/watch?v=d84KvoCN40Q](http://it.youtube.com/watch?v=d84KvoCN40Q)
## Post #31
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-05-16T17:38:13+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from federico
>
> ok Sorry for the third post in a row, but in this forum there's not the modify option.
You are wrong, you may use the edit button to edit your posts.

> I thinlk I can solve this and release the plugin with the source. Do you think that the old scary Granny would sue me in a court of law for this? no, seriously, in your experence is that illegal?
To quote the hacker manifest:

> We explore... and you call us criminals.  We seek
>
> after knowledge... and you call us criminals.  [...]
>
> You build atomic bombs, you wage wars, you murder, cheat, and lie to us
>
> and try to make us believe it's for our own good, yet we're the criminals.
>
> 
>
> Yes, I am a criminal.  My crime is that of curiosity.  My crime is
>
> that of judging people by what they say and think, not what they look like.
>
> My crime is that of outsmarting you, something that you will never forgive me
>
> for. 

Good work, looking forward to see your code
## Post #32
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-18T23:44:56+00:00
- Post Title: Re: granny engine .gr2 question

Ok. I created a site with all the infos I got so far about the granny powered games and the related tools. There you can download my plugin compiled for 3dsmax 2008, and the source for all the max versions and gmax. I also updated the grnreader source & binary that now outputs skinnable meshes. In the Tips&Tricks section I suggest you a way to get the models in 3dsmax without pain.



The game list is huge but it isn't complete. They licensed quite all the game companies in the game industry. 
So I encourage you to email me ([gr2.decode@gmail.com](mailto:gr2.decode@gmail.com)) if you discover some new gr2 game or if you successfully can import the content using my plugin. 
As I said, I'm really excited about the large archive of animation that these games could provide to the indie developpers.
## Post #33
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-23T13:02:34+00:00
- Post Title: Re: granny engine .gr2 question

sorry, I keep posting my progress as if this were my blog.   

I combined the two tools. The plugin imports the skeleton and the animations, as usual but it also  exports  the skeleton in smd format.
the grnreader append to that file the mesh data with the vertex weighted to the bones (still in smd format). I also figured out the mesh group data so the result is a skinned mesh linked to the skeleton in SMD format. Yeah! 
I tried in max and milkshape and the result is good. I'm adding the last two features and I'm ready to release the final version: extract the texture, and adding the other three vertex weight layer.

[](http://img371.imageshack.us/my.php?image=reffw1.jpg)
[](http://img267.imageshack.us/my.php?image=animyk2.jpg)
## Post #34
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-05-23T13:06:34+00:00
- Post Title: Re: granny engine .gr2 question

Amazing work!
But still... we don't know any way to get something back into gr2 format
## Post #35
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-23T17:36:49+00:00
- Post Title: Re: granny engine .gr2 question

Today I discovered that there's an exporter!.   
The Obsidian Expotron utility (only for max 7/8) has a granny exporter.
Right now I'm still focused on the importer plugin (gave up on the textures side) but I tried an export from max 7 and something happened. The export isn't perfect but it's a start. The export plug it's highly customizable and I didn't included in my importer  the unit scale and world axis (for example the oddworld models are upside down), so there are ways to improve the result. 
[](http://img206.imageshack.us/my.php?image=screenhunter01may231929um2.jpg)
(the little dots that you can see in the eyes are the MAX bone dummies. The granny format is great, if you hide them in max, the exporter hide them for you in the resulting gr2 file).

I think that the people more interested in a compatible import/export are the NWN2 modders. I don't have the game and actually I'm not so interested in it (my main end is gamedev, I made all this stuff to grab the animations). So if someone is willing to try the tools for that game I would be more than happy to see what I can do.

The expotron plugin seems to be not avaible anymore at the obsidian official site. I don't remember where I found it, but I still can include it in the new release of the importer...
## Post #36
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-23T18:33:43+00:00
- Post Title: Re: granny engine .gr2 question

Ok that's it. Here are two shots of vertex weight in max and milkshape.

[](http://img58.imageshack.us/my.php?image=screenhunter02may232028cu7.jpg)
[](http://img389.imageshack.us/my.php?image=screenhunter04may232028zn9.jpg)

Tomorrow I will pack all the stuff (binary. source, tools) and I'll write a tutorial.
## Post #37
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-28T12:34:24+00:00
- Post Title: Re: granny engine .gr2 question

Sorry for the delay.   
Actually I finished updating the plugin and the converter and I wrote all the docs, but still there's something keeping me working on this. I'm trying to collect most of the games licensed for the grannny format, and my findings were unexpected. 
For example: Anno 1701, which I know interested Rheini (your tools are great, man). The point is that some gr2 files contain only the meshes but not the skeleton, others only the animations. So I think I have to re-work some part of the code because I had to make some ad-hoc hack just to export those data. 
You just have to wait two days... no more.
## Post #38
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-29T09:29:51+00:00
- Post Title: Re: granny engine .gr2 question

OK. Here we go.

I updated the site with the new downloads for the MAX plugin, the Mesh converter, the exporter, and new step-by-step docs. I think there's all an indie developper needs to take a look at the work of the pros. Nonetheless, the willing modders should use those tools carefully, because they weren't created for that purpouse and I never tried it in this context. If someone wants to go that way, I could try try to help, but it's not something you should expect from me right now. I interested though in trying the tools on all the game licensed for granny3d, so if you discover new games supported by the gr2 format or if you own one of those games, please write me a line (gr2.decode AT gmail.com) and eventually send me a couple of gr2 models to try.

I added some new infos about the game "Settlers II - 10th Anniversary" (thanks to mrmocool for the info). I tried to use the tools on Anno1701 but I wasn't able to load the models in the converter for unknown reasons. Sorry about that, I may give it another try.
I will try to get some datas from Scarface, which probably use the gr2 format (I found the info in this forum).
## Post #39
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-05-30T00:28:03+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from federico
>
> I added some new infos about the game "Settlers II - 10th Anniversary" (thanks to mrmocool for the info)
btw, that was me 
good job mate.
keep going, your work is very appreciated!
## Post #40
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-05-30T10:55:48+00:00
- Post Title: Re: granny engine .gr2 question

thanks a lot Rheini. 
Today I downloaded the demo of Stronghold 2 for Windows. The gr2 files aren't archived nor compressed. The import/export worked like a charm.  Info and screens in the
## Post #41
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-03T18:58:15+00:00
- Post Title: Re: granny engine .gr2 question

Confirmed support for Dungeon Lords by Heuristic Park, distrubuted by dreamcatcher. Screens and infos in the Credits Jwatson.
## Post #42
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-10T00:22:08+00:00
- Post Title: Re: granny engine .gr2 question

Thanks to the useful infos and tools provided by  F. Fischer (aka SiENcE), I wrote a little tutorial to import .grn Granny1 files using the gr2 tools 


Confirmed support for the game SpongeBob SquarePants: Employee of the Month by Awe Productions (.grn format).
## Post #43
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-17T13:36:08+00:00
- Post Title: Re: granny engine .gr2 question

The Download link of the Gr2 Mesh Converter was broken, now has been fixed. I also added the SMD tools you could need. Check out the 


Added a new game to the games list: Catz II by Ubisoft. Thanks Topper Carson for the info!
## Post #44
- Username: Nirvana Jung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 21, 2008 2:28 am
- Post datetime: 2008-06-21T02:17:29+00:00
- Post Title: Re: granny engine .gr2 question

first off, i'd say thanks all u guys making gr2 importer

im not a programer i just design 3d art and game modding which is graphics
so i came here to asking what i need for my work
i'm a korean and lack in english so some my gramer could be missunderstanding

OK, here is my deal 

what im wondering is about Age of Empires3 GR2 files (include animations)
i attempted use a AoE3 *.gr2 files in units and Animations for my work
but 3dsmax2008 doesnt work for those gr2 files Also granny viewer doesnt load for those files
especially when i tried import mesh for unit gr2 files, 3dsmax was just crashed 

i have read all documents of xxxxxxxxxxxxxxxxxx and i figured out how can import and convert normaly
Fortunately, the building gr2 files was successed to import at 3dsmax 2008


however units and Animations are doesnt work

for searching problems,i linked sample files is here ( you may wait to see download button )

i really want to get Aoe3 units and animations in 3dsmax2008 for my work , thanks
## Post #45
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-21T09:37:10+00:00
- Post Title: Re: granny engine .gr2 question

I attached to this post a version of the grnreader that correctly exports the model files you sent me. In the vertex struct there's another parameter: granny_real32 Tangent[3];

I'm not completely satisfied by this hack because it won't export the standard gr2 format. Probably it should work on the Settler II models too, but I can't try because I've just deleted the demo.

The samples you sent me are confusing, so I've really proceeded on trial and error. Anyway you should always load your models in the GrannyViewer to see the additional data. For example, my importer has not implemented any scaling using the unit's meter data contained in the gr2 format. That's a great limitation for a modding usage of the tools. The cavalery models have a scale ratio of 0.615157 while the animations of 39.857684 
Naturally the result is a little model stretched by the big animation. I think you could solve this trouble in the modelerer. For the modding purpouse you should carefully play with the expotron plugin just to find the correct setting to overcome these issues, if they used those scale values there's probably a reason somewhere.   
A note: animation import works correctly. You just have to import the model before the animations because the skeleton data aren't embedded in the animation files.

[](http://img514.imageshack.us/my.php?image=cavuq6.jpg)
[tangent_hack.zip](https://xentaxbackup.github.io/file/1551_tangent_hack.zip)
## Post #46
- Username: Nirvana Jung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 21, 2008 2:28 am
- Post datetime: 2008-06-21T16:38:03+00:00
- Post Title: Re: granny engine .gr2 question

ok thanks, i'll try it
btw how can import a gr2 model in MilkShape? i have milkshape but i didnt see
any file options and plugins 
is that just allow to new version of Milkshape ? or is there any plugins ?
----------------------------------------------------------------
Additional :

i tried convert gr2 to maxscript *.ms file but attaced grnreader_hack doesnt work
for me 

its same result when i run maxscript and grnreader_hack was error after export ms file
here is screen ( i have MS winows korean edition but i think its doesnt matter to work because the building gr2 does work correctly without any error in there )

anyway i tried open that ms file in notepad to find out what is mssing
and there is something missing information in vertex info
there is no vertex coordinates at all just writed zero
here is vertex coordinates info of exported ms file

```
temp = mesh numverts:10656 numfaces:212
setNumTVerts temp 10656
buildTVFaces temp
setVert temp 1 [0.000000,0.000000,0.000000]
setTVert temp 1 [0.000000,-0.000000,0.000000]
setNormal temp 1 [0.000000,0.000000,0.000000]
setVert temp 2 [0.000000,0.000000,0.000000]
setTVert temp 2 [0.000000,-0.000000,0.000000]
setNormal temp 2 [0.000000,0.000000,0.000000]
setVert temp 3 [0.000000,0.000000,0.000000]
setTVert temp 3 [0.000000,-0.000000,0.000000]
setNormal temp 3 [0.000000,0.000000,0.000000]
setVert temp 4 [0.000000,0.000000,0.000000]
setTVert temp 4 [0.000000,-0.000000,0.000000]
setNormal temp 4 [0.000000,0.000000,0.000000]
setVert temp 5 [0.000000,0.000000,0.000000]
setTVert temp 5 [0.000000,-0.000000,0.000000]
setNormal temp 5 [0.000000,0.000000,0.000000]
setVert temp 6 [0.000000,0.000000,0.000000]
setTVert temp 6 [0.000000,-0.000000,0.000000]
setNormal temp 6 [0.000000,0.000000,0.000000]
.
.
.
setTVert temp 10656 [0.000000,-0.000000,0.000000]
setNormal temp 10656 [0.000000,0.000000,0.000000]
setFace temp 129 [54,228,226]
setFace temp 130 [131,123,269]
setFace temp 131 [32,214,218]
setFace temp 132 [281,287,144]
.
.
.
for f = 1 to temp.numfaces do setTVFace temp f (getface temp f)
)
create()

```

but the buildings gr2 file just shows vertex coordinates as well in there
here is converted files which i used with attached new grnreader_hack
[error files.zip](https://xentaxbackup.github.io/file/1553_error files.zip)
## Post #47
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-21T22:34:55+00:00
- Post Title: Re: granny engine .gr2 question

Have you read carefully the docs?

Milkshape imports SMD files. the .ms file it's just for backup in case of failure of the SMD format.

Have you first imported the gr2 in 3dsMax? Do the importer generated the two gr2.smd and gr2.dat files? Are they in the same directory of your gr2 file?
Try to be more specific. As you saw I successfully imported the cavalery model, so just start from there and see if it works.
## Post #48
- Username: Nirvana Jung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 21, 2008 2:28 am
- Post datetime: 2008-06-21T23:58:44+00:00
- Post Title: Re: granny engine .gr2 question

well.. i have read carefully all ur document 
the problem is i haven't took any smd files as i showed you my error screen
grnreader hack just dumps out ms file
there is empty in smd file 
i couldnt took any right smd files with grnreader
that doesnt work for me that is main issue, not about steps

yes i have imported gr2 file in 3dsmax and i saw smd file and dat 
and i ran the grnreader for gr2 file but grnreader just crashed after export files as i showed you above
there was empty and there is nothing at all for mesh in smd (there is no triangles information in smd file)
that mean the gr2 mesh exporter doesn't inject to write any triangles data to pre smd file
## Post #49
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-22T09:42:56+00:00
- Post Title: Re: granny engine .gr2 question

Nirvana Jung, I really want to help you, but I'm not a magician. Really, I don't know what's going on in your computer   
So you just have to provide more information. The screen you sent just tells me that the program has crashed but not why.
So as I said: Could you please import the cavalery models you sent me so we can compare what's different between us? 
I try to break it down in steps for you so we can find where's the error. Please follow these steps.

- I've unpacked the tangent_hack archive in a folder. I've choosen the file named: cav_archer_1age_rider.gr2
[](http://img528.imageshack.us/my.php?image=19848575dr7.jpg)

- Started 3dsMax 2008. Using the GR2 plugin I loaded that gr2 file. The skeleton of the model has been imported.
[](http://img528.imageshack.us/my.php?image=192.jpg)[](http://img59.imageshack.us/my.php?image=46411784fr8.jpg)

- As a result the plugin has generated two files: cav_archer_1age_rider.gr2.smd and cav_archer_1age_rider.gr2.dat
the former has this content:

```
nodes
0 "Bip01 Root" -1 
1 "Bip01 Prop2" 0 
2 "Bip01 Prop1" 0 
3 "Bip01 Pelvis" 0 
4 "Bip01 Spine" 3 
5 "Bip01 R Thigh" 4 
6 "Bip01 R Calf" 5 
7 "Bip01 R Foot" 6 
8 "Bip01 L Thigh" 4 
9 "Bip01 L Calf" 8 
10 "Bip01 L Foot" 9 
11 "Bip01 Spine1" 4 
12 "Bip01 Neck" 11 
13 "Bip01 Head" 12 
14 "Bip01 L Clavicle" 12 
15 "Bip01 L UpperArm" 14 
16 "Bip01 L ForeArm" 15 
17 "Bip01 L Hand" 16 
18 "Bip01 R Clavicle" 12 
19 "Bip01 R UpperArm" 18 
20 "Bip01 R ForeArm" 19 
21 "Bip01 R Hand" 20 
end 
skeleton 
time 0
0 0.000000 0.000000 0.000000 -0.000000 1.570796 0.000000 
1 -0.063173 0.018507 -0.456884 0.000000 0.000000 0.000000 
2 -0.063173 0.018507 0.456884 0.000000 0.000000 0.000000 
3 0.000000 0.000000 0.000000 -1.570795 0.000001 -1.570796 
4 -0.116393 0.000000 0.000189 -0.000004 -0.000796 -0.000001 
5 0.116393 -0.101211 -0.000282 0.017488 0.000011 2.987840 
6 -0.506055 0.000000 -0.000000 0.000000 0.001381 -0.000000 
7 -0.506055 0.000000 -0.000000 -0.017497 0.000506 0.153743 
8 0.116393 0.101211 -0.000281 -0.017489 0.000011 -2.982161 
9 -0.506055 -0.000000 0.000000 0.000000 0.001381 0.000000 
10 -0.506055 -0.000000 0.000000 0.017486 0.000606 -0.159421 
11 -0.237042 -0.000000 0.000189 0.000000 -0.000000 0.000000 
12 -0.237042 -0.000000 0.000073 0.000000 -0.000000 0.000000 
13 -0.091290 0.000000 0.000000 0.000000 0.000798 0.000000 
14 -0.000000 0.035424 -0.000073 -0.033683 3.018745 1.308668 
15 -0.174710 0.000000 0.000000 0.114725 -0.031526 0.854904 
16 -0.303633 -0.000000 -0.000000 -0.000000 0.461799 -0.000000 
17 -0.303633 0.000000 0.000000 -1.570000 0.000000 0.407847 
18 -0.000000 -0.035424 -0.000073 0.033682 3.018750 -1.308668 
19 -0.174710 0.000000 0.000000 -0.114725 -0.031526 -0.854904 
20 -0.303633 0.000000 -0.000000 0.000000 0.461799 0.000000 
21 -0.303633 0.000000 -0.000000 1.570000 -0.000000 -0.407847 
end
```

the latter, this one:

```
Bip01 Prop2
Bip01 Prop1
Bip01 Pelvis
Bip01 Spine
Bip01 R Thigh
Bip01 R Calf
Bip01 R Foot
Bip01 L Thigh
Bip01 L Calf
Bip01 L Foot
Bip01 Spine1
Bip01 Neck
Bip01 Head
Bip01 L Clavicle
Bip01 L UpperArm
Bip01 L ForeArm
Bip01 L Hand
Bip01 R Clavicle
Bip01 R UpperArm
Bip01 R ForeArm
Bip01 R Hand
```


- opened a command line dos app in the folder containing my gr2 file. typing in: grnreader cav_archer_1age_rider.gr2
- no errors. the cav_archer_1age_rider.gr2.smd file has been injected with mesh data. Additionally a .ms file has been generated.
[](http://img528.imageshack.us/my.php?image=194.jpg)[](http://img528.imageshack.us/my.php?image=193.jpg)

- The smd file can be imported using Milkshape or  the SMD tools for 3dsMax you could find in the  site.
[](http://img116.imageshack.us/my.php?image=91046551ak6.jpg)

I attached the files converted. I hope this could help. 
[test_result.zip](https://xentaxbackup.github.io/file/1554_test_result.zip)
## Post #50
- Username: Nirvana Jung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 21, 2008 2:28 am
- Post datetime: 2008-06-22T15:59:25+00:00
- Post Title: Re: granny engine .gr2 question

right, you showed me what i was doing collectly 
i did extactly same steps what you doing 
excepted injecting with mesh data to smd file
becauss when i was enter grnreader cav_archer_1age_rider.gr2 in command line dos app in the folder containing my gr2 file
gr2 mesh converter just crashed however the building gr2 files are works succefully

maybe its cause different of my pc or Windows editon but i have no idea
i tested with other theree pcs in the CyberCafe but always crahsed at that time

is there any restriction for any korean language(Unicode) in relation to file name ?

Additional :
--------------
nevermind, i solved my self there was different gr2 formats from reference model
a strange issue is mesh converter does works success for just some of AoE3 original models
i mean, i tried with AoE3 expansion (Asian Dynasty) models but all of gr2 files crahsed
cavalry model which i attaced file is original model not expansion title

i linked AoE3 Asian Dynasty models try looking around the difference of them 
[http://www.savefiles.net/d/cqbgn8rhk4pd.html](http://www.savefiles.net/d/cqbgn8rhk4pd.html)

anyways thanks new gr2 mesh converter for AoE3 
it would be very useful for AoE3 fans and modders

btw, the GR2 Expotron Exporter (3dsMax) is compatible for AoE3 model ?
could it makes a gr2 file for AoE3 model compatibly ? or is it needs to make another version something for AoE3 model ?
## Post #51
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-23T13:01:55+00:00
- Post Title: Re: granny engine .gr2 question

Ok, good.   
So, if I correctly understood, using the cavalery models the hacked grnreader worked just fine but the Asian Dinasty expansion crashes the app. I could look at your new files.
About the expotron plugin. I really don't know how it could work with your game. The plugin is plenty of options so I think it could be tweaked to get a proper result. I suggest you to try by yourself looking carefully at the original data opening the models in the grannyviewer: in the model section, right click->View detail and then browsing the data structures. I have not this game and I'm not really interested in Mods, but I'm happy to help as far as I can.
## Post #52
- Username: Nirvana Jung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 21, 2008 2:28 am
- Post datetime: 2008-06-24T01:52:56+00:00
- Post Title: Re: granny engine .gr2 question

ok thanks your help :I’m looking forward to get all of AoE3 models
and i have good news for you
i found out a game which uses Granny2 models   
im making a mod which the ancient time concept
i was digging many ancient concept games and i just found that as chance would have it  

that game is  Caesar IV
the game achive aresn't compressed and gr2 models aresn't encryptioned
its allow to see models and animations with granny viewer
and textures format is dds it's not encryptioned at all


but strange thing, the Caesar lV gr2 files are not affects with mesh converter and 3dsmax plugin
i dont know why it should open in the granny viewer though
but i couldn't anything with your the grnreader and 3dsmax plugins
when i entred command line in gnreader it says :

-Log < 3 9> c:/dev/rad/granny/rt/granny_file.cpp<351> : file is not a Granny file
Couldn't read GR2 file '<null>' - maybe it's not right name, or not in the right folder

i used new grnreader and basic grnreader both

here is a sample file included Caesar lV gr2 model files
[Caesar lV sample files.zip](https://xentaxbackup.github.io/file/1556_Caesar lV sample files.zip)
## Post #53
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-24T16:12:33+00:00
- Post Title: Re: granny engine .gr2 question

Thanks for your discover, but it's a shame: Cesar IV models use the granny RAW format, which we are not able to open (though the grannyviewer can). 
The asian dinasty models use a format for vertex strucy really unusual, in fact even the grannyviewer is not able to display them correctly. I don't think I could get something out of them...
## Post #54
- Username: Nirvana Jung
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Sat Jun 21, 2008 2:28 am
- Post datetime: 2008-06-24T20:19:34+00:00
- Post Title: Re: granny engine .gr2 question

Ok, i see then we don't have a chance to get the Asian dynasty models in SMD format currently ?
and as for Cesar IV models, have any plans making a solution for that ? or it just unable to open currently?

if so it's needs to solved by someone
## Post #55
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-06-26T19:13:14+00:00
- Post Title: Re: granny engine .gr2 question

No, about the Caesar model I don't see any handy solution for the next future. I said it was the raw format. I was wrong, it's kind of a new format compression (from granny 2.7.0): form oodle0 to oodle1, they say in the granny site, does anybody know what does it mean? and if there's some tool for that...  

I [updated the infos about the Petz games](http://www.gr2decode.altervista.org) - thanks again Toppen Carson! - with Catz II and Dogz II. 
Support confirmed for Jimmy Neutron vs. Jimmy Megatron (.grn format)
I updated the GR2 mesh exporter that now ask confirmation before exporting the maxscript mesh (some models crash on this but not in the SMD export).

No one is willing to help me figuring out the Legend Hand of God archive format, so I'm extracting some models manually cutting and pasting out the data using the hex editor (I know the beginning hexes of the gr2 format). If someone has some idea, or better code, to split a file in sections delimited by an hex value, I would be grateful for life.
## Post #56
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-06-26T22:03:06+00:00
- Post Title: Re: granny engine .gr2 question

Well afaik the old compression algorithm already was some custom stuff. But maybe they changed it into something more popular.
## Post #57
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2008-07-01T12:14:49+00:00
- Post Title: Re: granny engine .gr2 question

I suspected that the problem laid in the dll version and I was right. The 2.7 dll can import and convert those new files. I had to change both the gr2 converter and the max plugin because they changed the format a bit. I'm still working on this, next week it should be ready.

[](http://img360.imageshack.us/my.php?image=caesarivyt4.png)
## Post #58
- Username: risy
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Mar 01, 2009 5:45 am
- Post datetime: 2009-04-30T17:53:48+00:00
- Post Title: Re: granny engine .gr2 question

Hi I've Been Reading This Post I'm Working On Modding Rise N fall Civilization at war The Game Before Cesar IV I've The Gr2 Files Are Seperated into animations and models gr2 importer dosen't do anything mesh converter crash when using with animations it just say "no meshes i'll just give up" plz help
## Post #59
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-05-19T04:36:34+00:00
- Post Title: Re: granny engine .gr2 question

I apologize if he didn't want this posted or if it has already been posted, but here's a script that works pretty darn good (just follow the readme!).




Awesome script!
## Post #60
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-10-07T08:32:03+00:00
- Post Title: Re: granny engine .gr2 question

Hi, i want ask you about new (civ5, civ revolution) granny format. Can author implement support to your plugins for 3ds max or to converter?
I attached files from Civilization 5 (PC - american_washington_civ5_pc.zip) and from Civilization Revolution (XBox360 - adv_dom_ind_civ_rev_xbox360.rar)
Thank you.

Civilization 5 (PC) - [Download sample](http://www.mediafire.com/?d4199wnhzl6hw9l)
Civilization Revolution (XBox360) - [Download sample](http://www.mediafire.com/?ohjul14lcc677p7)

p.s.: sorry if i'm doing wrong with old topic, but for new research all helping information can be found here.
## Post #61
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2010-12-22T02:05:25+00:00
- Post Title: Re: granny engine .gr2 question

*BUMP*

I was having a problem getting GR2 files into 3dsmax, and the SMDs wouldnt import into the latest milkshape either. I tried to import the MS files into 3dsmax and some worked, and some didn't. problems were either out of memory, or a total crash of 3dsmax.

I created another script to import the MS files, seems to be easier on resources, as some outputed MS files from GRNReader were 50mb+
I suspect that was the reason behind max crashing. the script I made reads the outputed MS piece by piece, instead of trying to load 50MB into the interpreter at once O_o

```
caption:"imports gr2.sm files" \
types: "GRN Reader MaxScript Dump(*gr2.ms)|*.MS|All files (*.*)|*.*|"
if (fsource!=undefined) AND ((doesFileExist fsource)==true) then(
f = fopen fsource "rb"
fext=           getFilenameType fsource
fpath=          getFilenamePath fsource
fbatch=         getFiles (fpath+"*"+fext)
fname=  getFilenameFile fsource
fsize=          getFileSize fsource
st = timestamp() --get start time in milliseconds
clearlistener()
openLog (fpath+fname+"_log.txt") mode:"w" outputOnly:true
print (fname+fext+"\n"+localTime+"\n")
--===========================================================================
undo off(

fn ReadFixedString bstream fixedLen =
(
	local str = ""
	strON=true
	floatnum=false
	for i = 1 to fixedLen do	(
		if strON==true do(
		str0=ReadByte bstream #unsigned
		if str0==0x2E do floatnum=true
		if str0==0x0D do (fseek bstream 1 #seek_cur)
-- 		if str0==0x2C do (fseek bstream -1 #seek_cur)
		if str0==0x5D do (fseek bstream -1 #seek_cur)
		if str0==0x5B do str0=0
		if str0==0x20 OR str0==0x0D OR str0==0x2C OR str0==0x5D
		then strON=false
		else str += bit.intAsChar str0
	))
	if floatnum==true then (str as float) else (str as integer)
)
with redraw off (
	
offsetArray=#()
	
do (
byte1 = readbyte f#unsigned
if (byte1==0x66) then(
byte2 = readbyte f#unsigned
if (byte2==0x6E) then(
byte3 = readbyte f#unsigned
if (byte3==0x20) then(
byte4 = readbyte f#unsigned
if (byte4==0x63) then(
byte5 = readbyte f#unsigned
if (byte5==0x72) then(
byte6 = readbyte f#unsigned
if (byte6==0x65) then(
byte7 = readbyte f#unsigned
if (byte7==0x61) then(
byte8 = readbyte f#unsigned
if (byte8==0x74) then(
append offsetArray (ftell f+27)
skip=false
))))))))) while (ftell f)!=fsize

for x =1 to offsetArray.count do(
vertArray=#()
faceArray=#()
uvwArray=#()
	
fseek f offsetArray[x] #seek_set
vertCount=readFixedString f 8
fseek f 0x09 #seek_cur
faceCount=readFixedString f 8
fseek f 18 #seek_cur
vertCount=readFixedString f 8
fseek f 19 #seek_cur
for y = 1 to vertCount do(
fseek f 13 #seek_cur
idx=readFixedString f 8;fseek f 1 #seek_cur
vx=(readFixedString f 10)*100
vy=(readFixedString f 10)*100
vz=(readFixedString f 10)*100
fseek f 18 #seek_cur
idx=readFixedString f 8;fseek f 1 #seek_cur
tu=readFixedString f 10
tv=readFixedString f 10
tw=readFixedString f 10
fseek f 18 #seek_cur
idx=readFixedString f 8;fseek f 1 #seek_cur
nx=readFixedString f 10
ny=readFixedString f 10
nz=readFixedString f 10
append vertArray[vx,vz,vy]
append uvwArray[tu,tv,tw]
fseek f 3 #seek_cur
	)
for y = 1 to faceCount do(
fseek f 13 #seek_cur
idx=readFixedString f 8;fseek f 1 #seek_cur
fa=readFixedString f 8
fb=readFixedString f 8
fc=readFixedString f 8
append faceArray[fc,fb,fa]
fseek f 3 #seek_cur
)
msh = mesh vertices:vertArray faces:faceArray
msh.numTVerts = vertArray.count
buildTVFaces msh
for j = 1 to vertArray.count     do setTVert  msh j uvwArray[j]
for j = 1 to faceArray.count   do setTVFace msh j faceArray[j]
)


--===========================================================================
Print ("Last Read @ 0x"+((bit.intAsHex(ftell f))as string))
gc()
fclose f
flushLog()
closeLog()
enableSceneRedraw()
Print ("Done! ("+((((timestamp())-st)/60)as string)+" Seconds)") --print time to finish
))) else (Print "Aborted.")

```
## Post #62
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-23T04:07:21+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from mariokart64n
>
> *BUMP*

I was having a problem getting GR2 files into 3dsmax, and the SMDs wouldnt import into the latest milkshape either. I tried to import the MS files into 3dsmax and some worked, and some didn't. problems were either out of memory, or a total crash of 3dsmax.

I created another script to import the MS files, seems to be easier on resources, as some outputed MS files from GRNReader were 50mb+
I suspect that was the reason behind max crashing. the script I made reads the outputed MS piece by piece, instead of trying to load 50MB into the interpreter at once O_o
How to get *.gr2.ms?
## Post #63
- Username: angels85
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 07, 2011 6:22 am
- Post datetime: 2012-01-10T18:11:35+00:00
- Post Title: Re: granny engine .gr2 question

Sorry 


I have a BIG problem 

i export gr2 file for metin2 game online and the new animation need of oversampling "0 s"  but the exporter can be able to only "2,00000 s "

What Could i do?   

Write me soon
Thanks
## Post #64
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2012-01-11T01:15:21+00:00
- Post Title: Re: granny engine .gr2 question

just quick note.
i can not use methods in this thread and i found [tool](http://dl.eve-files.com/media/0801/evegr2toobj.2.zip) for converting gr2 to obj. 
test it on Anno 1404 files, works fine
## Post #65
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-01-11T20:27:41+00:00
- Post Title: Re: granny engine .gr2 question

Hi, recently tried to play with Everquest 2 files, here is the information that it uses granny engine.

Inside vpk archives, there are model files with extensions .draw .anim. .skeleton Both Granny1 & Granny2 viewers doesn't understand them as granny files.

So, did someone managed to import or convert these draw/anim files? 

Here is the example of files
## Post #66
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2012-01-12T08:49:53+00:00
- Post Title: Re: granny engine .gr2 question

Look at this:

[http://eq2.blazlabs.com/](http://eq2.blazlabs.com/)

in his eq2 lib is a loader for .draw / .anim files. a while ago i used this to create a model viewer.

VeRenderMesh.cs for draw files
VeAnimation.cs for anim files
VeSkeleton.cs for skel files

also take a look at Eq2Reader.cs because this class reads the "first part" of every file.
## Post #67
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-01-14T14:21:27+00:00
- Post Title: Re: granny engine .gr2 question

Yes, I have seen this site, but i'm not a programmer  , and the other thing that i'm interesting in possibility to import them in 3d application (3ds max, Blender), not just view them. Or at least to convert them in some format (.dae for example) that can be further loaded to these applications.

And so, if i'm undersstand right, these files are not granny format files?
## Post #68
- Username: delium
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Jun 14, 2010 6:26 pm
- Post datetime: 2012-01-14T17:30:36+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from Axolotl
>
> Yes, I have seen this site, but i'm not a programmer  , and the other thing that i'm interesting in possibility to import them in 3d application (3ds max, Blender), not just view them. Or at least to convert them in some format (.dae for example) that can be further loaded to these applications.

And so, if i'm undersstand right, these files are not granny format files?

well thats not hard.. here is a first screen of my import skript. when it´s ready to use i will release it here.

on screen you can see the mesh of the Dragon Nagafen
## Post #69
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-01-15T09:37:12+00:00
- Post Title: Re: granny engine .gr2 question

Oh, that's will be great. Is your script can inmport only static mesh, or it will be support skinning and animation too?
## Post #70
- Username: angels85
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Dec 07, 2011 6:22 am
- Post datetime: 2012-01-19T18:35:49+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from Tosyk
>
> just quick note.
i can not use methods in this thread and i found tool for converting gr2 to obj. 
test it on Anno 1404 files, works fine

Yes i know =)

I just import model: character + skin and after i apply texture.....but the exporter in gr2 files for new "ANIMATION" is wrong =(

i know that the original export cost 12500 USD o.o and only one Private-server(metin2mester.hu) in the world can be able to export with this proprety (oversampling 0 s).

Would you try to create a tool or modify this exporter, i will be very happy =) ^^

this is the Gr2 model viewer, you can use to see proprety of animation (oversampling -.-" ) xD
## Post #71
- Username: Axolotl
- Rank: advanced
- Number of posts: 44
- Joined date: Sun Nov 07, 2010 7:52 am
- Post datetime: 2012-02-06T21:48:08+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from delium
>
> Axolotl wrote:Yes, I have seen this site, but i'm not a programmer  , and the other thing that i'm interesting in possibility to import them in 3d application (3ds max, Blender), not just view them. Or at least to convert them in some format (.dae for example) that can be further loaded to these applications.

And so, if i'm undersstand right, these files are not granny format files?

well thats not hard.. here is a first screen of my import skript. when it´s ready to use i will release it here.

on screen you can see the mesh of the Dragon Nagafen

Hi, Delium, is there any progress with the script?
## Post #72
- Username: johnwhile
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 2:44 am
- Post datetime: 2012-05-07T14:18:51+00:00
- Post Title: Re: granny engine .gr2 question

HI, i ask here because in whole internet I didn't find someone who know something about granny2 engine.
In a game the animation of model are stored as .Raw format of .Gr2 format, i made a little test to convert gr2 into raw with granny2.dll, i compipled this code in cpp and c:
[http://dl.dropbox.com/u/47659776/scambi ... %2B%2B.zip](http://dl.dropbox.com/u/47659776/scambio/project%2B%2B.zip)

I downloaded from internet the granny sdk to understand something more and to get the header granny2.h. There are write that raw format is a simple decompressed gr2 format for slow pc or to customize their own game but not more... I know that .anim format contain only animation, the 3d mesh are stored in another format (that i already know). I know very well 3dstudio maxscript so isn't a problem import it or also use a c# dll into maxscript.

I read  , but i don't undestand now extract and reimport these animation data.

Can someone help me please ? I don't know which way to turn
## Post #73
- Username: BigRegOne
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 18, 2012 4:32 pm
- Post datetime: 2012-05-18T08:47:30+00:00
- Post Title: Re: granny engine .gr2 question

HI

Here is a link to a topic where an importer / exporter for. GR2 used in Silent Hunter 5 (exports in. OBJ) it is not finished yet, but already very promising : [http://www.subsim.com/radioroom/showthread.php?t=188290](http://www.subsim.com/radioroom/showthread.php?t=188290)
## Post #74
- Username: johnwhile
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 2:44 am
- Post datetime: 2012-05-18T20:29:17+00:00
- Post Title: Re: granny engine .gr2 question

very good work, but can we have a source code purely related to gr2 dll functions to understand also for other works ?
## Post #75
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-05-21T08:39:10+00:00
- Post Title: Re: granny engine .gr2 question

I've been doing quite a bit of work on extracting models and animations from GR2 files. For instance, I've updated code from grnreader, to work with granny2.dll v2.7.0.28, and I've combined grnreader code with code from NWN2Utils v2.0.1 (the source of the Expotron plugin).

For one specific game, I've tested many kinds of 'granny_curve_data' structures, to be able to extract animations properly.
My code includes new definitions for functions like '_GrannyCurveGetDataTypeDefinition', '_GrannyEvaluateCurveAtT', '_GrannyCurveGetDataTypeDefinition', '_GrannyCurveGetKnotCount', '_GrannyCurveExtractKnotValue', '_GrannyCurveExtractKnotValues'.
I've also implemented 'GrannyGetModelInitialPlacement4x4'.

Here's a listing of newly implemented functions (compare grnreader source):

```
//                 I assume this is equal to one in case the parameter is missing,
//                OR the function 'GrannyFindTrackGroupForModel' should be used (Granny SDK **);
//					( bool GrannyFindTrackGroupForModel( granny_animation const * Animation, char const * ModelName, granny_int32 * TrackGroupIndex ); );
//
//*(void**)&_GrannyFindTrackGroupForModel = GetProcAddress(GrannyDLL, "_GrannyFindTrackGroupForModel@12");
//int (__stdcall *_GrannyFindTrackGroupForModel) (int, int, int);
FUNC(bool, GrannyFindTrackGroupForModel, (t_Animations* anim, char* modelName, int* trackGroupIndex));

//------------------------------//
// Sept.04, 2010 (Granny2 SDK);
//granny_data_type_definition const * GrannyCurveGetDataTypeDefinition( granny_curve2 const * Curve );
FUNC(granny_data_type_definition*, GrannyCurveGetDataTypeDefinition, (granny_curve2* curve));
FUNC(void, GrannyEvaluateCurveAtT, (granny_int32 dimension, bool normalize, bool backwardsLoop, granny_curve2* curve, bool forwardLoop, granny_real32 curveDuration, granny_real32 t, granny_triple resultTriple, granny_triple identityVector));

//------------------------------//
// Added, Sept.24, 2011;
FUNC(granny_real32, GrannyCurveExtractKnotValue, (granny_curve2* curve, granny_int32 knotIndex, granny_real32* controlResult, granny_real32 const* identityVector));
FUNC(void, GrannyCurveExtractKnotValues, (granny_curve2* curve, granny_int32 knotIndexStart, granny_int32 knotCount, granny_real32* knotResults, granny_real32 * controlResults, granny_real32 const* identityVector));

//------------------------------//
// Added Sept.06, 2010;
FUNC(void, GrannyFreeFile, (GrannyFile* pFile));
FUNC(int, GrannyCurveGetKnotCount, (granny_curve2* pCurve));	// SDK: granny_int32x GrannyCurveGetKnotCount(granny_curve2 const * Curve);
//FUNC(int, GrannyCurveGetDimension, (granny_curve2* pCurve));	// SDK: granny_int32x GrannyCurveGetDimension(granny_curve2 const * Curve);

FUNC(bool, GrannyFindBoneByName, (granny_skeleton* skel, char* boneName, granny_int32* boneIndex));

//------------------------------//
// Added Sept.25, 2010;
FUNC(void, GrannyGetModelInitialPlacement4x4, (t_Models* model, granny_real32* placement4x4));
```


In the code I'm using there are TWO definitions of the struct 'granny_transform', one for animation data and one for model/skeleton/bone data:

```
struct granny_transform_simple { granny_int32 Type; float v[3]; float q[4]; float m[3][3]; };
```


```
struct granny_transform
{
    granny_uint32 Flags;
    granny_triple Position;
    granny_quad Orientation;
    granny_triple ScaleShear[3];
};
```
## Post #76
- Username: johnwhile
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 2:44 am
- Post datetime: 2012-05-21T10:55:23+00:00
- Post Title: Re: granny engine .gr2 question

i think the best solution is using the tutorial inside the granny sdk and read the granny.chm document, in my opinion using directly the dll's function is too exotica.
I compiled this example with visual studio express because devc++ don't work with granny.h :
[http://www.gamefront.com/files/21735401 ... torial.zip](http://www.gamefront.com/files/21735401/BasicLoadingTutorial.zip)

my personal interest is about the .anim file, at the end of it there are a string : Exported with Granny 2.6.0 SDK etc.... i see that was very similar with raw file ... can someone help me to understand about it ?
## Post #77
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-05-21T20:21:33+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from johnwhile
>
> .. using directly the dll's function is too exotica.
I compiled this example with visual studio express..

I guess tazpn an federico just love exotic code 
One difficulty with 'their' way - used generally - is that sometimes a DLL requires class instantiation, and I've seen a case where this can only be done by starting a game's engine.. Anyway, with respect to their granny2 code, a lot can be learned about what data is actually present inside a GR2 file, and about 'failsafe' methods to retrieve that data.

> Reply from johnwhile
>
> .. the .anim file, at the end of it there are a string : Exported with Granny 2.6.0 SDK etc.... i see that was very similar with raw file ... can someone help me to understand about it ?

Tis is a first for me, I've never seen such a string at the end of a GR2 file.
Furthermore, people have started using the granny2 DLL for model extraction, because it was too difficult to do reverse engineering of the GR2 file format.
## Post #78
- Username: Pesmontis
- Rank: beginner
- Number of posts: 33
- Joined date: Mon Jun 21, 2010 12:10 am
- Post datetime: 2012-05-27T20:50:49+00:00
- Post Title: Re: granny engine .gr2 question

> .. but i don't undestand now extract and reimport these animation data..
Extracting animations only works with 3DSmax 2008 and the NWN 2.0.1 import plugin by tazpn.

tazpn's code for animation data isn't complete and it's specifically written for GR2 animation files from NWN.
That it sometimes works for GR2 file from other games is just sheer luck, because the GR2 format defines an enormous lot of animation structs. It's quite a hassle for a programmer to create code for all that, and to correctly identify and read those structs. Then there's also differences in the file format and DLL functions definitions between v2.5.x, v2.6.x etc.
I don't think that a newer version is backward compatible, so a general GR2 reader would have to check the file version.

An updated version of grnreader is my 'grnreader98', debug v1.4.0.3, which I re-uploaded to [http://tatooinebase.star-fleet.org/UPLO ... .debug.rar](http://tatooinebase.star-fleet.org/UPLOAD/grnreader98.v1.4.0.3.debug.rar). This version was explicitly developed for the game Sacred 2, and a tutorial for it can be found here: [http://darkmatters.org/forums/index.php ... r2-models/](http://darkmatters.org/forums/index.php?/topic/16371-tutorial-importing-and-exporting-gr2-models/). It seems that it also works to some extent for Metin 2, Eve 2 ([http://cargocollective.com/ThomasM/Eve- ... Characters](http://cargocollective.com/ThomasM/Eve-2-Unreal-UDK-Characters)), and for Microsoft Flight ([http://forum.avsim.net/topic/365258-imp ... ge__st__25](http://forum.avsim.net/topic/365258-importing-files-into-pak/page__st__25)).
## Post #79
- Username: Privateer
- Rank: veteran
- Number of posts: 104
- Joined date: Fri Oct 21, 2011 8:33 pm
- Post datetime: 2012-05-30T15:51:02+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from johnwhile
>
> i think the best solution is using the tutorial inside the granny sdk and read the granny.chm document

Admitting you have the SDK could get you in trouble with RAD Games real fast.
Generally they send you a message as a warning.
They may also contact the Admins here. Which is not a good thing.

I've had the 'pleasure' of dealing with persons at RAD Games on issues such as this in the past in several forums.
I'd not be surprised to get another message from them about this being posted in a forum I visit.
## Post #80
- Username: johnwhile
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed Nov 30, 2011 2:44 am
- Post datetime: 2012-06-02T15:01:55+00:00
- Post Title: Re: granny engine .gr2 question

ok.
## Post #81
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-10-23T17:15:31+00:00
- Post Title: Re: granny engine .gr2 question

Anyone can reupload 3ds Max importer (modded by federico) for NWN2 with animation support ?

thx ...
## Post #82
- Username: AZinX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 19, 2014 11:38 pm
- Post datetime: 2014-10-25T06:52:22+00:00
- Post Title: Re: granny engine .gr2 question

Yes. Now find this file is very difficult. But I was able to 
And sadly he is not working for my .gr2 files (

[http://rghost.ru/58702093](http://rghost.ru/58702093)

and Federico is not responding
## Post #83
- Username: federico
- Rank: beginner
- Number of posts: 28
- Joined date: Thu Sep 28, 2006 1:00 am
- Post datetime: 2014-10-25T13:49:09+00:00
- Post Title: Re: granny engine .gr2 question

hello everybody. I had to dig really deep in some backup hdd. I attach to this post all the resources I found. GR2DecMax7 is a compiled version of the 3dsmax import plugin for 3dsMax 7. That's what I ended up using most of the time.

[https://www.mediafire.com/?dbn8jja6fyex8c2](https://www.mediafire.com/?dbn8jja6fyex8c2)
[https://www.mediafire.com/?cng8zvb86l5xq3p](https://www.mediafire.com/?cng8zvb86l5xq3p)
[https://www.mediafire.com/?2mfe4a7ya8627bp](https://www.mediafire.com/?2mfe4a7ya8627bp)
[https://www.mediafire.com/?2mfe4a7ya8627bp](https://www.mediafire.com/?2mfe4a7ya8627bp)

I think you could also browse the old website through archive.org

[https://web.archive.org/web/20111230063 ... vista.org/](https://web.archive.org/web/20111230063051/http://gr2decode.altervista.org/)

Sometimes after that the site was hacked and by that time I didn't have a local copy anymore.
## Post #84
- Username: AZinX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 19, 2014 11:38 pm
- Post datetime: 2014-10-26T07:10:25+00:00
- Post Title: Re: granny engine .gr2 question

Finally I was able to import .gr2 animation into the 3ds max. It turned out it was all in the wrong version of granny viewer, which not corrent convert .grn to .gr2.

And, of course, federico thank's for that links.
## Post #85
- Username: fulgerul46
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Aug 11, 2014 12:15 am
- Post datetime: 2014-11-02T10:20:12+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from federico
>
> hello everybody. I had to dig really deep in some backup hdd. I attach to this post all the resources I found. GR2DecMax7 is a compiled version of the 3dsmax import plugin for 3dsMax 7. That's what I ended up using most of the time.

https://www.mediafire.com/?dbn8jja6fyex8c2
https://www.mediafire.com/?cng8zvb86l5xq3p
https://www.mediafire.com/?2mfe4a7ya8627bp
https://www.mediafire.com/?2mfe4a7ya8627bp

I think you could also browse the old website through archive.org

https://web.archive.org/web/20111230063 ... vista.org/

Sometimes after that the site was hacked and by that time I didn't have a local copy anymore.

Is possible to import gr2 models with skined model?
## Post #86
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2014-11-02T18:21:23+00:00
- Post Title: Re: granny engine .gr2 question

Is there any way to get 3DSMax 7 working on Win 7 64 bit? Or a plugin for more recent versions of 3DSMax or blender? Or maybe a different method to get gr2 models into better 3d programs. 

I've looked around the net and as far as I can tell Max 7 won't work with Win 7 64bit and nobody ever released another way to work with gr2 models. Figured I'd ask here just in case someone here knows something.
## Post #87
- Username: deltaone
- Rank: beginner
- Number of posts: 37
- Joined date: Sat Feb 19, 2011 8:18 am
- Post datetime: 2014-11-03T12:55:40+00:00
- Post Title: Re: granny engine .gr2 question

> Reply from ssringo
>
> Is there any way to get 3DSMax 7 working on Win 7 64 bit? Or a plugin for more recent versions of 3DSMax or blender? Or maybe a different method to get gr2 models into better 3d programs. 

I've looked around the net and as far as I can tell Max 7 won't work with Win 7 64bit and nobody ever released another way to work with gr2 models. Figured I'd ask here just in case someone here knows something.
Just use virtual machine with Windows XP ...
## Post #88
- Username: AZinX
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Oct 19, 2014 11:38 pm
- Post datetime: 2014-11-08T12:23:41+00:00
- Post Title: Re: granny engine .gr2 question

I have worked on windows 7 64 bit in 3ds max 7. But, anyway, correctly imported into max from .gr2 does not work.  Granny Viewer is almost always not correctly converted .grn to .gr2 model's skeleton therefore the animation of these parts when importing it from .gr2 files are not correctly displayed.

Very, very sad...
## Post #89
- Username: trussive
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 06, 2019 5:51 am
- Post datetime: 2019-11-30T14:44:53+00:00
- Post Title: Re: granny engine .gr2 question

hey, sorry to bump this, but does anyone have the link to the 3ds max 7 plugin? the mediafire link is gone, and I am desperate.
## Post #90
- Username: Henchman800
- Rank: mega-veteran
- Number of posts: 308
- Joined date: Sat Nov 17, 2018 12:00 am
- Post datetime: 2019-12-01T03:36:58+00:00
- Post Title: Re: granny engine .gr2 question

> hey, sorry to bump this, but does anyone have the link to the 3ds max 7 plugin? the mediafire link is gone, and I am desperate.

Maybe my snocross (arcade) guide helps you. This workflow convertes .gr2 files to .obj and extracts their textures....at least for me   

[viewtopic.php?f=16&t=21279&p=157147&hil ... ss#p157147](https://forum.xentax.com/viewtopic.php?f=16&t=21279&p=157147&hilit=Snocross#p157147)

Let me know if it helped

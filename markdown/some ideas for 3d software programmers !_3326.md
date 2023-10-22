## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-01-25T13:05:26+00:00
- Post Title: some ideas for 3d software programmers !

I have some ideas for 3d software programmers !

1:  I feel developing an application that can graph collection of 3d models in form of thumbnail and arrange them on count of vertex , polygons, volume, surface, and other properties of 3d objects is necessary.

2: an application that can with it easily modify 3d objects so that from 3d extracted models of games create 
new objects (functions like split combine appling math formulas on vertex )that anyone can't  recognize the 3d model achieved from what game ?

If you have other ideas please add to this article !

and tell me what is your answer about my ideas ? thank
 I am not a professional 3d pogrammer yet else i do some of them !
## Post #2
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-01-26T14:27:16+00:00
- Post Title: some ideas for 3d software programmers !

the 1st thing makes no sense to me.
It started sounding like you wanted to be able to view models as thumbnails but then suddenly it changed to organisation per vertex and i got confused. Perhaps you can detail this a little more.

2: a program that makes it possible to edit 3d models extracted from games?
You mean like...every 3d software...as thats their job...to edit and create things, u cant really create a program that supports ALL game formats as thats too many really and ontop of that even if a program supports the models it doesnt mean the models would be useable, they could have reversed normals, body parts upside down, a missing face, no texture, all sorts of things.

I am a 3d programmer but im not entirely sure what your trying to say, or if you realise the ammount of work that goes into making a 3d app, its not 20 minutes work, to create something with less options...(milkshape for example) can take months even years.

If you could elaborate on what you mean thatd be great as i think i might missunderstand some of this.
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-01-26T15:26:42+00:00
- Post Title: some ideas for 3d software programmers !

deep exploration generates thumbnail views of files inside the program its self.
you could just arrange them bye size and get almost the same effect you are going for in sorting them.
I would suggest looking at the source code of a current viewer of some format and going from there.
## Post #4
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-01-27T12:43:33+00:00
- Post Title: some ideas for 3d software programmers !

thank dear lionheartuk for your answer *
i try to tell my think clearly !
1: about suported format the target application must suport only one standard format like "3ds" because with
other appliation that can extract 3d models from games can easily convert extracted models to it .

2: my purpose from editing models is some capability that no exist in professional softwares like maya and 3dmax but an automatic process can executed on lots of models at the same time according to some option and simple expression that amateurs easily can understand it [ example : i have a collecton of 100 body models i want to take apart all of them to their heads,hands,foots,.... and in the end combine  head of one of them with hands of an other model randomly so that the new model it is not recognizable from wich game extracted ? or another example i am going to position all the vertexs in integer from decimal for all of my models this cause models appears strange and more simple !] 
 try to understand excuse me my main language it is not english 
3: thumbnail view and arrangement according count of vertex , polygons , volume , surface will very helpful
for creating composite objects .
## Post #5
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-01-27T13:03:16+00:00
- Post Title: some ideas for 3d software programmers !

> Reply from shekofte
>
> thank dear lionheartuk for your answer *
i try to tell my think clearly !
1: about suported format the target application must suport only one standard format like "3ds" because with
other appliation that can extract 3d models from games can easily convert extracted models to it .

2: my purpose from editing models is some capability that no exist in professional softwares like maya and 3dmax but an automatic process can executed on lots of models at the same time according to some option and simple expression that amateurs easily can understand it [ example : i have a collecton of 100 body models i want to take apart all of them to their heads,hands,foots,.... and in the end combine  head of one of them with hands of an other model randomly so that the new model it is not recognizable from wich game extracted ? or another example i am going to position all the vertexs in integer from decimal for all of my models this cause models appears strange and more simple !] 
 try to understand excuse me my main language it is not english 
3: thumbnail view and arrangement according count of vertex , polygons , volume , surface will very helpful
for creating composite objects .

Well i kinda understand mostly what you mean.
But i dont think a whole new program is good i think it would be much faster and easier to just Create a MEL script in maya or  PYTHON script in Blender or a script in XSI or MAX (not sure what scripting languages those are as ive never used the languages within the programs...Ive only used the programs and plugins ...unfortunatly).

Do you not think this would be faster, to create a program that your asking is kinda complicated though anyways, even as a plugin, as seperating for example 100 models into seperate parts if they are all the same format isnt too bad, but not all games have the model in seperate Parts, in fact many games use 1 part models with really good rigs, of course this isnt true for all games, Final fantasy VII for example used diffrent body parts but rigged, whereas a game like MGS2/3/4 uses 1 single mesh for a model, in which case having an automated program figure out what parts to extract is difficult, unless you went in BEFOREHAND and took apart the models and named the body parts yourself, otherwise the program wouldnt know what to search for and wouldnt work.

Dont worry about the english^_^ mines pretty screwed...and i AM english...
## Post #6
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-03-22T08:48:42+00:00
- Post Title: some ideas for 3d software programmers !

ANIMATION CURVE MIXER
animation curve mixer is very similar to an audio mixer .
------------------------------------------------------------
for example this is the list of games that released by VALVE company :
Half-Life Team Fortress Classic	Counter-Strike	Half-Life: Opposing Force Deathmatch 
Classic Day of Defeat Ricochet Counter-Strike: Condition Zero Half-Life: Source Half-Life 2	Half-Life 2: Deathmatch Counter-Strike: Source Day of Defeat: Source Half-Life 2: Episode One The Orange Box	      Half-Life 2: Episode Two Portal	Team Fortress 2	Left 4 Dead
--------------------------------------------------------------
around 20 games,if we suppose that each games contains 200 animatio files and each file 10 animation curve
---> 20 X 200 X 10 = 40000 , we have 40000 animation curve .
--------------------------------------------------
the purpose of using animation curve mixer is that we mix such animaton curves with together by some effects and in the end achieve new animation curves(in other word animation curve mixer is a motion builder)
-------------------
I predict the GUI of animation curve mixer in the following chart :
1: skeleton viewer --> consist of some  lines and points as joints and skeleton
2:shows position of an animation curve on the GUI
3:each joint has a main curve , formula of main curve X= zigma x , Y=zigma y , Z=zigma z
you can add effects to each curve , for example instead of equalizer in an audio mixer you can use an effect for setting of curve scale , or reverse , and .........
-------------------
programming process:
the development of this software dos not correlate to mastering of  3d functions or GL , DX ...
it uses simple math functions
but you should be master on some file structures !
----------------
I guess you understood my purpose..................
[mix.JPG](https://xentaxbackup.github.io/file/1934_mix.JPG)
## Post #7
- Username: shekofte
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-03-22T12:02:34+00:00
- Post Title: some ideas for 3d software programmers !

you want to use Motion builder?

[http://usa.autodesk.com/adsk/servlet/in ... id=6837722](http://usa.autodesk.com/adsk/servlet/index?siteID=123112&id=6837722)
## Post #8
- Username: lionheartuk
- Rank: double-veteran
- Number of posts: 749
- Joined date: Wed May 17, 2006 5:55 am
- Post datetime: 2009-03-24T23:51:01+00:00
- Post Title: some ideas for 3d software programmers !

the creation of a 'motion builder' as u call it isnt NEARLY as simple as A: that random screenshot or B: your description.

Also you are still missing my main point from before...this means that it has to be CONSTANTLY updated with new formats...and ontop of that, most games DONT let you inject new animations, and most of us here, have been through many games but VERY FEW of those games we can rip ANIMATIONS from, let alone inject them back in...
Some games dont even USE bones, they use a different type of thing (there is a name for it i suppose...but i dont know it).

The premise of your ideas are "cool" but thats kinda where it ends for me, i can understand that these ideas could be really amazing if they worked...but the IF factor is so huge its unbelievable. INDIVIDUALS dont build games normally, its companies, and companies work the animations and everything else.

If i had A: the skill/talent or B: the time, then i would make something like this myself, but even if i was awesome (which im clearly NOT) by the time i had it to a standard reasonable enough to SHOW anyone this forum or topic would probably be closed anyway.

Im not saying these ideas are impossible, im just saying that research into programming and everything a little and you will see that these requests are awfully complicated and time consuming for even a professional.
## Post #9
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-03-29T10:39:10+00:00
- Post Title: some ideas for 3d software programmers !

@lionheartuk , you mentioned to some tips that I did not know so far , thanks Deft !
## Post #10
- Username: potemkis
- Rank: beginner
- Number of posts: 24
- Joined date: Sun Mar 01, 2009 2:11 pm
- Post datetime: 2009-05-19T04:33:19+00:00
- Post Title: some ideas for 3d software programmers !

3ds Max uses MaxScript. The syntax is fairly straight forward (I'm trying to learn it right now). I'm actually trying (and pulling my hair out in the mean time) to write a script to import Dawn of War 2 models into 3ds max- damn Havok stuff keeps getting in the way...
## Post #11
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2009-05-19T12:39:33+00:00
- Post Title: some ideas for 3d software programmers !

> Reply from potemkis
>
> 3ds Max uses MaxScript. The syntax is fairly straight forward (I'm trying to learn it right now). I'm actually trying (and pulling my hair out in the mean time) to write a script to import Dawn of War 2 models into 3ds max- damn Havok stuff keeps getting in the way...
as i see , dear potemkis , your request don related to this topic , you should open a topic ...........

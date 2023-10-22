## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-12-19T22:13:38+00:00
- Post Title: Counterstrike Source Models

Call me dumb, but has anyone got an easy way to adapt the player models of Counterstrike: Source? I've been looking with G-ay-oogle, but found nothing as yet.
## Post #2
- Username: omfgpota
- Rank: advanced
- Number of posts: 67
- Joined date: Tue Apr 13, 2010 9:52 pm
- Post datetime: 2010-12-19T22:51:12+00:00
- Post Title: Counterstrike Source Models

MrAdults Noesis  can support counterstrike source *.smd and *mdl format, be sure to get the latest version  

cheers
## Post #3
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-12-20T08:02:29+00:00
- Post Title: Counterstrike Source Models

You can also do it the old way. 
SourceSDK + [Cannonfodder's MDL Decompiler](http://www.chaosincarnate.net/cannonfodder/cftools.htm) + [GCFScape](http://nemesis.thewavelength.net/index.php?p=26).
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-12-20T08:30:18+00:00
- Post Title: Counterstrike Source Models

Looking good there. Thanks! Now, basically I want to change the faces of the models primarily, and I've used a tool called FaceGen to grab a realistic face and change it into a model. I guess now I've got to be a hardcore 3ds max user to do that, right? Then I'll have to read up on the subject.
## Post #5
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-12-20T16:42:55+00:00
- Post Title: Counterstrike Source Models

In this case, you should do it the old way. You need to decompile your CS model, not simply convert it with Noesis.
You don't have to be a hardcore Max user.
The whole process in short is a matter of decompiling the model, importing the reference.smd into Max, swapping the head with a custom one, exporting back to SMD and recompiling the model.
## Post #6
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-12-20T17:07:54+00:00
- Post Title: Counterstrike Source Models

You might wanna reduce the amount of polygons in your head tho as face-gen heads have a lot more polygons than a CS model head i believe. 
Altho if you really wanted to go down that route and wanted to have a whole character model in the same kinda quality then you would be better looking into a program called "Poser" rather than face-gen,  its basically a character designer and animator and uses models of similar quality and better than face-gen. In fact the Poser head creator works almost identical to the face-gen head creator, it just means you can easily and quickly create whole characters rather than just heads. I use both programs often so ive seen the comparisons when loaded into a 3d editor like max or light-wave.

EDIT:

Just had a look at the poly counts for the different models.  i looked at a couple of TF2 characters ( the Heavy and the scout to be precise ) they are similar quality to CS models, the head was around the 2000 polygon mark, for a Poser 4 head ( we are now using poser 8 so a p4 head is considered low quality ) the poly count is around 4000 polygons, a poser 8 head is around 8500 polygons (not including the eyes, inner mouth or hair etc, just the skin)  and a face-gen head comes out at about 6100 polygons ( and bearing in mind ALL face-gen heads originate from the same base model so they will all have the same poly count )

It just gives you an idea of what you will be dealing with, depending which route you decide to take, quality may or may not be a factor ( a lot of detail these days is faked with Normal maps / Bump maps ) either way this might give you a little more of an option when it comes to making your CS character.

Good luck and have fun.

Nobby.
## Post #7
- Username: greywaste
- Rank: n00b
- Number of posts: 10
- Joined date: Fri Jul 30, 2010 5:10 am
- Post datetime: 2010-12-21T00:53:56+00:00
- Post Title: Counterstrike Source Models

Alternatively, if you have fallout 3 (noticed the avatar) or oblivion you could use the more limited functionality to produce a head in game and then grab that with 3dripper dx.  The fallout 3 head is about 2.3k polys.

But to go straight from facegen, I seem to remember it has obj export, could do that with your finished head take it into max/blender and it'd be a matter of rescaling, positioning and lowering poly count if needed and rigging I guess and then what Firsak posted.  I've never rigged on the valve skeleton though only Bethesda games ones  and custom heads are trickier than bodies/armor.

Hope someone with CSS experience can help more.
## Post #8
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-21T02:59:12+00:00
- Post Title: Counterstrike Source Models

What do you need help with? Your last reply doesn't really say you have a problem, just that you have to try a few things and see how that goes. As for my opinion on the whole idea, I don't think it'll work well. Each the programs are going to create weird meshes that will be out of proportion with the css models, and the css models are actually already out of proportion (Short legs, long arms). But share your results/findings!
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-12-21T18:42:02+00:00
- Post Title: Counterstrike Source Models

Well, I'm thinking that it won't be too easy to replace a head with a custom one, am I right?
## Post #10
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2010-12-21T18:51:06+00:00
- Post Title: Counterstrike Source Models

> Reply from Mr.Mouse
>
> Well, I'm thinking that it won't be too easy to replace a head with a custom one, am I right?
There is nothing difficult in it, but judging from the fact that you're asking this kind of question - you don't have much (if any) experience with 3dsMax. So if this is true - it might be a difficult process for you.
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-12-21T19:12:57+00:00
- Post Title: Counterstrike Source Models

You got that right, I have no experience whatsoever with 3ds max.
## Post #12
- Username: Nobby
- Rank: veteran
- Number of posts: 109
- Joined date: Thu May 13, 2010 7:35 am
- Post datetime: 2010-12-23T00:21:06+00:00
- Post Title: Counterstrike Source Models

The people going on about having to rescale and reposition the head to make it work right make it sound like that's gonna be a lot of work. its really not.  rescaling, is what it says...  your gonna adjust the scale of the object,  that's fairly easy to do (in any 3D app, its one of the most common functions available to you) you just click the scale button and then drag on the object to make it bigger or smaller.  Same with repositioning, thats just another word for move/rotate  which is also one of ANY 3d apps common functions, in max  all 3 of those functions will be located next to each other, probably in the top toolbar ( it is in max 2010 i know that ). This is what they should look like..  

It's just going to be a case of..  Load your CS man, load your face-gen/poser head, select scale, select your face-gen head, scale it down to a rough same size, Move and rotate the model closer to the CS model's head, scale a bit more if need be. Each time you scale down the one model to match the other, zoom in again that way you have maximum view of both objects at once. 
Then once you have it in the same place and same size, delete the old head and you should be left with a CS body with a Face-gen head on it. What you have to do to get it back into the game afterwards i have no idea, im assuming you have looked into that already, or are planning to    But yeah really its just a case of scale it down, move it into position, then fine tune the scale and positioning till it matches up, should take all of about 10 mins, once you locate the buttons to match the two objects together... It really is that simple to do  

In regards to 
> Reply from invisghost
>
> I don't think it'll work well. Each the programs are going to create weird meshes that will be out of proportion with the css models, and the css models are actually already out of proportion
Actually the models from Face-gen and poser are very clean models, nothing weird about them and yes they will be out of proportion, most models are. Hardly ever do two games or two 3d apps run at the same unit of scale ( the exception to that rule is if your using real world units of size like meters or inches ).

Here's a quick comparison between a face-gen model and a TF2 model ( they are similar levels of detail to a CS model, plus i don't have CS to get a model comparison anyway.. )

The TF2 model... [](http://img84.imageshack.us/i/tf2a.jpg/)  The Face-gen model....[](http://img571.imageshack.us/i/facegen.jpg/)

Nothing weird about either to be honest, just the face gen has a lot more polygons in it and altho you can't really tell from those images, the face-gen model is a lot bigger, but that just means you have to do a bigger down scale ( no harder than doing a small scale adjustment )
## Post #13
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-23T04:10:10+00:00
- Post Title: Counterstrike Source Models

in facegen you can chose quality of head: middle, high, low

with small manipulations you can also use base head meshes from oblivion.
## Post #14
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2010-12-23T04:21:10+00:00
- Post Title: Counterstrike Source Models

All I'm saying is it'll be difficult to do nicely when you're new to Max (or Maya). Yes the facegen will end up having more polygons in the end because of triangulation (which the tf2 head already had) but it won't be unusual to have a high poly face, if any part of the model was to be high poly it would most likely be the head. You will have to rig it up again but that should be simple enough since you can just bind it to the head node and call it a day.
## Post #15
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2010-12-23T05:35:50+00:00
- Post Title: Counterstrike Source Models

I think for "just" user of 3ds max problem is not in getting good model of the head or count of the polygons, but in skining of the face with bones.

btw, in facegen you can using several types of heads:

[](http://i019.radikal.ru/1012/df/274180b9ffc2.jpg) [](http://i025.radikal.ru/1012/29/c87f2c17370f.jpg)
[](http://i040.radikal.ru/1012/24/76d01b165e19.jpg) [](http://i028.radikal.ru/1012/dd/c17186e17a5c.jpg)
[](http://s013.radikal.ru/i323/1012/6c/71b42847bf75.jpg) [](http://i048.radikal.ru/1012/7c/d43a0df6cb2a.jpg)
[](http://s48.radikal.ru/i122/1012/26/4541810fd09d.jpg) [](http://s011.radikal.ru/i317/1012/30/5f1e43830b81.jpg)
[](http://s49.radikal.ru/i125/1012/d1/d43cbf2c4387.jpg) [](http://s008.radikal.ru/i303/1012/90/b73a488d21f4.jpg)

## Post #1
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-01T08:13:05+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Hi, 

Looking around to see who can do the following. Change the head of a character into another, real person's face in a game like Counterstrike:Source or other 3D game. Using FaceGen [http://facegen.com/](http://facegen.com/) I have created a 3d model of the person's head using a photograph. The idea is to get this head on a character in a game, and release this mod as a PR stunt. 

Is there anyone with this type of experience who can do that ?
## Post #2
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-09-01T09:07:45+00:00
- Post Title: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> Hi, 

Looking around to see who can do the following. Change the head of a character into another, real person's face in a game like Counterstrike:Source or other 3D game. Using FaceGen http://facegen.com/ I have created a 3d model of the person's head using a photograph. The idea is to get this head on a character in a game, and release this mod as a PR stunt. 

Is there anyone with this type of experience who can do that ?
Maybe I can do that, but aren't Facegen heads a little overkill?
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-01T11:29:07+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Because of too many polygons? Is there an easier way to transform photos of faces into good models? 
What would you suggest?
## Post #4
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2012-09-01T15:03:05+00:00
- Post Title: Change head of 3d-game characters as PR stunt

since its CS, you can use the SDK to compile a new model. You can decompile the files with cannonfodder's decompiler I believe. which will attempt to export the source files used by the SDK compiler.

SMD will be the mesh, and QC will be the script file which holds information on linking files or configuring physics and animation related items.

So as an overview you need to;
-Decompile
-Import the SMD into a 3D editor.. stick on the head
-Export to SMD
-Clean QC file
-Compile QC and SMD with Offical SDK Compiler

The compiler of course is just taking all these ascii formats and converting them into Valve's Binary formats optimized for their engine.

The text formats are so basic that they can be easily reverse and plugins created for any 3d editor or what not.. Don't know where they offer that actual format specs for the acsii formats though.

On the other topic, you want to do a very specific thing on the model editing side, which is to use a face gen model. on a separate note, you can also use 123d CATCH to take a exact scan of your face. I posted about this on another site [link](http://forums.kc-mm.com/index.php?topic=45788.msg937538#msg937538)

Regardless of how you obtain a 3D head scan, or generation. the polygon count will likely be pretty high. Source is pretty flexible though if its not too much you'll be able to get away with it. However 3dsmax has a modifier called ProOptimizer which can reduce the polygon count without losing the mapping information for your textures.

Anyway I would offer to do this for you, but its been like 6 years since I did this stuff.. so I can only imagine it would be a train wreck if I tried. your best off asking someone still active in the CS modding scene. The SDK is always getting changed, thats why the way I use to do things are likely out of date. I'm speaking in terms of the SOURCE SDK and how you compile models for the engine.
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-01T20:49:05+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Here is the output I got from facegen as a first to use. I wonder if you can make some sense of that. Honestly, I have no experience with 3d modelling, so simply sticking a head on...I would not know where to begin.
[face.zip](https://xentaxbackup.github.io/file/5743_face.zip)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-02T00:27:46+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Wait.

Who's head did you base it on? Lol
## Post #7
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-02T04:13:12+00:00
- Post Title: Change head of 3d-game characters as PR stunt

I'll work on this for you. I should be able to do it relatively easily. I'll be putting it into Fallout: New Vegas. I'll post an in-game pic within a day as long as I don't run into any snags.

EDIT:

Here you go. I can make it so the character has hair, but it was quicker to just equip a helmet on him. I put him in Charlie's armor from Binary Domain, the AvP Colonial Marine armor, and the marine armor from Crysis 1. (Thanks to chrrox for the Noesis plugin for Binary Domain, and Revelation for the Crysis and AvP plugins.) In Fallout: New Vegas...

 

Let me know what other kind of shots you need. Specific armor requests? Location or pose requests? I'll be happy to oblige. I'm glad to give something back to the forums here.
## Post #8
- Username: onelove1210
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T09:04:22+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Awesome! Brilliant!

The head is from one of our right wing politicians in The Netherlands, and we are heading for elections on the 12th of September. I thought it a nice idea to have some of the parties leaders in a game going for each other's throat in a match of counterstrike or similar, but perhaps putting them as opposing forces in Fall-Out: New Vegas or so is also a nice option. Isn't there an arena of sorts we could pit them against eachother? I can work on the other faces.

Would be terrific if we could release a mod for anyone to install in the game
## Post #9
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-02T13:00:01+00:00
- Post Title: Change head of 3d-game characters as PR stunt

A friend of mine is very good at posing people and putting them in fighting scenarios. He recently took Chris Redfield and Duke Nukem, put them in an arena, and took a series of screenshots that had them fighting each other. It was pretty neat. So, if you're able to make another face, I can pit them against each other no problem. Or, I can even put the faces on, say, Caesar in the game 

EDIT: Here are a collection of two battles he posed with characters I rigged for the game: [http://www.mediafire.com/?4wd5ck918aj3cw2](http://www.mediafire.com/?4wd5ck918aj3cw2)
## Post #10
- Username: onelove1210
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T13:41:57+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Cool, I'll work on some more faces. Would be swell if players could select to play as one politician fighting the others, by his or her choice.   If you have a file I can use in my copy of Vegas to take a look at the model you created with the previous face, please drop me an email at [mr.mouse@xentax.com](mailto:mr.mouse@xentax.com)
## Post #11
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-02T14:34:56+00:00
- Post Title: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> Cool, I'll work on some more faces. Would be swell if players could select to play as one politician fighting the others, by his or her choice.   If you have a file I can use in my copy of Vegas to take a look at the model you created with the previous face, please drop me an email at mr.mouse@xentax.com

Sure, no problem. The way I have the head set up is that it can be equipped and carried in inventory like any headgear. It just replaces the character's head.
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T18:18:13+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Okay, cool. Would be nice to have them all in one game and the player can then select who he represents, and battle the others if he wants in some kind of arena, if at all possible. Here's the second face, from Mr. Rutte. I also added the photo I used to generate the first, Mr. Wilders.
[face_rutte.zip](https://xentaxbackup.github.io/file/5745_face_rutte.zip)
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T19:21:14+00:00
- Post Title: Change head of 3d-game characters as PR stunt

And to go on: here's Mr. Samsom.
[samsom.zip](https://xentaxbackup.github.io/file/5746_samsom.zip)
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T19:53:04+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Mr. Roemer.
[roemer.zip](https://xentaxbackup.github.io/file/5749_roemer.zip)
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T20:28:41+00:00
- Post Title: Change head of 3d-game characters as PR stunt

Mr. Buma, teeth don't fit nicely, but it'll do.
[buma.zip](https://xentaxbackup.github.io/file/5750_buma.zip)
## Post #16
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-02T20:39:18+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> Mr. Buma, teeth don't fit nicely, but it'll do.

Is he not favorable? LOL
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-02T21:06:57+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Favourable?  For election? 

Anyway, here's Mr. Pechtold. I may add just one or two more tomorrow.
[pechtold.zip](https://xentaxbackup.github.io/file/5751_pechtold.zip)
## Post #18
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-03T04:03:07+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
>  Favourable?  For election? 

Anyway, here's Mr. Pechtold. I may add just one or two more tomorrow.

Model for CS 1.6, not CSS, because pic is CS 1.6 mod CSS 
Sorry because ugly and big head  ( i'm lazy to scale )



Link: 
```
http://www.mediafire.com/?p2w6pm42d9c2166
```

Sorry about my bad Eng
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-03T04:43:46+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

haha, cool, can you do more people ( and scale  ) How does one make the hair? Facegen sadly doesn't do that.
## Post #20
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-03T11:45:19+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> haha, cool, can you do more people ( and scale  ) How does one make the hair? Facegen sadly doesn't do that.

I just can do this  

edit: maybe it will violation
## Post #21
- Username: huckleberrypie
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-03T16:26:30+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Would be cool to release both (or even more games) mods, and get some striking poses. You know, this Mr. Wilders is a fool, so he can be portrayed like one. The mods could have the theme: "They play with us, we play with them". 

A Friday release ?
## Post #22
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-09-04T08:17:05+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

CSS    

[http://i771.photobucket.com/albums/xx35 ... 17-187.png](http://i771.photobucket.com/albums/xx353/trishty/hl22012-09-0414-59-17-187.png)
[http://i771.photobucket.com/albums/xx35 ... 27-140.png](http://i771.photobucket.com/albums/xx353/trishty/hl22012-09-0414-59-27-140.png)
Optimize to 3500 triangles
He have a little bug, when he dead the anim turn to T-pose. Maybe i can fix it
## Post #23
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-04T08:48:56+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Lol! Coming along great!!
## Post #24
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-05T21:36:44+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Three mods in the making: 

Fallout: New Vegas (practically completed) 
Counterstrike 1.6 (getting there)
Counterstrike Source (getting there)

There is still time to do even more, if anyone feels like it. The above ones are going to rock ! 

I have another version of the Roemer lookalike, getting the ears a bit better:
[roemer2.zip](https://xentaxbackup.github.io/file/5768_roemer2.zip)
## Post #25
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-05T21:54:50+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Here's a look at my work on all six. These photos all show armors made thanks to plugins from chrrox and revelation. This shows models from Syndicate, The Force Unleashed, Star Wars Kinect, Crysis 2, and Hellgate London. I really appreciate all the tools these guys provide. I'm glad to give something back.
## Post #26
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-05T22:09:01+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Great, great work! Knocks me off my feet!
## Post #27
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-06T21:48:21+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

First mod released. The Fallout:New Vegas one. [viewtopic.php?f=22&t=9608](http://forum.xentax.com/viewtopic.php?f=22&t=9608)
We wait for the Counterstrike mods with eager anticipation!
## Post #28
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-09-07T00:55:30+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Mind if I do GTA IV peds from these Dutch politicians?
## Post #29
- Username: dragbody
- Rank: veteran
- Number of posts: 126
- Joined date: Tue Sep 20, 2011 11:33 am
- Post datetime: 2012-09-07T01:19:49+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from huckleberrypie
>
> Mind if I do GTA IV peds from these Dutch politicians?

I believe Mr. Mouse would like that very much. Get started!
## Post #30
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-07T05:21:12+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

You're free to do what you like!
## Post #31
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-09-07T12:28:38+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
>  You're free to do what you like!

K, will do lol. Just give me the exploitable heads and I'll take care of the rest.
## Post #32
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-07T12:49:56+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from huckleberrypie
>
> Mr.Mouse wrote: You're free to do what you like!

K, will do lol. Just give me the exploitable heads and I'll take care of the rest.

Sent you an email with the models.
## Post #33
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-07T15:32:08+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Model for CS 1.6 ( very ugly ) (








```
http://www.mediafire.com/?33udqnyn6js57sa
```


if they have errors, just tell me  i will fix them as soon as possible

 PM for pass and sorry about my bad Eng
## Post #34
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-09-08T00:32:14+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Trishty
>
> CSS    
Optimize to 3500 triangles
He have a little bug, when he dead the anim turn to T-pose. Maybe i can fix it

Lol how'd you optimise the head to just 3K polygons? I can use Optimize or ProOptimizer on Max, but it causes the model geometry to go fugly.
## Post #35
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-08T07:58:45+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from onelove1210
>
> Model for CS 1.6 


if they have errors, just tell me  i will fix them as soon as possible

 PM for pass and sorry about my bad Eng

They look great! Three questions:
1. Can you remove the facial gear of CT to show the faces? 
2. I noticed one CT waving his weapon as a sort of bug when he jumped
3. The Wilders face of the terrorist: his head seems rather smaller compared to the others and also compared to his body, is that fixable? 

Other than that: great models, cool to put them in a never ending fight like that!
## Post #36
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-08T08:53:58+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> onelove1210 wrote:Model for CS 1.6 


if they have errors, just tell me  i will fix them as soon as possible

 PM for pass and sorry about my bad Eng

They look great! Three questions:
1. Can you remove the facial gear of CT to show the faces? 
2. I noticed one CT waving his weapon as a sort of bug when he jumped
3. The Wilders face of the terrorist: his head seems rather smaller compared to the others and also compared to his body, is that fixable? 

Other than that: great models, cool to put them in a never ending fight like that!

1. If i do that, it will terrible, 'cause some faces i scale too much  so i hide them in CT's gear  in other way, we need to remake them  cannot fix 
2. sorry i will fix it soon 
3. just his hair make his face small 

sorry about my bad Eng
## Post #37
- Username: huckleberrypie
- Rank: ultra-veteran
- Number of posts: 351
- Joined date: Mon Apr 26, 2010 1:51 pm
- Post datetime: 2012-09-08T11:06:24+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

I only did Geert for IV, but at least he looks 'swell enough ingame:




He even fought alongside Kit Kittredge:


I'll PM Mr. Mouse with links to the ped model in a bit.
## Post #38
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-08T11:12:33+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

huckleberrypie, that looks great!
## Post #39
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-08T20:42:38+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

[viewtopic.php?f=22&t=9608&p=78548#p78548](http://forum.xentax.com/viewtopic.php?f=22&t=9608&p=78548#p78548) Second mod out: the first rough version of a Counterstrike 1.6 mod.  Thanks to onelove1210!
## Post #40
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-09T02:21:42+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> viewtopic.php?f=22&t=9608&p=78548#p78548 Second mod out: the first rough version of a Counterstrike 1.6 mod.  Thanks to onelove1210!

FIX 


1. and 2. fixed 

Link: [http://www.mediafire.com/?2mkagym2fgx1p5c](http://www.mediafire.com/?2mkagym2fgx1p5c)
## Post #41
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-09-09T04:09:05+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Are these being distributed to the relevant game communities?
I did a search on google but didn't see anything about dutch politicians in CS
## Post #42
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-09T07:18:54+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from onelove1210
>
> 

1. and 2. fixed 

Link: http://www.mediafire.com/?2mkagym2fgx1p5c

Wow! Great, i will update the post!
## Post #43
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-09T07:19:43+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from finale00
>
> Are these being distributed to the relevant game communities?
I did a search on google but didn't see anything about dutch politicians in CS

Which communities would you suggest?
## Post #44
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2012-09-09T08:30:25+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

CSS complete   

dl link in PM

@huckleberrypie: i use ProOptimizer 30% keep texture, uv
## Post #45
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-09T10:47:48+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Brilliant! I tried it, it looks very cool!
## Post #46
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-09T19:27:25+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

[viewtopic.php?f=22&t=9608](http://forum.xentax.com/viewtopic.php?f=22&t=9608) CS: Source mod is released !!
## Post #47
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-09T19:43:45+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

[viewtopic.php?f=10&t=9608](http://forum.xentax.com/viewtopic.php?f=10&t=9608) And the GTAIV Wilders mod is released
## Post #48
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-11T11:18:41+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

Gamebanana: [http://gamebanana.com/css/skins/120627](http://gamebanana.com/css/skins/120627)
## Post #49
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2012-09-11T11:38:09+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

[http://www.duimschroef.nl/2012/09/zin-o ... an-gewoon/](http://www.duimschroef.nl/2012/09/zin-om-politici-dood-te-schieten-dat-kan-gewoon/)

and 

[http://www.gamer.nl/redactiepost/377886 ... -new-vegas](http://www.gamer.nl/redactiepost/377886/de-nederlandse-politiek-in-fallout-new-vegas)

Share as much as you can!!!
## Post #50
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2012-09-11T13:07:36+00:00
- Post Title: Re: Change head of 3d-game characters as PR stunt

> Reply from Mr.Mouse
>
> 

http://www.duimschroef.nl/2012/09/zin-o ... an-gewoon/

and 

http://www.gamer.nl/redactiepost/377886 ... -new-vegas

Share as much as you can!!!

the user of gbn is someone, not me :-"

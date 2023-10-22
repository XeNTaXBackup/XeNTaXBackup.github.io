## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-27T20:33:05+00:00
- Post Title: Mr.Adults, Kinect, Noesis! Amazing also i have a question

I see this release and its incredible, also i have a question for Mr. Adults, i hope i can give me answer, The Kinect and Noesis system works with any skeletal structure? or works only with something defined by Kinect? also its posible save animations? i work with a MMORPG mu online, and i see the animations are separated inside of the player.bmd file, i have all the animations separated and something times i play with this animations, but i search import the animations i make with Kinect and noesis inside of the game and make funy new animations, with this the players bee hapy, and not only for mu online, i think with this its posible make more new animations for more games with decrypter/encrypter animation files, i hope Mr. Adults can give me answer, anyway this its one of the greatest releases i see ever.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2010-12-28T20:54:00+00:00
- Post Title: Mr.Adults, Kinect, Noesis! Amazing also i have a question

Oh, I missed this. For future reference, you can just post in the Noesis thread if you wanna talk about Noesis. 

Anyway, the way it works is by allowing you to provide a mapping from the "generic" OpenNI/NITE skeleton to the skeleton of the model of your choice. A usually-works formula is to tick the "identity base" box, then map the left/right shoulder, elbow, hip, and knee, and map the torso to your root bone. And possibly also tick the global x/y axis flips, and the z origin flip. That's just an example for the coordinate system that the significant majority of console games seem to like using.

Once you record the anim, you can export the model+anim to COLLADA, or just the anim to an anim-only format like md5anim. Or PSA, although as has been mentioned, PSA will modify your hierarchy unless you happen to be using a model with a hierarchy that it likes.

I guess if you can get your model that you want new anims for into something generic and importable like COLLADA, that would be your best bet. Well, and you need to be able to export it back from COLLADA too, to use it in the game of your choice. If you can do that, I'd import the COLLADA, record the anim, then "Export from preview" to COLLADA again with your new anim sequence.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2010-12-29T21:47:27+00:00
- Post Title: Mr.Adults, Kinect, Noesis! Amazing also i have a question

perfect, also the models i search animated with noesis and write the animations are this 

[viewtopic.php?f=16&t=5525c](http://forum.xentax.com/viewtopic.php?f=16&t=5525c)

## Post #1
- Username: hanz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 03, 2012 8:52 pm
- Post datetime: 2012-07-03T13:00:30+00:00
- Post Title: [3DSMAX] how to make character into standard sequence ?

how to make character into standard sequence ?

hello ,i have a problem ,please help

some models i download has non-standard animation position (they have bones)
and i want to make them back to the standard position ,sothat i can assign a new bone to them easier in milkshape
(because i 'm noobs of 3ds max)
is it simple ? please tell me how to make them back to the standard position

here's an example :

the current position of the model




the standard position i want to make them back



or



thank you
## Post #2
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-03T18:14:10+00:00
- Post Title: [3DSMAX] how to make character into standard sequence ?

Select your armature.
At the top, go to Animation > skin pose mode .

If skin pose mode is greyed out try Animation> assume pose mode and then Set as pose mode click confirm,
then undo your assume pose mode by pressing ctrl+z,
then your skin pose mode should be clickable and to undo the pose mode reclick skin pose mode.
(save before doing any of this  )

Iirc this is if your animation holds the info to do this.
If the armature is a biped, which I doubt, you can change it to pose mode in the motion menu on the right after selecting your biped.

EDIT: I don't see any keyframes on your timeline, is the model even animated/rigged?
## Post #3
- Username: hanz
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jul 03, 2012 8:52 pm
- Post datetime: 2012-07-04T04:40:27+00:00
- Post Title: [3DSMAX] how to make character into standard sequence ?

> Reply from Demonsangel
>
> Select your armature.
At the top, go to Animation > skin pose mode .

If skin pose mode is greyed out try Animation> assume pose mode and then Set as pose mode click confirm,
then undo your assume pose mode by pressing ctrl+z,
then your skin pose mode should be clickable and to undo the pose mode reclick skin pose mode.
(save before doing any of this  )

Iirc this is if your animation holds the info to do this.
If the armature is a biped, which I doubt, you can change it to pose mode in the motion menu on the right after selecting your biped.

EDIT: I don't see any keyframes on your timeline, is the model even animated/rigged?

thank you for helping ,the model (at the first pic) already has bone and has animation
,but the her animation position is not standard ,so i want to ask if there 's a simple way to change her position to T, A or star pose
or we must manually choose every specific BIP and rotate it ?
## Post #4
- Username: Demonsangel
- Rank: mega-veteran
- Number of posts: 241
- Joined date: Sat Aug 06, 2011 4:31 am
- Post datetime: 2012-07-04T09:27:52+00:00
- Post Title: [3DSMAX] how to make character into standard sequence ?

If the above didn't work I don't know, sorry.
## Post #5
- Username: blabba
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Oct 31, 2014 1:26 pm
- Post datetime: 2014-10-31T05:35:01+00:00
- Post Title: [3DSMAX] how to make character into standard sequence ?

The easiest way would be to write a short little script to do it.

If you know the rotations and positions of the bones in the second image, and the skeletons are the same between it and your first image, you can easily write a Maxscript to convert the bone data.
(It'd just be a simple copy paste sort of thing for the values)

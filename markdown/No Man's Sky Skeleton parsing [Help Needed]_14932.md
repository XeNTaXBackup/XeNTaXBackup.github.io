## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2016-08-24T14:52:02+00:00
- Post Title: No Man's Sky Skeleton parsing [Help Needed]

Hello, once again I'm having a hard fucking time with extracting skeletons (for now) from a game.

Models were really easy to get, but I'm stuck again on getting the skeletons to align with the model.

So first of all the game has some descriptor files which contain information about the corresponding geometry files and also contain information about the bone hierarchy of the model. So since there are no more information about that within the geometry file, i assume that this descriptor file should be more than enough in order to load the default skeleton of the model.

I'm attaching a hierarchy sample right here

[http://pastebin.com/u68mircS](http://pastebin.com/u68mircS)
*the transmat field should be actually Translation/Rotation/Scale values I just saved all 9 values together to gain some space.

From what I've played around so far it seems like the transformation values within the descriptor file, are used in order to transform the children bones. For every new children that is processed I'm adding up the parent's values along with the current bone values and i'm passing the new values to the next children. This seems to partially work on some bones of some models but it completely fails for others. So something is probably very wrong.

This is my code so far that loads the "joint" types into a bone armature.
[http://pastebin.com/McSbXfDe](http://pastebin.com/McSbXfDe)


And here is a pic of the mess (from another model which the skeleton looks like its going to fit)
[http://i.imgur.com/qDEtqAH.png](http://i.imgur.com/qDEtqAH.png)

Any help is highly appreciated

Thanks
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-24T15:17:26+00:00
- Post Title: No Man's Sky Skeleton parsing [Help Needed]

Need actual file sample of the original skeleton, your exported data which is broken isn't of much use at all.
## Post #3
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2016-08-24T15:30:46+00:00
- Post Title: No Man's Sky Skeleton parsing [Help Needed]

> Reply from Gh0stBlade
>
> Need actual file sample of the original skeleton, your exported data which is broken isn't of much use at all.

Its not broken, i just pasted the joint part only, because the rest data is not useful for the skeleton.

Anyway I'm attaching the full files that correspond to the pic situation.
This is the binary file i extracted all the hierarchy information
[https://www.dropbox.com/s/gjay9frpgk8o3 ... .MBIN?dl=0](https://www.dropbox.com/s/gjay9frpgk8o3ek/ASTRONAUT01.SCENE.MBIN?dl=0)
And this is the full version of the extracted data
[https://www.dropbox.com/s/4joooelzm1jop ... .json?dl=0](https://www.dropbox.com/s/4joooelzm1joph0/temp.json?dl=0)

Let me know if you need something more.
## Post #4
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2016-08-25T07:52:38+00:00
- Post Title: No Man's Sky Skeleton parsing [Help Needed]

Did some progress today. I thought of applying the rotations in a "XZY" system instead of the normal "XYZ" because the game is written opengl and there are some Axis differentiations over there.

For some models this worked PERFECTLY
[http://i.imgur.com/jeP5tuN.png](http://i.imgur.com/jeP5tuN.png)

But for the initial one i still get some misplaced bones
[http://i.imgur.com/gZ1OecB.png](http://i.imgur.com/gZ1OecB.png)


Any further idea?

## Post #1
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-12-11T21:37:39+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

Hello. I'd like to get some models from this game. 
I tried to open the .ab file using UnityStudio and was able to open the .ab file.

The problem is, some of the exported .fbx file are lacking T-Pose, like example below.
How do I fix it? Is there any way to get the model in T-pose with UnityStudio?

Thank you.
[Build Problem 1.png](https://xentaxbackup.github.io/file/15310_Build Problem 1.png)
## Post #2
- Username: newlegend
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Dec 10, 2012 2:19 am
- Post datetime: 2018-12-13T14:00:05+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

when i imported it into 3ds max i was able to get some in t-pose by selecting the animation list and selecting no animation
not sure if you could do the same in blender
## Post #3
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-12-13T22:15:28+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

Can you help me specifically with this file? 
[https://drive.google.com/open?id=10fD5L ... b4TlD0a5vY](https://drive.google.com/open?id=10fD5Log8W3vKQlmF3wQmRGb4TlD0a5vY)

This is one of the files containing models that isn't in T-pose initially.
Also, how do I select "No Animation"?

I apologize for not familiar with 3ds Max interface
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-14T14:20:37+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

> Reply from kaiser21
>
> I tried to open the .ab file using UnityStudio and was able to open the .ab file.
How? Tried Unity Studio v0.5.1b3 but nothing was loaded.
However AssetStudio by Perfare does work though.



t.jpg (21.36 KiB) Viewed 181 times
## Post #5
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-12-14T21:46:28+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

I used UnityStudio v0.9.0 [https://github.com/Perfare/AssetStudio/ ... tag/v0.9.0](https://github.com/Perfare/AssetStudio/releases/tag/v0.9.0)

And yeah, while the initial model is in T-pose and can be extracted as .obj,
I haven't be able to export the models into .fbx with T-pose.
The exported .fbx will have the model pre-posed not in T-pose, which resulting in some parts disappearing.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-15T02:15:55+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

> Reply from kaiser21
>
> The exported .fbx will have the model pre-posed not in T-pose
You can delete the armature in Max (or any app you're using) to restore the T-pose, but you'll lose the skeleton of course. No way to keep them both.



RestoreTpose.jpg (160.77 KiB) Viewed 175 times


But if you try to export it from the fbx with Noesis, the initial info will be lost.

> Reply from kaiser21
>
> which resulting in some parts disappearing.
Like what?
## Post #7
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-12-16T12:17:05+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

> Reply from Bigchillghost
>
> kaiser21 wrote:which resulting in some parts disappearing.
Like what?

The model has two wrist parts for each hand, the "closed fist" and "open palm".

If I export the model from.ab file to .fbx as it is, the "open palm" hand part will disappear because it is scaled to 0 in its initial pose.
But, if I export it as .obj, that hand part will still exist.

You can see from your pic above as example.
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-12-16T14:53:08+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

> Reply from kaiser21
>
> If I export the model from.ab file to .fbx as it is, the "open palm" hand part will disappear because it is scaled to 0 in its initial pose.
I see. That's because this static frame needs to show only the desired part. You can replace all these lines

```

```
 in the fbx file with

```

```
 using Notepad++ to retrieve their visibility.
As for the T-pose issue, I'm afraid there's no better solution than copying the skeleton from its other costume variants.
Might need some corrections though, or you can use the transfromation info from the fbx file directly, which however will require some programing knowledge.



copy.jpg (67.22 KiB) Viewed 164 times


BTW shouldn't there be another model with T-pose if the game needs more than just a show-case?
## Post #9
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-12-19T02:11:24+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

> Reply from Bigchillghost
>
> I see. That's because this static frame needs to show only the desired part. You can replace all these lines
Code: Select allP: "Lcl Scaling", "Lcl Scaling", "", "A",0,0,0
 in the fbx file with
Code: Select allP: "Lcl Scaling", "Lcl Scaling", "", "A",1,1,1
 using Notepad++ to retrieve their visibility.

Thanks. I'll try it later.

> Reply from Bigchillghost
>
> As for the T-pose issue, I'm afraid there's no better solution than copying the skeleton from its other costume variants.
Might need some corrections though, or you can use the transfromation info from the fbx file directly, which however will require some programing knowledge.
copy.jpg
BTW shouldn't there be another model with T-pose if the game needs more than just a show-case?

Well, the only models who had problem like this are Build (except Build Genius), and Cross-Z has similiar problem but only for the feet.
As far as I know, other Rider models had their models in T-pose, without having bugs like Build does.
I think, Build model is missing the "information" about its initial T-pose, or something like that.
## Post #10
- Username: kaiser21
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Aug 19, 2017 10:52 am
- Post datetime: 2018-12-25T16:32:07+00:00
- Post Title: Kamen Rider: Climax Scramble Zi-O .ab

Okay.
So apparently, I can "return" the pose of the model back to its initial T-pose
By using Blender, then select the armature, then in Pose Mode, press Alt+G, then Alt+R, and finally Alt+S
Then export again as .fbx.

Except there is this one model that I can't load into Blender because it has this error.
[error blender small.jpg](https://xentaxbackup.github.io/file/15377_error blender small.jpg)

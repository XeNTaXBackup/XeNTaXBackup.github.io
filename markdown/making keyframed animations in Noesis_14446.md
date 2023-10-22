## Post #1
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-09T05:31:59+00:00
- Post Title: making keyframed animations in Noesis

Hi, I was wondering if someone could offer some insight on how to use some code for a Noesis plugin I'm working on. I'm at the point where I have my vertices and bones loaded up in Noesis and now it's time to give Noesis the animation data. I'm trying to hand Noesis key-frames instead of matrices since the data in the animation file seems to specify keyframes. For this task I am constructing the data using the Noesis classes: NoeKeyFramedValue, NoeKeyFramedBone, and NoeKeyFramedAnim.

Here is some sample code of what I'm doing to get the quaternions/rotation data:

```
        for i in range(numAnimBones):
            rotationKeys = []
            for frameIdx in range(kfbCat[i].rTrans):
                keyFrame = bs.readUInt()
                quat = NoeQuat.fromBytes(bs.readBytes(0x10))
                rotationKeys.append(NoeKeyFramedValue(keyFrame, quat))
            kfBones[i].setRotation(rotationKeys)

```

I do similar things to construct scaling and translation data. And so I end up constructing an animation object by doing the following:

```

```

And after doing this is where I believe I'm doing something wrong. My question is to which method does this object need to be passed to? For example with animations constructed using 4x3 matrices we pass these to NoeAnim's constructor instead of NoeKeyFramedAnim's constructor, and in turn we pass the new NoeAnim instance to the method called setAnims from the object created by rapi.rpgConstructModel() like this:

```
mdl.setAnims(animList)
mdlList.append(mdl)
```

Where animList is a list of NoeAnim instances. But that's when we're using matrices (NoeMat43). I'm using NoeKeyFramedAnim instead. So to which method do I need to pass this object? I've tried to pass it to setAnims to see if it would work but the results are entirely wrong; I only get 1 frame out of 100+ frames in the animation, so I assume the problem might be that I'm passing NoeKeyFramedAnim to the wrong method? I've google-searched the web and this forum to try to find examples using NoeKeyFramedAnim but nobody seems to have used them yet? So now I'm stuck, and unsure of how to proceed.

Any insight will be greatly appreciated.

I guess rephrasing the question would be: does the mdl object I created in my previous post have a setKeyFramedAnims method so i can pass to it my NoeKeyFramedAnim object? Or where can i find a list of methods for the mdl object, a.k.a. rapi.rpgConstructModel()? If there was some documentation for these objects/libraries it would make writing scripts a lot easier.
## Post #2
- Username: errno
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-06-09T18:16:06+00:00
- Post Title: making keyframed animations in Noesis

Documentation is located in Noesis/Plugins/Python/__NPReadMe.txt
## Post #3
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-09T20:31:24+00:00
- Post Title: making keyframed animations in Noesis

> Reply from Gh0stBlade
>
> Documentation is located in Noesis/Plugins/Python/__NPReadMe.txtThanks a lot, so that helped me find what kind of object is returned by rpgConstructModel, which seems to be just a NoeModel. So from inc_noesis.py I can see that setAnims accepts both kinds of animation objects, NoeAnim and NoeKeyFramedAnim. So that answers my question, setAnims method does take in NoeKeyFramedAnim objects after all and so that part of my code is fine.

However, since that part of the code is correct then this means I must be constructing my NoeKeyFramedAnim object incorrectly. I'm thinking the problem might be happening while I'm creating my NoeKeyFramedValue objects. I am sort of confused about this class' constructor/initializer, its signature is:

```
def __init__(self, time, value):
```

Now, it's clear to me from the comment in the source code that value may be NoeQuat, NoeVec3, or float. But it's not that clear to me what the time parameter needs to be. In my animation file I'm just given rotation, scaling, and translation data of each bone for each frame in the animation (some frames are left as gaps too in the animation so for example there might be no frames between the 15th and 19th frame). So I am only given a frame index, but not anything that resembles a form of "time" for the frame, so I'm just passing this frame index as the time parameter and hoping that will work but apparently that may not be what this constructor wants the time parameter to be because when I load it all in Noesis I get 1 or 0 frames for the entire animation which is supposed to have 100+ frames. Sadly there is no comment in the source code (inc_noesis.py) explaining what time must be (maybe it's so obvious what it should be but I just don't get it since it's the first time I'm working with animations).

But anyway, does anyone know what exactly this time parameter needs to be or where can I find the documentation or source code that shows how the NoeModel object is parsed by Noesis? Or maybe some suggestions on how to construct the time for each frame? Thanks a lot for reading.
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-06-16T11:39:18+00:00
- Post Title: making keyframed animations in Noesis

I hadn't seen this post, but since I already replied to your PM about it, I guess you understand now. But yeah, typically if you have non-linear keyframe data, you'll have an explicit time somewhere in the data. Otherwise, if you have a linear series of keyframes, time is just going to be frameInterval * frameIndex. The Gamebryo script shows how to use/create NoeKeyFramedAnim pretty effectively.
## Post #5
- Username: errno
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Oct 05, 2014 7:08 am
- Post datetime: 2016-06-17T22:07:54+00:00
- Post Title: making keyframed animations in Noesis

Thanks a lot for the help. So I finally got it to show the animation correctly in the sense that the rotations and translations look as what they are supposed to be. I had a small bug in my code, the variable I named "keyFrame" is supposed to be the time parameter for the NoeKeyFramedValue object, but as can be seen from the code I wrote in my previous post, I was mistakenly reading those bytes as integer type instead of what they truly are, floating-point type. That was the reason why Noesis was telling me the animations had 1 or 0 frames. After I changed it to float it now seems to construct the frames correctly (after some other fine-tuning too).

So for people who might have this question in the future, if you find that each keyframe's time for your animation is a bunch of  floating-point integers ranging from 1.0 to the last frame number (as float), it seems to work fine if you just pass these values as your time parameter to construct your NoeKeyFramedValue object. Then once you construct your NoeKeyFramedAnim object you can set its framerate parameter to 1.0 and finally, after you give the list of these anims to your model, you can specify the default playback framerate using rapi.setPreviewOption("setAnimSpeed", "30") for a 30 fps in this example.

But anyway, I'm now left with another question which hopefully the people who have dealt with animations in the past can identify what this data can be. In the animation file I have found what I am guessing might be the scaling information for the keyframes. However, I was expecting this data to be just a single float per bonekeyframe, which I could simply multiply by the transform matrices to apply scaling to them, but instead I get 8 float values for each bonekeyframe. The first float I know is the time of the keyframe, so theoretically every keyframe could have different scale applied to it. However, only the first frame's scale for every bone seems to be ever specified, and for scaling the rest of the frames I guess the first frame's scale would just naturally propagate up and to the final frame and so maybe that's why only the scale for the first frame is specified? I'm not really sure how the math would work here but anyway, moving on, the next 7 floats I've made out to be 3 floats to make a vector, and the last 4 floats form a quaternion. This strangely matches the format of the data that the animation file provides for every frame: positions are given as a 3D vectors and rotation are given as quaternions.

The big question then is, if this is supposed to be the scaling information, how would I apply it to my frames? As I said before I was expecting to find just a single float for scaling but instead I found what seems to be a vector and a quaternion. My first guess is, just  multiplying each component of the position-vector and rotation-quaternion of the first keyframe by the respective component of the scale-vector and scale-quaternion. Has anyone ever seen scale specified in this format? Or maybe this information might be something else other than scaling, but I can't think of what else it could be used in the animation. I lack the experience of working with different animation formats to be able to identify what else it might be for, or if it's indeed for scaling I'm unsure how it should be applied and further how to use it to construct a NoeKeyFramedValue object.

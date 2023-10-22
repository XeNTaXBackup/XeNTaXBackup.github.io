## Post #1
- Username: guoqiaoxi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 12, 2018 11:32 am
- Post datetime: 2022-06-14T04:11:02+00:00
- Post Title: rip animation clips( Kizuna AI Touch the Beat)

hey guys, I meet a weird problem here:
 trying to rip the asset from VRgame  kizuna ai touch the beat using asset studio; it easy at first I can find everything I can see from the game; but ANIMATIONCIPS for dance motion it s the only thing I can't extract; 
green arrow point to the animator I find   red arrow is the action I can export successfully; pink one is fail;
red action is all small action used on idle animation  (which is not super important)
pink arrow is pointing to dance motion; that is what I want
I find the (kizuna AI )character animator  and it work fine with these small action in the same container   ;  but when I trying to extract with the big motion clips  in this case(hello world) I can only get the character FBX out with no keyframe ;    

can someone help me out this;  thanks in advance      
       here is the apk file
[https://mega.nz/file/qHJSCZpL#98gKZ-tU6 ... p-F7C7siQI](https://mega.nz/file/qHJSCZpL#98gKZ-tU6nl1RDgCRiRjEHLdBp0joI3kTp-F7C7siQI)
  best
## Post #2
- Username: guoqiaoxi
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Nov 12, 2018 11:32 am
- Post datetime: 2022-06-14T04:24:10+00:00
- Post Title: rip animation clips( Kizuna AI Touch the Beat)

picture backup  and here is the apk file [https://mega.nz/file/qHJSCZpL#98gKZ-tU6 ... p-F7C7siQI](https://mega.nz/file/qHJSCZpL#98gKZ-tU6nl1RDgCRiRjEHLdBp0joI3kTp-F7C7siQI)
## Post #3
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2022-06-14T10:52:02+00:00
- Post Title: rip animation clips( Kizuna AI Touch the Beat)

As for the dance animation, it seems that Humanoid is used.
Since the animationclip is large size for a humanoid, it is difficult to handle in an environment where memory is in short supply.

Humanoid animations can be applied to all Humanoid models in Unity, so you can import them into Unity, attach the desired clips to the model's animation, play them back, and output them with the "fbx recorder."
It is possible to convert from humanoid to regular generic animation, but requires paid assets.

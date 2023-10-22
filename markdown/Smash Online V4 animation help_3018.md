## Post #1
- Username: fatduck
- Rank: mega-veteran
- Number of posts: 315
- Joined date: Thu Aug 03, 2006 5:07 am
- Post datetime: 2008-04-20T14:57:02+00:00
- Post Title: Smash Online V4 animation help

I need help with this type of animation which it used a lot ingame!
there are ver3 animation as well but that was easy and already figured out!

Please help!

V4 format I got so far:

```
dword          nVersion     //4
dword          unknown1
dword          unknown2
word           nBones
word           nFrames     //??
word           nFPS         //??
word           unknown3
dword          unknown4
dword          uknRef1
dword          uknRef2
Struct BoneArray {
   char[]      szBoneName
}
Struct BoneData {
   word        uknB01
   word        uknB02
   word        uknB03     //Related to uknRef2
   word        uknB04     //Related to uknRef1
   float X 3   posXYZ    //should be Initial Position
   Byte X 12   ??         //should be Initial Rotation   
}
<data> ??

```

[V4_anm.rar](https://xentaxbackup.github.io/file/1494_V4_anm.rar)
## Post #2
- Username: MrJolly
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 26, 2008 2:07 pm
- Post datetime: 2008-05-03T14:43:34+00:00
- Post Title: Smash Online V4 animation help

Fatduck im really sorry to bother you here but can you please contact me - thankyou
## Post #3
- Username: jildert
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jun 27, 2010 12:06 am
- Post datetime: 2010-08-06T08:08:50+00:00
- Post Title: Smash Online V4 animation help

*bump*

I know this thread is like 2 years old. But does anyone know if anyone ever completly figured out the 
format for the v4 animation file? Would be great if someone has some info for me.

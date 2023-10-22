## Post #1
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-22T17:51:17+00:00
- Post Title: animation compression

Hi

Please help how to decode quaternion compression 48bit (15bit+15bit+15bit+3bit) used by Cryengine.

the end:  [http://docs.cryengine.com/display/SDKDO ... ionDetails](http://docs.cryengine.com/display/SDKDOC3/Copy+of+Using+the+Resource+Compiler#CopyofUsingtheResourceCompiler-AnimationCompressionDetails)
## Post #2
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-22T18:16:53+00:00
- Post Title: animation compression

Are you sure there is nothing like this in the unreal engine 4 source code?
I imagine the last few bits contain the sign for w

[here](http://forum.xentax.com/viewtopic.php?f=16&t=8630&start=15)
## Post #3
- Username: Szkaradek123
- Rank: mega-veteran
- Number of posts: 292
- Joined date: Thu May 06, 2010 3:21 am
- Post datetime: 2014-12-22T18:33:53+00:00
- Post Title: animation compression

Yes i have seen this topic.
I can't write script with full of ^ or & or >> symbols. I don't understand language bits operation.
I need some code.
## Post #4
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-22T18:49:42+00:00
- Post Title: animation compression

If you mean bms then I can't really help. I only know the c languages

```
 s0 = 1.41421*(s0-0x3FFF)/0x7FFF
  s1 = 1.41421*(s1-0x3FFF)/0x7FFF
  s2 = 1.41421*(s2-0x3FFF)/0x7FFF
  s3 = sqrt(1-(s0^2+s1^2+s2^2))

  case AxisFlg of (
   3: return (quat s2 s1 s0 s3)
   2: return (quat s2 s1 s3 s0)
   1: return (quat s2 s3 s1 s0)
   0: return (quat s3 s2 s1 s0)
  )--end case

```
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-12-22T20:03:58+00:00
- Post Title: animation compression

> Reply from Szkaradek123
>
> I need some code.In the docs link u gave it is said
"You can find more details in the 'QuatQuantization.h'."

This header file should help us further but it doesn't seem to be part of the CryEngine 3 SDK.
## Post #6
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2014-12-24T04:25:24+00:00
- Post Title: animation compression

I found out more about this possible representation by checking out the  Lua decompiler (LOL)

> Signed representation
>
> ---------------------------
>
> It doesn’t use 2s complement. Instead, it has a bias equal to half the maximum integer that can be represented by its unsigned counterpart.
>
> For a field size of 18 bits, we can hold a maximum unsigned integer value of 262143, and so the
>
> bias is 131071 (calculated as 262143 >> 1). A value of -1 will be encoded as (-1 + 131071)
>
> or 131070 or 1FFFE in hexadecimal.

So in our case 
the Bias might be  

```

```

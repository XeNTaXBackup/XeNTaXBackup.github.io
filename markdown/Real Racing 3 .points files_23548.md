## Post #1
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-05T17:57:39+00:00
- Post Title: Real Racing 3 .points files

I'm converting Real Racing 3 cars, and I need a new way of figuring out where the wheels are positioned. I found a file with ".points" appended to it. When I look inside this file's data, it has the name of the wheel dummy. After that is short garbled data that I can't seem to understand. The headlight dummies have scale to them. Is there a way to convert this into a text file or something?
Note that I use the 3D modelling program Blender. If scripts get made for another program to solve my problem, then it will not be useful to me.
Sample: [https://www.mediafire.com/file/6b7z9q5r ... oints/file](https://www.mediafire.com/file/6b7z9q5r9qm0ea2/1993_alfa_romeo_155_v6_ti.points/file)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T15:10:27+00:00
- Post Title: Real Racing 3 .points files

You wouldn't expect someone digging into a .points file without having the belonging model file, do you?
## Post #3
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T17:23:26+00:00
- Post Title: Real Racing 3 .points files

How did I not notice that!?!?!?    Sorry, here's the M3G and the converted FBX.
FBX:
[https://www.mediafire.com/file/cl8gt3f2 ... a.fbx/file](https://www.mediafire.com/file/cl8gt3f2bgry72k/1993_alfa_romeo_155_v6_ti_a.fbx/file)
M3G:
[https://www.mediafire.com/file/g7c84h7g ... a.m3g/file](https://www.mediafire.com/file/g7c84h7gwywlaib/1993_alfa_romeo_155_v6_ti_a.m3g/file)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T19:28:16+00:00
- Post Title: Real Racing 3 .points files

So it's for the wheels? Problem is, there's LOD_A_STEERING_WHEEL_mm_cab in the model file
and POINT_WHEEL_BL, POINT_WHEEL_BR, POINT_WHEEL_FR, POINT_WHEEL_FL in the points file.

But none of them is in both. 
(At least not from the ASCII names. Maybe they're referenced via hash, too, dunno.)

(well, and didn't find the 4 wheels' mesh in the model file)
## Post #5
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T19:39:18+00:00
- Post Title: Real Racing 3 .points files

The wheels are in a separate model file. 
m3g [https://www.mediafire.com/file/kzhpmd79 ... d.m3g/file](https://www.mediafire.com/file/kzhpmd79lringes/1993_alfa_romeo_155_v6_ti_shared.m3g/file)
fbx [https://www.mediafire.com/file/ufkp3659 ... d.fbx/file](https://www.mediafire.com/file/ufkp3659tn8uvrq/1993_alfa_romeo_155_v6_ti_shared.fbx/file)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T19:48:37+00:00
- Post Title: Real Racing 3 .points files

yeah, ok, but they're in place!? So we'd need some hint in the .points file for the misplaced steering wheel to get it's position offset, correct?

Maybe I didn't get what you meant with this:

> Reply from ReVolt ↑Sat Mar 06, 2021 1:57 am at Sat Mar 06, 2021 1:57 am
>
> 
I'm converting Real Racing 3 cars, and I need a new way of figuring out where the wheels are positioned.
## Post #7
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T19:54:26+00:00
- Post Title: Real Racing 3 .points files

> Reply from shakotay2 ↑Sun Mar 07, 2021 3:48 am at Sun Mar 07, 2021 3:48 am
>
> 
yeah, ok, but they're in place!? So we'd need some hint in the .points file for the misplaced steering wheel to get it's position offset, correct?

Maybe I didn't get what you meant with this:
ReVolt wrote: ↑Sat Mar 06, 2021 1:57 am
I'm converting Real Racing 3 cars, and I need a new way of figuring out where the wheels are positioned.
I meant that I use the LOD_F wheel model to figure out where the wheels are positioned. Sometimes it does it wrong tho. The LOD_F has its wheels in place. The LOD_A wheel is like the steering wheel, it's not fixed in place. We do need a hint in the points file for the steering wheel. I'm sure there's some sort of order in there that defines the point's position.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-06T20:08:18+00:00
- Post Title: Real Racing 3 .points files

ok, are you familiar with floating point IEEE754 format? You'll need to understand at least where a coordinate component starts.

I load 1993_alfa_romeo_155_v6_ti.points into hex2obj to give you the idea (any hex editor capable of showing floats should do, too).

Here we go:
.



a-points-file.png (64.24 KiB) Viewed 109 times



You need to vary the start addresses 'till you get some meaningful position.

Positioning the steering wheel manually in your 3D app may help to give an idea for which values to search for.

Seems we got a matrix (well, broken a little bit  ), so there's rotation and position x,y,z: -9.578007 -67.851753 12.298819.
But for which part?

Maybe TRANSFORM_EXHAUST_02 (or _03)?

(Seems there's too many parts and too less matrices in that points file?)
## Post #9
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2021-03-06T20:22:57+00:00
- Post Title: Real Racing 3 .points files

> Reply from shakotay2 ↑Sun Mar 07, 2021 4:08 am at Sun Mar 07, 2021 4:08 am
>
> 
ok, are you familiar with floating point IEEE754 format? You'll need to understand at least where a coordinate component starts.

I load 1993_alfa_romeo_155_v6_ti.points into hex2obj to give you the idea (any hex editor capable of showing floats should do, too).

Here we go:
.
a-points-file.png

You need to vary the start addresses 'till you get some meaningful position.

Positioning the steering wheel manually in your 3D app may help to give an idea for which values to search for.

Seems we got a matrix (well, broken a little bit  ), so there's rotation and position x,y,z: -9.578007 -67.851753 12.298819.
But for which part?

Maybe TRANSFORM_EXHAUST_02 (or _03)?

(Seems there's too many parts and too less matrices in that points file?)

Where can I find hex2obj? I remember having it on my computer, but I don't know where it went. The link to the download doesn't seem like it ever existed! Searching "uploadmb" on google returns nothing!
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-07T14:33:29+00:00
- Post Title: Real Racing 3 .points files

View link in my sig or here 
> Reply from shakotay2 ↑Tue Oct 22, 2013 10:06 pm at Tue Oct 22, 2013 10:06 pm
>
> 

But it's a quick workaround only. A capable hex editor (with "data inspector") would do better, I guess.
(Can't tell which, because for me it's easier to just write some C code for tasks like this one.)

> Reply from ReVolt ↑Sun Mar 07, 2021 4:22 am at Sun Mar 07, 2021 4:22 am
>
> 
The link to the download doesn't seem like it ever existed! Searching "uploadmb" on google returns nothing!Yeah, strange. I'll create a temporary post for download 'till I find a new file hoster.

See here:

> Reply from shakotay2 ↑Sun Mar 07, 2021 10:29 pm at Sun Mar 07, 2021 10:29 pm
>
>
## Post #11
- Username: ReVolt
- Rank: veteran
- Number of posts: 158
- Joined date: Tue Jun 16, 2020 9:21 am
- Post datetime: 2022-02-27T02:14:38+00:00
- Post Title: Real Racing 3 .points files

I'm thinking of returning to ripping RR3 again...but not until I got this file format solved.

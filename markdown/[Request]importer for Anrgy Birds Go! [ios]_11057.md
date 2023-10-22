## Post #1
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2013-12-19T05:38:00+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

hi guys, 
Can anyone help me write a importer for 3dmax for *.xgm and *.xga file, these are Angry Birds Go! mesh file and anim file.

cannon.xgm 
[http://www31.zippyshare.com/v/64386656/file.html](http://www31.zippyshare.com/v/64386656/file.html)
cannon_fire.xga 
[http://www31.zippyshare.com/v/78388911/file.html](http://www31.zippyshare.com/v/78388911/file.html)
splitgateat002r000.xgm 
[http://www31.zippyshare.com/v/14602660/file.html](http://www31.zippyshare.com/v/14602660/file.html)
splitgateat002r000_loop.xga 
[http://www31.zippyshare.com/v/75733980/file.html](http://www31.zippyshare.com/v/75733980/file.html)
## Post #2
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2013-12-19T21:21:20+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

Funny you should ask, I just started extracting the models from that game a little while ago.

[http://www.models-resource.com/other_sy ... rybirdsgo/](http://www.models-resource.com/other_systems/angrybirdsgo/)

Once I figure out how to automate the script so that I don't have to punch in certain values manually, I'll post the script up here. Unless someone else does so before I get the chance to, it's not like the model format's that hard to decipher or anything.

The animations are another thing though, I don't have any plans for those.
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-19T22:11:42+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

> Reply from RandomTBush
>
> [...], it's not like the model format's that hard to deciphersigned.
cannon:
[](http://www.pic-upload.de/view-21677035/cannon.jpg.html)
## Post #4
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2013-12-20T02:19:33+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

> Reply from shakotay2
>
> RandomTBush wrote:[...], it's not like the model format's that hard to deciphersigned.
cannon:
that's cool shakotay2,can you share the fileformat,or you can pm me
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-20T17:49:29+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

the file format is given by this H2O file:
0x3FBC 1368
VB1
28 20
0x19C 540
0200

which means: VertexBlock size= 28 bytes
3 floats (12 bytes) per vertex position
(UVpos=20 might be wrong)

unit16 faceindices

use hex2obj
## Post #6
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2013-12-28T08:46:48+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

> Reply from RandomTBush
>
> Funny you should ask, I just started extracting the models from that game a little while ago.

http://www.models-resource.com/other_sy ... rybirdsgo/

Once I figure out how to automate the script so that I don't have to punch in certain values manually, I'll post the script up here. Unless someone else does so before I get the chance to, it's not like the model format's that hard to decipher or anything.

The animations are another thing though, I don't have any plans for those.

hi, RandomTBush, are you still in progress? And do you extracting the tracks too?
## Post #7
- Username: RandomTBush
- Rank: ultra-veteran
- Number of posts: 356
- Joined date: Thu May 13, 2010 11:11 pm
- Post datetime: 2014-01-06T06:13:48+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

> Reply from sailingjia
>
> RandomTBush wrote:Funny you should ask, I just started extracting the models from that game a little while ago.

http://www.models-resource.com/other_sy ... rybirdsgo/

Once I figure out how to automate the script so that I don't have to punch in certain values manually, I'll post the script up here. Unless someone else does so before I get the chance to, it's not like the model format's that hard to decipher or anything.

The animations are another thing though, I don't have any plans for those.

hi, RandomTBush, are you still in progress? And do you extracting the tracks too?Got most of the characters up now, I'll be getting the rest (and the karts, later on) sometime soon-ish since I figured out how to extract their textures properly.

And I don't have any plans to get the tracks at the moment, either, partly because they're located in those *.stm archives, I think.
## Post #8
- Username: sailingjia
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Dec 16, 2013 5:04 pm
- Post datetime: 2014-03-05T08:33:25+00:00
- Post Title: [Request]importer for Anrgy Birds Go! [ios]

> Reply from RandomTBush
>
> sailingjia wrote:RandomTBush wrote:Funny you should ask, I just started extracting the models from that game a little while ago.

http://www.models-resource.com/other_sy ... rybirdsgo/

Once I figure out how to automate the script so that I don't have to punch in certain values manually, I'll post the script up here. Unless someone else does so before I get the chance to, it's not like the model format's that hard to decipher or anything.

The animations are another thing though, I don't have any plans for those.

hi, RandomTBush, are you still in progress? And do you extracting the tracks too?Got most of the characters up now, I'll be getting the rest (and the karts, later on) sometime soon-ish since I figured out how to extract their textures properly.

And I don't have any plans to get the tracks at the moment, either, partly because they're located in those *.stm archives, I think.
hi RandomTBush ,are you still working on it?

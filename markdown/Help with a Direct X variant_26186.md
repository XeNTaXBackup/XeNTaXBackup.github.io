## Post #1
- Username: DavidDeBergerac
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2023 4:54 pm
- Post datetime: 2023-01-13T09:00:35+00:00
- Post Title: Help with a Direct X variant

Hi,  

I've been trying to study the animations from this old game called Rumble Fighters. I'm able to view the 3d models using 3DObjectConverter, however, I have no idea how I can view the 3d animations and skeletal animations. I believe it uses a variant of the Direct X .X file. (It's called .NSS and .NSX)

Can somebody help me out? If you're interested, I'll provide a dropbox link to a few of the animation files. Thanks

[https://www.dropbox.com/s/0uwpl6x7d8tf6 ... l.zip?dl=0](https://www.dropbox.com/s/0uwpl6x7d8tf67a/Default%20Scroll.zip?dl=0) <- Link to the game files
[https://www.dropbox.com/sh/vwqdjt90wq2f ... l-CIa?dl=0](https://www.dropbox.com/sh/vwqdjt90wq2fhiy/AADC_5hCYBOIpes36FMZl-CIa?dl=0) <- More animation files
## Post #2
- Username: roswell
- Rank: advanced
- Number of posts: 62
- Joined date: Tue Apr 02, 2019 8:00 am
- Post datetime: 2023-01-17T00:46:49+00:00
- Post Title: Help with a Direct X variant

This is a DirectX file stored in the DirectX format. The reason it doesn't load is because they either changed or added new template names.  DirectX templates allow you customize the format to anything you want.

These files are in binary format, so perhaps if you were to convert them to text format, you could study the format better, and possibly rename the template names to something readable.  I don't know of any converters offhand other than the ones that come with the DirectX SDK.
## Post #3
- Username: 05SpeedMaster
- Rank: veteran
- Number of posts: 128
- Joined date: Tue Feb 11, 2020 4:24 am
- Post datetime: 2023-01-17T20:42:42+00:00
- Post Title: Help with a Direct X variant

They may have done a simple transmutate on the files.
One format I found years ago (And got me kicked off a site) was to simply add to each float starting from 0 to 255 then repeating.
So by removing that I could extract models at will.
## Post #4
- Username: DavidDeBergerac
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2023 4:54 pm
- Post datetime: 2023-01-18T04:23:09+00:00
- Post Title: Help with a Direct X variant

> Reply from 05SpeedMaster ↑Wed Jan 18, 2023 4:42 am at Wed Jan 18, 2023 4:42 am
>
> 
They may have done a simple transmutate on the files.
One format I found years ago (And got me kicked off a site) was to simply add to each float starting from 0 to 255 then repeating.
So by removing that I could extract models at will.

I'm sorry, I'm not a very technical guy. Can you explain this to me in simpler terms?
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2023-01-18T11:36:18+00:00
- Post Title: Help with a Direct X variant

> Reply from DavidDeBergerac ↑Fri Jan 13, 2023 5:00 pm at Fri Jan 13, 2023 5:00 pm
>
> 
I'm able to view the 3d models

send those files too, because these animations don't have a skeleton, only keyframes...
## Post #6
- Username: DavidDeBergerac
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Jan 13, 2023 4:54 pm
- Post datetime: 2023-01-18T15:27:26+00:00
- Post Title: Help with a Direct X variant

> Reply from Durik256 ↑Wed Jan 18, 2023 7:36 pm at Wed Jan 18, 2023 7:36 pm
>
> 
DavidDeBergerac wrote: ↑Fri Jan 13, 2023 5:00 pm
I'm able to view the 3d models


send those files too, because these animations don't have a skeleton, only keyframes...

ok, I will pm you

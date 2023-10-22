## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-29T14:33:24+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Experimental tool. Works on workarounds. Some meshes will fail. If I'll be in a good mood, I can improve it and read buffer information from shaders. Right now I'm too lazy to do that. So here it is, with all skeletons, meshes, and textures.

Usage is simple: after using corrected BMS script on PKZ files, drag extracted file onto the tool.
If UVs will not work (like in this CEO example) - try running it with 2nd command line parameter (which can be any word), it will extract another UV pair.



[spdrmn_eot.rar](https://xentaxbackup.github.io/file/13049_spdrmn_eot.rar)
## Post #2
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-06-29T18:08:39+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Amazing,thanks.
i know in first post you said about that,but how i can run that "2nd command line parameter"? i'm asking this because i tried to extract model but it has no UVs and i didn't understand correctly
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-29T20:57:47+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

run command line or batch, with something like...

SpidermanEoT.exe some.pkz.ext 2

this "2" is 2nd parameter. It can be anything, doesn't matter what you type there, the tool will try to get 2nd UV pair.
## Post #4
- Username: Rutabaga
- Rank: veteran
- Number of posts: 115
- Joined date: Tue Jan 26, 2016 9:26 pm
- Post datetime: 2017-06-30T10:33:59+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Thanks a lot!
Is this a possible extract anims too?
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-06-30T11:00:27+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

I'm not planning this. Animations usually take too much time.
## Post #6
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-07-24T07:33:52+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Any chance this tools will support Shattered Dimensions and the 2 Amazing Spider-man games? They seem to have the same pkz files, probably different encryption.
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-24T18:10:42+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

> Reply from riccochet
>
> Any chance this tools will support Shattered Dimensions and the 2 Amazing Spider-man games? They seem to have the same pkz files, probably different encryption.

what are you talking about? there is no encryption here
## Post #8
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2017-07-24T20:17:58+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Ok maybe I'm using the wrong terminology. I tried the tool on ps3 files from the amazing Spiderman 2 game, since they also use pkz the bms didn't work. Then I tried it on ps3 shattered dimensions, the bms worked , then I ran the tool on the files and it dumped some textures, however they are not able to be viewed. 
So what I meant was maybe those files were packed differently into the pkz for each different game.
## Post #9
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2017-07-25T16:55:12+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

yes, these games must have different formats
## Post #10
- Username: Ecelon
- Rank: advanced
- Number of posts: 49
- Joined date: Fri Oct 17, 2014 9:50 am
- Post datetime: 2019-03-23T09:51:32+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Hey I 'm just wondering if anyone has the updated PKZ BMS script. I've been looking for an hour now and haven't been able to find it. The only one I've found is Chroxx's. Cheers guys.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-06-29T16:09:09+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Animations tool



[https://www.youtube.com/watch?v=eBVFaR3QJCI](https://www.youtube.com/watch?v=eBVFaR3QJCI)

Usage is the same: drag extracted file onto the tool, or use command line. Just instead of mesh/textures it will export all available animations.

Note that animations need correct skeleton to work, and some skeletons will be in another package (.pkz file). For that reason, tool dumps all skeletons from PKZ to a subfolder. Once you export all skeletons from all files, all animations should be able to export. So probably you will need to process all files twice: 1st to export skeletons, 2nd to export animations.

Also note that i didnt apply any interpolation, so some animations may be shaky or look incorrect. I had no time to test that yet.

Another note is that for some weird reason, some animations point to a mesh instead of skeleton. To handle that, you need to copy skeletons with another name (corresponding to mesh hash). I found 3 most used ones:

```
copy 2D225A8F.skel 17CE8E22.skel
copy DD403DC2.skel 5A1C30BA.skel
```


These are Amazing Spiderman, 2099 Spiderman and Crusher models.
[spdrmn_eot_anims.7z](https://xentaxbackup.github.io/file/23991_spdrmn_eot_anims.7z)
## Post #12
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2023-07-01T14:22:18+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

Hello!

Did you experemented with extracted *ANIM animations from Spider-Man 3 the game? There are lot's of interesting unused animations but I can't understand how to interact with it
[sm3-anim-files.zip](https://xentaxbackup.github.io/file/24004_sm3-anim-files.zip)
## Post #13
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-03T07:24:06+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

> Reply from PaHaNchickT ↑Sat Jul 01, 2023 10:22 pm at Sat Jul 01, 2023 10:22 pm
>
> 
Did you experemented with extracted *ANIM animations from Spider-Man 3 the game? There are lot's of interesting unused animations but I can't understand how to interact with it
these files are not animations
## Post #14
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2023-07-03T11:30:08+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

oh thanks.. I know that it's animations that were extracted from PCPACK archive (from SM3 the game) and how tool developer said 
> .anim is game format, you can't open them. I extract them so maybe someone will like to research them So maybe do you have any ideas what could I do with this .anim files? Maybe it could be reexported into .fsb format?
## Post #15
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-07-03T11:39:49+00:00
- Post Title: Spider-Man: Edge of Time (PS3)

> Reply from PaHaNchickT ↑Mon Jul 03, 2023 7:30 pm at Mon Jul 03, 2023 7:30 pm
>
> 
So maybe do you have any ideas what could I do with this .anim files? Maybe it could be reexported into .fsb format?
there is nothing to do or research there. These files are NOT animations.
## Post #16
- Username: PaHaNchickT
- Rank: beginner
- Number of posts: 26
- Joined date: Wed Dec 23, 2020 5:23 am
- Post datetime: 2023-07-03T14:19:16+00:00
- Post Title: Re: Spider-Man: Edge of Time (PS3)

okay I see, so sorry
## Post #17
- Username: Platys
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 17, 2023 9:40 pm
- Post datetime: 2023-10-11T21:30:10+00:00
- Post Title: Re: Spider-Man: Edge of Time (PS3)

hey dude sorry for wasting your time but i have a question
when i extract the pkz file with the tool it just gives me a ext file wich i dont know how to open
can you help me?
## Post #18
- Username: Platys
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Jul 17, 2023 9:40 pm
- Post datetime: 2023-10-13T20:53:16+00:00
- Post Title: Re: Spider-Man: Edge of Time (PS3)

so when i use the bms script on the pkz file it becomes a ext file wich i dont know how to open 
can yall help me with this?
## Post #19
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2648
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-10-14T05:42:29+00:00
- Post Title: Re: Spider-Man: Edge of Time (PS3)

use the tool included

## Post #1
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-08-29T18:04:50+00:00
- Post Title: Bioshock infinite animations (morpheme)

After making tools for Overwatch & Black Ops III animations, I decided to try something really hard. So this is the tool for Morpheme animations from Bioshock infinite.

[https://www.youtube.com/watch?v=zBG65TvtucY](https://www.youtube.com/watch?v=zBG65TvtucY)

How to use it:

1. extract .morphemeanimset and .morphemeanimsequence files from package with gildor's extract tool
2. use bsi_anim tool on .morphemeanimsequence files to convert animations to .SMD
- Use batch command to convert all files at once (for %a in (*.morpheme*) do bsi_anim "%a")
- animsets are needed for skeleton structure and initial pose, so keep them as they are, in a root folder for each animation set.
3. load the corresponding model into editor, load and apply SMD animation to it.
- animations in UE3 are left-handed, so you need to mirror the model or the animation before applying it.

Important notes and restrictions:
- animation type 2 not supported (usually used for short or very simple animations)
- spline rotations not supported (haven't seen any of this type yet)
- in some files you may encounter interpolation problems. I have to time to fix it properly yet, so for now you can add extra parameter to the command line, and this will turn time-expanding off, this will fix the issue.
[bsi_anim.rar](https://xentaxbackup.github.io/file/11628_bsi_anim.rar)
## Post #2
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2016-09-07T19:01:23+00:00
- Post Title: Bioshock infinite animations (morpheme)

Holy shit, i never tought i see the day when Morpheme got decoded. This is awesome!

Do you think you can take a look at Enslaved Odyssey to the West? It's simmilar to Bioshock Infinite with Unreal Engine 3 and Morpheme.
## Post #3
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-08T15:13:51+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from artmancarver
>
> Do you think you can take a look at Enslaved Odyssey to the West?

Maybe. I can look at some examples, if you have them. Maybe they are not even different from bioshock.
## Post #4
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2016-09-09T10:51:23+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from daemon1
>
> artmancarver wrote:Do you think you can take a look at Enslaved Odyssey to the West?

Maybe. I can look at some examples, if you have them. Maybe they are not even different from bioshock.

Just tell me what kind of examples do you need and i will upload them somewhere.
## Post #5
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-09T15:09:46+00:00
- Post Title: Bioshock infinite animations (morpheme)

.morphemeanimset and .morphemeanimsequence files
## Post #6
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2016-09-09T21:26:32+00:00
- Post Title: Bioshock infinite animations (morpheme)

Ok, here is an archive, PC version of the game. I included: 1 .morphemeanimset, 6 .morphemeanimsequence, a skeletal mesh of a model that is associated with those animations. Also in binaries folder there was a lot of develpments stuff, i included a various executables and dll's. those seems to be a part of morpheme SDK, tought they would be useful to you. I can drop the entire binaries folder if you want.

[https://www.dropbox.com/s/zfvydg8dzly7k ... f.zip?dl=0](https://www.dropbox.com/s/zfvydg8dzly7k8m/Enslaved_Stuff.zip?dl=0)
## Post #7
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2016-09-11T07:38:12+00:00
- Post Title: Bioshock infinite animations (morpheme)

These files look too much different from bioshock morpheme version. To make this work, I need to start it all from scratch. I don't have time for this now.
## Post #8
- Username: artmancarver
- Rank: n00b
- Number of posts: 14
- Joined date: Mon Oct 10, 2011 8:00 am
- Post datetime: 2016-09-11T08:39:53+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from daemon1
>
> These files look too much different from bioshock morpheme version. To make this work, I need to start it all from scratch. I don't have time for this now.
Ok i understand. Thanks for taking time to look at it.

Thanks for making Bioshock Infinite animations working, that's a huge thing on its own regardless!
## Post #9
- Username: WalterNEST
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Apr 16, 2018 3:41 am
- Post datetime: 2022-06-10T22:14:47+00:00
- Post Title: Bioshock infinite animations (morpheme)

I am fruitlessly trying to figure out from which package can I extract .morphemeanimset and .morphemeanimsequence - I used Gildor's uModel to extract all the packages, but after searching the 80GB of files it produced there is no .morphemeanimset or even anything similarly named. It seems the instructions in the first step are missing something.
## Post #10
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-16T13:46:11+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from daemon1 ↑Tue Aug 30, 2016 2:04 am at Tue Aug 30, 2016 2:04 am
>
> 
After making tools for Overwatch & Black Ops III animations, I decided to try something really hard. So this is the tool for Morpheme animations from Bioshock infinite.

https://www.youtube.com/watch?v=zBG65TvtucY

How to use it:

1. extract .morphemeanimset and .morphemeanimsequence files from package with gildor's extract tool

Where do I find these morpheme files? I exported everything with gildor's tool and there is no such files anywhere in the dump. Any help?

> Reply from WalterNEST ↑Sat Jun 11, 2022 6:14 am at Sat Jun 11, 2022 6:14 am
>
> 
I am fruitlessly trying to figure out from which package can I extract .morphemeanimset and .morphemeanimsequence - I used Gildor's uModel to extract all the packages, but after searching the 80GB of files it produced there is no .morphemeanimset or even anything similarly named. It seems the instructions in the first step are missing something.

Did you ever end up finding them by any chance? I can't find them.
## Post #11
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-09-16T16:38:15+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from AxelNoir ↑Sat Sep 16, 2023 9:46 pm at Sat Sep 16, 2023 9:46 pm
>
> 
Where do I find these morpheme files? I exported everything with gildor's tool and there is no such files anywhere in the dump. Any help?
They are everywhere, almost in every package. You probably used wrong tool. Use extract tool, as its stated in the post.
## Post #12
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-16T20:14:12+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from daemon1 ↑Sun Sep 17, 2023 12:38 am at Sun Sep 17, 2023 12:38 am
>
> 
AxelNoir wrote: ↑Sat Sep 16, 2023 9:46 pm
Where do I find these morpheme files? I exported everything with gildor's tool and there is no such files anywhere in the dump. Any help?

They are everywhere, almost in every package. You probably used wrong tool. Use extract tool, as its stated in the post.

Ah my apologies you're right, I was using the wrong tool. I seem to be having some issues with it however, I'm trying to get some animations from the DLC and they seem to be messing up Elizabeth's model when they play, like weird rotations and her face is being messed up too. How do I fix this?

For anyone reading this in the future, don't use Umodel viewer to find the animation files, you need Gildor's Package Extractor to extract the files from the .xxx packages.
## Post #13
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-16T21:05:20+00:00
- Post Title: Bioshock infinite animations (morpheme)

Weird creepy stuff like this happening:



Like parts of her body simply aren't part of the animation and incorrectly rotated lol
## Post #14
- Username: daemon1
- Rank: MEGAVETERAN
- Number of posts: 2649
- Joined date: Wed Mar 25, 2015 3:12 am
- Post datetime: 2023-09-17T07:29:52+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from AxelNoir ↑Sun Sep 17, 2023 5:05 am at Sun Sep 17, 2023 5:05 am
>
> 
Weird creepy stuff like this happening:
Like parts of her body simply aren't part of the animation and incorrectly rotated lol
It was so long ago. I dont remember much about it now. Probably it means you have wrong animset in the root folder. The animset is telling the tool about the bone set and their order inside animations.
## Post #15
- Username: AxelNoir
- Rank: mega-veteran
- Number of posts: 247
- Joined date: Sat Feb 03, 2018 4:24 am
- Post datetime: 2023-09-17T14:39:20+00:00
- Post Title: Bioshock infinite animations (morpheme)

> Reply from daemon1 ↑Sun Sep 17, 2023 3:29 pm at Sun Sep 17, 2023 3:29 pm
>
> 
It was so long ago. I dont remember much about it now. Probably it means you have wrong animset in the root folder. The animset is telling the tool about the bone set and their order inside animations.

I see. I don't know if that's what I'm doing wrong though, for example the animset for an animation I'm loading is titled, "GenLiz_EMSmokey_Base.MorphemeAnimSet", and then the sequence for it is in a seperate folder titled, "GenLiz_EMSmokey_Base". Inside that folder I'm using the sequence, "MorphemeAnimSequence_0.MorphemeAnimSequence". 

Despite this when I load the animation onto Elizabeth's model her rotations are messed up and parts of her skeleton aren't even animating. Could it be Elizabeth's model itself? I extracted it using Gildor's Model Viewer and imported it as a .psk file. Other than that I don't know what to do.

## Post #1
- Username: Reck1501
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 05, 2016 11:47 pm
- Post datetime: 2016-05-31T19:04:14+00:00
- Post Title: UE4 .uasset

Is it at all possible (by possible I mean by a tool or something that's released to the public) to uncook .uasset files (specifically dreadnought/fractured space)?
I know that extracting the models is super easy, but what about all the other stuff such as materials, animations, rigs, blueprints, scripts, etc..?
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-05-31T19:50:10+00:00
- Post Title: UE4 .uasset

The source code for UE4 is free, maybe you can look at that.
## Post #3
- Username: Reck1501
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 05, 2016 11:47 pm
- Post datetime: 2016-05-31T21:09:57+00:00
- Post Title: UE4 .uasset

> Reply from Gh0stBlade
>
> The source code for UE4 is free, maybe you can look at that.
Not to be rude, but that's kinda the opposite of what I asked for
## Post #4
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-05-31T22:50:16+00:00
- Post Title: UE4 .uasset

you can't really "uncook" assets as the conversion from source -> packed binary is lossy.

blueprints lose a lot of information from their compiled state in the editor.

the source would actually show how vanilla assets are packages - but remember devs can easily tweak the engine   

materials might be possible as you might have examples on different platforms, but i have no clue is theres a tool for it
## Post #5
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-06-01T07:13:03+00:00
- Post Title: UE4 .uasset

> Reply from Reck1501
>
> Gh0stBlade wrote:The source code for UE4 is free, maybe you can look at that.
Not to be rude, but that's kinda the opposite of what I asked for
Oh, you're not being rude at all. But there is a reason for me directing you to the UE4 source code. UE4's source code will contain the info required (structs for all file formats). That could potentially help you or someone else figure out how to write a tool to partially uncook or retrieve more data from the .uasset files. Doing this with no source code would be a very painful task but fortunately it's there.

Nevertheless, I don't believe that fully uncooking everything is possible.

Regards.
## Post #6
- Username: Reck1501
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Feb 05, 2016 11:47 pm
- Post datetime: 2016-06-01T11:09:50+00:00
- Post Title: UE4 .uasset

> Reply from WRS
>
> you can't really "uncook" assets as the conversion from source -> packed binary is lossy.

blueprints lose a lot of information from their compiled state in the editor.

the source would actually show how vanilla assets are packages - but remember devs can easily tweak the engine   

materials might be possible as you might have examples on different platforms, but i have no clue is theres a tool for it

Darn.. Would've hoped to be able to extract rigs & animations, and stuff.. I'm not really the most creative type when it comes to the visual stuff 

> Reply from Gh0stBlade
>
> 
Oh, you're not being rude at all. But there is a reason for me directing you to the UE4 source code. UE4's source code will contain the info required (structs for all file formats). That could potentially help you or someone else figure out how to write a tool to partially uncook or retrieve more data from the .uasset files. Doing this with no source code would be a very painful task but fortunately it's there.

Nevertheless, I don't believe that fully uncooking everything is possible.

Regards.

I have absolutely no experience in decompressing files, or anything remotely similar to it, so I don't think the source code would be of any help to me. I appreciate the suggestion though
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2016-06-01T20:12:10+00:00
- Post Title: UE4 .uasset

> Reply from Reck1501
>
> Darn.. Would've hoped to be able to extract rigs & animations, and stuff.. I'm not really the most creative type when it comes to the visual stuff

okay, watch out here! uncooking implied you wanted to import it back into unreal - but extracting rigs/animation is possible. have you tried [http://www.gildor.org/en/projects/umodel](http://www.gildor.org/en/projects/umodel)? (ignore that fact it isn't listed as compatiable)

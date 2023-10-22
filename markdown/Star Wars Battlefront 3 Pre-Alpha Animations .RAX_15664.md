## Post #1
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-12-30T09:20:34+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

Alright so i'm posting hoping someone can take a look at these and find away to finally get these to work cause they do share the same file format as the models do and we already have those cracked with a Unwrap 3d plugin.

So here is a file of various different animations some are really small like 2kb and some are a bit bigger but looking at them in a hex editor doesn't tell me much about them but than again i'm not great at stuff like this but i thought at least it'd show some data for the bones but it doesn't.

Anyways if someone could possible crack these animations open it would help out a lot of people like the guys over at Battlefront III Legacy mod and many others working on projects and mods to recreate the cancelled game.

[http://www.mediafire.com/file/9lexh24wl ... ations.rar](http://www.mediafire.com/file/9lexh24wl4vl17r/SWBF3_Animations.rar)
## Post #2
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-12-31T03:16:45+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #3
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2016-12-31T05:20:29+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

Well damn you're the one person i wanted to reply and give me hope it could be done cause you cracked the models but now you're saying it's impossible, well alright so i guess it's completely out of the question on the animations.
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2016-12-31T06:20:36+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #5
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-01T01:45:05+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #6
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-01-01T01:47:56+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Wobble
>
> Impossible just became possible.

http://imgur.com/jQGLl3p

Dude you are amazing like this just made what's left of a crappy 2016 a awesome one.

Will this be an update to the RAX model plugin on unwrap3d or a separate plugin for unwrap 3d later on?
## Post #7
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-01T01:59:37+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #8
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-01-01T03:34:15+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Wobble
>
> The same RAX plugin will be able to load animations.  But, it still needs some more work.

Animation data can be encoded in several different formats: floats, shorts, bytes, etc...  I have only decoded floats.

Grevious was an exception, because all of its data was encoded in floats.  Not so lucky with other files.

And the actual animation plays faster than this gif.

Well i'm hopeful you can get the other types working cause i didn't even think it would get this far as it did.
## Post #9
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-01T04:14:05+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #10
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-01T17:15:45+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #11
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-03T00:22:19+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #12
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-01-03T00:31:52+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Wobble
>
> I think rotation is correct, but still having problems with unpacking position.

The plugin scales everything up by 10 by default, so the original scale of the model is actually very small, usually less than 1.0. I think they're using that fact to normalize all of position values between -1 and 1.  If anything goes outside that range, they switch it over to floats, like Grievous walking away from his origin.  But, they must be adding in some kind of offset, since I don't think zero is really zero, but 0x7FFF.

I will release the plugin as beta anyway soon.  Rotations will look correct, but the character's feet may shift around.

I've seen game devs do animations like this in the past where they walk away from the origin i think they do it on purpose, but the other stuff about the feet i don't mind as long as the rest look great.

Thank you so much for all your hard work with this games file formats, so what character animations will be supported?
## Post #13
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-03T02:05:34+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #14
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-01-03T02:09:44+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Wobble
>
> All animations should load, but I've only tested a few.

There is also a scaling issue.  Animation position is scaled to -1 to 1.  But, the model may be larger than 1.0. For example, the spiderdroid model is larger than your typical character model.  Since animation is still small, it scales down the model's geometry, which isn't correct.  So, I'm missing a scaling factor.

Well, you can download it now.  I'm finished until something new comes up.
That's alright I can scale it with the root bone so that won't be a problem, thank you so much for your work.
## Post #15
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-03T04:07:15+00:00
- Post Title: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #16
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-01-03T08:42:46+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Wobble
>
> I don't think that would work, at least in UU3D.  You would need to modify the position keys directly.  It's too tedious to do by hand, so you would need to export the animation to some readable text format, and process it with a script or some other tool.

btw, this animation format is very similiar to League of Legends latest anim format.  They also use the 10-bit packed rotation, and packed WORDs for position.  But, this RAX format is missing the bounding box information to unpack it back into the correct scale again.

Um yeah i'm i notice the legs twitching a lot when it's just simple animations on the upperbody and arms for like reload...ect but that isn't to hard to fix just remove the animations on the legs for when they aren't missing.

Also i noticed a lot of the cutscene animations either don't load or load but just mess up the model some,as well some of the positions are off and you'll see on some characters their hands and other parts are pulled just a bit away from the mesh or stretched out farther not sure if this a problem with the script or Free Radical not finishing things yet.

Do you happen to think that some of this missing bounding box information is in the models havok.rax or novodex.rax files?
## Post #17
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-03T16:11:06+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #18
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2017-01-04T03:33:17+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Wobble
>
> I didn't look at the cutscene animations.  But, all animation should be valid.  Every animation is usually paired with an unique object. Two different objects can't use the same animation.  Especially if they have a different skeleton with a different bone count.
JakeGreen wrote:
Do you happen to think that some of this missing bounding box information is in the models havok.rax or novodex.rax files?

I think those files deal with physics and collision.  Havok and Novodex are two different physics APIs.  Animation should be self-contained in one file.  But if there's no scaling, then they could be using a constant value for all animations.

Ah well it was worth a shot asking, but i've noticed a lot of aniamtions missing from the files extracted that i can clearly see while playing the pre-alpha so my guess is the quickbms script isn't getting every file out.
## Post #19
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2017-01-04T22:59:43+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

[out]
## Post #20
- Username: cocco1960
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri Jun 10, 2016 4:01 pm
- Post datetime: 2017-10-06T14:53:16+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

Any progress with the animations?
## Post #21
- Username: TrumpetPro
- Rank: advanced
- Number of posts: 73
- Joined date: Wed Jul 06, 2016 8:51 am
- Post datetime: 2018-06-18T14:19:00+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

So is this project dead?
## Post #22
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-06-19T07:44:58+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

does anyone have files? I wanna see if I can pull something out off of it
thanks in advanced
## Post #23
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2018-06-19T07:47:22+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from Tosyk
>
> does anyone have files? I wanna see if I can pull something out off of it
thanks in advanced

Here you go [http://www.mediafire.com/file/9lexh24wl ... mations.ra](http://www.mediafire.com/file/9lexh24wl4vl17r/SWBF3_Animations.ra)
## Post #24
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-06-19T07:49:21+00:00
- Post Title: Re: Star Wars Battlefront 3 Pre-Alpha Animations .RAX

> Reply from JakeGreen
>
> Tosyk wrote:does anyone have files? I wanna see if I can pull something out off of it
thanks in advanced

Here you go http://www.mediafire.com/file/9lexh24wl ... mations.rahey, man, thanks. do you have a full build or link to it?

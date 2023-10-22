## Post #1
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-30T09:27:33+00:00
- Post Title: 3ds max model looking the same as Noesis preview

How do I make the model which looks like this in 3ds max



look like this in noesis 



When I click the cycle blend button, it became the same with 3ds max which results like this 



So how do I make model in 3ds max look the same like in noesis?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-30T10:19:56+00:00
- Post Title: 3ds max model looking the same as Noesis preview

it looks like the model was welded in max you will need to fix the normals.
you cn cheat to do this by setting the material to 100% self illumination.
## Post #3
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-30T11:16:20+00:00
- Post Title: 3ds max model looking the same as Noesis preview

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: ultimaespio
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Thu Apr 15, 2010 2:55 am
- Post datetime: 2011-08-30T17:28:24+00:00
- Post Title: 3ds max model looking the same as Noesis preview

You haven't set an Opacity map for the textures.

Which FullMetal game did this come from? He works in Dissidia 012 sometimes.
## Post #5
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-08-31T01:58:26+00:00
- Post Title: 3ds max model looking the same as Noesis preview

Ok I'll try that.

It's from full metal alchemist brotherhood for psp or Hagane No Renkinjutsushi - Senaka Wo Takuseshi Mono.
## Post #6
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-08-31T09:17:59+00:00
- Post Title: 3ds max model looking the same as Noesis preview

> Reply from ultimaespio
>
> You haven't set an Opacity map for the textures.

Which FullMetal game did this come from? He works in Dissidia 012 sometimes.

I confirm that the problem is simply to set the opacity of the textures correctly.

[](http://imageshack.us/photo/my-images/822/fullmu.jpg/)
## Post #7
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-11T00:09:19+00:00
- Post Title: 3ds max model looking the same as Noesis preview

How do I do that?

I tried adding map opacity but it becomes transparent in the perpective view and only looks fine when rendered, although it can obviously be seen that it became transparent.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-11T13:33:23+00:00
- Post Title: 3ds max model looking the same as Noesis preview

set the mono channel output to image alpha.
## Post #9
- Username: khanbot
- Rank: beginner
- Number of posts: 29
- Joined date: Tue Dec 13, 2011 6:12 pm
- Post datetime: 2012-03-11T20:10:58+00:00
- Post Title: 3ds max model looking the same as Noesis preview

hi, I am having the same problem as OP.

I have some Soulcalibur 4 models lying around, and I've tried making opacity maps, I open the texture in photoshop and invert.  so it a new dds file I make

how does noesis do this operation auto when I click cycle blend?

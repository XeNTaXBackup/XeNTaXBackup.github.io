## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T07:06:06+00:00
- Post Title: [Request] Yi Jian Xiang

Hello guys, well I found a cool game with cool stuff, I downloaded few minutes ago, I get files easy but the problem is model format, the format is .FAK and texture DDS, ok here I upload some samples for someone interested,take a view.

Model: FAK
Texture: DDS

<link removed due forum rules violation>
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T07:22:39+00:00
- Post Title: [Request] Yi Jian Xiang

lol I think it is the very similar to Loong FAK, except instead of wide-space characters they just have regular ascii or something.

EDIT: nvm, some differences 

Ugh now I have to change the loong FAK plugin just because they have the same idstring but encoded differently
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T07:53:06+00:00
- Post Title: [Request] Yi Jian Xiang

yeah, I try see files in Noesis and doesn't work, hope can do something with this.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T08:11:23+00:00
- Post Title: [Request] Yi Jian Xiang

Ya it's pretty much the same format.

Except...this thing has a massive number of vertex buffers.

Might take some more time to figure out what's going on. There's like at least 100+ vertex groups when there are only 5-6 face groups.

Evidently I don't know the relationship between the face groups and the vertex groups, and that's why it looks like I'm missing faces.

[http://db.tt/AoF2HH1h](http://db.tt/AoF2HH1h)

EDIT: ok, I see it now, each vertex section starts with a 4-char string indicating what "pose" it is.
So for example, you have the "std" (standard) pose, and the "atck" pose, etc.

But even then, there's still a lot of "atck"...
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T08:34:16+00:00
- Post Title: [Request] Yi Jian Xiang

cool work finale, here testing files, some errors.





G151 (ERROR)


G153 (ERROR)
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T16:20:54+00:00
- Post Title: [Request] Yi Jian Xiang

Yes, as I said, there are more vert groups than face groups so am not sure how it's supposed to be drawn.

This is because they store absolutely all of the poses in the model for some reason.
Each vert group starts with the name of the pose. A single pose is made from several groups, and there are multiple versions of the same pose.

For example, here's the dragon in G153, except I drew triangles for every vertex group randomly.



If you look at my debug log, you'll find "std", "bek", walk", etc along with the number of vertex groups associated with that "pose"

I just looped over the vert groups and randomly assigned a face group to it.
If you look carefully, you'll notice that it actually looks like it's capturing each "frame" of the dragon's walking animation.

Now I'm pretty curious why they actually do this. Isn't this the whole point of animation?
## Post #7
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2012-02-12T18:47:28+00:00
- Post Title: [Request] Yi Jian Xiang

damn, this is really confused, I don't understand the part of animation, and what about UNWRAP? in Noesis all be worked fine, but take a look after exported :S, really fucked, so how we fix it?

UNWRAP G151



OK now take a look UNWRAP of Valiant Monster, 1 Texture and 2 UNWRAP? WTF

Upbody



Legs
## Post #8
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-12T19:50:25+00:00
- Post Title: [Request] Yi Jian Xiang

lol I'm not sure what that means.
Maybe MrAdults knows what might be happening.

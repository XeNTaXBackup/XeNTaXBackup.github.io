## Post #1
- Username: tashmailok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 12:15 pm
- Post datetime: 2021-10-02T03:25:04+00:00
- Post Title: Tutorial - modding unreal engine files

I've actually modded Batman Arkham Asylum's Frontend.umap files to replace xbox button icons with playstation ones . I believe you can mod your game's packed files as well. The best way to explain the process would be with my example.

Tools needed
UE Viewer: [https://www.gildor.org/en/projects/umodel](https://www.gildor.org/en/projects/umodel)
UPK pack/unpack: [https://zenhax.com/download/file.php?id=261](https://zenhax.com/download/file.php?id=261)

1) I used UE Viewer to extract Frontend.umap. It has a file called Main2.gfx that I wanted to edit. I modded it to my liking using JPEXS Decompiler.
2) Because UE Viewer can't repack, I also used the UPK repack/unpack tool to unpack Frontend.umap which does that with a way different method.
3) Next I searched Main2 and it returned Main2.GFxMovieInfo (from UPK repack/unpack tool) which does have the content Main2.gfx (from UE Viewer) has but it also has some encryption(?) or compression data in the form of a couple lines in the beginning and a few lines at the end.
4) So I used Hex Editor to copy the extra text (encryption) from Main2.GFxMovieInfo into my edited Main2.gfx. Then I renamed the edited Main2.gfx to Main2.GFxMovieInfo and pasted it over Main2.GFxMovieInfo. So now this file has my modded data as well as the footer and header (encryption).
5) Then I repacked the whole thing the UPK tool and it worked 
But be warned how you mod the files will decide if you mod works or not because unreal engine files use some kind of internal referencing pointing between them. In my example, since it is a gfx (swf) file, all I did was change the character tags (xbox icons shape tags to ps icon shape tags) between shapes in the file and not import or export these shapes because doing that crashed my game.
## Post #2
- Username: tashmailok
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-02T10:43:32+00:00
- Post Title: Tutorial - modding unreal engine files

Hi, this method you described is well known in the community, I have translated "Deadpool" this way, for example.
But I think nobody shared this method in the step-by-step instruction (beside me, but only on discord), 
so I'm moving this topic to the tutorial section. Maybe it will help someone.

I'm also sending as an attachment to this post my version of this tutorial.


> the footer and header (encryption).
Btw, it's not encryption. It is normal header and footer.
[UNREAL_ENGINE_TUTORIAL_v0.2.zip](https://xentaxbackup.github.io/file/20934_UNREAL_ENGINE_TUTORIAL_v0.2.zip)
## Post #3
- Username: tashmailok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 12:15 pm
- Post datetime: 2021-10-04T07:50:01+00:00
- Post Title: Tutorial - modding unreal engine files

> Reply from ikskoks ↑Sat Oct 02, 2021 6:43 pm at Sat Oct 02, 2021 6:43 pm
>
> 
Hi, this method you described is well known in the community, I have translated "Deadpool" this way, for example.
But I think nobody shared this method in the step-by-step instruction (beside me, but only on discord), 
so I'm moving this topic to the tutorial section. Maybe it will help someone.

I'm also sending as an attachment to this post my version of this tutorial.

the footer and header (encryption).
Btw, it's not encryption. It is normal header and footer.

Hey thanks man, appreciate what you did.

Had no idea this was so well known. 
Could you help me out with this? I'm trying to do the same thing for Arkham City but to no success. All I wanna do is exchange the tags for XBox B button and PS3 Circle button. I'm attaching the swf file in case you decide to check it out.

Thanks again.
[FrontMostLayer.zip](https://xentaxbackup.github.io/file/20940_FrontMostLayer.zip)
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2021-10-04T08:20:43+00:00
- Post Title: Tutorial - modding unreal engine files

> I'm trying to do the same thing for Arkham City but to no success.
Didn't you already ask about it here? [viewtopic.php?f=10&t=24564](https://forum.xentax.com/viewtopic.php?f=10&t=24564)

I haven't checked it yet, but if I'll come up with something, I'll let you know.
## Post #5
- Username: tashmailok
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Sep 30, 2021 12:15 pm
- Post datetime: 2021-10-04T08:54:14+00:00
- Post Title: Tutorial - modding unreal engine files

> Reply from ikskoks ↑Mon Oct 04, 2021 4:20 pm at Mon Oct 04, 2021 4:20 pm
>
> 
I'm trying to do the same thing for Arkham City but to no success.
Didn't you already ask about it here? viewtopic.php?f=10&t=24564

I haven't checked it yet, but if I'll come up with something, I'll let you know.

I read you tutorial you posted above and it did wonders for me!
All I had to do is make my edits and remove assets that I wouldn't use so the file size was the same. I was scratching my head staying up late a couple nights over this.
Now I'll be able to make the mod for City and Origins!
Thank you so much!

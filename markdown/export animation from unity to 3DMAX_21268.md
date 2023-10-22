## Post #1
- Username: oscarlai
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 12, 2018 3:06 am
- Post datetime: 2019-10-19T17:21:13+00:00
- Post Title: export animation from unity to 3DMAX

Hi, 

can anyone help me with a problem I seem to be having?

I'm tring to export some animation with models fromt unity, and export them to 3DMax. I've exported them with AssetStudio, but when I import them to 3DMax, there is no animations. Is there any tool or way to resolve it?

Any help is appreciate.
## Post #2
- Username: mono24
- Rank: double-veteran
- Number of posts: 848
- Joined date: Sat Nov 06, 2010 7:27 am
- Post datetime: 2019-10-19T23:55:15+00:00
- Post Title: export animation from unity to 3DMAX

> Reply from oscarlai ↑Sun Oct 20, 2019 1:21 am at Sun Oct 20, 2019 1:21 am
>
> ...when I import them to 3DMax, there is no animations...
Now this is based on my experience as follows.

Under Options:
First make sure to enable animations, assuming you didn't already.
As well make sure to have selected: Group by source file



example.png (88.14 KiB) Viewed 101 times


Then under Export: choose All assets.

That way you should get three type of files:
A character FBX with out animations.
Separate FBXs for each individual animation.
Or a single FBX character with each animations included, but keep in mind depending on games some animations are still separate FBXs, there for import and see which one works for you.

Sometimes you need to import the character alone, then import the animations after in 3dsMax and the scene will update with that imported animation.
## Post #3
- Username: oscarlai
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Oct 12, 2018 3:06 am
- Post datetime: 2019-11-02T11:27:12+00:00
- Post Title: export animation from unity to 3DMAX

Thank you very much. I found some .fbx files  contain animations, and some don't. In the game they all contains animations. Is there something wrong with my operation?

> Reply from mono24 ↑Sun Oct 20, 2019 7:55 am at Sun Oct 20, 2019 7:55 am
>
> 
oscarlai wrote: ↑Sun Oct 20, 2019 1:21 am...when I import them to 3DMax, there is no animations...
Now this is based on my experience as follows.

Under Options:
First make sure to enable animations, assuming you didn't already.
As well make sure to have selected: Group by source file
example.png
Then under Export: choose All assets.

That way you should get three type of files:
A character FBX with out animations.
Separate FBXs for each individual animation.
Or a single FBX character with each animations included, but keep in mind depending on games some animations are still separate FBXs, there for import and see which one works for you.

Sometimes you need to import the character alone, then import the animations after in 3dsMax and the scene will update with that imported animation.

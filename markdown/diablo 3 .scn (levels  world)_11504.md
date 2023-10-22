## Post #1
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-05-12T16:54:50+00:00
- Post Title: diablo 3 .scn (levels / world)

Does anyone have any information on how "levels" are put together ( locations for putting .app-meshes together )?
The .wlr and .lvl files look too small... maybe \coredata\scene\*.scn files contain the info I'm looking for...?

Regards,
  Roger
## Post #2
- Username: TaylorMouse
- Rank: ultra-veteran
- Number of posts: 348
- Joined date: Mon Sep 26, 2011 7:51 pm
- Post datetime: 2014-05-14T20:29:14+00:00
- Post Title: diablo 3 .scn (levels / world)

No research (that I know of) has been done in that direction, probably difficult too, since the scenes in Diablo are randomized.

The engine first places the essential locations for the story and then fill the gaps with additional content scenes. So no overall location exist.

If you want to put together Old Tristram for example, that is easily done, the files contain the location in the filename; when you import Old Tristram in Max, you will see some gaps, these are filled randomly each time you start the game

T.
## Post #3
- Username: kalmiya
- Rank: beginner
- Number of posts: 22
- Joined date: Mon Mar 24, 2014 12:23 am
- Post datetime: 2014-05-18T12:32:24+00:00
- Post Title: diablo 3 .scn (levels / world)

> Reply from TaylorMouse
>
> No research (that I know of) has been done in that direction, probably difficult too, since the scenes in Diablo are randomized.
T.

Indeed, completely randomized zones are probably difficult, but one step back, there must be something saying which models "connect" together" - like "a1dun_Leor_EW_01.app" connects to "a1dun_Leor_EW_02.app". I might just brute-force some sno-id's of models which belong together through all data and see what comes up. 

I'll also check out Tristram. Basically you are saying - if I understand you correctly - that it's one large static mesh... Interesting..

I also started taking a look at the .scn and .phm files ( .phm in a separate thread: [viewtopic.php?f=10&t=11517](http://forum.xentax.com/viewtopic.php?f=10&t=11517)). I'm wondering about some values, maybe someone has ideas.
My example has 9216 squares, structure of a square being something like this:

struct D3NavMeshSquare
{
    float z;
    NavCellFlags navCellFlags; // enum / bitflags
    short unk1; // padding?
};

But the 'z' doesn't quite match... it's usually 0 and occasionally some 'weird' float. 

 

I still have some more structs, but its quite messy. Need to first look at it a bit more myself, before asking more questions. Anyway, going to check it out and see what I come up with. Is anybody else looking at this fileformat ( for d3-rs ) ?

Regards

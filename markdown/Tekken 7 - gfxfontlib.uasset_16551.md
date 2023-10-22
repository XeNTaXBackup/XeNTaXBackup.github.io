## Post #1
- Username: SpookyMajora
- Rank: beginner
- Number of posts: 24
- Joined date: Wed Apr 13, 2016 5:58 am
- Post datetime: 2017-07-17T07:21:23+00:00
- Post Title: Tekken 7 - "gfxfontlib.uasset"

I was wondering if anyone could help me out with cracking open the gfxfontlib file in Tekken 7, I'm aware that it would usually be able to be opened with umodel, but since Tekken 7 is running on UE4 I have a feeling that it's got something to do with the fact that umodel won't extract the .swf file. I've got the .uasset from the game if anyone wants to take a look at it, thanks in advance.

[https://mega.nz/#!cEVlWILC!ZoY2e3geMV0V ... hiBC1f4ISY](https://mega.nz/#!cEVlWILC!ZoY2e3geMV0VHj98yY33A66mIw4jFp-D1hiBC1f4ISY)
## Post #2
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2017-07-17T08:29:03+00:00
- Post Title: Tekken 7 - "gfxfontlib.uasset"

You can use Gildor's "extract" tool from command-line:

```
extract.exe -game=tekken7 gfxfontlib.uasset
```

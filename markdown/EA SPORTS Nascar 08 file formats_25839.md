## Post #1
- Username: Jacoby1218
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 27, 2016 6:01 am
- Post datetime: 2022-09-25T05:25:46+00:00
- Post Title: EA SPORTS Nascar 08 file formats

Hi, I extracted one of the .rsf archives and got quite a few different formats out of it. I don't even know where to start (i'm assuming the .moe file under GEOM but i'm not sure), and if we can copy the UV mapping that would be nice as well.
[testint.7z](https://xentaxbackup.github.io/file/22851_testint.7z)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-25T09:33:43+00:00
- Post Title: EA SPORTS Nascar 08 file formats

Using hex2obj (view link in my sig):
.



01-moe.jpg (157.37 KiB) Viewed 108 times

(first submesh)
## Post #3
- Username: Jacoby1218
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri May 27, 2016 6:01 am
- Post datetime: 2022-09-25T19:04:52+00:00
- Post Title: EA SPORTS Nascar 08 file formats

That's awesome! looks great. the only other thing i was going to ask is if we could somhow pull the material mapping from the .lta file (if that's not possible, it should still be possible to work with this). Is there potentially a header separating the submeshes? I saw your test for extracting madden 12 and saw the header STRM but i found no such header in my .rsf or in the .moe
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-09-25T20:13:40+00:00
- Post Title: EA SPORTS Nascar 08 file formats

> Reply from Jacoby1218 ↑Mon Sep 26, 2022 3:04 am at Mon Sep 26, 2022 3:04 am
>
> 
That's awesome! looks great. the only other thing i was going to ask is if we could somhow pull the material mapping from the .lta fileI'm not "the texture man"; but you can search for "LTAM" (= matl) in the .lta files to find the material names, "sponsorSticker", "Glass", etc.
(Should also be possible to get values of "specularIntensity" for example, if you are a coder.)

> Is there potentially a header separating the submeshes? I saw your test for extracting madden 12 and saw the header STRM but i found no such header in my .rsf or in the .moedunno, what you searched for, but the params are simply to be found (using "MRTS" and "XDNI" for search of further sub meshes):
.



moe_params.jpg (148.04 KiB) Viewed 87 times

accompanied by the strings "MRTS" (-> "STRM") and "XDNI", the latter reads "INDX" backwards.

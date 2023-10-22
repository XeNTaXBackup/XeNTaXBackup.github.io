## Post #1
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2022-05-21T18:51:01+00:00
- Post Title: Midnight Club II *.xmod

[https://mega.nz/file/gCxg0Bra#BMrtbmg0f ... 81h8km1NuU](https://mega.nz/file/gCxg0Bra#BMrtbmg0fNw3DG2sgACpQcB76w0lr03-381h8km1NuU)
level models: [https://mega.nz/file/wCQBxaZT#ggDUzW1p7 ... b049LHzI-4](https://mega.nz/file/wCQBxaZT#ggDUzW1p7QowyMV8TUbtwfSHEheVNBAD_b049LHzI-4)

I tried this Noesis plugin from HimeWorks, but it got an error:



bandicam 2022-10-29 11-34-28-975.jpg (71.9 KiB) Viewed 71 times



It seems that *.xmod files from Midnight Club II are in an ASCII format. I also tried the PKG/XMOD converter, but it's super old and will crash

Anyone found a proper way to import *.xmod files with Noesis or Blender?
## Post #2
- Username: mrmaller1905
- Rank: advanced
- Number of posts: 65
- Joined date: Fri Dec 31, 2021 2:25 am
- Post datetime: 2023-01-24T13:36:14+00:00
- Post Title: Midnight Club II *.xmod

Bump
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-01-26T19:54:47+00:00
- Post Title: Midnight Club II *.xmod

> Reply from mrmaller1905 ↑Sun May 22, 2022 2:51 am at Sun May 22, 2022 2:51 am
>
> It seems that *.xmod files from Midnight Club II are in an ASCII format.Yeah, it's super easy to import a point cloud (after doing some replacements, n->vn, t->vt and some deletions):
.



mc2-vp_lexus_body_ui_h.xmod.png (16.63 KiB) Viewed 44 times


(Someone needs to add face indices; maybe auto created ones would do.)

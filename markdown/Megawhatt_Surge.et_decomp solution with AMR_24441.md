## Post #1
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-01T15:02:03+00:00
- Post Title: Megawhatt_Surge.et_decomp solution with AMR?

Hi guys, I have a issue with Advanced Mesh Reaper, I don't seem to get the texcoords, the UVs, and the model's texture with the normals though. but I need help with "Megawhatt_Surge.et_decomp" in Advanced Mesh Reaper, here's what the issue looks like:



Megawhatt_Surge_AMR_Issue.png (64.55 KiB) Viewed 81 times


And here's the link for the file on Google Drive.
[https://drive.google.com/file/d/1p0sSuK ... sp=sharing](https://drive.google.com/file/d/1p0sSuKBaoQebBjMuap76z5zmcvA2-r-i/view?usp=sharing)

P.S. This is my first time using Advanced Mesh Reaper.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-09-01T19:15:24+00:00
- Post Title: Megawhatt_Surge.et_decomp solution with AMR?

well, I see, you're trying at least - that's good!  

the "99" is wrong - that's the "code" (in hex2obj!) for: "uvs not handled". Well, I've never explained that properly.  

But this is AMR. And 0xddf is not the start of texcoords but positions.

UVs seem to start at 0xdf37, UVBsize is 8 for hex2obj. But they look a little bit weird using half floats (with shorts it looked even worse for me):
.



uvsOrnot.png (5.4 KiB) Viewed 61 times
## Post #3
- Username: lilyampykidXeNTaXalt
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Aug 28, 2021 5:11 am
- Post datetime: 2021-09-02T15:38:33+00:00
- Post Title: Megawhatt_Surge.et_decomp solution with AMR?

Thanks! It is my first time trying

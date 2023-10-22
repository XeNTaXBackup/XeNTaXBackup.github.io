## Post #1
- Username: DemiGhost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 22, 2015 9:55 am
- Post datetime: 2018-08-12T12:12:23+00:00
- Post Title: Hi please rip this model please please please

Hi please RIP this model 
[https://www.mediafire.com/file/hdyvdok8obnhiy4/Ise.zip](https://www.mediafire.com/file/hdyvdok8obnhiy4/Ise.zip)

please use this model viewer to rip the model 
[https://www.sas1946.com/main/index.php?topic=3004.0](https://www.sas1946.com/main/index.php?topic=3004.0)

THANK YOU  VERY MUCH IN ADVANCE  
THANK YOU THANK YOU VERY MUCH
## Post #2
- Username: tone
- Rank: beginner
- Number of posts: 35
- Joined date: Mon Jul 03, 2017 3:40 am
- Post datetime: 2018-08-13T16:11:12+00:00
- Post Title: Hi please rip this model please please please

from what game is this?
## Post #3
- Username: PredatorCZ
- Rank: mega-veteran
- Number of posts: 291
- Joined date: Tue Apr 22, 2014 3:32 am
- Post datetime: 2018-08-13T16:59:45+00:00
- Post Title: Hi please rip this model please please please

> Reply from tone
>
> from what game is this?

Its from Il-2 1946, everything is in readme. It's some mod.

Models are in ascii, very similar to obj format.
## Post #4
- Username: DemiGhost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 22, 2015 9:55 am
- Post datetime: 2018-08-14T12:40:33+00:00
- Post Title: Hi please rip this model please please please

so will anyone do it? please? THANK YOU ADVANCE btw
I think Ninja Ripper will work perfectly on RIPING the model in the model viewer , sorry I don't have experience using ninja ripper my apologies everyone..
so if anyone can rip the model IT IS HUGELY APPRECIATED THANK YOU AGAIN IN ADVANCE
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-08-16T09:41:04+00:00
- Post Title: Hi please rip this model please please please

> Reply from DemiGhost
>
> so will anyone do it? please?Model format is pretty simple 
so you simply need to add "v " (without the quotes) to the vertex lines:
[Vertices_Frame0]
0.549900 0.549900 1.283600 0.000000 0.000000 1.000000

add "vt " (without quotes) to the uv lines:
[MaterialMapping]
0.948280 0.454190 

and do some math with the face indices lines (and add uvs indices):
[Faces]
0 1 2
1 3 2

->
f 1/1 2/2 3/3
f 2/2 4/4 3/3

For Head6.msh it results in this:



Head6-msh.jpg (100 KiB) Viewed 62 times



(For me there's too many gun models in this game, so I'm off.)

edit: well, seems I completely misunderstood your request:

> Reply from DemiGhost
>
> please use this model viewer to rip the model 
https://www.sas1946.com/main/index.php?topic=3004.0Why don't you use it just yourself?
The "viewer" is a converter and capable of converting msh to obj files, for example.

Use File/Load Msh, then
File/Save to Obj,
done
## Post #6
- Username: DemiGhost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 22, 2015 9:55 am
- Post datetime: 2018-08-18T00:27:57+00:00
- Post Title: Hi please rip this model please please please

> Reply from shakotay2
>
> DemiGhost wrote:so will anyone do it? please?Model format is pretty simple 
so you simply need to add "v " (without the quotes) to the vertex lines:
[Vertices_Frame0]
0.549900 0.549900 1.283600 0.000000 0.000000 1.000000

add "vt " (without quotes) to the uv lines:
[MaterialMapping]
0.948280 0.454190 

and do some math with the face indices lines (and add uvs indices):
[Faces]
0 1 2
1 3 2

->
f 1/1 2/2 3/3
f 2/2 4/4 3/3

For Head6.msh it results in this:
Head6-msh.jpg

(For me there's too many gun models in this game, so I'm off.)

edit: well, seems I completely misunderstood your request:
DemiGhost wrote:please use this model viewer to rip the model 
https://www.sas1946.com/main/index.php?topic=3004.0Why don't you use it just yourself?
The "viewer" is a converter and capable of converting msh to obj files, for example.

Use File/Load Msh, then
File/Save to Obj,
done

I have tried, but the textures, parts came out all wrong, so yeah maybe using Ninja Ripper will work but well I admit that I don't have that much knowledge on Ninja Ripper  by the way to view the whole ship on the model viewer is to open the Hier.him

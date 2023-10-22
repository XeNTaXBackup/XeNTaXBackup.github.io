## Post #1
- Username: Elementalix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 10, 2018 2:19 am
- Post datetime: 2021-03-24T05:45:50+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

Hello the game is:Tokyo Necro:Suicide Mission from Nitro + . The model file is an mdl.
Here's same sample (Updated):[https://www.mediafire.com/file/m39gvi5q ... c.rar/file](https://www.mediafire.com/file/m39gvi5qg71xfel/ehc.rar/file) THX
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-24T15:22:51+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?


## Post #3
- Username: Elementalix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 10, 2018 2:19 am
- Post datetime: 2021-03-27T10:31:51+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

Hello i tried to open it with Asset Studio but nothing shows up .Thx for the reply !
## Post #4
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-03-27T14:48:40+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?


## Post #5
- Username: Elementalix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 10, 2018 2:19 am
- Post datetime: 2021-03-30T09:20:21+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

Hello again ,i know of the topic but the blender script will loop ,probably the encryption is different. THX for the reply! 
The code what the terminal is displays :
Root 28
Root 28
...
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-30T16:22:36+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

yeah, would take hours to understand/patch the script, I did it for one specific mdl only:
.



st_ehc_9310d-mdl.png (117.15 KiB) Viewed 115 times
## Post #7
- Username: Elementalix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 10, 2018 2:19 am
- Post datetime: 2021-03-31T08:32:39+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

I see, thx for the reply tho.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-31T08:45:34+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

I really don't like to care for weapons so I didn't bother any further but this as some hints:

The format has changed a little bit, if you patch the .py like so
.



patch_py.png (15.14 KiB) Viewed 100 times



the error message looks like this:

```
Traceback (most recent call last):
  File "sonicomi - org.py", line 556, in openfile
  File "sonicomi - org.py", line 383, in mdl_parser
  File "sonicomi - org.py", line 289, in frme
  File "sonicomi - org.py", line 144, in vertexuv
RuntimeError: mesh has no faces
```

With some rough understanding of the script you can apply another patch by copying some branches like 		

```
...
mesh.update()
```

from
def frme(n,mesh_id,parent)
to
def mdl_parser(filename)

(Blender will freeze in an endless loop displaying the chunk name you didn't handle so far.)

This is a very ugly patch but worked (more or less) for the models you uploaded.
## Post #9
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2021-04-01T23:51:52+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?


## Post #10
- Username: Elementalix
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Nov 10, 2018 2:19 am
- Post datetime: 2021-04-04T15:06:57+00:00
- Post Title: Hey guys ! dose any one have any idea how to convert mdl to fbx ?

Yeah bro,thx for help !

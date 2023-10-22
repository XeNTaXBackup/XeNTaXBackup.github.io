## Post #1
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-04T10:55:21+00:00
- Post Title: Uknown Model type

Hy guys, plz help me with miam vice psp model.
They have no extensions. I tryed to add in the end: 3d's,fbx tps step obj max, etc.

 (e.g. they come as "model" and I add model.obj) and open with a program but they can't be read. I tryde blender, openscade, model viewer. Here are the  models 
[https://www.mediafire.com/file/yyf0nsb7 ... s.zip/file](https://www.mediafire.com/file/yyf0nsb7v6lesia/blackmodels.zip/file)
## Post #2
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-04T12:58:33+00:00
- Post Title: Uknown Model type

> Reply from Bherisi ↑Sat Jun 04, 2022 6:55 pm at Sat Jun 04, 2022 6:55 pm
>
> 
I tryed to add in the end: 3d's,fbx tps step obj max, etc.
wow. nice methods.  
using hex2obj



pistol.png (16.5 KiB) Viewed 99 times
## Post #3
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-04T14:02:36+00:00
- Post Title: Uknown Model type

add ext [*.unk]

python script for add ext [*.unk] for all files in folder

```

dir = "C:\\Users\\admin\\Desktop\\folder"

for file in os.listdir(dir):
    os.rename(os.path.join(dir,file),os.path.join(dir,file + ".unk"))

```

[fmt_unk.zip](https://xentaxbackup.github.io/file/22315_fmt_unk.zip)
## Post #4
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-04T17:27:40+00:00
- Post Title: Uknown Model type

Atlast  Thanks.

But The human models (53 kb and others) can't be opened. 
How to view them
## Post #5
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-06-04T20:19:13+00:00
- Post Title: Uknown Model type

> Reply from Bherisi ↑Sun Jun 05, 2022 1:27 am at Sun Jun 05, 2022 1:27 am
>
> 
How to view them
add extension [*.char]

[fmt_char.zip](https://xentaxbackup.github.io/file/22316_fmt_char.zip)
## Post #6
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-05T13:18:06+00:00
- Post Title: Uknown Model type

Thanks.
## Post #7
- Username: Bherisi
- Rank: n00b
- Number of posts: 10
- Joined date: Thu Jun 02, 2022 7:08 pm
- Post datetime: 2022-06-06T15:04:11+00:00
- Post Title: Uknown Model type

How can I save it as a .unk or .char model again  after converting to obj??    #in-noesis

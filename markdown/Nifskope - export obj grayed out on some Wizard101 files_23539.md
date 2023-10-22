## Post #1
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2021-03-03T04:14:57+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

Hey there, so I've been messing around lately with converting Wizard101 files and for some reason some of the Marleybone dungeons are refusing to load properly. I can't figure out why it won't let me export this as an obj (but it'll let me export other stuff just fine). 
I'm using Nifskope 2.0 and had extracted the archive with the latest quickbms script. 



Screenshot 2021-03-02 220143.jpg (62.05 KiB) Viewed 98 times


I'm sorry for the low quality, it's kinda hard to see but the import/export options are definitely disabled. Any idea how to re-enable that? I noticed all the ones it had trouble with had a file name that started with "14G" or something like that, is it something with the file name? Thanks everyone
## Post #2
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2021-03-16T00:40:07+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

I'd also like to mention, though this may not be related, that when I open up some of the character models they get all mangled up like this.
Like I say though, this might not be related.
[Cursed2.jpg](https://xentaxbackup.github.io/file/19727_Cursed2.jpg)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-16T11:18:05+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

> Reply from xpunkrockyugox ↑Wed Mar 03, 2021 12:14 pm at Wed Mar 03, 2021 12:14 pm
>
> 
Hey there, so I've been messing around lately with converting Wizard101 files and for some reason some of the Marleybone dungeons are refusing to load properly.Without a sample noone can tell, I fear.
## Post #4
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2021-03-19T01:52:40+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

> Reply from shakotay2 ↑Tue Mar 16, 2021 7:18 pm at Tue Mar 16, 2021 7:18 pm
>
> 
Without a sample noone can tell, I fear.

Oh, right, definitely! I've got a Google Drive link containing both some stages/models that do work and some that don't. Most of these are in Marleybone. I didn't include the textures, however, because due to them being saved as .nifs the folder size is pretty big and I was both too lazy to convert them all (though I will need to later on for the ones that do work lol) and too lazy to wait for the folder to upload into Google Drive. Sorry about that, hope they're not crucial to figuring out what's wrong. 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/14dgVrcKcNmolSROPZ49zs8-1CUwGuSA5?usp=sharing) Here you go, hope this is able to shed some light on it
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-19T15:21:22+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

Thanks!
yeah, pretty simple, for 14G_MB_SkeletoneKey_JRT_01.nif Export is grayed out because nif version is 20.6.0.0.

This is hardcoded in the exe (grayout when getVersionNumber() >= 0x14050000). If you change that in source and export the resulting obj file is empty.

So the question is how comes that it can't export though the "room" is displayed correctly?
## Post #6
- Username: xpunkrockyugox
- Rank: beginner
- Number of posts: 34
- Joined date: Tue Aug 11, 2020 7:55 am
- Post datetime: 2021-03-19T19:53:33+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

> Reply from shakotay2 ↑Fri Mar 19, 2021 11:21 pm at Fri Mar 19, 2021 11:21 pm
>
> 
So the question is how comes that it can't export though the "room" is displayed correctly?

Thanks for the explanation! Trying to figure out what was wrong was definitely driving me crazy.   
So for those would I need to find a program that opens .nifs of that high of a version number? Or might I have to break out the hex editor and AMR again like I did for the Cars 2 models? (Which, if anybody's wondering about that, I've gotten all the models I wanted into Blender, but unfortunately I just haven't had the energy or whatever to learn how to use Blender and make the things I originally wanted to make with those models.)
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-03-19T20:34:58+00:00
- Post Title: Nifskope - export obj grayed out on some Wizard101 files

> Reply from xpunkrockyugox ↑Sat Mar 20, 2021 3:53 am at Sat Mar 20, 2021 3:53 am
>
> So for those would I need to find a program that opens .nifs of that high of a version number?Seems Noesis can handle it (fmt_gamebryo_nif.py from Rich, or maybe patched version by some guy).

> Or might I have to break out the hex editor and AMR again like I did for the Cars 2 models?For nif meshes the simplest things may work  :
.



SkeletoneKey_JRT_01.png (23.8 KiB) Viewed 40 times

But here you're better off to try out Noesis.

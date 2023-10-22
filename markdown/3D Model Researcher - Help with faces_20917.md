## Post #1
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-05T22:59:02+00:00
- Post Title: 3D Model Researcher - Help with faces

Hi guys, i'm having an issue extracting the faces of a model.

I've found the vertices but the faces will not extract properly, can anyone tell me what I'm doing wrong? 

I'm sure I have the starting address for the vertices and faces right, but I'm really new to this so I could be wrong

i will attach the file as a reply so feel free to examine it.

Any help is greatly appreciated!! Thank you in advance!!!!
-EDXZ



help.png (124.42 KiB) Viewed 206 times
## Post #2
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-05T23:08:59+00:00
- Post Title: 3D Model Researcher - Help with faces

6118.zip
(194.61 KiB) Downloaded 15 times



the file was originally .dat extension. Don't forget to change the file extension back to .dat when downloaded

Creator of 3D model researcher said i need to somehow convert the data but i'm not sure what that means, how to do it or what to convert it to
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-06T00:40:21+00:00
- Post Title: 3D Model Researcher - Help with faces

the starting offset for vertices looks like it should be 0x3c70 
and the starting offset for face indices should be 0x26460
but i don't think you can read them in a single array.
the file structure looks a lot like the rax files from SWBF3.
## Post #4
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-06T00:51:36+00:00
- Post Title: 3D Model Researcher - Help with faces

> Reply from Acewell ↑Tue Aug 06, 2019 8:40 am at Tue Aug 06, 2019 8:40 am
>
> 
the starting offset for vertices looks like it should be 0x3c70 
and the starting offset for face indices should be 0x26460
but i don't think you can read them in a single array.
the file structure looks a lot like the rax files from SWBF3.

The file is from Haze! It was made by the same developers. Both games were in production around the same time!   

But dude you're amazing! The offsets you gave me worked! 



progress.png (109.31 KiB) Viewed 180 times



When you say they cant be read in a single array, what does that mean? 3D MR has a Padding\Pad inter function, could it be related to that?
## Post #5
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-06T05:22:25+00:00
- Post Title: 3D Model Researcher - Help with faces

> Reply from EDXZ23 ↑Tue Aug 06, 2019 8:51 am at Tue Aug 06, 2019 8:51 am
>
> When you say they cant be read in a single array, what does that mean?
i mean the indices are stored together but i think they are split into material groups,
because when you try to render the whole array they look mangled. 
there might be start and stop offsets stored in the file.
## Post #6
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-06T10:38:44+00:00
- Post Title: 3D Model Researcher - Help with faces

> Reply from Acewell ↑Tue Aug 06, 2019 1:22 pm at Tue Aug 06, 2019 1:22 pm
>
> 
EDXZ23 wrote: ↑Tue Aug 06, 2019 8:51 amWhen you say they cant be read in a single array, what does that mean?
i mean the indices are stored together but i think they are split into material groups,
because when you try to render the whole array they look mangled. 
there might be start and stop offsets stored in the file.

Ohhhh right I understand you. How would I go bout finding them? 

Is there a pattern for the face indices I need to look out for? Or if you have the time could you help me find them? 

I really wanna learn all this so I could do this for myself and contribute to threads and help people like how you've helped me,
but there's still so much I need to learn.


PS. I genuinely appreciate how much you've helped me already, you have no idea how much it means. I've been working on this project for months
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2019-08-10T08:40:13+00:00
- Post Title: 3D Model Researcher - Help with faces

eh i don't really look into model formats much anymore, no time, too busy with texture formats.
all of my current research on the rax format is here though if you care to have a read through:
[viewtopic.php?f=16&t=13867&hilit=rax&start=60#p126467](https://forum.xentax.com/viewtopic.php?f=16&t=13867&hilit=rax&start=60#p126467)
## Post #8
- Username: EDXZ23
- Rank: n00b
- Number of posts: 19
- Joined date: Wed May 08, 2019 2:49 am
- Post datetime: 2019-08-10T21:47:04+00:00
- Post Title: 3D Model Researcher - Help with faces

> Reply from Acewell ↑Sat Aug 10, 2019 4:40 pm at Sat Aug 10, 2019 4:40 pm
>
> 
eh i don't really look into model formats much anymore, no time, too busy with texture formats.
all of my current research on the rax format is here though if you care to have a read through:
viewtopic.php?f=16&t=13867&hilit=rax&start=60#p126467

thanks man, you've been great with the help i really appreciate it. it seems these rax files are a lot more trouble than they are worth. I'll continue to research them and if i come up with anything new I'll be sure to let you know

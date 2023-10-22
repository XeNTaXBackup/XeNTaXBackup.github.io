## Post #1
- Username: WhiteTPoison
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 06, 2022 4:47 am
- Post datetime: 2022-01-11T20:46:45+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

Hey guys,

So, it's fairly well known you can extract files out of the sally_clean.bf file using many different extractors. My favorite at the moment is JadeStudio, for instance. However, once those files are ripped, there are supposedly models within some of these *.bin files. I took a look at a few of them using HxD and it looks like what discerns this is whether or not they contain something called a *.map file, and within that *.map file is several *.gao files, so my best guess is that these *.bin files are actually compressed archives in some way? I don't know where to go from here, and it looks like based on several days of googling and research that no one else does either. If you know what to do with these files to manually rip the models out of them, or have some resources that will teach me how, I would greatly appreciate it. I have quite a bit of programming/RE experience, just none when it comes to models. I would like to add functionality somewhere to rip the models, most likely a fork of JadeStudio, but first I need to tackle doing it manually... The bin files can be found here: [https://drive.google.com/file/d/1cpNAzA ... sp=sharing](https://drive.google.com/file/d/1cpNAzAuWFdr-95Ilh0pkSC2VJpA7a1qu/view?usp=sharing).

The engine BGE uses is a very early version of Jade Engine, and it looks like we have some serialization details here: [https://github.com/Adsolution/Ray1Map/t ... rializable](https://github.com/Adsolution/Ray1Map/tree/79f620428a8c9517cc4c772304070ea3505b753f/Assets/Scripts/Games/Jade/Serializable) (Rayman 1 map viewer source code,) but nothing that tips me into how a gao or map files are structured AFAIK.

Thanks in advance!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-11T21:47:06+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

> Reply from WhiteTPoison ↑Wed Jan 12, 2022 4:46 am at Wed Jan 12, 2022 4:46 am
>
> 
Hey guys,
[...]
and it looks like based on several days of googling and research that no one else does either.If no one else does you'll need to do it yourself.  
.



FF0084DF-decompressed-bin.png (23.73 KiB) Viewed 142 times
## Post #3
- Username: WhiteTPoison
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 06, 2022 4:47 am
- Post datetime: 2022-01-11T21:54:08+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

> Reply from shakotay2 ↑Wed Jan 12, 2022 5:47 am at Wed Jan 12, 2022 5:47 am
>
> 
WhiteTPoison wrote: ↑Wed Jan 12, 2022 4:46 am
Hey guys,
[...]
and it looks like based on several days of googling and research that no one else does either. 
If no one else does you'll need to do it yourself.  
.
FF0084DF-decompressed-bin.png

Yep! I just don't have any clue where to start. Could you send some resources my way on where you would start to look on how to deconstruct the pieces of this file?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-11T22:28:27+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

> Reply from WhiteTPoison ↑Wed Jan 12, 2022 5:54 am at Wed Jan 12, 2022 5:54 am
>
> Could you send some resources my way on where you would start to look on how to deconstruct the pieces of this file?The only resource I have is my experience - I can't send you that.  

(You might start reading the tutorial I linked to in my sig.)
## Post #5
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-01-16T02:42:45+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

I look forward to seeing this.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-16T07:38:26+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

Nothing will happen without new inputs. 
(reminder for me: why didn't I care for the face indices?  )

well, a matter of understanding structures, getting correct start addresses (vertex block) and such stuff:
.



2ndtry bey good&evil.png (128.38 KiB) Viewed 75 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-01-16T22:55:01+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

finally:
.



finally.png (113.76 KiB) Viewed 83 times
## Post #8
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2022-02-18T02:42:57+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

> Reply from shakotay2 ↑Mon Jan 17, 2022 6:55 am at Mon Jan 17, 2022 6:55 am
>
> 
finally:
.
finally.png

How did you do that?
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2022-02-18T09:56:25+00:00
- Post Title: Beyond Good & Evil/Beyond Good & Evil HD .bin Files

I collected the faces somehow. After 4 weeks I don't remember how exactly. I'm dealing with dozens of model formats, so you'll need to ask when the "iron is hot".

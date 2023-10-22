## Post #1
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-28T00:42:20+00:00
- Post Title: 武术世界 meshes

Hello I was able to get some samples of this game, but at see the data, doesn't look like a mesh data, seems different and dunno where tos start to get  any kind of mesh with hex2obj. Any kind of help gonna be much appreciated! Thanks!

[https://www.mediafire.com/file/s1uwnvsz ... es.7z/file](https://www.mediafire.com/file/s1uwnvszni0d5kk/%25E6%25AD%25A6%25E6%259C%25AF%25E4%25B8%2596%25E7%2595%258C_samples.7z/file)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-04-28T05:04:36+00:00
- Post Title: 武术世界 meshes

Unpack files with the following BMS cmds:

```
get fileCnt short
for i = 0 < fileCnt
	get Len short
	getdstring Name Len
	get Offset long
	get Size long
	set Ext string Name
	string Ext ! "."
	if Ext == "geom"
		set ZSize long Size
		math Size * 20
		clog Name Offset ZSize Size
	else
		log Name Offset Size
	endif
next i

```

The rest should be easy.



avatar.geom.png (115.51 KiB) Viewed 215 times
## Post #3
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-28T07:06:50+00:00
- Post Title: 武术世界 meshes

> Reply from Bigchillghost ↑Fri Apr 28, 2023 1:04 pm at Fri Apr 28, 2023 1:04 pm
>
> 
Unpack files with the following BMS cmds:
Thanks Bigchillghost! gonna be reviewing the model!
## Post #4
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-29T02:48:52+00:00
- Post Title: 武术世界 meshes

> Reply from Bigchillghost ↑Fri Apr 28, 2023 1:04 pm at Fri Apr 28, 2023 1:04 pm
>
> 
The rest should be easy.
Hello Bigchillghost!   , would you mind in share your values please? I tried with these
## Post #5
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-04-29T07:09:15+00:00
- Post Title: 武术世界 meshes

> Reply from moonpaladin ↑Sat Apr 29, 2023 10:48 am at Sat Apr 29, 2023 10:48 am
>
> 
would you mind in share your values please? I tried with these
What's your general routine for such tasks? Just randomly try some addresses and see if it will work? Obviously you still lack the concept of general datatypes and possibly used fields (counts, sizes, lengths, etc.) in archives/asset files. It's time to learn from the beginning. Read the tutorial through the 1st link in my signature.
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-29T11:32:40+00:00
- Post Title: 武术世界 meshes

> Reply from Bigchillghost ↑Sat Apr 29, 2023 3:09 pm at Sat Apr 29, 2023 3:09 pm
>
> 
What's your general routine for such tasks? Just randomly try some addresses and see if it will work?  Something like that...  
.



Unicorn.png (63.63 KiB) Viewed 170 times
## Post #7
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-29T15:15:44+00:00
- Post Title: 武术世界 meshes

> Reply from Bigchillghost ↑Sat Apr 29, 2023 3:09 pm at Sat Apr 29, 2023 3:09 pm
>
> 
 Read the tutorial through the 1st link in my signature.
Im reading it!
## Post #8
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-29T15:17:01+00:00
- Post Title: 武术世界 meshes

> Reply from shakotay2 ↑Sat Apr 29, 2023 7:32 pm at Sat Apr 29, 2023 7:32 pm
>
>  Something like that...
Thanks shakotay2!
## Post #9
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-30T05:17:29+00:00
- Post Title: 武术世界 meshes

> Reply from shakotay2 ↑Sat Apr 29, 2023 7:32 pm at Sat Apr 29, 2023 7:32 pm
>
> 
 Something like that...
Shakotay2! you had checked the uv values?   
I was reading Bigchillghost tutorial, but uv's always make it harder, using this values:
12---99
1C364---12
## Post #10
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-04-30T05:40:36+00:00
- Post Title: 武术世界 meshes

Finding the uvs' block is no rocket science here. Give the file a structure. Seems there's markers, 001700, 001400 (first occurrence only of each).
## Post #11
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-04-30T06:53:10+00:00
- Post Title: 武术世界 meshes

> Reply from shakotay2 ↑Sun Apr 30, 2023 1:40 pm at Sun Apr 30, 2023 1:40 pm
>
> 
Finding the uvs' block is no rocket science here. Give the file a structure. Seems there's markers, 001700, 001400 (first occurrence only of each).
Thanks! gonna be checking !
## Post #12
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-05-02T01:11:21+00:00
- Post Title: 武术世界 meshes

> Reply from shakotay2 ↑Sun Apr 30, 2023 1:40 pm at Sun Apr 30, 2023 1:40 pm
>
> 
Seems there's markers, 001700, 001400 (first occurrence only of each).
I have saw this part too, around DE2C but still wrong
## Post #13
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-05-02T07:26:47+00:00
- Post Title: 武术世界 meshes

> Reply from moonpaladin ↑Sun Apr 30, 2023 1:17 pm at Sun Apr 30, 2023 1:17 pm
>
> 
I was reading Bigchillghost tutorial, but uv's always make it harder
You read, yet not asking any questions. I wouldn't be optimistic to think you have learned the basic. If you'd ever noticed the 4-byte field before every data chunk, we wouldn't be here for this conversation.
## Post #14
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-05-02T12:33:53+00:00
- Post Title: 武术世界 meshes

> Reply from moonpaladin ↑Tue May 02, 2023 9:11 am at Tue May 02, 2023 9:11 am
>
> 
I have saw this part too, around DE2C but still wrongI have no words; UV's start is at 0xDE2A.
## Post #15
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-05-03T05:35:06+00:00
- Post Title: 武术世界 meshes

> Reply from Bigchillghost ↑Tue May 02, 2023 3:26 pm at Tue May 02, 2023 3:26 pm
>
> 
You read, yet not asking any questions. I wouldn't be optimistic to think you have learned the basic. If you'd ever noticed the 4-byte field before every data chunk, we wouldn't be here for this conversation.
I had not much time this week to read and practice with the examples on your guide, but gonna do it
## Post #16
- Username: moonpaladin
- Rank: ultra-veteran
- Number of posts: 404
- Joined date: Tue Mar 05, 2019 1:24 pm
- Post datetime: 2023-05-03T05:40:09+00:00
- Post Title: Re: 武术世界 meshes

> Reply from shakotay2 ↑Tue May 02, 2023 8:33 pm at Tue May 02, 2023 8:33 pm
>
> 
; UV's start is at 0xDE2A.
thanks shakotay2! was near but not enough, but dunno if I tried that value because I remember that kind of "80 3F" that appears in many games.

## Post #1
- Username: artbarot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 15, 2018 11:33 pm
- Post datetime: 2018-01-16T20:06:54+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

Hello, this is my first attempt extracting resources, I have been checking tutorials in here but I'm stuck in my personal project.

I have sucessfully extracted sound files, but regarding textures and models I have not been successfull.

My request is if someone could check the file I put in annex and could confirm my suspitions/ give me tips on further research.
In order to make this more easy, just import the bookmarks.

This is probably my favorite game and I wanted to do it to feel proud
Thanks in advance
[a.zip](https://xentaxbackup.github.io/file/13864_a.zip)
## Post #2
- Username: artbarot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 15, 2018 11:33 pm
- Post datetime: 2018-02-01T14:16:01+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

I'm bumping because I changed the previous question (I made some advancements, sorry if it is viewed as spamming)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-01T17:51:49+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

this bms script will split your bin sample  

```

get BIN_SIZE asize
get FOLDER basename
math i = 1 
for i
	get OFFSET long
	savepos TMP
	if OFFSET == BIN_SIZE
		break
	endif
	get NEXT_OFFSET long
	xmath SIZE "NEXT_OFFSET - OFFSET" 
	string NAME p "%s\%d.dat" FOLDER i
	log NAME OFFSET SIZE
	goto TMP
next i

```

i can't help you with the contents of PS2 files but the last one looks like paletted image data.
## Post #4
- Username: artbarot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 15, 2018 11:33 pm
- Post datetime: 2018-02-01T18:47:07+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

Man so much thanks!! I was viewing this for like 2 weeks, you come here instantly and do this. I have training now, when I finish I will test  this right away. A guy said the file contained textures and the last part model/models (in beggining there are 6 pointers (4byte) but the last one points to a different kind(maybe what you mention as paletted image data), but this is not sure.
## Post #5
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-02-01T20:17:37+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

The file you provided does in-fact contain 3d model information.
## Post #6
- Username: artbarot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 15, 2018 11:33 pm
- Post datetime: 2018-02-01T23:22:51+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

Thanks for the script it seems to be working perfectly. How did you manage to open the model, is it in some standard extension? Which .dat file you saw? I will keep researching meanwhile.

Btw the model you opened is Q002 (there is a Q000 in the .bin files hence +1) [http://choroq.wikia.com/wiki/List_of_Bo ... oro-Q_HG_2](http://choroq.wikia.com/wiki/List_of_Body_Information_in_Choro-Q_HG_2) . So theoretically this makes sense.

Thanks all for helping
## Post #7
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-02-02T01:18:32+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

I wrote a maxscript to open the file. It works on all but the last file which I'm also pretty sure is a texture file. You can have a look at it if you want to.
[Road Trip Adventure.zip](https://xentaxbackup.github.io/file/13865_Road Trip Adventure.zip)
## Post #8
- Username: artbarot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 15, 2018 11:33 pm
- Post datetime: 2018-02-05T19:37:48+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

Hey, first of all thanks aceWell and killercracker for your help. I don't quite understand how the script splits the data into 7 .dat since in this example there is only 6 offset? This is slowing me down to understand another .bin with slightly different headers.

Regarding the maxscript it works prefectly with car models (I'm still figuring out how to extract the texture). However when I try to open other type of files it gives very weird models:



w.png (185.86 KiB) Viewed 207 times



Is it fair to say I need to make adjustments to the maxscript in order to extract the model information? 
Thanks
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-05T21:16:28+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

> Reply from artbarot
>
> I don't quite understand how the script splits the data into 7 .dat since in this example there is only 6 offset? This is slowing me down to understand another .bin with slightly different headers.
the sample you posted had 7 offsets, that is why there is 7 dat files extracted.   
anyway if you have trouble with other files you must post more samples.
## Post #10
- Username: artbarot
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon Jan 15, 2018 11:33 pm
- Post datetime: 2018-02-06T00:37:14+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

I see, I assumed the last 4 byte before the 0 padding was the file size. I put in anex more 4 files, I just want you to check the header, checking if your bms script makes sense , and the problem lies in getting models / textures. I also put a file .GSL which I think is proprietary and is a achieve of several textures, so if it gives you trouble ignore it. The other 3 files are similar to the one in the main question. Have in mind I tested this and gives some results.

[https://we.tl/HzpALHrVTm](https://we.tl/HzpALHrVTm)

I would say that assuming each file "type" has the same structure(I think they do), if these ones are understood I have pretty much analized all types of files.

I'm leaving aside some other problematic files that have to be analyzed by IDA in order to decompiling the game "by hand", taking the MIPS or x86 assembly code and write C code that does the same thing.

Thanks
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-02-06T02:34:20+00:00
- Post Title: Need Help analyzing [PS2 - Road Trip Adventure] files

> Reply from artbarot
>
> I assumed the last 4 byte before the 0 padding was the file size.
it is, the offsets start at the beginning of the file, 
you can look at the bms script to see how it is reading the data.  

T00.BIN and STAMP.GSL look like archives with a series of paletted image data, no offset table.
001.BIN and C00.BIN extract okay with the bms script.

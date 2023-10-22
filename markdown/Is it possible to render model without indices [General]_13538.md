## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2015-11-14T12:47:08+00:00
- Post Title: Is it possible to render model without indices? [General]

I'm reversing the .pig format and specifically the Minion rush models. I've played around with all version of the game Windows 8/Iphone/Android.

Its not so difficult to reverse the format, even after the compressed streams they added but i'm stuck on something.

For some FUCKING reason, whereas the model information is EXACTLY THE SAME between the same model over all platforms, the windows version contains indices data, BUT iphone and adroid contain NOTHING at all... Its just missing... If i exclude some padding the files are pretty much IDENTICAL EXCEPT that missing indices section.


I remembered some years ago, when i was playing around with some models from the PS3, and i was stuck on EXACTLY THE SAME problem.

So i'm starting to believe that i am clearly missing something here that has to do with the platforms and their gpus or with the specific version of opengl-es.
Is this possible or not? Otherwise is it possible to extract the indices from other model information like UV's or something?


Any help is highly appreciated.

PS: I've tried to try and define triangles immediately from the vertex buffer. I've seen models like that. These particular ones are DEFINITELY NOT LIKE THOSE, because if they were there would clearly be some duplicate vertices in the vertex buffer, but there is not even a single one of them

PS2: I'll try to post some file data streams later on
## Post #2
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-11-15T03:55:59+00:00
- Post Title: Is it possible to render model without indices? [General]

maybe indices are compressed, I usually work in ps3 models from Sony games and is common in these games the absence of indices. thats why I work with dumped data from RAM, because the system can decompress or generate indices.

try to dump data of  the game from ram and check if the indices of the models are in the generated file. If the indices are in the dump is because are compressed, if not it is because they are generated with some algorithm.

if you find indices in ram dump you can fit these indices in your obtained vertices( should fit perfect. )
## Post #3
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2015-11-15T16:38:50+00:00
- Post Title: Is it possible to render model without indices? [General]

> Reply from luxox18
>
> maybe indices are compressed, I usually work in ps3 models from Sony games and is common in these games the absence of indices. thats why I work with dumped data from RAM, because the system can decompress or generate indices.

try to dump data of  the game from ram and check if the indices of the models are in the generated file. If the indices are in the dump is because are compressed, if not it is because they are generated with some algorithm.

if you find indices in ram dump you can fit these indices in your obtained vertices( should fit perfect. )

Thanks a lot for your reply first of all.

Questions:

Even if i find out how to dump memory from the Iphone or an Android Phone, how can you locate the indices from a vast memory dump and i guess that should be even harder if the stream is compressed as well.

Also, could this happen to pc version as well? That's what i want to clear out basically. Is this something that is used commonly in consoles and stuff and it is chosen from the devs NOT to happen in the pc ports of the game?

And lastly, after you locate the indices, that's your solution to the "problem"? Using indices dumped from memory, or you eventually find the compressed streams in the game files?
## Post #4
- Username: luxox18
- Rank: mega-veteran
- Number of posts: 176
- Joined date: Sat Jul 30, 2011 4:18 am
- Post datetime: 2015-11-15T20:42:32+00:00
- Post Title: Is it possible to render model without indices? [General]

I always search indices using 00 00 00 01 00 02 with a hex editor or I try locate the data with the eyes because the structure is unique and easy to recognize.

In pc is difficult that this occur because there are more memory available for work. this happened in old games when RAM was very low.

I'm not expert in the reverse of compression data, that's why I use the indices from ram. maybe someone can find the compression method.

try to upload some example files.
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2015-11-17T09:13:07+00:00
- Post Title: Is it possible to render model without indices? [General]

You're probably dealing with unindexed triangle strips, there was good motivation to do this on older PVR/iOS devices.

It's unlikely you're dealing with index compression on mobile, and very unlikely you're dealing with any kind of runtime index compression.

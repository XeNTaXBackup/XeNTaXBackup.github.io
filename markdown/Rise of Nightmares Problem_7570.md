## Post #1
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-26T04:56:23+00:00
- Post Title: Rise of Nightmares Problem

Hey guys,

I'm having some trouble with this model format. Below is four sample files. Header is very consistent. Vertex and index buffer data is also very consistent. Starting at 0x50 and ending at 0xBF are <offset, information> pairs. 0x80 is vertex information pair, where you follow offset to read data about vertex information. 0x88 is vertex data pair, where you follow offset and you read the vertex buffer data. 0xA8 is the index buffer pair, where you follow offset and you read the index buffer data.

When sent to output file, vertices are fine and you can clearly see the model. However, the faces are not correct. I've tried everything: triangle lists, triangle strips, triangle strips with strip-cut indices, triangle fans, triangle fans with strip-cut indices, yet nothing looks 100% right. Using triangle strips it looks 75-80% right most of the time. Try sample 3 first. You'll see using triangle strips it looks good but two triangles are not correctly connected.



Then try sample 1. Character model doesn't look so good. Mostly right, but a lot is wrong.



Samples:
[http://www.filesonic.com/file/2737062784](http://www.filesonic.com/file/2737062784)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-26T10:35:12+00:00
- Post Title: Rise of Nightmares Problem

what did you use to extract the game files.
also 99% of people wont download from pay sites.

Also did you reset the strip when you read 0xFFFF
it should be triangle strip then when you read 0xFFFF you re read triangle index 1 and 2 again then continure the strip as ususal.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-26T10:59:01+00:00
- Post Title: Rise of Nightmares Problem

The files are cpk; the same as neptunia mk2, so hcs's cpkextract tools work great.
Yes, i reset them. I basically copied and pasted my code from Rage, which also uses 0xFFFF delimited strip-cut indices.
Maybe triangle strip with adjacency?
## Post #4
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-27T05:35:48+00:00
- Post Title: Rise of Nightmares Problem

Nope, not with adjacency either. XBox360 doesn't have direct support for geometry shaders and many tristrips have an odd number of indices.

Source code for those who want to try to help out.

Important function is 

```
{
 ...
}

```


at line 276. Just import MS vcproj file into a new solution and you will be ready to go. If you have the game and can extract the files, the code
to extract textures and all model files is included as well.
[rise_of_nightmares.7z](https://xentaxbackup.github.io/file/4812_rise_of_nightmares.7z)
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-28T02:11:19+00:00
- Post Title: Rise of Nightmares Problem

Did you read table 3 in this format it gives you the mesh pieces sizes to load if you are not that explains the problem with the faces.
example


```
00000000 00000000 00000000 00000043 00000150 00000000 000000C2 00000150 000000B1 00000212 00000000 00000000 00000001 00000000 00000000 00000000

```
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-28T07:44:32+00:00
- Post Title: Rise of Nightmares Problem

cool, thanks. yeah, i ignored some of the offset pairs. sucks i don't have a lot of time to finish this one. if u want to finish it... be my guest .

edit: omg, no wonder i didn't see that data... i just realized right now that all offsets are relative to GSGM rather than the beginning of the file. I was adding 0x20 to some things but not to others lol.
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-10-28T21:10:05+00:00
- Post Title: Rise of Nightmares Problem

yeah that solves the problem also note that the face sections i labeled are the lod's you only need to import the first one to get the best version of the model.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-28T23:31:15+00:00
- Post Title: Rise of Nightmares Problem

Nice! I knew this one seemed easy to crack. Very nice format structure with some nice models too.  Too bad the game itself kind of sucked.
## Post #9
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2011-10-30T13:19:17+00:00
- Post Title: Rise of Nightmares Problem

Finally had some time to play with this too he he he...

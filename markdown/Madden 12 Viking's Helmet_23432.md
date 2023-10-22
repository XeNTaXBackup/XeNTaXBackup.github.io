## Post #1
- Username: deerlybeloved
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 20, 2021 1:08 am
- Post datetime: 2021-02-10T19:54:03+00:00
- Post Title: Madden 12 Viking's Helmet

With the use of shakotay's hex2obj tool, I've been extracting the models of the mascots found in Madden 12. I've had success with each character up until the last one, that being Viktor the Viking. I've been able to get every submesh except for his helmet. I checked to make sure I had entered the right addresses, but whenever I tried to view the mesh, it would appear as a scrambled mess. Any help would be appreciated. I've attached a file of the helmet, for anyone willing to help. The addresses are 11 for the face indices, and 1B9E for the vertices.
[Helmet.zip](https://xentaxbackup.github.io/file/19514_Helmet.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-10T21:11:08+00:00
- Post Title: Madden 12 Viking's Helmet

Not too hard if you know (you do, don't you?  ) that big endian is used:
.



helmet-rsf.png (79.5 KiB) Viewed 56 times


(uvs were a little bit trickier)
## Post #3
- Username: deerlybeloved
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 20, 2021 1:08 am
- Post datetime: 2021-02-11T23:30:45+00:00
- Post Title: Madden 12 Viking's Helmet

I'm afraid I don't quite understand. I've set hex2obj to use bigE, but this is the resulting mesh I get. Is there something I'm missing?



brokenhelmet.png (34.99 KiB) Viewed 43 times
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-02-12T10:16:09+00:00
- Post Title: Madden 12 Viking's Helmet

> Reply from deerlybeloved ↑Fri Feb 12, 2021 7:30 am at Fri Feb 12, 2021 7:30 am
>
> 
I'm afraid I don't quite understand. I've set hex2obj to use bigE, but this is the resulting mesh I get. Is there something I'm missing?
brokenhelmet.pngwell, watch the format! Why did you set it to short all (means using short for vertices and uvs)?
In fact it is "HF_UV", means using half float for uvs and float for vertices.

Maybe update your browser's cache (I have the strange feeling that the first picture I uploaded had "WordUV"  ).
## Post #5
- Username: deerlybeloved
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Wed Jan 20, 2021 1:08 am
- Post datetime: 2021-02-12T17:47:29+00:00
- Post Title: Madden 12 Viking's Helmet

Ah, my bad! I've been using ShortAll out of habit, since I was used to all the other meshes using it... 
With that, I've finally gotten all the mascot models I've been looking for. I would've been completely lost without your help, so I want to say thank you very much! I mean it!

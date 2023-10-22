## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-19T23:40:16+00:00
- Post Title: Parasite Eve

[](https://ibb.co/61Zgq39)

I was able to figure out the algorithm finally to this game. Still seem to have a few things wrong but I'm hoping to have some help now. 
Looking at the Eve Stage 2 Long Arms file I made I found we have the correct vertex by starting at the beginning set of zeros. 
[](https://ibb.co/5rbXc8Z)
This is what we see in the viewer.
[](https://ibb.co/jJdKCPv)
For the faces we go just below the 80 80 80 80 's and it starts after 80 80 80 OA. But this first OA is part of the actual mesh. 
[](https://ibb.co/J5Thm03)
And we get this in the viewer. 
[](https://ibb.co/MsnF6K6)
It seems like most of her mesh is there but I still see some things missing. I know i should go through each offset and find where it starts and ends. Like her head, arms, dress, ect. That would make it easier. But I still cant figure out the UV's. 
Here is were they start.
[](https://ibb.co/5KKyb3Z)
I was able to use a program a buddy made for me and it does work for reading them. Something about the color palette. The 80 70 is one and the 88 00 is another. That is the triangle UV's.
[](https://ibb.co/m414Jh5)
This is the quad UV's offset start. You can tell the from the C0 70 and then 88 00. Not sure how these are read. 
[](https://ibb.co/2Wt9jkL)
From the program
[](https://ibb.co/VjjCPhF)
With the texture applied in into the program you can see they all line up perfectly with the image. 
[](https://ibb.co/Nr7Q09z)
But for some reason I cant get this UV map to show in Model Researcher. Any help on this would be appreciated. I've been working on this project for 2 years now. Each day seems to get me closer but I could really use some help at this point.
## Post #2
- Username: nightwolf1982
- Rank: veteran
- Number of posts: 158
- Joined date: Fri May 05, 2017 2:19 pm
- Post datetime: 2019-10-20T02:45:07+00:00
- Post Title: Parasite Eve

Do you have a sample file you can post/link to?
## Post #3
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-20T04:17:44+00:00
- Post Title: Parasite Eve

Yes here is a link to all my research. 
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1bRnp8q7B9JhFSRlUa7vklHD_MmhCMmNz?usp=sharing)
## Post #4
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-10-25T10:47:53+00:00
- Post Title: Parasite Eve

Most likely, the problem is in negative coordinates. If the coordinate is less than 0, then the program converts by subtracting the coordinate from 1.
--
if u < 0: u = 1 - abs(u)
Perhaps this is the wrong approach.
## Post #5
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-27T15:48:26+00:00
- Post Title: Parasite Eve

Not to sure what that means, thanks for the reply. My other buddy said something about quads and triangles. This file somehow uses both. Have you ever seen this kind of architecture ? I know you have studied hundreds of files I'm sure. As have I. But I cant seem to break this one. How would one go about in reversing that ? I know the offsets of all the data. Its just the order, or the padding I'm hoping. But every time I try to do a certain order. Model Researcher don't support it. So I could really use some help. Been on this project for 2 years now. And what do you mean by abs(u) ?
## Post #6
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-10-28T17:20:45+00:00
- Post Title: Parasite Eve

Sharppy
This will seem strange, but I have not studied hundreds of files. I am not very good at researching and unpacking resources. Most 3D formats are very simple, so the data from them can be read using programs such as Hex2Obj.
As for texture coordinates, I don’t know how this program reads data. MR does not support quadrangles. This is apparently another reason for the incorrect display. I will try to add support in the near future.
The abs() function returns the absolute value of a number. abs(-1) = 1
You can try writing a script for Noesis.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2019-10-28T19:01:43+00:00
- Post Title: Parasite Eve

> Reply from Sharppy ↑Sun Oct 27, 2019 11:48 pm at Sun Oct 27, 2019 11:48 pm
>
> I know the offsets of all the data. Its just the order, or the padding I'm hoping. But every time I try to do a certain order. Model Researcher don't support it.You need to tell how your buddy's prog reads the uv data.

This for example (for tris) doesn't seem to work:
.



parasite uvs.png (5.72 KiB) Viewed 131 times
## Post #8
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-28T22:22:36+00:00
- Post Title: Parasite Eve

Thanks for the reply. Unfortunately i cant. He went ghost on me about 10 months ago. His sites are down and he is just gone.. I don't know. And I know he said something about color palettes. Like every other set of bytes was a pointer. I know he cant be the only one to see the algorithm. In the attached file in the "Research" section are the pictures of what he sent explaining it. But he was wrong on a few things. I told him he was wrong and he got all shitty with me kinda. But he was. Vertex start at the 00 00 00 00 sets. Not the CD FF 3D 3F sets. I didn't just figure that out until about a month ago. But i just knew there was something wrong. Because it wasn't right lol
## Post #9
- Username: Omission7x
- Rank: n00b
- Number of posts: 15
- Joined date: Sat Nov 15, 2014 4:15 pm
- Post datetime: 2019-10-29T02:15:25+00:00
- Post Title: Parasite Eve

very interesting! does this mean we'll be able to mod the characters? or be able to boost the game's internal resolution?
## Post #10
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-10-29T07:57:49+00:00
- Post Title: Parasite Eve

Sharppy
Can you send an example file from the screenshot and the program?
## Post #11
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-29T09:36:46+00:00
- Post Title: Parasite Eve

Here is the program Lazov
[https://drive.google.com/file/d/1ZkvJZX ... sp=sharing](https://drive.google.com/file/d/1ZkvJZXhES1ZTilAlkcLa6yjrGVtG1KxQ/view?usp=sharing)
You need to load a .PEM from the PEM folder in my research. Here is an example file.
[https://drive.google.com/file/d/1RIrgrd ... sp=sharing](https://drive.google.com/file/d/1RIrgrd2eBmiucfReITUnlM8L9aBummXg/view?usp=sharing)
And here is her texture
[https://drive.google.com/file/d/1KQjkVQ ... sp=sharing](https://drive.google.com/file/d/1KQjkVQfvWOBncosfLSxMbscijpzeDp76/view?usp=sharing)
Screenshot of this file
[](https://ibb.co/gMDdfLS)

My count and offsets arent right in this picture. This was just my research snap. They are close to them ranges though.
## Post #12
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-29T09:50:57+00:00
- Post Title: Parasite Eve

Omission I don't think we can increase the res or anything. Unless you modded the textures but then the repack would be crazy hard since it was all binary information. I'm doing this for model researching. I have already started my HD remake of this game about a year ago. I just would like to have the models as a reference to the high-poly ones im creating along with uv's. Im not good at laying out my UV's and since these already have them I would like to know how they are laid out. Its hard to tell by the programs I have I need the whole model textured to really see what goes where.
## Post #13
- Username: Lazov
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Oct 08, 2016 6:56 pm
- Post datetime: 2019-10-29T10:07:36+00:00
- Post Title: Parasite Eve

I have a different result:
[](https://imgbb.com/)
## Post #14
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2019-10-29T10:31:18+00:00
- Post Title: Parasite Eve

Um.. that might be a different file I used at that time. Sorry about that. Try this one. 
[https://drive.google.com/file/d/1TTVr0F ... sp=sharing](https://drive.google.com/file/d/1TTVr0FWbTwHM53ioTRfqMb-P7hrxR9mT/view?usp=sharing)
[](https://ibb.co/0YXnchF)

And it looks like you were close to the data just had to go up or down a few. It looks all like that until its on the first offset then it all comes into view so i might of been wrong on them. I have changed the files since then cutting out unnecessary data. They are close to them ranges though. Thanks for looking into this.
## Post #15
- Username: adolthered
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 27, 2020 6:14 pm
- Post datetime: 2020-06-27T10:16:17+00:00
- Post Title: Parasite Eve

Hi were you ever able to put these up somewhere? Also were the PE2 models extracted?

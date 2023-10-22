## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-01-18T14:49:12+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

I'm trying to get the models using hex2obj, but it comes out as a garbled mess. What am I doing wrong?



Here is the model file:
[http://puu.sh/eGJuR.amw](http://puu.sh/eGJuR.amw)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-18T16:07:15+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

> Reply from lemurboy12
>
> I'm trying to get the models using hex2obj, but it comes out as a garbled mess. What am I doing wrong?lack of experience, I guess.

It's required to give the file some structure.
Search for 0000 0100 0200  for example (view attached pic).

You're on a good way   but: your face indices count is too big.
(seems there are 7 submeshes)

Are there further patterns which give the file a structue?
-> here 16x 00  (findings past 0x7B1A might be 4x 0.0f)

3rd occurence at: 0x7B1A
Scroll up to some possible start of vertices, here 0x2C2C

0x7B1A- 0x2C2C = 0x4EEE (= 20206 = 631*32 dec.)

Vertex block size is 32. The block should contain about 631 vertices (for the whole model?)


calculate vertex start of next submesh: 0x2C2C + 162x32 (dec.) = 0x406C

(I didn't combine the submeshes, good luck.)

Creating a max script for example would be best choice for this format.
Remember: hex2obj is primary intended for a quick first approach.

btw: the version you're using is pretty outdated



format_amw.JPG (96.3 KiB) Viewed 295 times
## Post #3
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-01-18T17:47:06+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

I'm still missing something.
## Post #4
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-01-19T15:52:56+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

Still not sure what I'm doing wrong. I'm following all your instructions, and I'm still getting a garbled mess, though not as garbled.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-20T10:39:04+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

> Reply from lemurboy12
>
> Still not sure what I'm doing wrong. I'm following all your instructions,seems, you did not.

Use the formula I gave to calculate the vertex block address of the next submesh (go3 startaddr).

Also use the startadresses of the face indices blocks in the attached pic of my previous post.
The one for the 3rd submesh is 0xC152.
Number of face indices to be calculated by:

(0xC1B8 - 0xC152)  / 2 = 51 dec.
division by 2 because the face indices are WORDs (uint16)

Not sure why you used 51 as a vertex count.

(You really should try to get a basic understanding of what has to be done.  )



fred_SM_3.JPG (10.02 KiB) Viewed 262 times
## Post #6
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-01-20T19:47:05+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

but how do I get the start address of the vertices? I've been doing 17*32 + 2C2C.
## Post #7
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-01-21T09:47:38+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

Just look for floats
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-01-21T14:35:21+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

this is the formula for start of vertices:

vert_addr_next = vert_addr_prev + VBsize * vertCount_prev

(check if it fits for all .amw of this game)

vertex start address: 0x2C2C (to be found with some experience/trial 'n error)
next addr: 0x406C as shown some post before
further addresses:

```
   0x64CC     =      0x62AC    + 32 x 17  
   0x65CC     =      0x64CC    + 32 x 8
   0x6C0C     =      0x65CC    + 32 x 50
   0x726C     =      0x6C0C    + 32 x 51
```

end vertices: x796C
vertex count 618 = 162 + 274 + 17 + 8 + 50 + 51 + 56 

resulting mesh:



fred.JPG (17.17 KiB) Viewed 231 times
## Post #9
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2015-01-21T23:54:46+00:00
- Post Title: Flintstones Bedrock Bowling .AMW

Well, I meant more of how to get the start of the vertices in the first place, but at least I have the model and gained some experience with hex2obj. Thank you, though it would help if you were a little more clear on finding the start of the vertices to base all submeshes off of.

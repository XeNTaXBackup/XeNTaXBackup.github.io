## Post #1
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2011-07-19T22:32:15+00:00
- Post Title: [Need Help] Trying to figure out the structure.

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-19T23:09:53+00:00
- Post Title: [Need Help] Trying to figure out the structure.

post what you have so far so people can help.
## Post #3
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2011-07-19T23:18:33+00:00
- Post Title: [Need Help] Trying to figure out the structure.

The contents of this post was deleted because of possible forum rules violation.
## Post #4
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2011-07-21T19:27:36+00:00
- Post Title: [Need Help] Trying to figure out the structure.

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-21T22:26:53+00:00
- Post Title: [Need Help] Trying to figure out the structure.

Don't see the pattern you are trying to point out.

With the sample you posted, at offset 0x26CA you see a bunch of shorts. Probably the face indices, but maybe not. Keep going down and you'll find that it increments, but then you should see a point where it goes to B0, 00, 01, ..

This happens 3 times in total, so you have 4 different sections full of shorts.
I don't know if this is significant or not, but you should note that the largest number is B0, and the smallest is 00, so if these were face indices then there should be B1 vertices, so you go to the top and you see a B1 00 00 00. Maybe that is the number of vertices

They are followed by four A6 02 00 00. Don't know what those are.

Then there's a section of random stuff, so I'm guessing they're floats and it's the vertices section. No clue what it might be so just highlight everything all the way down to the faces section. You should highlight 9912 bytes. Divide that by 0xB1 (177) and you get 56 bytes per vertex. Maybe that is the correct number, who knows, but 56 bytes sounds pretty cool (so does 32)

We then examine the faces some more. If you highlight each section from 00 to B0, you will find that it is length 1356, which is exactly 678 * 2, or (678 / 3) * 6, assuming each face has 3 vertices. Note that 678 == 0x02A6, and there are 4 sections, which match what you had up there.

And ya...I didn't spend anymore time thinking about what they could be so I just quickly wrote a plugin to test my guesses and got this:



Sort of looks like a snowman's head?

```
dword numVerts
dword_4 numFaces (don't know why 4 sections)

numVerts vertex {
   float_3 vx, vy, vz
   float_11 other_stuff
}

#repeat following section as many times as necessary. I think 4?
numFaces face { 
   word_3 indices
}

```


What game is it? I called my parser "unknown_z3m" and I don't want to keep it nameless.
## Post #6
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2011-07-22T08:14:36+00:00
- Post Title: [Need Help] Trying to figure out the structure.

The contents of this post was deleted because of possible forum rules violation.
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T12:56:37+00:00
- Post Title: [Need Help] Trying to figure out the structure.

I don't use 3dmax.
I usually just post up what I found and others can just write things for their own programs of choice.
## Post #8
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2011-07-22T13:45:18+00:00
- Post Title: [Need Help] Trying to figure out the structure.

Ah okay. That helped me already much. Thanks for that.
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-07-22T14:34:07+00:00
- Post Title: [Need Help] Trying to figure out the structure.

Is it possibly "Risk your life"?
## Post #10
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2011-07-22T16:08:02+00:00
- Post Title: [Need Help] Trying to figure out the structure.

The contents of this post was deleted because of possible forum rules violation.
## Post #11
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2015-01-15T11:38:09+00:00
- Post Title: [Need Help] Trying to figure out the structure.

Hello, srry for bump this old topic, but wich program did you use for open that snow helmet? Noesis?can you release the plugin? I need help with thi kind of 3d format .Z3m, i would like to convert it to .obj, and after edit it, convert back to .z3m. Is this possible?
[Examples of Z3m.rar](https://xentaxbackup.github.io/file/8481_Examples of Z3m.rar)
## Post #12
- Username: RonaldinhoR9
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Aug 23, 2014 3:56 pm
- Post datetime: 2016-02-21T05:21:44+00:00
- Post Title: [Need Help] Trying to figure out the structure.

Bumping this topic. Finale00, can help here?
## Post #13
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2016-02-21T12:07:19+00:00
- Post Title: [Need Help] Trying to figure out the structure.

Here I inserted some information how to edit the original .z3m file:

- Open the .z3m file with 3D Object Converter

- Export it to 3D Studio .3ds format
  (If you export it to .obj format the 3D Studio MAX will optimize the loaded model, in this case it is bad.)

- Import the .3ds to 3D Studio Max
    - turn on the Completely replace current scene
    - turn off the convert units
      (If you don't turn it off the 3DS Max scales down the models 40-fold!)

- Modify the 3d geometry (you can move the 3d points, but don't delete 3d points)

- Export it to .3ds format

- Import the .3ds to 3D Object Converter

- Export it to .z3m file (with selecting the original .z3m file). (This export module needs to be registered!)

The exported .z3m file will contain the original missing datas (Bone; Vertex Bone Weight datas ?) with the new 3d geometry.
[z3m_to_3ds.zip](https://xentaxbackup.github.io/file/10514_z3m_to_3ds.zip)
## Post #14
- Username: muqri
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 12, 2019 6:27 pm
- Post datetime: 2019-05-12T10:29:35+00:00
- Post Title: [Need Help] Trying to figure out the structure.

so how to combine after i create new 3d because i use 3dmax and want go back to z3m is say need bone original so this problem how to do

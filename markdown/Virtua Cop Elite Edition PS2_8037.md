## Post #1
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-01-12T22:19:12+00:00
- Post Title: Virtua Cop Elite Edition PS2

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-12T22:46:30+00:00
- Post Title: Virtua Cop Elite Edition PS2

Since I don't see any index buffers and it's a PS2 games, I'm going to assume it also uses one of those implicit face definition by just stringing together a bunch of vertices.

But I haven't written any code to do something like that so I can't verify it.
Do all of the files follow this format?

```
int32 0
int32 0
int32 5

char[12] "frame"
dword

char[12] "Micro"
dword

char[12] "Shape"
dword

char[12] "Hrchy"
dword

byte[404] just skipping

vertexSection maybe

```
## Post #3
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-01-12T23:18:21+00:00
- Post Title: Virtua Cop Elite Edition PS2

Yes, I believe all the models follow that format.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T00:03:39+00:00
- Post Title: Virtua Cop Elite Edition PS2

These look like related files so all of the counts are the same.
Try finding one that's distinctly different (maybe the name isn't anything close to SCN1)
## Post #5
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-01-13T00:20:38+00:00
- Post Title: Virtua Cop Elite Edition PS2

The contents of this post was deleted because of possible forum rules violation.
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-13T00:30:43+00:00
- Post Title: Virtua Cop Elite Edition PS2

Each file has a whole bunch of vertex groups(don't know how to determine beforehand. SCN1 has about 5000+ while SCN1B has about 10000+), and I don't know how the faces are drawn.

Any idea what this might be?



It's not all vertices...there are some weird parts too in between sometimes.

```
            unk1, unk2, unk3, numVerts = self.inFile.read('4L')
            if numVerts == 0 or unk2 // numVerts != 16:
                self.inFile.seek(32, 1)
            else:
                self.parse_vertices(numVerts)

```
## Post #7
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-01-13T13:27:15+00:00
- Post Title: Virtua Cop Elite Edition PS2

I believe it is part of one of the levels.
## Post #8
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-01-15T20:49:25+00:00
- Post Title: Virtua Cop Elite Edition PS2

How can I go about using this to import the vertices?

```
            unk1, unk2, unk3, numVerts = self.inFile.read('4L')
            if numVerts == 0 or unk2 // numVerts != 16:
                self.inFile.seek(32, 1)
            else:
                self.parse_vertices(numVerts)
```
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-01-15T21:04:06+00:00
- Post Title: Virtua Cop Elite Edition PS2

[download/file.php?id=4983](http://forum.xentax.com/download/file.php?id=4983)

Put it in noesis/plugins/python
## Post #10
- Username: themonkeyman
- Rank: n00b
- Number of posts: 19
- Joined date: Fri Nov 27, 2009 8:49 am
- Post datetime: 2012-01-16T15:22:09+00:00
- Post Title: Virtua Cop Elite Edition PS2

The contents of this post was deleted because of possible forum rules violation.

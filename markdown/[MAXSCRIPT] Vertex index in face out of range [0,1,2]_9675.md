## Post #1
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-25T18:17:46+00:00
- Post Title: [MAXSCRIPT] "Vertex index in face out of range: [0,1,2]"

Im trying to append some shorts into a vertex array i may show you my code:

```

f1=readshort f
f2=readshort f
f3=readshort f
append Faces_array[f1,f2,f3]
)

```


Am i doing something wrong? If you need more information to help me, just write it in here  sorry to bother you
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-25T18:18:33+00:00
- Post Title: [MAXSCRIPT] "Vertex index in face out of range: [0,1,2]"

Just add +1 to all of them.
## Post #3
- Username: Valerian
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Jul 20, 2011 6:25 am
- Post datetime: 2012-09-25T18:20:23+00:00
- Post Title: [MAXSCRIPT] "Vertex index in face out of range: [0,1,2]"

LOL.
It works!  
but is there any explanation to this?
## Post #4
- Username: Valerian
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-09-25T19:48:51+00:00
- Post Title: [MAXSCRIPT] "Vertex index in face out of range: [0,1,2]"

max is a 1 based system most game engines are 0 based.

## Post #1
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-01-30T18:12:51+00:00
- Post Title: Ghost Online? :D

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-01-31T01:14:03+00:00
- Post Title: Ghost Online? :D

"?" You mean by you are not sure what it refers to? Usually when LJUMP 1 and 2 it must either be referring to the jump parts (rise and fall) or alternate jump animations. Like Damage 2 is alternate (most likely) to Damage. And attack 2 would be like swinging left and attack would be swinging right. Alternates that way.

And the mot files may just designate the frames according to their position in the sheet (if it uses sheets) or the number of frames per animation (seperate images per frame).

ENV may be the script files for entities. 

SPR is obviously universal for sprite and I believe you are right about mot. BUT I am not sure about the others. What of music and sound or is that just standard format WAV/MP3/OGG?
## Post #3
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-01-31T18:13:39+00:00
- Post Title: Ghost Online? :D

Theres a "Sound" folder with just MP3's and WAV's, those are not encrypted or anything. But for the rest, I have no clue!:O
## Post #4
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-03T09:31:26+00:00
- Post Title: Ghost Online? :D

Okay. I made some progress.

CSP seems to be some Pack file.
The first byte, contains the amount of files in the section.
So if the first byte is Hex 10, there's 16 files.And I think the files in are zlib compressed, because I see a x 25 bytes after the end of the file name, like this:

\.D.a.t.a.\.O.B.J.\.I.t.e.m.\.r._.0.0.6...s.p.r.....B...................x

\.D.a.t.a.\.O.B.J.\.I.t.e.m.\.r._.0.0.7...s.p.r.....B...................x

\.D.a.t.a.\.O.B.J.\.I.t.e.m.\.r._.0.0.8...s.p.r.....B...................x

I think the x is where the zlib compressed data starts. 

Every file also has duplicate filenames, that seems to be include file information.

After file 12, the pattern gets changed. (I'm talking about ring.csp currently). File 12 seems to be linked till the end of the file(File 16), because every file starts like this:

r._.0.1.3...s.p.r...I.t.e.m.\.r._.0.1.2...s.p.r.....B...................x

r._.0.1.4...s.p.r...I.t.e.m.\.r._.0.1.2...s.p.r.....B...................x

r._.0.1.5...s.p.r...I.t.e.m.\.r._.0.1.2...s.p.r.....B...................x

And so on. 

This is correct at other files too, Dress.csp contains hex value 7E, and indeed consists of 126 files.

d._.0.0.1...s.p.r..._..|............................B...................x

Maybe the first byte of these file names stand for (D = Dress), (R = Ring), 

n._.0.0.1...s.p.r...............B...............x

Here N would mean necklace, which is correct, because it seems to be in the necklace file. 

This is the same for .cmo files, but the .cmo files only consist of 1 file(Always hex value 01)


Edit: Then again, that pattern shows randomly in other files too. Gah, it's confusing me

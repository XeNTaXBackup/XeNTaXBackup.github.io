## Post #1
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-16T13:47:02+00:00
- Post Title: New Member in need of help (Opening ARC File)

Ok, I am new and will probably ask a lot of questions. Anyway, I am in dire need of something to open a Sonic the Hedgehog 2006 Xbox 360 ARC file. I have no experience in programming (But if anyone can teach me, I'd be greatful.) Any advice?
## Post #2
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-18T02:21:24+00:00
- Post Title: New Member in need of help (Opening ARC File)

Actually, All i need is some practice. I want to start with an arc file. Any suggestions on how to begin?
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-18T02:23:45+00:00
- Post Title: New Member in need of help (Opening ARC File)

just upload an arc to look at most likely it is using xmem compression so you can use xbedecompress from the xbox sdk to extract it.
if you upload a sample i can tell you.
## Post #4
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-18T02:32:47+00:00
- Post Title: New Member in need of help (Opening ARC File)

The contents of this post was deleted because of possible forum rules violation.
## Post #5
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-19T09:08:04+00:00
- Post Title: New Member in need of help (Opening ARC File)

Well...

If someone can give me a full explanation of how quickbms.exe & xbdecompress.exe works, I'd be really greatful. Then I could do this stuff all by myself. I am sorry & request so many things. I am new to this whole conversion/hacking thing.
## Post #6
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-06-19T10:55:20+00:00
- Post Title: New Member in need of help (Opening ARC File)

this sonic game uses zlib i can't make an extraactor for all files without a lot of samples but this will work for the file you gave me.

```

goto 0x70
savepos tblstart
math namestart + 0x120
for i = 0 < 9
goto tblstart
get unk01 short
get nameoff1 short
get offset long
get zsise long
get size long
savepos tblstart
set nameoff namestart
math nameoff + nameoff1
goto nameoff
get name string
comtype unzip_dynamic
clog name offset size size
next i

```
## Post #7
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-19T11:13:00+00:00
- Post Title: New Member in need of help (Opening ARC File)

Absolutely. I need that extractor. I've been trying to get Mephiles' Model for a few days now.
## Post #8
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-20T17:56:40+00:00
- Post Title: New Member in need of help (Opening ARC File)

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-22T18:12:55+00:00
- Post Title: New Member in need of help (Opening ARC File)

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-24T23:05:57+00:00
- Post Title: New Member in need of help (Opening ARC File)

Never mind.

I found a tool called arctool.exe at X-Cult and extracted the files from the .arc files.

now i need something to turn xnm files into 3ds files.

or does 3ds max 2011 have a xnm support plugin?

To tell the truth, I have no clue which is the model file.
## Post #11
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-06-27T17:56:20+00:00
- Post Title: New Member in need of help (Opening ARC File)

Sorry to bump this topic, but i need something to convert .xno files (Which, if i'm not mistaken, are model files.
## Post #12
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2010-07-11T04:44:14+00:00
- Post Title: New Member in need of help (Opening ARC File)

I really want Mephiles' model. All I want is a way to convert .xno files.

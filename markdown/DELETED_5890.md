## Post #1
- Username: NecessAndAry
- Rank: n00b
- Number of posts: 10
- Joined date: Tue Dec 28, 2010 9:51 am
- Post datetime: 2011-01-23T11:37:29+00:00
- Post Title: DELETED

DELETED
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2011-01-24T21:17:21+00:00
- Post Title: DELETED

Maybe [http://www.cplusplus.com/doc/tutorial/files/](http://www.cplusplus.com/doc/tutorial/files/)
## Post #3
- Username: invisghost
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Jul 14, 2010 2:16 am
- Post datetime: 2011-01-26T19:31:07+00:00
- Post Title: DELETED

Failing to read at 1gb is an odd size to fail at. The 32bit limit is 4gb and it might also fail at 2gb for a few reasons. Have you checked if you're running out of memory? You can read bigger files if needed but you have to read them in chunks. You cant just do a single fread() call because you aren't able to hold the entire file in memory (32bit limitation).
## Post #4
- Username: VoLT
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Aug 13, 2010 8:39 pm
- Post datetime: 2011-01-30T01:49:11+00:00
- Post Title: DELETED

not sure ... maybe so 

```
__int64 pos;
int	sz;
BYTE	bIGbuff[BUFFER_SIZE]={0};
_lseeki64(m_fh, pos, SEEK_SET);
_read( m_fh, bIGbuff, sz )
```

more examples  [http://msdn.microsoft.com/en-us/library ... s.80).aspx](http://msdn.microsoft.com/en-us/library/40bbyw78%28v=vs.80%29.aspx)
PS Work in 32 and 64 bit 
PPS Support large 4Gb files

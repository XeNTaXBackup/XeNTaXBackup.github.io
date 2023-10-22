## Post #1
- Username: Jason
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 14, 2009 5:47 pm
- Post datetime: 2009-07-15T22:16:30+00:00
- Post Title: Timesplitters 2 PAK Formats Request

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-16T21:47:50+00:00
- Post Title: Timesplitters 2 PAK Formats Request

I've figured out the format. Just hold your breath till I update MexCom and post the solution.
## Post #3
- Username: Jason
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 14, 2009 5:47 pm
- Post datetime: 2009-07-16T23:11:43+00:00
- Post Title: Timesplitters 2 PAK Formats Request

Thank you very much, Mr. Mouse! I greatly appreciate your time in looking into this.
## Post #4
- Username: Jason
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-24T20:50:55+00:00
- Post Title: Timesplitters 2 PAK Formats Request

BMS 

> Get ID Long 0;
>
> Get tailoffset Long 0;
>
> Get filenum Long 0;
>
> If ID = 1262696528;
>
> Get stringtableoffset Long 0;
>
> Get stringtablesize Long 0;
>
> For t = 1 To filenum;
>
> GoTo tailoffset 0;
>
> Get stringoffset Long 0;
>
> Math stringoffset += stringtableoffset;
>
> Get filesize Long 0;
>
> Get fileoffset Long 0;
>
> SavePos tailoffset 0;
>
> GoTo stringoffset 0;
>
> Get filename String 0;
>
> Log filename fileoffset filesize 0 0;
>
> Next t;
>
> EndIf;
>
> If ID = 1262695504;
>
> Get reserved Long 0;
>
> Math filenum /= 60;
>
> GoTo tailoffset 0;
>
> For t = 1 To filenum;
>
> GetDString filename 48 0;
>
> Get fileoffset Long 0;
>
> Get filesize Long 0;
>
> Get dummy Long 0;
>
> Log filename fileoffset filesize 0 0;
>
> Next t;

The format, there are two formats, the P8CK format and the P4CK format:
The sound.pak anim format is P4CK for instance, while ch.pak is in P8CK format.
Here are the descriptions. 

> #P4CK:
>
> 
>
> // header
>
> 
>
> char(4)		ID string ("P4CK")
>
> UINT32		Offset of tail
>
> UINT32		Tailsize ( divide by 60 to get the Number of resources in the archive)
>
> UINT32		Reserved (0)
>
> 
>
> // TAIL (for all files in sequence)
>
> 
>
> char(48)	Filename 
>
> uint32		File offset
>
> uint32		File size
>
> uint32		Reserved(0)
>
> 
>
> #P8CK
>
> 
>
> // header
>
> 
>
> char(4)		ID string ("P8CK")
>
> UINT32		Offset of tail
>
> UINT32		Number of resources
>
> UINT32 		String Table offset (Filename strings)
>
> UINT32		String Table size
>
> 
>
> // String Table (for all files in sequence)
>
> 
>
> char(x)		Filename, null-terminated string
>
> 
>
> // TAIL (for all files in sequence)
>
> 
>
> uint32		Filename offset in String Table
>
> uint32		Filesize
>
> uint32		Fileoffset
## Post #5
- Username: Jason
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Jul 14, 2009 5:47 pm
- Post datetime: 2009-07-24T22:32:30+00:00
- Post Title: Timesplitters 2 PAK Formats Request

Yes!! I'll be registering your product as soon as can, but for now this documentation is great for my education. THANK YOU.
## Post #6
- Username: TheMelonFiler
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Dec 07, 2015 4:21 am
- Post datetime: 2015-12-07T03:56:13+00:00
- Post Title: Timesplitters 2 PAK Formats Request

How did you manage to get a hold of the PAK in the first place? I can't view the xbox files on my disk or iso.

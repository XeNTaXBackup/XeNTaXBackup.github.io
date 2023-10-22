## Post #1
- Username: tuanbusku
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri May 18, 2018 12:28 pm
- Post datetime: 2018-09-06T15:10:00+00:00
- Post Title: Compression signature

Hi, ive started looking at ground control 2's .sdf-files. This is how far ive gotten: 

DWORD ident 
DWORD directory_offset 

<lots of data> 

at directory_offset: 
DWORD uncompr_size 
UINT24 compr_size 
BYTE flags 
<BYTE[compr_size]> 
:EOF 

i havent identified the compression scheme used, it starts like this: 
5D 00 00 80 00 
do you recognize this signature?
## Post #2
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2018-09-06T16:36:46+00:00
- Post Title: Compression signature

> 5D 00 00 80 00
>
> do you recognize this signature?

It looks like lzma.

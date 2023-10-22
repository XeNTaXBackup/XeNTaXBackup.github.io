## Post #1
- Username: sigget
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-06-28T12:38:34+00:00
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
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-07-27T13:26:55+00:00
- Post Title: Compression signature

No, but thanks for the info!!

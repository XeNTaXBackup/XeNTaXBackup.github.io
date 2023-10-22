## Post #1
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2007-01-15T00:14:06+00:00
- Post Title: Torrente 3: El Protector

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-01-16T19:41:33+00:00
- Post Title: Torrente 3: El Protector

Okay, this is the general format:

```
uint32    version?
uint64    unknown
uint64    data size
uint64    data offset
uint32    number of resources (entries?)
uint64    offset of FAT
byte[]    data start (data size in size)

@FAT:

uint32    size of filename text table (and relative offset of location table)
byte[]    filename text table (a list of null terminated strings)

@Location table:

// for each entry 

uint32    start offset of filename text in filename text table
uint32    end offset of filename text in filename text table
uint32    resource id number (starting with 0)
uint64    compressed size?
uint64    uncompressed size?
uint64    offset
uint32    date in case of dir?
uint32    entry type (1 = folder, 2 = file)

```


I'll create a plugin for MexCom soon.
## Post #3
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2007-01-17T15:04:50+00:00
- Post Title: Torrente 3: El Protector

Okey waiting plugin
## Post #4
- Username: Infinity
- Rank: n00b
- Number of posts: 11
- Joined date: Sat Sep 09, 2006 11:42 pm
- Post datetime: 2007-01-31T23:53:22+00:00
- Post Title: Torrente 3: El Protector

Any new Mr.Mouse ?
## Post #5
- Username: Vash
- Rank: mega-veteran
- Number of posts: 183
- Joined date: Fri Apr 29, 2005 9:39 pm
- Post datetime: 2007-03-21T17:59:49+00:00
- Post Title: Torrente 3: El Protector

i would be very interested too, thanks

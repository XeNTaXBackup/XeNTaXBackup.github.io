## Post #1
- Username: Gorvin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 23, 2008 7:47 am
- Post datetime: 2008-11-23T09:54:54+00:00
- Post Title: Pirates of the Burning Sea

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Gorvin
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Nov 23, 2008 7:47 am
- Post datetime: 2008-12-08T00:13:26+00:00
- Post Title: Pirates of the Burning Sea

```
byte {1036} - null
uint32 {4} - Unknown 
uint32 {4} - Unknown 
// for each file 
   byte {5} - Unknown (02 33 18 00 00) 
   byte {5} - Unknown (01 33 18 00 00)
   uint32 {4} - Filename Length 
   char {X} - Filename
byte {5} - Unknown (01 33 18 00 00)
// for each file 
   uint32 {4} - Offset (may be null)
   uint32 {4} - null
   uint32 {4} - Compressed File Size(if Offset=null all (byte)255's)
   uint32 {4} - Unknown
.............

```

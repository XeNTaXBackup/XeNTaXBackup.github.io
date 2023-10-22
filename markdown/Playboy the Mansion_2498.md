## Post #1
- Username: oncesailor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 06, 2007 7:49 am
- Post datetime: 2007-03-07T00:28:05+00:00
- Post Title: Playboy the Mansion

I've been using my MultiEx Commander to take a look at all the .cam's in the game.  While it works great for .cam's with single file formats, is there some way to have it "unpack" multiple file formats.

(IE maindata.cam contains USEL,  NIMD, PICT, DATA and USEO files.)
(charhigh.cam contains multiple CYLBPC headings, and NIMD, NISL, NIAN files.)

Thanks

P.S. If you need an attachement let me know.  (Problem is that maindata is around 6M and charhigh is around 40M.)
## Post #2
- Username: oncesailor
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Mar 06, 2007 7:49 am
- Post datetime: 2007-03-09T21:21:54+00:00
- Post Title: Playboy the Mansion

Since the majority of the activity seems to be tied to textdata.cam, I'm trying to use MultiEX Commander to modify some of it.  Have already done a few , like opening up the developer's cheat menu and (modifying textures.cam) dressing the bunnies in just garters using just hex editing.

If you want to see some of the stuff I've done, check out:
[http://boards.ign.com/playboy_the_mansion/b6928/p1](http://boards.ign.com/playboy_the_mansion/b6928/p1)
Look for my Updated Downloads post.

What I found is that textdata.cam is similar to the .cam type 2 found in the XenTaXWiki.

textdata.cam looks like this:

char {8}     - Header (CYLBPC + 0x20 0x20) 
uint16 {2}   - Cam File Type 
uint16 {2}   - Version 
uint32 {4}   - Number Of Segment Types 
uint32 {4}   - length of the data segment type description area 

// for each type
uint32 {4}   - Segment Type ID 
uint32 {4}   - Byte number of the segment descriptor record 

// segement descriptor record, one for each segment type 
uint32 {4}   - Number of records 
uint32 {4}   - unknown (0x0000) 

// data records descriptors for each segment 
uint32 {4}   - data record name, ie. p012, p013, p014 etc. 
unit32 {16}  - null data
uint32 {4}   - Byte number of the start of data 
uint32 {4}   - data length 

the difference being in the data records decriptors, with a 16 byte null between the data name and the start of data.  (It also doesn't have a lot of the other stuff in .cam type 2)

So if someone can help me with a script to open it in MUltiEX Commander, I'd be greatful.

Thanks

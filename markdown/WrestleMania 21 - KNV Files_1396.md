## Post #1
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-14T20:04:15+00:00
- Post Title: WrestleMania 21 - KNV Files

Hi,

I dont really know if the knv files of WrestleMania 21 are Archives but I know that they contain .RES textures from wich I was able to extract a few with HexWorkshop but cant reinsert them.
The .KNV files are the Arenas.

There maybe some similaries to the WM21 .k files wich are the character files and do also contain .RES  textures.


Heres is the first and last MB of the RAW.knv file produced by Filecutter:

[http://www.wrestlinggames.de/mods/wmxxi ... aw.knv.zip](http://www.wrestlinggames.de/mods/wmxxi/tools/Raw.knv.zip)


The original size of RAW.knv is:

8.327.168 bytes
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-14T20:20:00+00:00
- Post Title: WrestleMania 21 - KNV Files

Allright! Will take a look.
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-14T20:55:19+00:00
- Post Title: WrestleMania 21 - KNV Files

Ok, it's preceded by some table file, but then come a collection of .K files. At the end there's another table-ish section. 

I will need to create a plugin for this one.
## Post #4
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-07-14T23:36:09+00:00
- Post Title: WrestleMania 21 - KNV Files

If we can start updating arena's, I will  move back to the modding scene, and create a complete update.

I was very close to opening up .bin files where the body types are located.
but then I quit, because of other games that caught my attention.
## Post #5
- Username: jasmine
- Rank: VIP member
- Number of posts: 77
- Joined date: Tue May 10, 2005 1:07 pm
- Post datetime: 2005-07-15T23:46:41+00:00
- Post Title: WrestleMania 21 - KNV Files

> Reply from Hammer
>
> If we can start updating arena's, I will  move back to the modding scene, and create a complete update.

I was very close to opening up .bin files where the body types are located.
but then I quit, because of other games that caught my attention.

How close?  Any details?
## Post #6
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-16T19:55:19+00:00
- Post Title: WrestleMania 21 - KNV Files

> Reply from Hammer
>
> If we can start updating arena's, I will  move back to the modding scene, and create a complete update.

I was very close to opening up .bin files where the body types are located.
but then I quit, because of other games that caught my attention.

Are you talking about Animation or 3D Model BIN Files?

If you are talking about 3D Models I would urge you to continue your work!
It would be awesome if I could make a 1994 Undertaker Model or a better Kane or... or... or... the possibilities would be endless!
## Post #7
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-18T10:50:22+00:00
- Post Title: WrestleMania 21 - KNV Files

Any Updates on the KNV files yet?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-18T10:54:35+00:00
- Post Title: WrestleMania 21 - KNV Files

Yeah sorry, I have a busy life, I haven't quite gotten round to it. It's not difficult, just a bit of work.  

Hopefully, when the Rahly's Plugin Manager is finished, more people that know how to program join up to add support, besides me, Kornet and Watto. 

It is already possible for others to create so called MexCom plugins. Anyone have ideas on how to reach people that would team up? Please send them over! 

Anyway, will fix up a plugin a.s.a.p. !
## Post #9
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-18T11:59:53+00:00
- Post Title: WrestleMania 21 - KNV Files

There is at whom a description of a format KNV ?
## Post #10
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-20T11:37:24+00:00
- Post Title: WrestleMania 21 - KNV Files

@Kornet
I do not understand, do you need a sample KNV file?
## Post #11
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-20T12:39:08+00:00
- Post Title: WrestleMania 21 - KNV Files

No no.....
Is not present to me the information on archive is necessary: Here for example description PAK of a format from game Archangel 

// ARCHIVE HEADER 
uint32 {4}   - Version (1) 
uint32 {4}   - Number Of Files 

// FILE DATA 
// for each file
byte {X}     - File Data 
uint32 {4}   - Unknown (26) 

// DIRECTORY 
// for each file 
uint32 {4}   - File Offset 
uint32 {4}   - File Size 

// FILENAME DIRECTORY 
// for each file
uint32 {4}   - Filename Length (including null) 
char {X}     - Filename 
byte {1}     - null Filename Terminator 

// ARCHIVE FOOTER 
uint32 {4}   - Offset to something
## Post #12
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-07-20T23:33:50+00:00
- Post Title: WrestleMania 21 - KNV Files

Ok, but how do I get this data?
## Post #13
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-21T09:26:38+00:00
- Post Title: WrestleMania 21 - KNV Files

Let's look that will tell Mr. Mouse or Watto... At them it well turns out
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-07-21T12:50:18+00:00
- Post Title: WrestleMania 21 - KNV Files

Hey um I didn't really see anything at quick glance, but I have put it back into my ToDo pile and will have a bit more of a look at it as soon as I can.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-08-02T16:28:44+00:00
- Post Title: WrestleMania 21 - KNV Files

Anybody made any more progress on this?
## Post #16
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-08-09T19:44:55+00:00
- Post Title: 

I was able to replace some textures in the KNV files:

[http://www.wrestlinggamesboard.de/index ... t&p=236501](http://www.wrestlinggamesboard.de/index.php?showtopic=14181&view=findpost&p=236501)

But the Game wont load Arenas that are outside of the DVD3.WAD file so we can just replace current Arenas yet.
## Post #17
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-08-10T06:12:26+00:00
- Post Title: 

> Reply from CrazyChris
>
> I was able to replace some textures in the KNV files:

http://www.wrestlinggamesboard.de/index ... t&p=236501

But the Game wont load Arenas that are outside of the DVD3.WAD file so we can just replace current Arenas yet.

How do you do it?

Anything special?
## Post #18
- Username: CrazyChris
- Rank: beginner
- Number of posts: 39
- Joined date: Mon May 30, 2005 7:52 pm
- Post datetime: 2005-08-13T11:05:32+00:00
- Post Title: 

I just searched for "TGA" in the KNV files and extracted the following RES file data with Hexworkshop.
Then I gave the file a DDS header, edited it in Photoshop and imported it back into the KNV file.

First I thougth that I made a mistake because the game crashed while loading the Arena out of the WM21 Main directory but then I realized  that WM21 can only load Arenas out of DVD3.WAD and you have to overwrite the old ones.
## Post #19
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-08-13T20:49:59+00:00
- Post Title: 

Thanks, I will see what I can do.
## Post #20
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-08-18T11:36:42+00:00
- Post Title: 

I think the arena's use a bsptree type structure. Like most any level file.
## Post #21
- Username: Hammer
- Rank: VIP member
- Number of posts: 51
- Joined date: Fri May 13, 2005 1:17 am
- Post datetime: 2005-08-18T23:11:32+00:00
- Post Title: 

> Reply from keshire
>
> I think the arena's use a bsptree type structure. Like most any level file.

What is that?
## Post #22
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-08-19T04:46:36+00:00
- Post Title: 

> Reply from Hammer
>
> keshire wrote:I think the arena's use a bsptree type structure. Like most any level file.

What is that?
[http://www.faqs.org/faqs/graphics/bsptree-faq/](http://www.faqs.org/faqs/graphics/bsptree-faq/)

> A Binary Space Partitioning Tree (or BSP Tree) is a data structure that is used to organize objects within a space. Within the field of computer graphics, it has applications in hidden surface removal and ray tracing. A BSP tree is a recursive sub-division of space that treats each line segment (or polygon, in 3D) as a cutting plane which is used to categorize all remaining objects in the space as either being in "front" or in "back" of that plane. In other words, when a partition is inserted into the tree, it is first categorized with respect to the root node, and then recursively with respect to each appropriate child. For more information on BSP trees, see the BSP Tree FAQ.
## Post #23
- Username: ModernDesigns
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 11, 2005 9:34 pm
- Post datetime: 2005-11-11T13:35:52+00:00
- Post Title: 

Can i ask, is there any update's on the model changing? It would be great to see if they could be changed, the possabilitys would be endless as CrazyChris, said in a earlyer post.

Thank you.
## Post #24
- Username: ModernDesigns
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 11, 2005 9:34 pm
- Post datetime: 2005-11-18T11:23:13+00:00
- Post Title: 

Well?, any new's then on how it's worked out?
## Post #25
- Username: keshire
- Rank: advanced
- Number of posts: 41
- Joined date: Thu Jul 15, 2004 1:15 pm
- Post datetime: 2005-11-18T12:09:06+00:00
- Post Title: 

I did all I'm willing to do on them. Unfortunately, the forum I had posted my work was run by a complete moron, and all was lost.
## Post #26
- Username: ModernDesigns
- Rank: n00b
- Number of posts: 11
- Joined date: Fri Nov 11, 2005 9:34 pm
- Post datetime: 2005-11-18T12:35:08+00:00
- Post Title: 

Oh?, dam that's a real shame sorry to hear. So your willing to look into editing the model's? if so it would be a great succes becuase the thing's you could pull out with that ability in wm21 is well, Amazing. if you can do this i would most be thank ful.

if you want to speak with me about i have a messenger, that's if you would like to speak.

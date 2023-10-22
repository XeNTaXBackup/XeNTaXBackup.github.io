## Post #1
- Username: esco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 14, 2018 12:40 pm
- Post datetime: 2018-02-14T05:40:15+00:00
- Post Title: Need help decompiling/unpacking a few salt & sanctuary files

Hi, everyone. This forum was recommended to me by someone as being an amazing place for help with game modding so here I am. I just put up a HUGE post with a bunch of tools and a mod update for an indie game called Salt and Sanctuary (the thread can be found here: [http://www.romhacking.net/forum/index.php?topic=25807.0](http://www.romhacking.net/forum/index.php?topic=25807.0)). As of now, MOST of the game is already moddable. However, there are a few key things that are still packed and thus not easily editable:

The master.zcm file: indicates which textures to load at runtime.
Sfx.zxp: ditto for which sound files to load
Fortress.zax: this is the map file. Things like enemy and item placements can be found here.
Zsx files for enemies and the player character: these seem to mostly have just basic animation data which is pivotal for modding enemies and attacks. But I am wondering if some of the damage multipliers for attacks may be here as well

I've looked into each of the files above with a hex editor and even changed a few things, and they all seem to use a very basic format. However, it is sadly beyond my ability to know how to put them into an unpacked format. So I wanted to come on here and ask for help with this.

The code itself for the exe has already been decompiled into C script (it can be found on the thread I linked to above and I uploaded the file with it and tons of mod tools here:  [http://www.mediafire.com/file/glt2petor ... 20Esco.zip](http://www.mediafire.com/file/glt2petor5gwnc3/S%26S%20Stuff%20-%20Esco.zip)) and a lot of files in the game use XML format once unpacked. I am at the moment noting the different structures and what different parts of interest in the code do.

Can someone please assist me with decrypting these files? For all 4 of the files it should be just a matter of unpacking the files (though ideally an actual editor for the map file would be hugely helpful as well). They all probably use the same format similar to the depacked xml files where the developers just made up different file extensions at the end of their names. I have included a link with each of the files and four of the zsx files I asked about above here to use as examples: [http://www.mediafire.com/file/gfs5qb854 ... packed.zip](http://www.mediafire.com/file/gfs5qb854jt9abw/S%26S%20files%20packed.zip)

I do not just want these tools for myself. My hope is to find a way to do this so that I can spread the tools around and more of a mod community can come into existence for this amazing game. Thanks in advance to anyone who takes the time to get back to me with this.  

P.S. Best emoticon ever:
## Post #2
- Username: esco
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Feb 14, 2018 12:40 pm
- Post datetime: 2018-03-02T21:37:30+00:00
- Post Title: Need help decompiling/unpacking a few salt & sanctuary files

Really? In this whole place, no one knows how to help with the things I asked about above.... with all the talented geniuses we have in here?

Come on peoples.... step up.   Let's make this happen together.
## Post #3
- Username: Thecodefender
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 30, 2020 11:50 pm
- Post datetime: 2020-06-30T15:54:20+00:00
- Post Title: Need help decompiling/unpacking a few salt & sanctuary files

I am getting out of memory error on unpacking. Also did you find the solution to changing / adding enemy placements?

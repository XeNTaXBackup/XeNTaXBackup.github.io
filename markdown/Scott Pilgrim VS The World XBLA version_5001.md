## Post #1
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-09-10T15:14:19+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Hello folks! I've been messing around with the internal files of this game, trying to extract any graphics data it may have. Now, in the root folder were two 'gamedata' files, and twelve png images. What I'm looking for is the character sprites. It turns out the pngs were just the achievement images. However, their simple format leads me to believe that within these 'gamedata' files must lie other simple formats, it's just a matter of extracting them. I've run them through filestripper but with no luck.

Here is a link containing a zip which holds both gamedata files. Could someone please take a look at them and let me know if there's any way to get the graphics out of them?
[http://www.sendspace.com/file/klwket](http://www.sendspace.com/file/klwket)

This is sort of an important project for me and I was hoping it could be resolved quickly, but don't worry about it if it takes time to figure out, I'm patient.
## Post #2
- Username: Caboose
- Rank: advanced
- Number of posts: 67
- Joined date: Sat Sep 19, 2009 1:20 am
- Post datetime: 2010-09-10T20:42:20+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Both gamedata, and gamedata1.fat are compressed with zlib. I don't see any files inside of these, just a bunch of int32's. Maybe this has the size, offset, CRC, etc of each file in another archive.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-10T20:45:46+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

the fat contains the chunk pointers needed to uncompress the other. was working on the script - i wont bother if someone else is?
## Post #4
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-09-10T21:08:27+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Oh! Awesome of you to take the initiative. I wouldn't be able to do this without help from fine folks like you. Uhm...if you get that script done, I'll be very thankful, as I'm very unintelligent when it comes to scripting and such. Thanks a lot fellow!
## Post #5
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-10T22:48:28+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

unfortunately i can't figure out the zlib error when decompressing the chunks!

```

if EXT != ""

  print "Error\n\nRun this script on the file without an extension!"
  cleanexit

endif

# find the matching fat

get FAT_DESC basename
string FAT_DESC += "1.fat"
open FDSE FAT_DESC 1
get s_FAT_DESC asize 1

# uncompress fat

clog MEMORY_FILE 0 s_FAT_DESC 0xfffff 1

endian big

get CHUNKS long MEMORY_FILE
print "Expected chunks: %CHUNKS%"

get TSIZE asize MEMORY_FILE

append
log MEMORY_FILE2 0 0

for i = 1 to CHUNKS

  get UNKNOWN long MEMORY_FILE # 1
  get UNKNOWN long MEMORY_FILE # 2
  get CHUNK_POINTER long MEMORY_FILE # 3
  
  savepos CPOS MEMORY_FILE
  
  if CPOS == TSIZE # no more chunk defs, so use filesize
  
    get ENDSAT asize
  
  else # else get next chunk pointer
  
	set TMP long CPOS 
	math TMP += 8
	
	goto TMP MEMORY_FILE
	get ENDSAT long MEMORY_FILE
	
	goto CPOS MEMORY_FILE
  
  endif
  
  set CHUNK_SIZE long ENDSAT
  math CHUNK_SIZE -= CHUNK_POINTER
  
  ## unfortunately, the script errors here
  
  if i == 1779
  
	print "Pointer: %CHUNK_POINTER% Size: %CHUNK_SIZE%"
	
	append
	get SIZE asize MEMORY_FILE2
	log "scott_dump.dat" 0 SIZE MEMORY_FILE2
	
	append

  endif
  
  ##

  clog MEMORY_FILE2 CHUNK_POINTER CHUNK_SIZE 0xfffff

next i

```
## Post #6
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-09-10T22:59:17+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Well...maybe the fat file should be without the '1' at the end. I added a 1 to it so I could easily distinguish the two when I was archiving. That's the only problem I could think of...and again I'm very ignorant of scripts. I don't even know how to run one properly unless it's given to me in BMS form or EXE form.
## Post #7
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2010-09-10T23:03:23+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

i only have what you uploaded, so the script uses the names you gave it.

and just copy the block of green text into notepad and save it somewhere. so long as you remember where, so you can find with with quickbms, you can load it

edit: but then again, at the moment its incomplete. it can spit out 1.2 mb of data before there is a zlib (decompression) error. theres no obvious flag to say its handled differently either, so i'm stuck for now.
## Post #8
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-09-10T23:06:58+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Hum...well...I get an error too. I'm not sure what would cause it though. Size error or something perhaps? I don't really know what the requirements are for these...
## Post #9
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-09-12T04:55:15+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Oh heavens I love this game. I'd love to have the graphics for it too. It'd be really great if someone figured out this format. I believe from what I was informed before is that these files work together to unpack the larger file, and unpack to a series of DAT files, which I assume will need to be unpacked as well. I'm just not entirely sure how to do this. If anyone has any information on how to get these things out it'd be really helpful.

Seriously, this is one fo the games I love the most. It would be like an early and ultimate christmas gift if I could get all the graphics from this game!
## Post #10
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-09-14T15:31:59+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

I guess the XBOX360 is more like the PC than we thought...DAT files can be used for anything...

Anyway, if someone could help out here perhaps we could get this unraveled properly. There's a wiki I'd like to contribute to with the information in these files, and I'm fairly certain a few other 360 games have the same method of compression. It'd be really helpful to have these worked out in any case...
## Post #11
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2010-09-29T21:10:43+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Hi there, I recently signed up here, to see if I could help out with this, seeing as i'm interested in this too.

I tried decompressing the gamedata and gamedata.fat with a zlib decompression program to see what I got.

I ended up with an extremely small gamedata file, and a gamedata.fat with a bigger size.

I got both files [here](http://www.mediafire.com/?cog6qs4o1j3aw88).

I hope this helps.

If not, at least I tried
## Post #12
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-10-01T00:49:58+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Well, it's a good attempt but I can't say much about the result. I still have no idea what we're looking for as extracted data unless it's as simple as .dat files or .png files. I think the script posted before was the closest with extraction, but we need to resolve the error.
## Post #13
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2010-10-20T20:12:20+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

Oh! Perhaps try running one of the new files through Filestripper?

Does anyone else have any ideas on what we can do to open this up properly? i think the above script is on the right track, we just need to resolve that error and we should be sailing free from there, unless it dumps into a bunch of DAT files, in which case we would need further research into it.

Also, when one closely reads the end credits, it states that the game was made entirely in FLASH! Isn't that cool? It reminds me of Castle Crashers and Alien Hominid in that aspect. Maybe we will be able to extract it, and it will dump to a bunch of SWF files? Just imagining things, sorry.
## Post #14
- Username: Nega
- Rank: beginner
- Number of posts: 27
- Joined date: Thu Sep 30, 2010 4:57 am
- Post datetime: 2010-10-20T20:33:32+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

> Reply from EldritchDecross
>
> Oh! Perhaps try running one of the new files through Filestripper?

Does anyone else have any ideas on what we can do to open this up properly? i think the above script is on the right track, we just need to resolve that error and we should be sailing free from there, unless it dumps into a bunch of DAT files, in which case we would need further research into it.

Also, when one closely reads the end credits, it states that the game was made entirely in FLASH! Isn't that cool? It reminds me of Castle Crashers and Alien Hominid in that aspect. Maybe we will be able to extract it, and it will dump to a bunch of SWF files? Just imagining things, sorry.

The filestripper method's been done before, with no success. If we can figure out the error from the BMS script, we could get somewhere.

Speaking of which, has there been progress on the script?
## Post #15
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-10-21T12:12:09+00:00
- Post Title: Scott Pilgrim VS The World XBLA version

We haven't had much progress with the script thus far, no one's even been here to take a look at it. Perhaps we should PM a certain someone about it...would anyone care to?

I didn't know this game was made in flash!
## Post #16
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2010-11-15T21:46:29+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

[http://www.sendspace.com/file/dmjmng](http://www.sendspace.com/file/dmjmng)
Here's an updated package of all the files in the Scott Pilgrim game.
## Post #17
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-04-06T00:30:16+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

[http://www.sendspace.com/file/n8j3lr](http://www.sendspace.com/file/n8j3lr)

Once again I must update this topic.

Have people lost interest?

Looking at the XEX file, I've determined that is a XEX2 format.
And with a little research...
XEX2: 20B185A59D28FDC340583FBB0896BF91
## Post #18
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-04-15T23:28:20+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

Well, since no one else is doing anything I've been fooling around with the XEX file with XEXtool. However all it seems to give me is the achievement images which we already had.

Come on guys. I'd like to have this finished before I start chemotherapy, cause from what I hear that crap leaves you in no condition for brainwork.

Anyway, I was thinking perhaps someone should look into the .toc files as well...I'm not sure what they are.
## Post #19
- Username: EldritchDecross
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 27, 2010 10:39 am
- Post datetime: 2011-04-26T19:36:11+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

I'm surprised this hasn't gotten more attention...I'd really love to have the graphics from this game as well...
## Post #20
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-06-23T01:10:22+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

Well, I'm about ready to give up. All I can manage is getting the achievement images out, which we already had. I desperately need the graphics from this game though so I still come here...

ANYONE got ANY ideas?
## Post #21
- Username: ShinKun
- Rank: veteran
- Number of posts: 132
- Joined date: Sun Aug 08, 2010 10:02 pm
- Post datetime: 2011-07-21T04:52:38+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

The contents of this post was deleted because of possible forum rules violation.
## Post #22
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2011-07-25T00:35:49+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

Looking over the ATN files, at the end it is notable that 'LAYER' appears in ASCII. I'm looking over the larger DAT file now.
## Post #23
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2014-02-09T09:08:15+00:00
- Post Title: Re: Scott Pilgrim VS The World XBLA version

Damn, I know this is a horrid necropost, but I found something similar. Another game by Ubisoft has the same style. Might and Magic: Duel of Champions uses the 'gamedata/gamedata.fat' method of compression, and there's been a modding program written for it.
This here link will take you right to the place where you can find it. Perhaps if we do what the original post suggests in decompiling it, we can find the 'missing piece' for Scott Pilgrim? Just wishful thinking...
[http://forums.ubi.com/showthread.php/78 ... ool-Forums](http://forums.ubi.com/showthread.php/783555-Tool-Zenity-s-Modding-Tool-Forums)

Could someone experienced in coding and BMS possibly find out what we're missing from this?

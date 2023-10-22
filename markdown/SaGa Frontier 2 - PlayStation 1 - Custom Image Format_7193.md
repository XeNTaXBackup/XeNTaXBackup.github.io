## Post #1
- Username: Death
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 18, 2011 2:56 am
- Post datetime: 2011-08-17T19:13:02+00:00
- Post Title: SaGa Frontier 2 - PlayStation 1 - Custom Image Format

If you look at the files on the game disc (or the files in a disc image, which is a digital copy of a game disc), then you will see that SaGa Frontier 2 has only three files: SAGA2.IMG, SLUS_009.33, and SYSTEM.CNF. Every other PS1 game I've ever seen has at least a dozen files, and some have hundreds of them.

Here's the size of each file:
*SYSTEM.CNF
**68 bytes
*SLUS_009.33
**454 Kilobytes
*SAGA2.IMG
**591.6 Megabytes

Most of the game's data is in SAGA2.IMG.  I don't know if it's compressed or not, so I asked someone and he helpfully supplied some info.

> Well looking at the format of numbers in the first 0x8D4 bytes of the file, they clearly look like pointers of some kind, but with a few odd values that don't match up. Considering this file would have been stored on a disc it probably might index stuff with sectors in mind, however there's still no obvious pattern that I can see. With 0x00s and 0xFFs highlighted in a hex editor you can quite clearly see image patterns appear around the 2/4 of the file, unfortunately since TileMolester can't open big files, I can't confirm this properly :/
>
> Hope this helps...

Alfador, of Verve Fanworks, said the following:

> PSicture was willing to take the entire disc image and disgorged over a hundred TIM images, most of which appear to be backgrounds of some sort (plus one instance of what looks like menu text). My spot-checks didn't turn up anything in that set resembling model textures, so they're probably in a different format (or simply have an external CLUT, which PSicture doesn't handle either).
>
> 
>
> Other PSX-era Squaresoft games sometimes use a TIM-format variant with a slightly different header for model textures. It's a PITA to work with, unfortunately. The examples I've seen were palettized images with an 8-bit CLUT (Colour LookUp Table).
>
> 
>
> You could also be dealing with LZSS-compressed data, although I doubt it--I've never heard of it being used to compress images.
>
> 
>
> SaGa Frontier II almost certainly does store file location information in a table near the beginning of the disc, or at least, other Squaresoft PSX games are known to do that. Unfortunately, it doesn't follow the lead of the game I'm most familiar with and put the table at sector 24, and a quick skim of the beginning of the disc in a hex editor didn't turn up a more likely location. The table may have information other than file location pointers in it, such as file lengths, end-sector padding lengths, or flags. It takes around 2.5 bytes to usefully encode a pointer to a CD sector, so look for a four-byte stride containing little-endian pointers of 2.5-3 bytes padded with other data.
>
> 
>
> If you can't find or decipher the file table, you could try carving the file into uniform-sized chunks small enough that TileMolester won't choke on them and see if anything turns up. Also, if you can, read up on other PSX-era Squaresoft games--a lot of what my quick skim of the disc turned up looked like fairly standard stuff, like AKAO sound tracker blocks. Try wiki.qhimm.com or RHDN for documents. qhimm in particular has a fairly good description of how TIM images work.

Yoshi314, of Qhimm, said the following:

> I really think you should go to xentax forums with this, you're more likely to find someone with the know-how.

I'm not sure if this post belongs here or in Compressed files and methods.  I'm trying to make a spreadsheet to dump and document initial character data, item data, and ability data for SaGa Frontier 2, so I'm not interested in extracting pictures.  I tried to locate initial character data, but it seemed like it was broken into several pieces and spread over a large area in such a way that I can't find it, or it was duplicated.

These are the topics I made at other boards.  They don't have any additional info right now, but they might in the future.
[http://www.gamefaqs.com/boards/198538-s ... 2/60045037](http://www.gamefaqs.com/boards/198538-saga-frontier-2/60045037)
[http://www.verve-fanworks.com/SMF/index.php?topic=479](http://www.verve-fanworks.com/SMF/index.php?topic=479)
[http://forums.qhimm.com/index.php?topic=12273.0](http://forums.qhimm.com/index.php?topic=12273.0)

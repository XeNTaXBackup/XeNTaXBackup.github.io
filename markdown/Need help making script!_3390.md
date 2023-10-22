## Post #1
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2009-03-09T23:34:42+00:00
- Post Title: Need help making script!

Ok, I have figured out a file format, but I have not written a script before and I would like some help to do that.  Preferably, if someone could PM me with a way to IM you and get immediate help, or if you just want to add to the thread that is fine, but once I get help walking through this, I think I could do more on my own.

The file format is as follows (BTW it is an xbox 360 file which should be big endian):

The first four bytes are the archive name, in this case 2E5A4300

Then the next four bytes are the filesize of the fully decompressed and assembled file (the file is broken into 65kb sections, then zlib compression is added to each section and then those are put into the archive in order, the complete file is gotten by taking those sections out of the archive in order, decompressing them and then assembling them together to make the complete file)

Then the next two bytes are the length of the first file section.

After that file section, which is zlib compressed, there is another two bytes that are the length of the next file section.

Of course, none of the sections are ever larger than FFFF, and the uncompressed size of each section is always 64kb, except for the last one, which is the size of whatever is left over.

This continues on until you reach the end of the archive.

At that point you will have those file sections that will need to be zlib decompressed, then the decompressed sections need to be assembled together to make the complete file.

I hope I have explained this good enough that someone familiar with the scripting engine could help me.  After I get this figured out, I will of course submit the script for anyone to use that needs it.  Thanks.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-03-11T15:46:18+00:00
- Post Title: Need help making script!

If you want to present a file format, it's best practice to use some C-like notation:

```
uint filesize; // after full decompression
struct Section
{
	ushort sectionLength;
	byte data[sectionLength];
} sections[numberOfSections];
```

Did I understand your explanations correctly?

Well I'm not sure, but if it is composed like that I guess it's not possible to write a BMS for that.

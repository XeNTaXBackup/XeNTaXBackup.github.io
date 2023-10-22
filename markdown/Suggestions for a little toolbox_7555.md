## Post #1
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-23T20:46:50+00:00
- Post Title: Suggestions for a little toolbox

Searching for suggestions for stuff you want to see in a cross-platform toolbox for reverse engineering.
(I'm currently working on the stuff at '2D' myself)

Current ideas:

2D:
DDS header generator
raw rgb/a <-> raw DXT12345 <-> palette+raw image data conversion

3D:
raw basic data (vertex+UV) (No bones, I don't know how they work  ) -> obj

Documents + Templates:
standard file format description (.html + .css template), I made one but I don't know your needs
suggestions for standard licenses of tools
revamp of the definite guide to a very compact version or multipage .html+.css
request form with a checklist that maybe makes requests easier to understand for the community

General features for a tool:
CLI+GUI (no parameter = GUI, parameter = CLI)





I'm currently writing all the tools in Ruby that means on windows you get an .exe (with OCRA) or an optional ruby script, all other
platforms get just the ruby script.

Why did I choose ruby? Because it can do this (and read that struct with one line from a file):

```
  endian :little
  
  uint32 :filenameOffset
  uint32 :fileSize
  uint32 :fileOffset
  int32  :checksumFile #Probably a checksum of some sort
end

class ARC_header < BinData::Record
  endian :little
   
  string :magicNumber, :read_length => 8 #EZBIND + 0x00 padded to 8 Bytes
  uint32 :nOfFiles
  int32  :checksum1 #CRC for following block or for entire file? maybe something completly different
  array  :metadata, :type => ARC_metadata, :initial_length => :nOfFiles
end

class ASCIIZ < BinData::Record
   stringz :filename
end
```


Ruby supports pretty much all the stuff QuickBMS has (which makes it really easy to program with) and is (at least for me) easy to understand yet
can be deployed standalone.


So what are your suggestions for programs and other stuff that comes to your mind?
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-23T21:39:17+00:00
- Post Title: Suggestions for a little toolbox

Not a suggestion, per se, but the wiki covers a couple of your points under Documents + Templates. I've been working off-and-on towards a "standard" file format description format for years now, by way of metadata (though the DB corruption and reset a while back set me back quite a bit), and the DGTEFF is on the wiki (though it's currently full-protected... I really should unprotect it).
## Post #3
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-23T22:41:55+00:00
- Post Title: Suggestions for a little toolbox

DGTEFF is still impressive (I learned some important stuff through it), yet the wiki version doesn't work with all the symbols and outputs them cryptically
(the tables at the bottom are messed up) + some CONVERT ERRORS are cluttered around.


In my opinion it would need to be reworked with focus on readability, structure, an extensive glossary, sourcelinks and with a loooong introduction chapter and 
not just archive file formats but also sound files,2D and 3D stuff (maybe even 'real' reverse engineering with an exe but that would be overkill).
Also some 'new' methods like texture dumping from an emulator + searching for the resulting file data aren't covered, the list goes on...
more hexeditors+tools , quickBMS, how to publish results, explained file format specs (WAV/OBJ/DDS),...

By no means I intend to say that DGTEFF is bad, just missing some stuff that I think is really important.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-23T22:55:12+00:00
- Post Title: Suggestions for a little toolbox

Yep, those are all points I'm aware of as well. As far as the encoding issues are concerned, I actually fixed quite a lot of characters, but as you note, there are more to be done.

As far as reworking it is concerned, well, that's where the wiki really shines - not only does it let anyone edit pages (or will, once I unprotect DGTEFF), but it also fully tracks a page's history. Ultimately, the DGTEFF could grow into a resource above and beyond anything either of us could envision, precisely because it's on the wiki.
## Post #5
- Username: 0xFAIL
- Rank: VVIP member
- Number of posts: 50
- Joined date: Fri Oct 21, 2011 5:59 pm
- Post datetime: 2011-10-23T23:40:12+00:00
- Post Title: Suggestions for a little toolbox

I see you are entusiastic (as far as the history of the wiki page tells me ;-D ) yet I will try to fork it (or completly rewrite it, not sure)
as a multipage HTML+CSS cause wikipedia is problematic for really long documents and very
techy/specific content (in my opinion).

You don't have any suggestions to the toolbox mentioned above? (Except the documents)
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2011-10-24T01:04:00+00:00
- Post Title: Suggestions for a little toolbox

It can very easily be split on-wiki, with no fork required; I can do so for you if you're not sure how.  

As for other suggestions... not really; I don't really work with reverse-engineering tools enough to have any kind of tangible wishlist of features and functionality.

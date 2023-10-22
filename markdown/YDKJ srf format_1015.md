## Post #1
- Username: elcondor
- Rank: VIP member
- Number of posts: 18
- Joined date: Tue Dec 14, 2004 6:28 pm
- Post datetime: 2004-12-14T10:29:37+00:00
- Post Title: YDKJ srf format?

I know that someone's requested the .DAT file, but I think the majority of the sound is in srf - Script Resource Files. The major issue is that the srf file can take more than one file type - the sample I have is sound and text, but others have JPEG data and animation (I think the compression is a bit strange for those).

A sample of this file is available at [http://www.mametesters.org/elcondor/ABH.srf](http://www.mametesters.org/elcondor/ABH.srf) , and I include a document I 
found explaining how the file is put together - if anyone 
here knows how to make this into an easily usable tool, 
let me know.

Other examples can be found in games like You Don't 
Know Jack (1-4 US, the UK version and some of the 
German editions) - I believe some contain JPEG graphics 
data but it's custom compressed.

ok, here are my 15-minute findings. my head is not in 
the right state to 
dig much more but might be a start. first of all, the 
header is made of 
big-endian longs, not little endian. use some kind of hex 
editor to 
follow my ramblings, i use hex workshop (options -> byte 
order -> big 
endian). offsets are noted in hex, btw.

first long is the format identifier, "srf1". next long is the 
size of 
the file, 0x0005CA10, that's 379408 bytes. the third long 
is the size of 
the header without counting these three first longs, 
that's 208 bytes. 
so note that the first resource will be placed at decimal 
offset 208+12, 
that's offset DC.

the header is a list of structures for defining resources 
inside this 
file. i'm having a headache trying to understand 
the "STR " structure, 
because it says there are 8 strings, but actually there 
are nine, and 
two of the resource descriptors point to the last two 
longs of the file 
(which aren't resource space, as you'll see). part of 
this "STR " 
structure is similar to the "snd " one but there are holes 
in my 
theory... following so many numbers (according to the 
aussie aborigins, 
five or more = many) makes my head hurt.

i'll jump now to offset 74, where you can find the 4-byte 
string "snd ". 
next long, offset 78, is the number of sound resources in 
the file, in 
this case also 8. the next 24 longs are 8 groups of 3 
longs each one. 
each group has in this order: resource id, offset, size. 
for example, 
the first resource descriptor is at offset 7C, it 
says "resource id 
0x0000001, at offset 0x000001FC, with a size of 
0x000053BC bytes". which 
means that at decimal offset 508, you'll find a sound 
resource of 21436 
bytes. the last resource descriptor is at offset D0, and 
says "resource 
id 0x0A, at offset 347764, and is 31636 bytes long".
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-10T08:14:26+00:00
- Post Title: YDKJ srf format?

Just a reply in this thread, to say that El Condor already created a script for this! Well, for one SRF format anyway! See MexScript tutorial !

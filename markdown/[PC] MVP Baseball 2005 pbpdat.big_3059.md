## Post #1
- Username: kylew
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 07, 2008 10:26 am
- Post datetime: 2008-06-15T00:59:17+00:00
- Post Title: [PC] MVP Baseball 2005 pbpdat.big

Hello everyone. First I just want to thank Mike for fixing my registration problem. I joined here because me and some others are trying to mod this game's sound and to do this we have to be able to create this files from the ground up. I have been researching the file format and I almost have everything figured out except a few things I cannot understand. Let me explain how this works. There are 4 files involved. Pbpdat.off, pbphdr.off, pbpdat.big, pbphdr.big are the names. First, you look in pbphdr.off to get the offsets and lengths of the group headers which are in the pbphdr.big file. Once you have the group header’s offset and length you read pbphdr.big, go to the offset and then there is a header structure like this:

```
AfterID (16bit) – Always FF FF
unknownA (4 bit) – Almost always null. Value is 8 for 3 items.
#ofPadBits (4 bit) – How many padding bits are put between the file offset listings
#ofFiles (8 bit) – How many files are in this group
UnknownB (8 bit) – No idea what this is. It is usually (probably always) how many full bytes (FF) are in the EndBits.
GroupLength (16 bit) – After being converted to 24 bit this is the length of the group’s data chunk in pbpdat.big.
UnknownC (8 bit) – Don’t know what this is. Always null except once. For one group the value is 1.
OffsetListings (variable) – Inside this there is a listing of file offsets stored as 16 bit values, but must be converted to 24 bit to make sense. The amount of pad bits from the #ofPadBits value are also stored between the offsets.
EndBits (variable) – Here is where I’m lost. I cannot figure out what these mean. Most, but not all, of these are either 00, 70, or FF. 

```


After all this information is known you open pbpdat.off and go to the respective line (if you were on line 4 in pbphdr.off you go to line 4 in this as well) and read the group data offset and length. To extract the files you add the group data offset to the file offset you got from the OffsetListings and extract the data all the way to the next file’s beginning. 

Hopefully I explained that well enough. I have attached the 4 files mentioned above as well as a spreadsheet with all the headers from pbphdr.big broken down for better readability. In case you don’t want to open a spreadsheet I have also attached a plain text csv file with the same information. I only attached part of pbpdat.big because the full pbpdat.big is 202mb. It is available upon request.

Heres the files.
group headers spreadsheet [http://uploaded.to/?id=93y4fp](http://uploaded.to/?id=93y4fp)
group headers csv [http://uploaded.to/?id=apl3tx](http://uploaded.to/?id=apl3tx)
pbphdr.off [http://uploaded.to/?id=m8bz52](http://uploaded.to/?id=m8bz52)
pbpdat.off [http://uploaded.to/?id=psg441](http://uploaded.to/?id=psg441)
pbphdr.big [http://uploaded.to/?id=7r783y](http://uploaded.to/?id=7r783y)
pbpdat_partial.big [http://uploaded.to/?id=2dsg0y](http://uploaded.to/?id=2dsg0y)

I appreciate any help you are able to give.

Thank you so much,

Kyle
## Post #2
- Username: kylew
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 07, 2008 10:26 am
- Post datetime: 2008-06-20T23:11:20+00:00
- Post Title: [PC] MVP Baseball 2005 pbpdat.big

No one has any idea what these unknowns could mean? Please help if you can, asking you guys was my very last resort. If I can't figure this out I will have to abort the project.
## Post #3
- Username: kylew
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 07, 2008 10:26 am
- Post datetime: 2008-06-27T00:11:24+00:00
- Post Title: [PC] MVP Baseball 2005 pbpdat.big

thanks for all this advice!

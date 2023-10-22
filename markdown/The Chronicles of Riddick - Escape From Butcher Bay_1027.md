## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-12-26T12:37:48+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

hello

Iam need help!
for unpack xtc from "The Chronicles of Riddick - Escape From Butcher Bay"

thank you
## Post #2
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-12-27T18:32:41+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Level editor + GDK
[http://www.3dgamers.com/games/chronicle ... downloads/](http://www.3dgamers.com/games/chroniclesriddick/downloads/)
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-12-29T18:39:59+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

thx 

but gdk not include extractor or unpacker
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T21:11:20+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

There's no demo yet. Any chance of getting us a sample archive?
## Post #5
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-01-11T13:19:47+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Hi

Thx

this is attach xwc arrchive include sound file ogg
## Post #6
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-01-11T13:33:00+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

this is arrchive xtc

thx
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-12T11:23:35+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Thanks !
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-01-14T12:49:53+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Here Mr Mouse, my specs for the format...

```
| The Chronicles of Riddick - Escape From Butcher Bay *.xwc *.xtc |
+-----------------------------------------------------------------+

16 - Header (MOS DATAFILE2.0 + null)
8 - null
4 - Unknown
20 - null

// OPTIONAL PADDING
// Read the first few bytes - if it doesn't match the padding then
// the padding doesn't exist and you just move on to the loop following

X - Padding to offset 2048 (padded using repeats of 1234567890123456)

// for each file
  4 - Unknown (768)
  4 - Unknown (36864)
  4 - Length (excluding all header data - ie the length of the file data only)
  4 - Unknown (1)
  4 - Unknown
  4 - Unknown (36864)
  4 - null
  X - File Data

```


Yeah - really bad specs, but it is enough to extract the files from the archive

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-14T12:51:10+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Ok, great! Thanks a bundle, have been to busy with other stuff.
## Post #10
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-02-09T14:39:02+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Hi guys

How can i use this information to extract files from the game ?
Did i have to use the Mex Script Editor that i read about ?

Thx
## Post #11
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-09T22:12:54+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

hi Guest

no

you can't extract files

not create scripe for package!!
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-10T02:38:23+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Oh sorry, we didn't get a Mex Script for this game? I did make a Game Extractor plugin for it - not sure if I sent it to you or not. I have attached it here anyway just in case.

For the Guest, you can download Game Extractor from [http://www.watto.org/extract](http://www.watto.org/extract) and unzip the plugin I attached here into the plugins/ directory. Then start the program and open the archive you want.

Sorry about the Mex Script not coming along - I should really learn how to write them 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_XWC_MOS.zip](https://xentaxbackup.github.io/file/114_Plugin_XWC_MOS.zip)
## Post #13
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-11T07:52:42+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

hi mr watto

thank you  for plugins

but not work for all archives, only work on music.xwc without filename correct 

and other arrchives, message error : no plugin was....

thanks you again
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-11T11:16:09+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Well that error simply means that the other archives have a different structure. The only way to fix that is if you can give us a copy of the other archives.

Sorry about that, I hate it when this happens.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #15
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-11T11:36:17+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

this above attached arrchive open but complete arrchive all.xwc can't open  

after some second loading show error message 
not correct filename
## Post #16
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-02-11T11:37:53+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

1.open attached arrchive but complete arrchive all.xwc not open  

after some second loading show error message 
2.not correct filename
## Post #17
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-11T12:13:51+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Yeah thats OK, the second error "incorrect filename" is happening because Game Extractor is trying other plugins. Basically it means Game Extractor tried to use the correct plugin, but failed, so is trying a few others to see if any of them work.

I *may* be able to fix the plugin, but it is only a slight chance. What you can do is go to the logs/ directory and remove all the files. Now restart Game Extractor, try to open the archive, and close the program. Hopefully there is a file in the logs/ directory which contains the error information - if so then you can email the file to me and I *may* be able to fix the plugin.

Thanks mate,

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #18
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-02-12T11:30:27+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Hmm, thanks for the log file, but I don't think it will help much. I will try to repair the bug and send you a fix, but it shouldn't mak any difference to the plugin. I guess the formats are just different 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #19
- Username: SparedLife
- Rank: advanced
- Number of posts: 47
- Joined date: Sun Mar 07, 2004 1:37 pm
- Post datetime: 2005-06-03T23:22:13+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

Was this ever resolved?
 I checked out the Pa1_MainFrame_Precache.XDF for textures and found some DDS and TGA files but none compressed. If anyone wants to use a little Perl, this unfinished script reads the DXT1 formats and creates DDS files. I haven't had time to work with it and add the other file formats or the MIP filters so right now it extracts about 3300 files with most being useless. I'm not sure if I will ever be able to finish the script at the pace I am going.

```
die "Missing input file name.\n" unless $InputFilename;
open(INPUTFILENAME, "< $InputFilename") or die "can't open $InputFilename: $!\n";
binmode(INPUTFILENAME);
$FileStartOffset = 1;
$EXT = ".DDS";
$MyFileLength = (-s INPUTFILENAME);

 read (INPUTFILENAME,$FileContents,$MyFileLength,0) or die "can't read $MyFileLength bytes.\n";
 $FindString = "\3\0\0\0\120\0\0";
$DDSContent = @{[$FileContents =~ /$FindString/g]};
while ($FileStartOffset > 0)
{
$FileStartOffset = index($FileContents, $FindString,$Offset);
 $DDSFileOffset = ($FileStartOffset + 43);
 $FileName = $DDSFileOffset.$EXT;
 seek INPUTFILENAME, $FileStartOffset, SEEK_SET or die "can't seek to File Header.\n";
	read (INPUTFILENAME,$FileContent,32,0) or die "can't read $MyFileLength bytes.\n";
 ($Size2, $Size1)= unpack "(x[c]x10)Sx[S]S", substr $FileContent, 0,32;
$DDSLength = ($Size1*$Size2);
$DDSL1 = pack "SSSSSSSS", 17476, 8275, 124, 0, 4103, 10, $Size1, 0;
$DDSL2 = pack "SSSSSSSS", $Size2,0,0,2,0,0,0,0;
$DDSL345 = pack "LLLLLLLLLLLL", 0,0,0,0,0,0,0,0,0,0,0,0;
$DDSL6 = pack "LCCCCLL", 0,68,88,84,49,0,0;
$DDSL78 = pack "LLLLLLLL", 0,0,0,0,0,0,0,0;
 print "count = $DDSContent\n";
 print "Iteration = $Iter\n";
 print "Location = $DDSFileOffset\n";
 print "Width = $Size1\n";
 print "Height = $Size2\n";

{
seek INPUTFILENAME, $DDSFileOffset, SEEK_SET or die "can't seek for read.\n";
	read (INPUTFILENAME,$DDS,$DDSLength,0) or die "can't read File.\n";
open(OUTPUTFILE, "> $FileName") or die "can't open $SaveFile: $!\n";
binmode(OUTPUTFILE);


print OUTPUTFILE $DDSL1;
print OUTPUTFILE $DDSL2;
print OUTPUTFILE $DDSL345;
print OUTPUTFILE $DDSL6;
print OUTPUTFILE $DDSL78;
print OUTPUTFILE $DDS;
}
$Offset = ($FileStartOffset + 1);
}
```


 to use this you need Perl installed and the line writes as

 Perl riddickripper.pl Pa1_MainFrame_Precache.XDF

 This is assuming you save the perl script as riddickripper.pl
## Post #20
- Username: OmegaThree
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Mon May 17, 2004 5:06 am
- Post datetime: 2005-09-20T23:42:30+00:00
- Post Title: The Chronicles of Riddick - Escape From Butcher Bay

I've been working with FriendsOfWatto's header description in hopes of making a utility to extract files from Starbreeze's MOS 2.0 package format.  Unfortunately, I'm having some unrelated trouble reading the files because of all the nulls, but FOW's header description appears to be accurate â€” which I wholly expected.

I've been testing it with Enclave, and there are some discrepancies worth noting that may help others decode the format.  I will note them here as I find them.  (Please note, these discrepancies exist within Enclave and do not apply to 'Chronicles of Riddick' or 'Knights of the Temple,' as far as I know.)
________________________________________
Enclave-specific MOS 2.0 Archive Header Discrepancies

CompiledTextures.xtc does not have padding, but all the Waves_?.xwc files do.  They are padded to 2048 bytes, just as FOW said.  (He also mentioned that a file might not contain padding at all, which is the case here.)

For Enclave archives, the first unknown dword (after the padding) is 512, not 768 as in FOW's description.  This may be a game-related value.  I'll test Knights of the Temple as soon as I get a copy and see if it's different.

(Second unknown dword is 36864, just as FOW said.)

Data size:  there seems to be a 12-byte difference between the reported size in the MOS 2.0 and the actual size of the extracted file.  For example, the first OGG file in Waves_0.xwc reads as 7,198 bytes in the archive but is only 7,186 bytes when extracted.  Similarly, the first file in Waves_1.xwc is reported as 33,916 bytes but is only 33,904 bytes when extracted.  Not sure what to make of this.

The third unknown dword (after data size) is 1 in some cases and 2 in others.  Not sure what to make of this either.

Value of the fourth unknown dword varies between chunks.  Will need to finish my extraction tool before I can decipher it.

The fifth unknown dword (before the last null) is 32768, not 36864.
________________________________________

About that file size discrepancy:  I've extracted OGG files with both Dragon Unpacker 5 (HyperRipper 5.0.1d) and Extractor 2.4.  Perhaps these programs are simply chopping off the last 12 bytes?  I don't know, but I'll figure it out eventually.

There seem to be some key differences between XW and XMD formats.  My immediate concern is extracting usable data from the XTC/XWC archives, but I will work out the other formats in the future if at all possible.  (I'm not very good at deciphering formats, and I'd be nowhere without FriendsOfWatto's header description.)

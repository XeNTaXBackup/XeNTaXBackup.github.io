## Post #1
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-26T16:59:41+00:00
- Post Title: Burnout Paradise .BIN files. help!

Hey,

I'm actually looking for a .BIN extractor for burnout paradise files.
All gamefiles are .Bin and I can't seem to open them and I couldn't find anything wit google.

I hope someone here can help me.
Here are 2 bin files;

[http://ifile.it/ud79pw5](http://ifile.it/ud79pw5)
[http://ifile.it/64krsex](http://ifile.it/64krsex)




BTW: This is my first post here on the forums
## Post #2
- Username: Steefjan
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-26T17:58:01+00:00
- Post Title: Burnout Paradise .BIN files. help!

they are just zlib files I suggest using offzip 

I don't see names anywhere

the extracted files are defiantly proprietary.
## Post #3
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-26T18:12:01+00:00
- Post Title: Burnout Paradise .BIN files. help!

thanks for you response.
I've got the program but how do I use it?
Sorry I'm a total n00b to this stuff.  

thanks.
## Post #4
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-26T18:43:18+00:00
- Post Title: Burnout Paradise .BIN files. help!

Here are a extra file..
[http://ifile.it/ag209vd](http://ifile.it/ag209vd)



But when you extract them.. it just does some codes and it closes down.
And I don't see anything changed..

sorry for the double post
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-26T18:58:22+00:00
- Post Title: Burnout Paradise .BIN files. help!

offzip.exe -a PathToFileYouWantToExtract OutputFolder 0x0
## Post #6
- Username: Steefjan
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T19:37:24+00:00
- Post Title: Burnout Paradise .BIN files. help!

You can use this MultiEx Commander script to extract the compressed chunks or files that are mentiones in a table at the beginning of the bin files. However, sometimes a larger file is separated into multiple chunks of originally 65536 in size. I have not bothered yet to see if this is id-able somewhere. 

Anyway, the tex_vehicle.bin file you posted is also different, it is a collection of dds file data , without headers and compressed using zlib. Yet, the table only references small chunks that contain image information of the original dds file, such as height and width and which DDS type, but the image data is not referenced in a table, the compressed files are simply saved after everything else in sequence. 

Here's an example of a reconstructed first texture in there:



uncompressed_dds_1.jpg (53.09 KiB) Viewed 995 times



Here's the mexscript:

```
ComType ZLib1 ;
Get U1 Long 0 ;
Get U2 Long 0 ;
Get TableOffset Long 0 ;
Get Chunks Long 0 ;
Get TableOffset2 Long 0 ;
Get FileOffset Long 0 ; 
Get ArchiveSize Long 0 ;
Get ArchiveSize2 Long 0 ;
Set FN String "uncompressed_chunk_"; 
Set EXT String ".zlb" ; 
Set USize Long 65536 ;
For T = 1 To Chunks ;
GoTo TableOffset 0 ;
Get U3 Long 0 ;
Math TableOffset += 28 ;
GoTo TableOffset 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Math TableOffset += 12 ;
GoTo TableOffset 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Math FO += FileOffset ;
Set Name String FN ;
String Name += T ;
String Name += EXT ;
CLog Name FO FS FOO FSO USize 0 ;
Math TableOffset += 24 ;
Next T ;

```


And the bin.bms file to use in MultiEx Commander.
[bin.zip](https://xentaxbackup.github.io/file/2232_bin.zip)
## Post #7
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-26T19:46:22+00:00
- Post Title: Burnout Paradise .BIN files. help!

Wow mr Mouse thanks a lot!  
thanks thanks, I've searched ages on how to do this you're my  game modding hero!

I'm a total n00b to this stuff,
could you please PM me a step by step guide on how to do it.?

thanks a lot!,

sorry for my english I'm 14 and from the Netherlands..
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-26T20:14:45+00:00
- Post Title: Burnout Paradise .BIN files. help!

That depends, what is it that you wish to do? Create the DDS files? Use the script ? Something else?
## Post #9
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-26T20:16:37+00:00
- Post Title: Burnout Paradise .BIN files. help!

well I wanted to get textures out of the bin files.
So create the .DDS files
Or how did you get that texture out of it?

I'm sorry of my n00biness
## Post #10
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-27T08:20:15+00:00
- Post Title: Burnout Paradise .BIN files. help!

Well I made it to view the uncompressed chunks in the vichicletex.bin.


this is what I did;









So, I've got a uncompressed junk file wich is in Zlb, that's a zlib format (right?  )

But how can a compress the zlb file?
and get the .DDS files out of it?

thanks.
## Post #11
- Username: Gocha
- Rank: veteran
- Number of posts: 109
- Joined date: Sat Dec 13, 2008 3:16 am
- Post datetime: 2009-07-27T08:24:03+00:00
- Post Title: Burnout Paradise .BIN files. help!

Just add a simple question - how to determine file header offsets and data offsets to CutOut file from the archive by hands with HEX editor...
## Post #12
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-27T08:28:23+00:00
- Post Title: Burnout Paradise .BIN files. help!

thanks for the quick response.
so if I'm right I need to search for the .DDS  file info with a HEXeditor  

this is all I can see when I open a uncompressed junk using a hex editor.
## Post #13
- Username: Steefjan
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 26, 2009 8:33 pm
- Post datetime: 2009-07-27T13:06:21+00:00
- Post Title: Burnout Paradise .BIN files. help!

still can't find out how to use zlib...  
 I've tried everything! ..pff I've got hiliday but this just swallows my whole day up..



getting confused please can someone help me getting those DDS files out of the vehichletex.Bin..
## Post #14
- Username: rafal345
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Jun 07, 2010 2:24 am
- Post datetime: 2010-06-09T16:39:14+00:00
- Post Title: Burnout Paradise .BIN files. help!

Offzip also doesn't work on my computer, MultiEx too. I've got 64bit Vista. What should I do?

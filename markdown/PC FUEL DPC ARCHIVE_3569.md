## Post #1
- Username: demolos
- Rank: advanced
- Number of posts: 65
- Joined date: Mon Mar 12, 2007 10:38 pm
- Post datetime: 2009-07-08T18:02:34+00:00
- Post Title: PC FUEL DPC ARCHIVE

Hi,

I don't know how to read the archives from this game.

[http://www.2shared.com/file/6611977/c54 ... _fuel.html](http://www.2shared.com/file/6611977/c5499f3e/datas_fuel.html)

some files contain dds but without header DDS DXT...
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-07-09T21:30:12+00:00
- Post Title: PC FUEL DPC ARCHIVE

This MexScript will extract resource chunks from the archives.

```
GoTo 260 0 ;
Get FileNum Long 0 ;
GoTo 284 0 ;
Set FNS String "file" ;
Set EXT String ".bin" ;
Set OFF Long 2048 ;
For T = 1 To FileNum ;
Get U1 Long 0 ;
Get U2 Long 0 ;
Get PSize Long 0 ;
Get RSize Long 0 ;
Get U3 Long 0 ;
Get U4 Long 0 ;
Set FN String FNS ;
String FN += T ;
String FN += EXT ;
Log FN OFF RSize 0 0 ;
Math OFF += PSize ;
Next T ;

```


Here's the BMS file to add to your MultiEx Commander using the BMS->Add BMS to MRF... option in the tool.


 dpc.zip
(380 Bytes) Downloaded 141 times



There are still many unknowns, but the table at the front of the file is quite clear and points to these resources that you can extract. It is then up to you to see what these resources mean. 

The archives use a padding of 0x800. (2048) So, if a resource was only 2000 bytes in size, space would be reserved up to 2048 (so 48 trailing 0's) to accomodate the padding.
## Post #3
- Username: zeeh
- Rank: beginner
- Number of posts: 30
- Joined date: Sun Jul 26, 2009 9:10 am
- Post datetime: 2009-08-02T11:31:28+00:00
- Post Title: PC FUEL DPC ARCHIVE

I have extracted the fontes.dpc file and maybe there is some kind of compression (LZSS?).

[http://rapidshare.com/files/262823893/FONTES.rar.html](http://rapidshare.com/files/262823893/FONTES.rar.html)
## Post #4
- Username: klef
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jul 18, 2011 6:08 am
- Post datetime: 2011-07-17T22:41:37+00:00
- Post Title: PC FUEL DPC ARCHIVE

there are successes, but files "file *. bin"?

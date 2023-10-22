## Post #1
- Username: letoII
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 29, 2003 4:24 pm
- Post datetime: 2003-05-29T08:26:48+00:00
- Post Title: Syndicate wars

Do you know where i can find information on the syndicate wars storage format. If MultiEx cannot be modified to open the files, i can try programming the extractor myself.  If you know where i can find this kind of information msg me.
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-29T11:17:52+00:00
- Post Title: Syndicate wars

That's an old game! I will see if I can get a hold of it somewhere.
## Post #3
- Username: letoII
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu May 29, 2003 4:24 pm
- Post datetime: 2003-05-29T15:20:41+00:00
- Post Title: Syndicate wars

You can download it at 
[http://www.theunderdogs.cjb.net/](http://www.theunderdogs.cjb.net/)

You know a lot of file formats, do you just search for them or is there a resource site for this kind of stuff. I am surprised you even had one for ascendacy. I was looking for something to open those .cob files and just about gave up, until i stumbled upon your prog. Neat stuff, keep up good work.
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-29T15:24:02+00:00
- Post Title: Syndicate wars

Hmm... I downloaded a demo...just checking the sound.dat...looks promising.
## Post #5
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-30T09:37:52+00:00
- Post Title: Syndicate wars

Okay well, I am able to implement it in MultiEx Commander, at least the sound.dat. The format is something like this:

-ALL FILE DATA
-TAIL (WITH FILENAMES)

and at the back there's a pointer to the END of the tail, and is stored the SIZE of the tail. 

The thing is though, in the tail there are offsets.sizes of each individual file, that do not match the actual size of those files. That's weird.

I checked another .DAT file, and there the offsets and sizes DID correspond with the actual sizes and offsets.  

Meanwhile, this archive format is ONLY for the SOUND.DAT and SNDCRED.DAT. All the other files are stand-alone files and not really archives.
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-30T10:54:34+00:00
- Post Title: Syndicate wars

Ok this script is for SNDCREDS.DAT : use it in Mex3Scriptor to create a BMS file that you can use in MultiEx Commander. ("Run Custom BMS on...")

ImpType StandardTail ;
GoTo EOF 0 ;
SavePos TE 0 ;
Math TE -= 3 ;
GoTo TE 0 ;
Get TEND Long 0 ;
Math TE -= 52 ;
GoTo TE 0 ;
Get TS Long 0 ;
Math TEND -= TS ;
Math TEND += 32 ;
Set FN Long TS ;
Math FN /= 32 ;
Math FN -= 1 ;
GoTo TEND 0 ;
SavePos FST 0 ;
For T = 1 to FN ;
Get FNAME String 0 ;
Math FST += 18 ;
GoTo FST 0 ;
SavePos FOO 0 ;
Get FOFF Long 0 ;
Get D Long 0 ;
SavePos FSO 0 ;
Get FSIZE Long 0 ;
SavePos FST 0 ;
Math FST += 2 ;
GoTo FST 0 ;
Log FNAME FOFF FSIZE FOO FSO ;
Next T ;
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-05-30T11:07:10+00:00
- Post Title: Syndicate wars

Because the tail information does not fit the actual locations and sizes of the files in SOUND.DAT I can only give you this script to extract all the WAV files in there. They have noname, but just rename in *.WAV after you extracted them. 

Get S ASize 0 ;
For T = 1 To S ;
FindLoc B String RIFF 0 ;
GoTo B 0 ;
Get D Long 0 ;
Get FSI Long 0 ;
Math FSI += 8 ;
Set T Long B ;
Math T += FSI ;
Log "" B FSI 0 0 ;
Next T ;

Alternatively, you may rename the SOUND.DAT into SOUND.REZ and open it as a No One Lives Forever REZ file. That uses the same above script.

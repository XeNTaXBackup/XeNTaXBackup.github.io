## Post #1
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-07-08T20:18:01+00:00
- Post Title: Dance Dance Revolution Ultramix (XBox) *.SNG File

Hi there

I'm wondering if it is possible to extract the sound from an XBox *.SNG file.

I am guessing that this is the one that contains the music tracks. they are probably either mp3 or wma files...

Can you help? 

Oops.... file attachment!!

[http://talisman.clift.org/talismanisland/test/sng.rar](http://talisman.clift.org/talismanisland/test/sng.rar) 1500kb

Cheers for now
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-09T14:51:35+00:00
- Post Title: Dance Dance Revolution Ultramix (XBox) *.SNG File

Ok, try this custom script. 

I assume the files are MP3. I don't have a complete file so I can't test it fully. 

See below for BMS file, here's the script. 

Let me know if it works. 

```
Get FNum Long 0 ;
Set M String .MP3 ;
For T = 1 To FNum ;
GetDString FN 4 0 ;
String FN += M ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
Log FN FO FS FOO FSO ;
Next T ;

```

[sng.zip](https://xentaxbackup.github.io/file/343_sng.zip)
## Post #3
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-07-09T15:47:08+00:00
- Post Title: Dance Dance Revolution Ultramix (XBox) *.SNG File

Hi there

Well, the script works fine, but they aren't mp3 files...  

I can't work out what they are from looking into the file. Maybe someone knows?

Here is an example... rebi.rar

[http://talisman.clift.org/talismanislan ... x/rebi.rar](http://talisman.clift.org/talismanisland/test/multiex/rebi.rar)

Cheers for now

PS - There are another two files in the iso that seem to have the dance moves and backgrounds for these files. I shall post these after the music format has been discovered
## Post #4
- Username: KorNet
- Rank: VVIP member
- Number of posts: 444
- Joined date: Tue Apr 12, 2005 6:36 pm
- Post datetime: 2005-07-09T18:52:32+00:00
- Post Title: Dance Dance Revolution Ultramix (XBox) *.SNG File

Greetings. This archive means is ciphered + probably compressed... Not not sounds I there have not found schedules
## Post #5
- Username: Rusty_le_Cyborg
- Rank: advanced
- Number of posts: 48
- Joined date: Tue Jan 11, 2005 1:12 am
- Post datetime: 2005-07-11T17:57:28+00:00
- Post Title: Dance Dance Revolution Ultramix (XBox) *.SNG File

Could be some sort of PCM file though, but you have to use trial and error to find what to open it as... what a pain

## Post #1
- Username: phaseshift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 29, 2005 3:43 am
- Post datetime: 2005-08-28T19:53:22+00:00
- Post Title: Neocron PAK files

Could you possibly add support for Neocron PAK files?

I've attached a small (96kb) sample PAK file.

There's a 101mb demo available here:
[http://www.neocronnetwork.de/files/othe ... mo_eng.exe](http://www.neocronnetwork.de/files/other/neocron_offline_demo_eng.exe)

And a utility here:
Site: [http://www.geocities.com/d_evils_thrill/](http://www.geocities.com/d_evils_thrill/)
DL: [http://www.geocities.com/d_evils_thrill ... rowser.zip](http://www.geocities.com/d_evils_thrill/NcVFSBrowser.zip)
It can open the files, but only extracts sounds and images (a built-in restriction of the utility). It uses zlib.dll (if that's of any help).

Thanks for your help!  
[defs.zip](https://xentaxbackup.github.io/file/410_defs.zip)
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-28T21:24:49+00:00
- Post Title: Neocron PAK files

Thanks, our team will take a look at it!
## Post #3
- Username: PXR
- Rank: VIP member
- Number of posts: 61
- Joined date: Thu Mar 24, 2005 2:55 am
- Post datetime: 2005-08-29T11:18:37+00:00
- Post Title: Neocron PAK files

```
uint32 {4}   - Number of files


// FOR EACH FILE

uint32 {4}   - Length of this "fileblock"
uint32 {4}   - Absolute File Offset
uint32 {4}   - Compressed File Length
uint32 {4}   - Decompressed File Length
uint32 {4}   - Filename Length
byte   {x}   - Filename (null-terminated)

byte   {x}   - File Data
```


If "Compressed file Length"=="Decompressed File Length", then the file is not compressed.
If the filename contains one or more backslash, then the filename is actually a relative path.

I think that should be it...
## Post #4
- Username: Marvey
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Sep 03, 2003 8:12 pm
- Post datetime: 2005-08-29T16:14:53+00:00
- Post Title: Neocron PAK files

yeah i would like to have this too...
great one
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-30T12:25:05+00:00
- Post Title: Neocron PAK files

```
ComType ZLib1 ;
Get DATE Long 0 ;
Get FileNum Long 0 ;
For T = 1 to FileNum ;
Get BlSize Long 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos UCSO 0 ;
Get UCS Long 0 ;
Get FNS Long 0 ;
GetDString FN FNS 0 ;
CLog FN FO FS FOO FSO UCS UCSO ;
Next T ;

```


This is the script that should open that file. And perhaps more. It will however assume compression. You can also replace resources in there!

Just go to "Run custom script on...", select the pak.bms file (see below) and then select the .pak file of interest. You MUST add it to an MRF file using the MRF Manager if you wish to import. (Create a new one, then add the pak.bms file to it, specify game name as Neocron) and then set the new MRF file as Base. Now when you select open archive you will only see the Neocron PAK format. Better still, copy the mc.mrf file in the data/config dir to another location and choose to ADD that mrf file to the MRF Base. Then add the BMS to THAT file and choose to set it as Base. Then you have all PLUS the new (custom) script. Importation should work then!!
[pak.zip](https://xentaxbackup.github.io/file/415_pak.zip)
## Post #6
- Username: phaseshift
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Mon Aug 29, 2005 3:43 am
- Post datetime: 2005-08-31T03:01:52+00:00
- Post Title: Neocron PAK files

Works great. Thanks!

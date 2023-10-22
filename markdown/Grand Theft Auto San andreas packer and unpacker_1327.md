## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-06-16T11:51:41+00:00
- Post Title: Grand Theft Auto San andreas packer and unpacker

Here a differents files, the sfx and voices (i think are vorbis).
I upload it to rapidshare.de, 'coz the forum says "too big" and the files are 1 mb's.

[http://rapidshare.de/files/2419576/gta_ ... e.zip.html](http://rapidshare.de/files/2419576/gta_cutscene.zip.html)
and
[http://rapidshare.de/files/2419671/gta_sfxzip.zip.html](http://rapidshare.de/files/2419671/gta_sfxzip.zip.html)

Thaaanks
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-16T12:50:57+00:00
- Post Title: Grand Theft Auto San andreas packer and unpacker

```
Math FileNum -= 1 ;
For T = 1 To FileNum ;
Get Offset Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
SavePos J 0 ;
Get Size Long 0 ;
Math Size -= Offset ;
Log "" Offset Size 0 0 ;
GoTo J 0 ;
Next T ;
Get Offset Long 0 ;
GoTo EOF 0 ;
SavePos Size 0 ;
Math Size -= Offset ;
Log "" Offset Size 0 0 ;

```


That should extract from the sfxzip files. No idea about the compression that was used though. 

The cutscenes are not archives, at first glance.
[sfxzip.zip](https://xentaxbackup.github.io/file/286_sfxzip.zip)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-17T08:45:43+00:00
- Post Title: Grand Theft Auto San andreas packer and unpacker

Actually, I was an idiot and the script is not correct.

Here's the new one. 

```
Set Start Long 12 ;
Math Start *= FileNum ;
Set D Long 480 ;
Set DD Long Start ;
Math DD /= D ;
Math DD *= 480 ;
If DD < Start ;
Math DD += 480 ;
Set Start Long DD ;
EndIf ;
Math FileNum -= 1 ;
SavePos ST 0 ;
Math ST += Start ;
For T = 1 To FileNum ;
Get Offset Long 0 ;
Get D Long 0 ;
Get D Long 0 ;
SavePos J 0 ;
Get Size Long 0 ;
Math Size -= Offset ;
Math Offset += ST ;
Log "" Offset Size 0 0 ;
GoTo J 0 ;
Next T ;
Get Offset Long 0 ;
GoTo EOF 0 ;
SavePos Size 0 ;
Math Offset += ST ;
Math Size -= Offset ;
Log "" Offset Size 0 0 ;

```


Looks like there's some padding to 480 byte chunks is going on in the resource info header.
[sfxzip.zip](https://xentaxbackup.github.io/file/290_sfxzip.zip)

## Post #1
- Username: guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-14T15:17:54+00:00
- Post Title: playboy

Can u add support for xbxo playboy:the mansion's .cam files
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-15T14:59:19+00:00
- Post Title: playboy

The structure of this game is...

```
| Playboy: The Mansion *.cam |
+----------------------------+

8 - Header (CYLBPC  )
2 - Version Main (2)
2 - Version Sub (1)
4 - Number Of File Types

// for each file type
  4 - Size of the directory for this file type [+8] (including these 4 fields)
  4 - File Type Description (WAVE)
  4 - Size of each file entry (28) (OLD!)
  4 - Number Of Files of this type
  4 - null

  // for each file of this type
    4 - Filename? File ID?
    4 - File Offset
    4 - File Size
    4 - null
    
X - File Data
```


It is an updated version of a format used in some other games, thus the reason why I wrote OLD next to one of the fields. This field use to be the size of each file entry, but obviously it no longer has any affect.

Not sure whether Mr Mouse might be able to knock up a script for this? - I'm a little too busy at the moment. Otherwise, give me a few days and hopefully I will be able to make something for you.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-15T22:07:05+00:00
- Post Title: playboy

I will see. Time's not on my hands as well.
## Post #4
- Username: t_mac_ca
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 27, 2005 10:23 am
- Post datetime: 2005-05-27T02:24:15+00:00
- Post Title: playboy

Any progress on this game yet???
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-27T02:27:06+00:00
- Post Title: playboy

Hi there,

Well if you have Game Extractor (Full Version) then you can open these files. I don't think there is a MexCom script though yet.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-27T06:26:29+00:00
- Post Title: playboy

I do not have .cam files. Thus, I can't examine them. I could write a script based on those specs, but that would be tricky. 

I will see what I can do. Read the link to the thread in my signature how to add parts of those files to a thread so I can take a look at them.
## Post #7
- Username: t_mac_ca
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Fri May 27, 2005 10:23 am
- Post datetime: 2005-05-27T14:07:15+00:00
- Post Title: playboy

here is a .cam file for playboy the mansion.
[Playboymansion .rar](https://xentaxbackup.github.io/file/268_Playboymansion .rar)
## Post #8
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-27T14:17:31+00:00
- Post Title: playboy

Just for clarification Mr Mouse, I didn't get the Playboy files from that guy either - someone else a few weeks prior sent me a bunch of games to analyse and Playboy was one of them.

Just thought I should clarify that just incase you thought I got files over email without you getting them too.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-11T10:54:20+00:00
- Post Title: playboy

Okay, here's a script you can use in MultiEx Commander to open .CAM files. This will also enable importation (wait until I update the webdatabase for that part). 

```
IDString 0 CYLBPC ;
Get V Int 0 ;
Get V Int 0 ;
Get V Int 0 ;
Get FT Long 0 ;
For T = 1 To FT ;
Get DS Long 0 ;
Set EXTE String . ;
GetDString EXT 4 0 ;
String EXTE += EXT ;
Get ES Long 0 ;
Get FNum Long 0 ;
Get D Long 0 ;
Set U Long 1 ;
Do ;
GetDString FName 4 0 ;
String FName += EXTE ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get D Long 0 ;
Log FName FO FS FOO FSO ;
Math U += 1 ;
While U <= FNum ;
Next T ;

```


I used it on the cam file above. That actually had standard BMP files in there. Note however, that the files are extracted as PICT files, that are in a different format than the ones supported by my PICT2BMP. 

( [viewtopic.php?p=9778#9778](http://forum.xentax.com/viewtopic.php?p=9778#9778) )

Furthermore, the files are BMP files, but preceded by a 32-bit value (4 bytes)  of 8. This might be a file-type (pict type) denoter. Remove it to get the correct BMP format. I could have done this in-script, but I don't have other examples of cam files, with multiple file types etc. to check if it is common only for BMPs. 

Get the .bms script here:
[cam.zip](https://xentaxbackup.github.io/file/350_cam.zip)

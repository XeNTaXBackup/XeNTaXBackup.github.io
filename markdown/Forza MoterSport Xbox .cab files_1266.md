## Post #1
- Username: UnReAlMaCk!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-22T07:25:11+00:00
- Post Title: Forza MoterSport Xbox .cab files

ummm im gonna host the cab to a car, could you make a script or somethin for this? their only like 2 mb
## Post #2
- Username: UnReAlMaCk
- Rank: VIP member
- Number of posts: 15
- Joined date: Thu May 05, 2005 5:46 am
- Post datetime: 2005-05-22T07:33:37+00:00
- Post Title: Forza MoterSport Xbox .cab files

ok heres the .cab!

[http://uploadhut.com/view.php/121992.cab](http://uploadhut.com/view.php/121992.cab)

its really called car_dodgechallenger.cab, not 121992.cab if that helps
## Post #3
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2005-05-23T03:01:46+00:00
- Post Title: Forza MoterSport Xbox .cab files

And once you unpack the cab file, then unpack the Zlib files it contains you end up with absolutely nothing.  That cab file along with all those other cab files are placeholder files.  The structure of the cab files can be figured out from the file you gave, but it has absolutely nothing inside it.  

So basically, any cab that has a car name in it is worthless to unpack, just so you know ahead of time.  

It's the .ca2 files and the .cab files without a car name that you want to check out.
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T09:57:01+00:00
- Post Title: Forza MoterSport Xbox .cab files

Alright, here is a plugin for you. Will work with Game Extractor (Basic Version), but there will be problems with the decompression (it doesn't extract the files fully). If you have Game Extractor full version, email me and I will send you the better plugin, with correct decompression.

Enjoy.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_CAB.zip](https://xentaxbackup.github.io/file/245_Plugin_CAB.zip)
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T10:59:14+00:00
- Post Title: Forza MoterSport Xbox .cab files

And a MexCom script for this game too, but Mr Mouse can you please check the script because it uses compression and I havn't done a script with compression before.

```
ComType ZLib1 ;
GoTo 8 0 ;
Get FNum Long 0 ;
GoTo 24 0 ;
Get FNDir Long 0 ;
GoTo 306 0 ;
For n = 1 to FNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos DFSO 0 ;
Get DFS Long 0 ;
SavePos NextJump 0 ;
Math NextJump += 12 ;
GoTo FNDir 0 ;
Get FN String 0 ;
SavePos FNDir 0 ;
GoTo NextJump 0 ;
CLog FN FO FOO FS FSO DFS DFSO ;
Next n ;

```


And also a compiled script is attached.

Good luck.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[cab.zip](https://xentaxbackup.github.io/file/250_cab.zip)
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-23T12:05:07+00:00
- Post Title: Forza MoterSport Xbox .cab files

I have updated it, as there were a few bugs. 

Anyway, I have added it to the mc.mrf that is now available from the web. 
Import is working as well. 

MexCom users: update from within MexCom (Web)

Or wait until the new release is out. 

The script:

```
ComType ZLib1 ;
GoTo 8 0 ;
Get FNum Long 0 ;
GoTo 24 0 ;
Set FNDir Long 24 ;
GoTo 306 0 ;
Math FNDir *= FNum ;
Math FNDir += 306 ;
For n = 1 To FNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
SavePos DFSO 0 ;
Get DFS Long 0 ;
SavePos NextJump 0 ;
Math NextJump += 12 ;
GoTo FNDir 0 ;
Get FN String 0 ;
SavePos FNDir 0 ;
GoTo NextJump 0 ;
CLog FN FO FS FOO FSO DFS DFSO ;
Next n ;

```
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-23T22:49:43+00:00
- Post Title: Forza MoterSport Xbox .cab files

Ok excellent, thanks for checking it out.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: UnReAlMaCk!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-24T00:22:36+00:00
- Post Title: Forza MoterSport Xbox .cab files

thx guys!

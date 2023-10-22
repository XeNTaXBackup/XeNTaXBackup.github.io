## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-05-28T06:23:40+00:00
- Post Title: Still Life

hello

I have new request : Still life game,archives *.sl

thank you
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-06-04T21:19:42+00:00
- Post Title: Still Life

I'm interessed for the unpacker and packer for this game as well.
Ein?
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-06-05T04:52:04+00:00
- Post Title: Still Life

Support for this game is already available in Game Extractor (Full Version).

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-06-05T11:37:16+00:00
- Post Title: Still Life

```
IDString 0 VXBG ;
Get DirSize Long 0 ;
Set MaxSize Long 8 ;
Math MaxSize += DirSize ;
Set FO Long MaxSize ;
Do ;
Get FN String 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
SavePos CO 0 ;
While CO < MaxSize ;

```


This script will enable import as well. You can get it from the Web update option in MultiEx Commander.  Or use the custom bms option.

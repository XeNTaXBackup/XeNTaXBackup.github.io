## Post #1
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2013-03-05T04:11:47+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

Information about this game:[http://lh.x-legend.com.tw/](http://lh.x-legend.com.tw/)
Sample included here:
[http://www.mediafire.com/download.php?ht9kykpxuwkbc33](http://www.mediafire.com/download.php?ht9kykpxuwkbc33)
[http://www.mediafire.com/download.php?p48xizqqb4qo4ol](http://www.mediafire.com/download.php?p48xizqqb4qo4ol)
[http://www.mediafire.com/download.php?pep588nfgpcg7vn](http://www.mediafire.com/download.php?pep588nfgpcg7vn)
[http://www.mediafire.com/download.php?evtttmktnftzdma](http://www.mediafire.com/download.php?evtttmktnftzdma)
Thank!!!
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-05T17:55:06+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

I don't know what the game is about but I liked the girl with the blades so I will look at these.
## Post #3
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-06T02:10:35+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

Can't get past the archives
## Post #4
- Username: Spira1&He1ix
- Rank: beginner
- Number of posts: 20
- Joined date: Sun Jun 24, 2012 11:44 pm
- Post datetime: 2013-03-08T15:45:24+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

So this is your bad new!!!But may be i have good new,i saw the patch update use .nif file when it's downloading content to zip it!!!Hope someone will by bass this broblem
## Post #5
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-08T22:44:06+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

just run offzip on the files.
you will get nifs with the header
Gamebryo File Format, Version 20.3.0.9
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-08T23:06:21+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

Well at least we know it's zip compression lol
## Post #7
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-08T23:08:42+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

the textures are embedded in the nif files so names don't do much anyway. and the nif format is to new to be supported so archive extraction wont do any more then offzip does.
## Post #8
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-08T23:51:35+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

yeah always look for an 0x?8 followed by some number and then run this test. usually it's almost always 0x78 but sometimes i've seen 0x58.

```
{
 // first byte check
 if(b1 == 0x18) ;
 else if(b1 == 0x28) ;
 else if(b1 == 0x38) ;
 else if(b1 == 0x48) ;
 else if(b1 == 0x58) ;
 else if(b1 == 0x68) ;
 else if(b1 == 0x78) ;
 else return false;

 // second byte check
 uint32 u1 = (uint32)b1;
 uint32 u2 = (uint32)b2;
 return ((u1*256 + u2) % 31) == 0;
}

```
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2013-03-09T01:01:54+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

I have self-proclaimed filename OCD and require all my files to be nicely named   

Guess I should take an hour or two to figure out how nif.xml works...I mean, presumably it's just a matter of adding a couple extra lines to the specs to map out the format of these new chunks.
## Post #10
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-03-09T01:46:31+00:00
- Post Title: Plz help get 3d model from Pride of Soul!!!

yeah i wanted to do the same thing never got around to it.

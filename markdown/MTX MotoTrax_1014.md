## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-12-10T20:40:43+00:00
- Post Title: MTX MotoTrax

hello

I need extractor for wad arrchive
please help me

thx
## Post #2
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2004-12-11T15:36:03+00:00
- Post Title: MTX MotoTrax

check the header of file..you'll see BIK...

look for radgametools dot com for the binkplayer and you'll hear your samples...

cya
## Post #3
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2004-12-11T21:01:07+00:00
- Post Title: MTX MotoTrax

this is package include biks but i need extractor for extract biks with file name
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-09T22:12:51+00:00
- Post Title: MTX MotoTrax

Well, I created a small script that will do it. 

> Do ;
>
> FindLoc OFF String BIK 0 ;
>
> Set JP Long OFF ;
>
> Math JP += 4 ;
>
> GoTo JP 0 ;
>
> Get SIZE Long 0 ;
>
> Math SIZE += 4 ;
>
> Log "" OFF SIZE 0 0 ;
>
> While NotEOF <> 0 ;

And saved it in a custom MRF file, that you can use to overwrite the one in MultiEx Commander's data/config directory. (BACK-UP the old one, just in case). 

Get the attached file. Also note that [http://www.necrotech.de/](http://www.necrotech.de/) have a nice tool that will also do this for you.
[mc.zip](https://xentaxbackup.github.io/file/91_mc.zip)
## Post #5
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-01-11T16:13:38+00:00
- Post Title: MTX MotoTrax

thank you mr mouse

but not extractor correct file name

i need correct file name

thx again
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-01-11T16:29:12+00:00
- Post Title: MTX MotoTrax

I'm sorry, but there are no filenames saved in the archive you attached. All the BIK files are in there without filenames.

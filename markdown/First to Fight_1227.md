## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-05-08T20:12:01+00:00
- Post Title: First to Fight

hello

iam back with new file (request)
please see First to Fight package
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-08T23:42:25+00:00
- Post Title: First to Fight

Ah, I like the easy ones 

```
| First To Fight *.pwb |
+----------------------+

4 - Number Of Files

// for each file
  4 - File Offset

X - File Data
```


I will try to get the script done when I get home in a few hours

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-09T12:03:03+00:00
- Post Title: First to Fight

Here we are...

```
Math FNum -= 1 ;
For n = 1 to FNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos JP 0 ;
Get FS Long 0 ;
Log " FO FS FOO 0 ;
GoTo JP 0 ;
Next n ;
SavePos FOO 0 ;
Get FO Long 0 ;
GoTo EOF 0 ;
SavePos FS 0 ;
Math FS -= FO ;
Log "" FO FS FOO 0 ;

```


Or just grab the compiled script below.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[pwb.zip](https://xentaxbackup.github.io/file/217_pwb.zip)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-09T13:44:46+00:00
- Post Title: First to Fight

Nice work!
## Post #5
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-05-09T21:01:40+00:00
- Post Title: First to Fight

hello

good work

but not completed

because open file but incorrect file name
## Post #6
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-09T23:42:01+00:00
- Post Title: First to Fight

There are no filenames in this archive, at least none that I noticed at first glance.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #7
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-05-10T17:51:31+00:00
- Post Title: First to Fight

mr mouse and mr watto

iam send complete arrchive to mail you
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-10T17:59:04+00:00
- Post Title: First to Fight

Thanks for the file, Sajad! But I also did not see any filenames in there!  They just saved the sounds without filenames.
## Post #9
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-10T18:18:07+00:00
- Post Title: First to Fight

By the way, there was a small bug in the script. 

In the looped section, FS was not corrected  (missing Math FS -= FO ; statement)

```
Math FNum -= 1 ;
Set FEX String .WAV ;
For n = 1 To FNum ;
SavePos FOO 0 ;
Get FO Long 0 ;
SavePos JP 0 ;
Get FS Long 0 ;
Math FS -= FO ;
Set FN String Wave ;
String FN += n ;
String FN += FEX ;
Log FN FO FS FOO 0 ;
GoTo JP 0 ;
Next n ;
Math n += 1 ;
SavePos FOO 0 ;
Get FO Long 0 ;
GoTo EOF 0 ;
SavePos FS 0 ;
Math FS -= FO ;
Set FN String Wave ;
String FN += n ;
String FN += FEX ;
Log FN FO FS FOO 0 ;

```


I also included the new string functions so files now have the Wavennn.wav names. 

Please try that with the new Commander on these files! I hope it works! 

Damn, I will have to release the new Binder soon.
[pwb_names.zip](https://xentaxbackup.github.io/file/219_pwb_names.zip)
## Post #10
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-11T02:18:56+00:00
- Post Title: First to Fight

Excellent Mr Mouse! I hope you are documenting the new features in the scriptor like this filename thingy!

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)

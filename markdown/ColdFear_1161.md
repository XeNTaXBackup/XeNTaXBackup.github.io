## Post #1
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-07T21:33:58+00:00
- Post Title: ColdFear

hello again

please look file below
this is file coldfear game

thanks
## Post #2
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-08T01:17:17+00:00
- Post Title: ColdFear

This is a slight variation on the FSB format used in NRL 2003. Here is the update...

```
4 - Number Of Files
4 - Directory Length
4 - Data Length
4 - Unknown
4 - null

// for each file
  2 - Entry Length (80)
  30 - Filename
  4 - soundLengthWithHeader?
  4 - Compressed Length (SIZE IN ARCHIVE)
  4 - null
  4 - soundLengthWithoutHeader?
  32 - Sound Header Information (bit rates etc.)
```


The only real difference is that each file entry has an additional 16 bytes of data at the end. But, as with the original format, the files are like compressed or encrypted or something, so you won't have any benifit from opening them. Oh, and the field names/descriptions in the code above are not all that correct - I was experimenting with purposes in the past.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-08T05:49:09+00:00
- Post Title: ColdFear

Nice.
## Post #4
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-08T15:13:03+00:00
- Post Title: ColdFear

please look below file
## Post #5
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-10T03:57:06+00:00
- Post Title: ColdFear

OK, here is the script...

```
Get FNum Long 0 ;
Get FO Long 0 ;
Math FO += 24 ;
Get DataLen Long 0 ;
Get Dummy1 Long 0 ;
Get DummyNull Long 0 ;
For n = 1 to FNum ;
SavePos Start 0 ;
Get EntryLen Int 0 ;
Math Start += EntryLen ;
SavePos EndFN 0 ;
Math EndFN += 34 ;
Get FN String 0 ;
GoTo EndFN 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
GoTo Start 0 ;
Log FN FO FS 0 FSO ;
Math FO += FS ;
Next n ;

```


And I have attached a compiled script. Please don't expect it to work very well though, because the files in these archives are compressed or encrypted or something 

Oh, Mr Mouse, this script should also work for the game NRL 2003, so you can add 2 games into your supported list.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[FSB.zip](https://xentaxbackup.github.io/file/166_FSB.zip)
## Post #6
- Username: sajad
- Rank: VIP member
- Number of posts: 128
- Joined date: Fri May 14, 2004 8:20 pm
- Post datetime: 2005-04-10T19:36:12+00:00
- Post Title: ColdFear

hi

thanks mr watto

iam test script 

but when extracting show error message "file error encountered"

and some files...

show error when extracting below files
[coldfear.JPG](https://xentaxbackup.github.io/file/170_coldfear.JPG)
## Post #7
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-11T05:12:43+00:00
- Post Title: ColdFear

OK, but this error can not be fixed at the moment (Mr Mouse, please confirm this)

The problem is that some filenames are cut off if they are too long, and others have junk added at the end if they are too short. I don think MexCom can read non-null terminated strings?

Sorry about that.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #8
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-11T05:49:30+00:00
- Post Title: ColdFear

Well, if theay are of fixed length you can use GetDString (get Determined-size string). 

Like:
GetDString FileName 30 ; 

Get a string of 30 in length.

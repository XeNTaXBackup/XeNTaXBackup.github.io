## Post #1
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-26T22:10:06+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

I think it's easy, i don't found compression.
I send a small file, like example.
All game it's this structure:
Data\Fonts\fonts.pkf
       Sounds\Sounds.pkf etc....

Thanks in advance
[Messages.zip](https://xentaxbackup.github.io/file/192_Messages.zip)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-29T12:26:03+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

Nobody  know this?
## Post #3
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-29T13:14:56+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

Yes, and it's easy. 

```
uint32		Number of files

[FILE-INFO]
string_256	Full path of original file (string of 256 characters)
string_256	Filename (string of 256 characters)
uint32		Absolute offset of file in archive
uint32		unknown (0) : perhaps compression yes/no (0 = no)
uint32 		Size of file in bytes (perhaps un/compressed size)
uint32		Size of file in bytes (perhaps un/compressed size)

[FILE-DATA]

```
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-30T02:44:54+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

Alright, here is the script...

```
Get FNum Long 0 ;
For n = 1 to FNum ;
SavePos JP 0 ;
Math JP += 256 ;
GoTo JP 0 ;
Get FN String 0 ;
Math JP += 256 ;
GoTo JP 0 ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get Dummy Long 0 ;
SavePos FSO 0 ;
Get FS Long 0 ;
Get Dummy Long 0 ;
Log FN FO FS FOO FSO ;
Next n ;

```


Or just grab the attached compiled script. Use it by going to Tools-->Use Custom Script

Note that I havn't tested the script on any of the actual archives though, so it could be buggy.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[PKF.zip](https://xentaxbackup.github.io/file/204_PKF.zip)
## Post #5
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2005-04-30T09:17:44+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

How i can test the compiled script?
If i open the Gamex and tools>Run script custom, open a windows to make a registration and can't continue.

It'a another way to test the script's? And of course soon i pay the 5$ for this great program
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-30T09:26:27+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

There's a lot of blood, sweat and tears gone into the program....That's why such nice functionality is for Friends of MultiEx only.
## Post #7
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2005-05-01T13:40:06+00:00
- Post Title: Packer and unpacker for Wanted guns (.pkf format)

and dont expect to find a crack for a such nice tool! 

at least for now..i've seen cardware cracked times ago...

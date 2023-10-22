## Post #1
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-19T07:28:05+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

Hi! all
Please, I need help
How to unpack HexaSuper viewer files?
[http://www.mediafire.com/?so1v91jjy12851v](http://www.mediafire.com/?so1v91jjy12851v)

Thanks in advance!
## Post #2
- Username: SirLoon
- Rank: advanced
- Number of posts: 45
- Joined date: Sat Dec 19, 2009 12:26 am
- Post datetime: 2011-08-19T08:17:09+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

> Reply from youngmark
>
> Hi! all
Please, I need help
How to unpack HexaSuper viewer files?
http://www.mediafire.com/?so1v91jjy12851v

Thanks in advance!
Do you mean 7z or exe files inside? 
(sorry i dont have sandboxie installed so i wont run those exe files   )
## Post #3
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-19T09:09:22+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

> Reply from SirLoon
>
> youngmark wrote:Hi! all
Please, I need help
How to unpack HexaSuper viewer files?
http://www.mediafire.com/?so1v91jjy12851v

Thanks in advance!
Do you mean 7z or exe files inside? 
(sorry i dont have sandboxie installed so i wont run those exe files   )

Double click on the *.exe to start the HexaSuper viewer program
## Post #4
- Username: Ares722
- Rank: veteran
- Number of posts: 154
- Joined date: Thu Jul 15, 2010 9:15 pm
- Post datetime: 2011-08-19T10:30:22+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

These models are really high detailed , Can i ask you where did you find them?
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T12:36:39+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

unpack "viewer" data?
What kind of viewer is that?
## Post #6
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-19T12:42:50+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

> Reply from finale00
>
> unpack "viewer" data?
What kind of viewer is that?
六角大王Super is 3D polygon modeling software for 3D computer graphics.
Made by Japan
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-19T18:54:34+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

So they can build a 3D model and then export it as a stand-alone viewer so anyone can look at it without having the program? o.O
## Post #8
- Username: Falo
- Rank: advanced
- Number of posts: 78
- Joined date: Fri Oct 23, 2009 8:29 pm
- Post datetime: 2011-08-19T20:12:39+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

here a quickbms script to unpack both exe files:

```

get sig short #V6
get numFiles short
get fileSize long
get fileptr long #offset from start of exe file, same as overlay offset

for x = 1 to numFiles

get type short
get fnmbr short
get Size long
get Offset long

math Offset += fileptr

if type = 0x5636
   set Name "rokview\data.6kt"
elif type = 0x5641
   set Name "rokview\anime"
   string Name += fnmbr
   string Name += ".6kw"
elif type = 0x5642
   set Name "rokview\button.bmp"
elif type = 0x5644
   set Name "rokview\def.txt"
elif type = 0x5650
   set Name "rokview\pose"
   string Name += fnmbr
   string Name += ".6kw"
elif type = 0x5654
   set Name "rokview\data"
   string Name += fnmbr
   string Name += ".JPG"
else
   set Name "rokview\\"
   string Name += x
   string Name += ".unk"
endif

if Size > 0 #skip dummys
   log Name Offset Size
endif

next x
```


the extracted data.6kt should be openable with HexaSuper6.
## Post #9
- Username: youngmark
- Rank: veteran
- Number of posts: 145
- Joined date: Thu Sep 02, 2010 8:38 pm
- Post datetime: 2011-08-20T10:20:32+00:00
- Post Title: HexaSuper(六角大王Super) viewer file

> Reply from Falo
>
> here a quickbms script to unpack both exe files:
Code: Select allgoto 0x181000 # start of overlay

get sig short #V6
get numFiles short
get fileSize long
get fileptr long #offset from start of exe file, same as overlay offset

for x = 1 to numFiles

get type short
get fnmbr short
get Size long
get Offset long

math Offset += fileptr

if type = 0x5636
   set Name "rokview\data.6kt"
elif type = 0x5641
   set Name "rokview\anime"
   string Name += fnmbr
   string Name += ".6kw"
elif type = 0x5642
   set Name "rokview\button.bmp"
elif type = 0x5644
   set Name "rokview\def.txt"
elif type = 0x5650
   set Name "rokview\pose"
   string Name += fnmbr
   string Name += ".6kw"
elif type = 0x5654
   set Name "rokview\data"
   string Name += fnmbr
   string Name += ".JPG"
else
   set Name "rokview\\"
   string Name += x
   string Name += ".unk"
endif

if Size > 0 #skip dummys
   log Name Offset Size
endif

next x

the extracted data.6kt should be openable with HexaSuper6.
Thanks for your help.
But, 6kt file is locked.
How to unlock 6kt files?

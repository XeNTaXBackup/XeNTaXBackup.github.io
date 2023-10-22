## Post #1
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2013-06-04T02:16:10+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

I've uploaded it to mediafire. I'd like to edit these files at will. But lack the knowledge to do so. Plainly put, I'm a beginner. I normally just find something and change numbers when I mod. haha. 

there may possibly be a chance that this is in a different language as well. But I can't be sure since I'm pretty much retarded when it comes to this.

I'm trying to edit some values on some vehicles but when I try to open these .XML files I get jibberish. If you could find a way to edit them, and teach me how I would be more then happy. 

The files are found from this game. It's not out yet, but there's a demo. And would like to get a headstart on the release.

```
http://www.kickstarter.com/projects/358753914/spintires-the-ultimate-off-road-challenge 
```


```

http://www.mediafire.com/view/7aazndrso0qqaff/maz.xml
```
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2013-06-05T07:41:53+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

The files are encoded with a simple algorithm. Here is the code of the decoder function (in Delphi):

```
Var I : Integer;
    p : ^Byte;
    B : Byte;
Begin
  p := pBuffer;
  For I := 0 To BufferSize - 1 Do
    Begin
      B := 251 - (I * 14);
      p^ := p^ + B;
      Inc(p);
    End;
End;

```
## Post #3
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2013-06-05T21:47:30+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

so is it a big deal that you figured that out? Because I couldn't have ever. Probably something easy for you though  

I'm unsure of what to do though with this.. Like I said I'm a noob with this stuff. I switched over to pc gaming for modding alone. I'm still trying to figure a lot of things out. Is there any way you could give me a step by step way to edit this file and get it to work in game? 

Things like:

How do I edit this file? My lack of knowledge on this stuff is crazy.. But I'm hoping someone can teach me a few things.

If I somehow manage to decode this file, do I edit, and then need to re-encode it for it to work in game? 

Is delphi a program I need for this?

Also, thank you bactor for taking the time to look at the files.
## Post #4
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-06-06T09:37:06+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

> Reply from bacter
>
> The files are encoded with a simple algorithm. Here is the code of the decoder function (in Delphi):
Code: Select allProcedure SpinTires_Decoder(pBuffer : Pointer;BufferSize : Integer);
Var I : Integer;
    p : ^Byte;
    B : Byte;
Begin
  p := pBuffer;
  For I := 0 To BufferSize - 1 Do
    Begin
      B := 251 - (I * 14);
      p^ := p^ + B;
      Inc(p);
    End;
End;

I'm trying to implement your code in c# but having never coded in delphi I'm having a hard time understanding what it's doing.
As far as I can tell for each byte in the file you are  taking 251 then subtracting the current offset (I) and * by 14 and adding this to the original byte value? 
Unless I've missed something I'm not sure how this would work as the value is almost always going to be less than 0 and therefor less than Byte.MinValue?
## Post #5
- Username: octaviousrex
- Rank: veteran
- Number of posts: 109
- Joined date: Mon May 06, 2013 9:58 pm
- Post datetime: 2013-06-06T09:38:40+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

I threw it into both 3d studio max and or deep hemisphere 3D file format converter and I cannot seem to open it into either though it is an .xml file format. I have the demo myself and I like the game a lot. I am also looking at modding for this game in the future. sorry I am not more help yet. but I'll keep seeing what I can do on my end.
## Post #6
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2013-06-06T18:54:27+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

Yeah, it's definitely got me stumped. Glad to see some more posts about it. The game is heavy under development, but it'd be great to see it with mods early at release. This game has a very innovative design and I know after the community gets a hold of it it will be more then fun to play. The developer says he wants to support modding, but it's already seeming very difficult to even read the xml files.
## Post #7
- Username: figuare9
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2013-06-06T22:42:05+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

quickbms script to convert these files

```
string name + .xml
get size asize
set MEMORY_FILE binary ""
for i = 0 < size
set b i
math b * 14
set c 251
math c - b
get tmp byte
math tmp + c
math tmp & 0xFF
putVarChr MEMORY_FILE i tmp byte
next i
log name 0 size MEMORY_FILE

```

[http://pastebin.com/uRds30Zp](http://pastebin.com/uRds30Zp)
## Post #8
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2013-06-07T08:20:28+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

Haven't tested it in game but put together a simple decode/encode app that should do the job, creds to chrrox for the decode algo. 

[http://www.mediafire.com/?ru9nu9ti7x69ao7](http://www.mediafire.com/?ru9nu9ti7x69ao7)
## Post #9
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2013-06-07T20:28:38+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

All of you guys are awesome!! Many thanks.
## Post #10
- Username: figuare9
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 01, 2010 2:39 pm
- Post datetime: 2013-06-07T21:49:41+00:00
- Post Title: Stumped on a simple XML file in Spin Tires game. (SOLUTION)

> Reply from twisted
>
> Haven't tested it in game but put together a simple decode/encode app that should do the job, creds to chrrox for the decode algo. 

http://www.mediafire.com/?ru9nu9ti7x69ao7

Tested on 0606 Build (Latest) and it's working

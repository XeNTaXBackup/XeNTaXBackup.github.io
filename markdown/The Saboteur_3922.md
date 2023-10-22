## Post #1
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-12-04T12:47:52+00:00
- Post Title: The Saboteur

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-12-04T19:08:09+00:00
- Post Title: The Saboteur

Double-post.
## Post #3
- Username: GameZelda
- Rank: advanced
- Number of posts: 61
- Joined date: Thu Nov 15, 2007 12:56 am
- Post datetime: 2009-12-04T19:08:46+00:00
- Post Title: The Saboteur

```
{
    uint32_t unk1;
    uint32_t unk2; // Number of sections?
    uint32_t unk3;
    DLGSection[] sections;
}

struct DLGSection
{
    char type[4]; // "TXTD" for string sections, "DNEC" for the last section;
    if type == "TXTD"
    {
        uint unk; // ID?
        ushort textNameLen;
        char[textNameLen] textName;
        ushort textLen;
        wchar[textLen] text;
    }
}

```
## Post #4
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-12-04T20:26:11+00:00
- Post Title: The Saboteur

With what can I open it up? Program name?
## Post #5
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-04T21:32:03+00:00
- Post Title: The Saboteur

I ported Zeldas Struct to an quickbms script, but i doesnt work perfect because of the "DNEC" Type.

```

Get Unknown1 Long
Get Unknown2 Long
Get Unknown3 Long


Do
	GetDString Type 4
	
#	Print "Section %Type%"

	If Type == "TXTD"
		Get Unk Long
		
		Get TextNameLen Short		
		GetDString TextName TextNameLen
		
		
#		Print "TextNameLen: %TextNameLen% TextName: %TextName%"
		
		Get TextLen Short
		Math TextLen *= 2
		Math TextLen -= 2 # strip last 00 00
		
		SavePos CurrentOffset
		
		Log TextName CurrentOffset TextLen
		
		Math TextLen += 2
		Math CurrentOffset += TextLen
		
		Goto CurrentOffset
		
#		GetDString Text TextLen
		
#		 Print "TextLen: %TextLen% Text: %Text%"
		
	Else If Type == "DENC"
		Get Unk Long
		Get Unk Long
	Else
		print "Unkown Type: %Type%"
	Endif
	
While 1 = 1

```
## Post #6
- Username: nightvison
- Rank: beginner
- Number of posts: 35
- Joined date: Tue Oct 20, 2009 2:35 pm
- Post datetime: 2009-12-19T08:46:54+00:00
- Post Title: The Saboteur

Any idea? (unpack and repack)
## Post #7
- Username: Piedon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 10, 2007 2:03 am
- Post datetime: 2009-12-29T13:06:07+00:00
- Post Title: The Saboteur

> Reply from evilpie
>
> I ported Zeldas Struct to an quickbms script, but i doesnt work perfect because of the "DNEC" Type.
There is a mistake in it. 

"Else If Type == "DENC"" It is not DENC, but DNEC.
## Post #8
- Username: oyunceviri
- Rank: advanced
- Number of posts: 75
- Joined date: Tue Jun 30, 2009 6:35 pm
- Post datetime: 2010-01-22T11:05:37+00:00
- Post Title: The Saboteur

The contents of this post was deleted because of possible forum rules violation.
## Post #9
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-04-30T15:06:23+00:00
- Post Title: The Saboteur

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2011-05-09T19:27:25+00:00
- Post Title: The Saboteur

Someone can help me, the ps3 is endians file....
## Post #11
- Username: badboytm25
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 13, 2012 4:38 pm
- Post datetime: 2012-03-04T14:15:07+00:00
- Post Title: The Saboteur

please can you help me with ps3 dlg file ???

I need extract it - translate and then repack.

Here is this file

Thanks a lot

BBTM
[gametext.rar](https://xentaxbackup.github.io/file/5138_gametext.rar)
## Post #12
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-03-05T20:16:06+00:00
- Post Title: The Saboteur

Can anyone help with the files on PS3, please.
[gametext.rar](https://xentaxbackup.github.io/file/5147_gametext.rar)

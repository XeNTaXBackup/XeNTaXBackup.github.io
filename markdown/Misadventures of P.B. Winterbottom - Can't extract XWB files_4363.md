## Post #1
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-21T09:42:36+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-22T09:41:41+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

I managed to extract the music with unxwb.
It didn't work via drag&drop, but when I used the command line tool it worked.
Is there any way to read the .xsb file and name the titles correctly while extracting?
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-04-23T17:05:22+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

unxwb doesn't support the reading of filenames from the optional xsb files because their format was too much chaotic for being able to write something "universal".
## Post #4
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-23T17:14:16+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

> Reply from aluigi
>
> unxwb doesn't support the reading of filenames from the optional xsb files because their format was too much chaotic for being able to write something "universal".

Ok, thanks for the info.
## Post #5
- Username: Apollo
- Rank: veteran
- Number of posts: 145
- Joined date: Sat Oct 21, 2006 7:58 pm
- Post datetime: 2010-04-25T06:51:57+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

Peculiar case, had a look on that XWB and luigi's unxwb writes a bit odd riff header, saying 23 kbps for 48khz stereo ms adpcm as well track lenghts are way off plus tool says 8 bit in listing??

as for filenames, you could use the -b name.xsb OFFSET (you have to look up the name offset start yourself with hex editor for example) assuming there was exactly same amount of filenames as files listed and this is not always the case :/
## Post #6
- Username: Faqew
- Rank: advanced
- Number of posts: 71
- Joined date: Fri Dec 18, 2009 12:42 am
- Post datetime: 2010-04-25T08:59:01+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

> Reply from Apollo
>
> Peculiar case, had a look on that XWB and luigi's unxwb writes a bit odd riff header, saying 23 kbps for 48khz stereo ms adpcm as well track lenghts are way off plus tool says 8 bit in listing??

as for filenames, you could use the -b name.xsb OFFSET (you have to look up the name offset start yourself with hex editor for example) assuming there was exactly same amount of filenames as files listed and this is not always the case :/

And the filenames would have to be in correct order, but I think that's not the case. =/

Edit:

Can you give me an example on how to do the xsb stuff?
I'm not really experienced with hex editors.
I opened the music.xsb in an hex editor and klicked on the first character of the first filename and got this:
[http://img443.imageshack.us/img443/9269 ... kopieg.jpg](http://img443.imageshack.us/img443/9269/ohnetitel1kopieg.jpg)
In the left bottom corner it says Offset=0x4da.
Then I did this in unxwb: unxwb.exe -b "music.xsb 0x4da", but the only thing that happens then is "unxwb.exe encountered a problem and has to be closed", the program stays open, but nothing more happens. Where's my mistake? 

Edit 2:

I got it to work.  I used this command: unxwb.exe -b music.xsb 0x4da music.xwb
But there are 5 more music tracks then filenames.
## Post #7
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-05-01T10:31:22+00:00
- Post Title: Misadventures of P.B. Winterbottom - Can't extract XWB files

@apollo
the generated header is perfect, use a player that support the ms adpcm codec like vlc or mplayer to play the files

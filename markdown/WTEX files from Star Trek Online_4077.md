## Post #1
- Username: kajee
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jan 21, 2010 2:01 pm
- Post datetime: 2010-01-23T13:04:38+00:00
- Post Title: WTEX files from Star Trek Online

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Cezero
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 28, 2010 11:37 am
- Post datetime: 2010-01-30T03:08:20+00:00
- Post Title: WTEX files from Star Trek Online

I am also interested in obtaining image/texture information from these files...
## Post #3
- Username: Cezero
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 28, 2010 11:37 am
- Post datetime: 2010-01-30T15:46:06+00:00
- Post Title: WTEX files from Star Trek Online

These files contain .dds textures... so WTEX appears to be some sort of a container file
## Post #4
- Username: Cezero
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 28, 2010 11:37 am
- Post datetime: 2010-01-30T15:59:09+00:00
- Post Title: WTEX files from Star Trek Online

Ok, so .WTEX files are really just .DDS files with an additional header.  If you edit the file and delete everything prior to the characters 'DDS |' then they will open in any program that can edit DDS files (Photoshop, etc).  I'm keen to know what the header info is, but it's not that hard to write a script to simply strip it and rename all the files to .dds
## Post #5
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2010-01-30T18:06:17+00:00
- Post Title: WTEX files from Star Trek Online

Little BMS Script, if it doesnt work post some more fils.

```
Get FileSize ASIZE
Get FileName FILENAME

Set Size FileSize
Math Size -= Offset
String FileName -= 5
String FileName += ".DDS"

Log FileName Offset Size
```
## Post #6
- Username: Cezero
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jan 28, 2010 11:37 am
- Post datetime: 2010-01-30T21:52:28+00:00
- Post Title: WTEX files from Star Trek Online

Works perfectly! thanks.
## Post #7
- Username: Enforcer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 27, 2010 11:39 pm
- Post datetime: 2010-03-12T15:02:05+00:00
- Post Title: WTEX files from Star Trek Online

> Reply from evilpie
>
> Little BMS Script, if it doesnt work post some more fils.
Code: Select allGet Offset LONG
Get FileSize ASIZE
Get FileName FILENAME

Set Size FileSize
Math Size -= Offset
String FileName -= 5
String FileName += ".DDS"

Log FileName Offset Size

Hi guys, may i ask for a little help? I have MultiEX commander but i have dot fugered out how to use the above bsm script. I saved it in not pad and hit bms and run Mex script and selected the not pad save, and then whet to the file, but no dice. I am new at this so sorry if i sound stupit. Can some one tell me what i did wrong?
## Post #8
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2010-03-13T17:55:08+00:00
- Post Title: WTEX files from Star Trek Online

Should have mention that this was quickbms, [http://aluigi.org/papers.htm#quickbms](http://aluigi.org/papers.htm#quickbms)
## Post #9
- Username: Enforcer
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jan 27, 2010 11:39 pm
- Post datetime: 2010-03-15T13:29:15+00:00
- Post Title: WTEX files from Star Trek Online

evilpie: THank for the reply, i was wondering what i missed,lol.
## Post #10
- Username: paulsfae
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Apr 29, 2010 7:10 pm
- Post datetime: 2010-04-30T08:32:13+00:00
- Post Title: WTEX files from Star Trek Online

Hi all.  Thanks to everyone's input so far it's easy to get the dds textures out for editing, but does anyone have any ideas on how to get them back again afterwards?  I've tried simply replacing the header info that was stripped out, but no luck.  Is there any way to convert dds back to wtex?

Any help would be much appreciated.
## Post #11
- Username: 212antt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 08, 2017 12:26 am
- Post datetime: 2017-06-09T12:24:58+00:00
- Post Title: WTEX files from Star Trek Online

I recommend using Wtex2DDS to convert a DDS to a Wtex and the opposite easily converting a Wtex to a DDS with a byproduct of a HED file.
## Post #12
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2017-08-08T02:24:39+00:00
- Post Title: WTEX files from Star Trek Online

> Reply from 212antt
>
> I recommend using Wtex2DDS to convert a DDS to a Wtex and the opposite easily converting a Wtex to a DDS with a byproduct of a HED file.
i can't find a copy of wtex2dds anywhere but if someone can upload samples i will modify evilpie's bms script to do the same thing.
## Post #13
- Username: 212antt
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jun 08, 2017 12:26 am
- Post datetime: 2017-08-08T17:07:41+00:00
- Post Title: WTEX files from Star Trek Online

Here's the file for wtex2dds.
[Wtex2DDS.zip](https://xentaxbackup.github.io/file/13178_Wtex2DDS.zip)

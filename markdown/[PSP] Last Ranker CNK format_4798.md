## Post #1
- Username: epopoe
- Rank: advanced
- Number of posts: 56
- Joined date: Thu Feb 11, 2010 9:22 am
- Post datetime: 2010-07-24T16:02:54+00:00
- Post Title: [PSP] Last Ranker CNK format

If you do want it
[BTL_BAT00.zip](https://xentaxbackup.github.io/file/3265_BTL_BAT00.zip)
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-07-24T17:46:56+00:00
- Post Title: [PSP] Last Ranker CNK format

its just zlib using offzip will extract it.
c:\offzip.exe -a c:\file.dat c:\etract 0x0
## Post #3
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-09T23:36:10+00:00
- Post Title: [PSP] Last Ranker CNK format

> Reply from chrrox
>
> its just zlib using offzip will extract it.
c:\offzip.exe -a c:\file.dat c:\etract 0x0

From .cnk files, how can we extract the models? I am a noob
## Post #4
- Username: dj082502
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Wed Oct 13, 2010 10:47 am
- Post datetime: 2012-03-12T23:37:30+00:00
- Post Title: [PSP] Last Ranker CNK format

The same INSM format is used in Black rock shooter PSP.
[viewtopic.php?f=21&t=7245](http://forum.xentax.com/viewtopic.php?f=21&t=7245)
[viewtopic.php?p=58499](http://forum.xentax.com/viewtopic.php?p=58499)
## Post #5
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-13T02:55:31+00:00
- Post Title: [PSP] Last Ranker CNK format

Damn it I want to get the black rock shooter format but I can't figure it out
## Post #6
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-16T11:16:55+00:00
- Post Title: [PSP] Last Ranker CNK format

> Reply from dj082502
>
> The same INSM format is used in Black rock shooter PSP.
viewtopic.php?f=21&t=7245
viewtopic.php?p=58499

Uhm.. I tried the bms script posted in that topic but it doesn't work. 
.cnk files probably are different..?
## Post #7
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T13:53:05+00:00
- Post Title: [PSP] Last Ranker CNK format

The archives are different but he probably means the models are the same.
## Post #8
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-16T14:36:17+00:00
- Post Title: [PSP] Last Ranker CNK format

> Reply from finale00
>
> The archives are different but he probably means the models are the same.

lol, I don't see any LR model in BRS but whatever. I hope there will be a way to extrack models in .cnk packages someday..
## Post #9
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T14:41:41+00:00
- Post Title: [PSP] Last Ranker CNK format

Chrrox says to just use offzip.
Which makes it easier to write a bms script in that case since you already know the compression it uses.
## Post #10
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-16T14:48:31+00:00
- Post Title: [PSP] Last Ranker CNK format

Where can I find this offzip? I searched for it but didn't find it.
Also, if someone could tell me how to use this tool I would be very grateful..
## Post #11
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T15:07:45+00:00
- Post Title: [PSP] Last Ranker CNK format

[http://aluigi.org/mytoolz.htm](http://aluigi.org/mytoolz.htm)
## Post #12
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-16T20:05:27+00:00
- Post Title: [PSP] Last Ranker CNK format

It doesn't work, sadly. The tool opens and closes in 2 seconds and I can't write everything in it...
## Post #13
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-16T20:20:21+00:00
- Post Title: [PSP] Last Ranker CNK format

read the readme that comes with it.
its a command line tool
run it from a command prompt.

c:\offzip.exe -a c:\file.cnk c:\output_folder 0
## Post #14
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-16T20:36:35+00:00
- Post Title: [PSP] Last Ranker CNK format

> Reply from chrrox
>
> read the readme that comes with it.
its a command line tool
run it from a command prompt.

c:\offzip.exe -a c:\file.cnk c:\output_folder 0

I see, there was no readme file in the archive I downloaded, thanks! By the way I tried and I obtained this: 

Error: recheck your options, c:\btl_ranker27_00.cnk is not valid



EDIT: Just got it, I had to write the command line without "c:\". Now, I have a bunch of files with unknown extensions like .efc and .ins. What comes next?
## Post #15
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T21:06:12+00:00
- Post Title: [PSP] Last Ranker CNK format

We haven't figured out the INSM format.
You can post some of those .ins files as samples.
## Post #16
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-16T21:10:44+00:00
- Post Title: Re: [PSP] Last Ranker CNK format

> Reply from finale00
>
> We haven't figured out the INSM format.
You can post some of those .ins files as samples.

Thank you guys for your replies   

Here, I've included 3 .efc and 3 .ins files in the archive.
[files.rar](https://xentaxbackup.github.io/file/5196_files.rar)
## Post #17
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-16T21:58:08+00:00
- Post Title: Re: [PSP] Last Ranker CNK format

Hmm, these start with INSA. Could be an animation file...
The textures in the EFC start with PTMD so it's probably the same as black rock shooter.

Since INSM and INSA files both start with the same characters offzip just names them all with .ins extension
It's the same as BRS

Too bad there aren't any filenames...
## Post #18
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-17T14:03:20+00:00
- Post Title: Re: [PSP] Last Ranker CNK format

If this could help, I attached more files from the CHR folder.

I also noticed there are some .BIN files in the folders and some .CNK can't be extract with offzip..
[files.rar](https://xentaxbackup.github.io/file/5199_files.rar)
## Post #19
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2012-03-17T14:09:57+00:00
- Post Title: Re: [PSP] Last Ranker CNK format

cnk is a generic container i saw uncompressed wave files and things like that in them probably those files offsip found nothing are audio or something like that.
## Post #20
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-03-18T14:10:06+00:00
- Post Title: Re: [PSP] Last Ranker CNK format

> Reply from chrrox
>
> cnk is a generic container i saw uncompressed wave files and things like that in them probably those files offsip found nothing are audio or something like that.

I see. Well I hope there will be a way to extract full models and textures..
## Post #21
- Username: RunaWhite
- Rank: veteran
- Number of posts: 158
- Joined date: Sat Jan 07, 2012 9:30 pm
- Post datetime: 2012-10-05T00:00:01+00:00
- Post Title: Re: [PSP] Last Ranker CNK format

Hi there!
I recently took another look to the files of LR and I noticed some .BIN files that could contain female characters or something.

If you could take a look, I'm giving you one of that files + another .cnk file that, this time, may contain a model (it has a character's name so it might be).

I'm experiencing many errors and issues with offzip lately, so if someone could quickly unpacked these files for me I'd really appreciate it. I had to store the archive on MF since it exceed the forum limit (1.06 MB) [http://www.mediafire.com/?ahds0p1tc4pp66p](http://www.mediafire.com/?ahds0p1tc4pp66p)

## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-05-23T15:39:38+00:00
- Post Title: Wii - MadWorld Announcer Sounds

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Strobe
- Rank: Moderator
- Number of posts: 411
- Joined date: Mon Oct 24, 2005 3:52 pm
- Post datetime: 2009-05-26T15:32:21+00:00
- Post Title: Wii - MadWorld Announcer Sounds

The audiodata is stored as mono ADPCM. there is no header though that i can make something out of , so
i dont really know what subformat of ADPCM it is =P yet.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-26T18:00:02+00:00
- Post Title: Wii - MadWorld Announcer Sounds

looks like the classical nintendo dsp adpcm at 16khz but it's not clear where is located the coefficient table so the result (a sequence of hispanic phrases) is a bit noisy
## Post #4
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-05-30T12:04:37+00:00
- Post Title: Wii - MadWorld Announcer Sounds

Yeah that's the Spanish announcers, if you guys want a sample of the English ones, ask for it and I'll give you a sample.

EDIT: So how can I play those files?
## Post #5
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-30T19:26:53+00:00
- Post Title: Wii - MadWorld Announcer Sounds

considering that the coefficient is not known and so the result is noisy it's not much useful to play it.
anyway it's necessary to add the header to the file for then passing it to vgmstream.

exists a graphical tool for creating the needed GENH header ([http://www.hcs64.com/manakoAT/genh_creator.html](http://www.hcs64.com/manakoAT/genh_creator.html)) but it doesn't work well indeed if you try to specify all the needed fields as I said you get only noise, that's why I had in mind from various months to create a quick tool for working with the genh and other headers (like ss2 and vag) but I continue to delay it.
## Post #6
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-05-30T19:39:25+00:00
- Post Title: Wii - MadWorld Announcer Sounds

Is there anything I could try to look on the ISO to help?
## Post #7
- Username: Agroman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 08, 2011 4:53 am
- Post datetime: 2011-06-07T20:54:59+00:00
- Post Title: Wii - MadWorld Announcer Sounds

The contents of this post was deleted because of possible forum rules violation.
## Post #8
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-06-08T10:24:02+00:00
- Post Title: Wii - MadWorld Announcer Sounds

Seems to be working perfectly, thank you very much. Mass conversion and mass laughs time now.
## Post #9
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-06-08T13:26:40+00:00
- Post Title: Wii - MadWorld Announcer Sounds

OK; correction: I've successfully extracted and converted the whole Spanish announcers and almost the whole English announcers... But an_c107_pack_eng seems to resist against the WAV converter, as the extraction is OK. Tell me if you want that file.
## Post #10
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2011-06-08T14:58:46+00:00
- Post Title: Wii - MadWorld Announcer Sounds

Sure, I'll take a look if you upload the file.  (I wrote the vgmstream support for that format)
## Post #11
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-06-08T16:09:51+00:00
- Post Title: Wii - MadWorld Announcer Sounds

The contents of this post was deleted because of possible forum rules violation.
## Post #12
- Username: Agroman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 08, 2011 4:53 am
- Post datetime: 2011-06-08T16:30:21+00:00
- Post Title: Wii - MadWorld Announcer Sounds

Glad to hear that, Im spanish too, superb announcers (+18) 

Sorry for bugs the extractor isn't perfect.
## Post #13
- Username: Agroman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 08, 2011 4:53 am
- Post datetime: 2011-06-08T20:55:36+00:00
- Post Title: Wii - MadWorld Announcer Sounds

The contents of this post was deleted because of possible forum rules violation.
## Post #14
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2011-06-09T10:17:10+00:00
- Post Title: Wii - MadWorld Announcer Sounds

Nice! Now it's just waiting until hcs solves those RSP.
## Post #15
- Username: klok
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Sep 28, 2011 9:24 am
- Post datetime: 2011-09-28T01:34:16+00:00
- Post Title: Wii - MadWorld Announcer Sounds

sorry if i'm necroposting, but i thought someone could help me here.
my problem is that i am trying to rip madworld's BGM music, said music being stored as rsd files.
now, i downloaded "extract.exe" and his former needs, proceeded to import the rsd's to wav and then BAM! it tells me that can't load the file.
could somebody help me?
## Post #16
- Username: Agroman
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Jun 08, 2011 4:53 am
- Post datetime: 2011-10-22T22:30:08+00:00
- Post Title: Re: Wii - MadWorld Announcer Sounds

> Reply from klok
>
> sorry if i'm necroposting, but i thought someone could help me here.
my problem is that i am trying to rip madworld's BGM music, said music being stored as rsd files.
now, i downloaded "extract.exe" and his former needs, proceeded to import the rsd's to wav and then BAM! it tells me that can't load the file.
could somebody help me?

You must use vgmstream to do that, my extract tool only work correctly with bin (rsd voices files) using vgstream together.

Get it here [http://sourceforge.net/projects/vgmstream/](http://sourceforge.net/projects/vgmstream/) extract zip and use from a cmd line: 'test.exe -o outputfile.wav originalfile.rsd' where originalfile.rsd is the BGM you choose.

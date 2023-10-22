## Post #1
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-09-11T14:16:05+00:00
- Post Title: The World Ends With You (NDS) sound package

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-11T17:56:22+00:00
- Post Title: The World Ends With You (NDS) sound package

Seems to be compressed, i don't know if the DS has a propertiery format or not but i cant decrepyt it.
## Post #3
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-09-11T19:18:10+00:00
- Post Title: The World Ends With You (NDS) sound package

Now I've did a quick search around and this file seems to have all sounds (I don't know how to hex-look, but there IS a list of filenames).
## Post #4
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-09-11T20:09:59+00:00
- Post Title: The World Ends With You (NDS) sound package

I looked in hex but found no filename lists.
## Post #5
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-09-11T20:12:32+00:00
- Post Title: The World Ends With You (NDS) sound package

Right after all the bytes from the start?
[](http://img73.imageshack.us/my.php?image=shotaudiojb7.jpg)
## Post #6
- Username: RonHayter
- Rank: beginner
- Number of posts: 33
- Joined date: Fri Aug 01, 2008 5:22 am
- Post datetime: 2008-09-14T05:03:28+00:00
- Post Title: The World Ends With You (NDS) sound package

[Here](http://kiwi.ds.googlepages.com/sdat.html) is the definition of the SDAT (Nitro Composer) file format. It seems to match your sound file.

I don't know what tools are available for extracting or replacing sounds in SDAT files.

Ron
## Post #7
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-14T05:34:15+00:00
- Post Title: The World Ends With You (NDS) sound package

Hey, I have some news for you. You CAN extract the sounds and stuff at present, but not recompile yet it seems, sadly. -_-

Here's a link to such a tool: [http://nintendon.s6.xrea.com/](http://nintendon.s6.xrea.com/) WANING: Japanese

Go to the link under the first, it is the download page. There you will find NDS Sound Extractor. When you get it, set the SDAT file in the same folder as the tool and have this set as the shortcut commandline:

ndssndext.exe -x (SDAT FILE HERE)

Doing that will rip all sound data it can find as stream (audio and instruments) and sequence (music)

Also there is a tool [HERE](http://tahaxan.arcnor.com/) that can explore NDS files for various data. I've played a small part in it but sadly it has not been updated in a long time... it was going to have SDAT exploring and editing, hopefully it'll revive someday.
## Post #8
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-09-14T09:49:48+00:00
- Post Title: The World Ends With You (NDS) sound package

Thanks for all the intel, I've extracted the stuff with the Japanese tool but I don't know how to, at least, play it.
## Post #9
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-14T20:38:41+00:00
- Post Title: The World Ends With You (NDS) sound package

The streams should all be playable with most common sound players. They should be WAVs.
## Post #10
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-15T03:21:30+00:00
- Post Title: The World Ends With You (NDS) sound package

Oops! Forgot to say this, sorry! Leave out the "-x" option! Without it, it converts the streams and wavesamples to WAV making them all playable! I have tested this and all sounds are extracted and playable. Voices work just fine!
## Post #11
- Username: mambox
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Wed Mar 24, 2004 9:06 pm
- Post datetime: 2008-09-16T15:52:37+00:00
- Post Title: The World Ends With You (NDS) sound package

Nice,it's everything needed to extract sounds!

ndssndext miss me!

thanks!
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-19T00:18:44+00:00
- Post Title: The World Ends With You (NDS) sound package

No problem! Glad I could help.
## Post #13
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-09-19T16:08:21+00:00
- Post Title: The World Ends With You (NDS) sound package

Thanks a lot for all the info. It's a shame to not having a chance to recompile the file, but it's better than nothing.
## Post #14
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-09-19T22:04:45+00:00
- Post Title: The World Ends With You (NDS) sound package

Maybe later they'll have something.
## Post #15
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-09-24T17:04:51+00:00
- Post Title: The World Ends With You (NDS) sound package

I don't want to bother, but do you guys know of somewhere I could ask for a compiler? (Or for someone who could help making one)
## Post #16
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-10-03T17:50:22+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

Well .Strm files couldn't be read by common audio players, but I found some tool to convert them to .Wav. Now, the point is, both tools (The one to extract .strm from the .sdat and the one to convert .strm to .wav) have their source codes, do you guys think someone could change the process to the other side? It would be great if someone could.
## Post #17
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2008-10-03T19:56:33+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

I guess you missed the whole...

```
Oops! Forgot to say this, sorry! Leave out the "-x" option! Without it, it converts the streams and wavesamples to WAV making them all playable! I have tested this and all sounds are extracted and playable. Voices work just fine!
```


XD you didn't have to look for tools.
## Post #18
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-10-03T21:41:49+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

I guess I forgot that, but as a matter of fact, one of my colleagues got it through somewhere else, used a SDAT extractor that spared the filenames contained in the SDAT. Thanks for pointing that out though.

Anyway, that is skipping my last question. Is there a way to revert the source code of those tools to get WAVs into a STRM?
## Post #19
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2008-11-04T18:55:32+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

After some reserarching, I've found out that SDAT files should be compressed in IMA-ADPCM format. Do you guys know of a program that can convert Microsoft PCM into IMA-ADPCM for inserting voices? Thanks.
## Post #20
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2009-02-28T17:29:33+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

Sorry to revive this but the page indicated for the extractor doesn't seem to have the program mentioned any more, unless I'm missing it entirely. I need it for a favor to a friend.
## Post #21
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2009-02-28T17:33:47+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

Here's a duplicate.
[http://endesh.blog60.fc2.com/blog-entry-285.html](http://endesh.blog60.fc2.com/blog-entry-285.html)
## Post #22
- Username: Doctor Loboto
- Rank: mega-veteran
- Number of posts: 213
- Joined date: Mon Oct 06, 2008 9:52 am
- Post datetime: 2009-02-28T17:59:01+00:00
- Post Title: Re: The World Ends With You (NDS) sound package

That just has a link to that same site. If someone could upload it to Megaupload or something real quick I'd appreciate it greatly.

Edit: Actually I found a mirror. This is a good program but I'd rather have it convert to WAV than Midi. I need to be able to convert them to MP3s with another program of mine.

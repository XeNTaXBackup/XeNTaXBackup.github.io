## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-18T02:00:06+00:00
- Post Title: NFS Undercover MUS format?

[http://www.megaupload.com/?d=G1XSUALA](http://www.megaupload.com/?d=G1XSUALA)

Welp another EA game and they changed there MUS format.

Instead there are no Mus segments inside here.
## Post #2
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-20T19:36:38+00:00
- Post Title: NFS Undercover MUS format?

Is there any source code out there to convert mus files?
Maybe they simply used some encryption.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-20T21:01:42+00:00
- Post Title: NFS Undercover MUS format?

They are headerless mus segments i found out in that file, problem is these are alot of segments and it will take time to add a  SCHII and SCCI or whatever header mus uses, i forogt how to add the ehader chunks so maybe if someone can create a header adder or something.
## Post #4
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-20T21:33:54+00:00
- Post Title: NFS Undercover MUS format?

How shall that work? WIthout headers you don't know where one sound ends and the other begins (cause I don't believe a single sounds takes up 62MB)
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-20T23:26:04+00:00
- Post Title: NFS Undercover MUS format?

Well i looked in the file and it had zeroes in between the data bglocks but i dunno if they are starting or ending blocks or if they are even the starting ending points of the files, 

EA did it really complicated with this stream system but its still the same EA/XA codec.
## Post #6
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-21T11:47:07+00:00
- Post Title: NFS Undercover MUS format?

Seems to be EA's strategy 
I'm also fighting with an EA audio format for some time now: [viewtopic.php?f=17&t=2756](http://forum.xentax.com/viewtopic.php?f=17&t=2756)
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-26T00:42:08+00:00
- Post Title: NFS Undercover MUS format?

So no way to figure out these headers i presume?
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-26T00:48:01+00:00
- Post Title: NFS Undercover MUS format?

Well, I guess either they are saved in another file or all files use a defined common format.
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-26T00:52:40+00:00
- Post Title: NFS Undercover MUS format?

There are also MPF files but they dont contain the MUS SCHII headers.
## Post #10
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-26T17:49:03+00:00
- Post Title: NFS Undercover MUS format?

Well if you knew which codec is used, you could probably convert it. Did you try any tools?
## Post #11
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-26T18:01:23+00:00
- Post Title: NFS Undercover MUS format?

It stil uses EA/XA codecs, same codec used in other MUS files its just the stream system is differnet, no headers, and we all know how MUS has many segments of mus files inside a bigfile, but without headers, theres nothign to scan them with.

I aslo tried to use EA's Sound exchange program but thats to confusing for me.
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-26T21:45:49+00:00
- Post Title: NFS Undercover MUS format?

Well what about the tools created for previous games, shouldn't it be easy for their developers to support this game as well?
## Post #13
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-26T22:11:46+00:00
- Post Title: NFS Undercover MUS format?

That is the problem, no tools can support can support this yet until someone figures out how the stream system works. It needs the headers, but adding a simple SCHII header won't do it either because it needs the additonal SCCI info and all that. So its complicated for that.

But even though if someone can create a tool that decodes dead space than maybe they can do the same thing for this. I cant even do dead spaces tool on the mus file either.
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-27T02:10:18+00:00
- Post Title: NFS Undercover MUS format?

> Reply from OrangeC
>
> That is the problem, no tools can support can support this yet until someone figures out how the stream system works. It needs the headers, but adding a simple SCHII header won't do it either because it needs the additonal SCCI info and all that. So its complicated for that.
Well, SCCI and SCDI are very easy, the SCHI header is the crucial part, e.g. supplying the number of samples in the stream.

> But even though if someone can create a tool that decodes dead space than maybe they can do the same thing for this. I cant even do dead spaces tool on the mus file either.
Well my point was, that those who developed tools for previous games of the NfS series have a working source code for decoding EA XA ADPCM, thus it should be easier for them to write a tool for this game.
## Post #15
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-27T02:43:27+00:00
- Post Title: NFS Undercover MUS format?

Yes thats true but i have not seen any other tools other than sound exchange.

HMM yes i dunno how many samples in a mus segment, most mus segments have a length of 2 seconds so i have no idea how many samples that have.
## Post #16
- Username: jfwfreo
- Rank: veteran
- Number of posts: 124
- Joined date: Sat Nov 15, 2008 8:31 am
- Post datetime: 2008-11-27T09:40:08+00:00
- Post Title: Re: NFS Undercover MUS format?

FFMPEG supports a number of variants of EA custom ADPCM and its code is available under the LGPL license for you to use.
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-27T18:17:05+00:00
- Post Title: Re: NFS Undercover MUS format?

Too Bad i don't know how to use those.
## Post #18
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-11-27T21:40:45+00:00
- Post Title: Re: NFS Undercover MUS format?

And the code is quite tied to the ffmpeg library.
## Post #19
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-11-28T00:52:32+00:00
- Post Title: Re: NFS Undercover MUS format?

So is there anyway i can use the FFMPEG to convert the raw EA/XA stream to an uncompressed PCM? unles FFMPEG needs the headers also.

Damn ea makes it so hard.
## Post #20
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2008-12-03T19:15:59+00:00
- Post Title: Re: NFS Undercover MUS format?

Hi guys,

any luck yet? I was thinking about offering a helping hand (working professionally as a C++ programmer), but there's a catch -- I'm very little skilled when it comes to "decrypting" file formats. I had small and nifty handbook somewhere around here, so I might try to have a look inside. 

Cheers.
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-03T19:32:48+00:00
- Post Title: Re: NFS Undercover MUS format?

No luck yet, without the file headers i don't see anything to decode these mus files.
## Post #22
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-03T23:57:35+00:00
- Post Title: Re: NFS Undercover MUS format?

Yeah, there's no real file format to figure out. You need to know the codec and the parameters to get along.
But thanks for your offer, we need programmers here 

btw: used to C++? Try D!
## Post #23
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2008-12-04T20:30:28+00:00
- Post Title: Re: NFS Undercover MUS format?

> Reply from Rheini
>
> Yeah, there's no real file format to figure out. You need to know the codec and the parameters to get along.
But thanks for your offer, we need programmers here 

btw: used to C++? Try D!

Does that means that it's not certain that the game uses the same audio codec that OrangeC was talking about?
## Post #24
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-04T20:37:20+00:00
- Post Title: Re: NFS Undercover MUS format?

Yes, the codec is determined by the header: [http://wiki.multimedia.cx/index.php?tit ... _Arts_SCxl](http://wiki.multimedia.cx/index.php?title=Electronic_Arts_SCxl)
As I already said, either they keep the header in a different file or they use a common, predefined format for all sounds.
## Post #25
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2008-12-04T20:57:27+00:00
- Post Title: Re: NFS Undercover MUS format?

Hmm, from a programmer's standpoint, I can see little point in storing file headers in a place different from the data itself -- that sort of beats the purpose of a header. So I guess they must have somehow consolidated the format. However, they still need to be able to quickly traverse the files' contents -- after all, the in-game music is supposed to dynamic, so there have to be some begin-end markers within the data along with some indices.

The hard part, of course, is to find out what they are...  Maybe the .mpf files that accompany the .mus file could be useful...
## Post #26
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-04T21:41:14+00:00
- Post Title: Re: NFS Undercover MUS format?

Okay here are all the MPF files for the mus files.

[http://www.megaupload.com/?d=EDZWYOP0](http://www.megaupload.com/?d=EDZWYOP0)
## Post #27
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2008-12-04T21:43:44+00:00
- Post Title: Re: NFS Undercover MUS format?

Well it's not that unsual. Sometimes games store the directory to their archives in another file, usually with the same name, but a different file extension.
## Post #28
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-05T02:56:09+00:00
- Post Title: Re: NFS Undercover MUS format?

Any luck with the MPF's
## Post #29
- Username: clayman
- Rank: n00b
- Number of posts: 16
- Joined date: Wed Dec 27, 2006 7:26 am
- Post datetime: 2008-12-05T07:25:27+00:00
- Post Title: Re: NFS Undercover MUS format?

> Reply from Rheini
>
> Well it's not that unsual. Sometimes games store the directory to their archives in another file, usually with the same name, but a different file extension.

Yes, that would be the indexing information, but you'd still need the file headers themselves (unless, of course, the data really is consolidated in some way). I guess the mpf files might be worth checking out, though the result may be uncertain.
## Post #30
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-12-21T04:34:17+00:00
- Post Title: Re: NFS Undercover MUS format?

CTPAX-X Team has updated there NFS tool to support undercover, but it doesnt support interactive music, only licensed stuff.

Dunno if i can trick it to convert the score.

## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-04-21T06:10:44+00:00
- Post Title: XMA 360 file format?

Now this is a tricky format although if you have the 360 XDK kit it be easy to decode to PCM, we need this tool XMAencode.exe, but you need a microsoft dev license to play/convert them.

In june the latest version of xaudio2 states that XMA will be playable on windows, if true it be awesome!! but until now i will include a sample of it for futher analyses.

Here is an XMA file from the game the darkness.
[Mus Castle Ev Castle.rar](https://xentaxbackup.github.io/file/1495_Mus Castle Ev Castle.rar)
## Post #2
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-06-19T14:51:25+00:00
- Post Title: XMA 360 file format?

The June 2008 SDK is released and still no XMA playback.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-08-09T20:24:12+00:00
- Post Title: XMA 360 file format?

August 2008 SDK is out and still no XMA converter. Hmm maybe they are focusing on xWMA damn.
## Post #4
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2008-08-11T08:56:51+00:00
- Post Title: XMA 360 file format?

> Reply from OrangeC
>
> August 2008 SDK is out and still no XMA converter. Hmm maybe they are focusing on xWMA damn.

Yes there is no tool to convert xma  except XACT... which is able to encode xma... into wave banks of course. 
I made a xwb unpacker for latest XACT banks,I added also adpcm decoding but xma is much harder to implement,so I'm looking for decoder too... I did some of "research" on XACT but without knowledge of WMA Pro its useless...

Maybe somebody will be able to do a decoder  I have no time for this atm...

I have one request for you  Can you please upload more xma files ??? similar for first one ? Maybe I'll be able to find xma structure....
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-08-11T15:24:10+00:00
- Post Title: XMA 360 file format?

Okay here are more darkness XMA's All i know is these xmas have no riff header and are big endian, All files atart with these bytes. 584D41

[http://www.megaupload.com/?d=NBMLVS23](http://www.megaupload.com/?d=NBMLVS23)
## Post #6
- Username: Silver
- Rank: veteran
- Number of posts: 80
- Joined date: Sat Apr 30, 2005 8:25 pm
- Post datetime: 2008-10-31T03:51:51+00:00
- Post Title: XMA 360 file format?

Here is some XMA files from Fable 2. I believe these to be XMA2.
[animals_bnk.zip](https://xentaxbackup.github.io/file/1709_animals_bnk.zip)
## Post #7
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2008-10-31T13:07:35+00:00
- Post Title: XMA 360 file format?

Yeah they are.

Has the riff wav header extensions but are not really.
## Post #8
- Username: Crypton
- Rank: advanced
- Number of posts: 60
- Joined date: Sat Aug 09, 2008 6:19 pm
- Post datetime: 2009-03-14T00:15:28+00:00
- Post Title: XMA 360 file format?

Still no luck with decoder ?:P do anybody know any pc app or game which uses xma ? I want to make a decoder for it but I have no resources to research
## Post #9
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-03-14T04:25:48+00:00
- Post Title: XMA 360 file format?

I don't think a PC game uses XMA.
## Post #10
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-04-19T00:58:27+00:00
- Post Title: XMA 360 file format?

Well looks like these guys did it!! great news!!!

[http://www.ctpax-x.ru/](http://www.ctpax-x.ru/)
## Post #11
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-04-20T02:16:46+00:00
- Post Title: XMA 360 file format?

Yup it is great news. All we need now is a scanner that'll extract the xma's from various 360 archives and we're good to go.
## Post #12
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-08T22:25:28+00:00
- Post Title: XMA 360 file format?

Could anyone find out the actual format? I'm really curious how they did it. I don't speak or understand any Russian.
## Post #13
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-05-11T22:54:25+00:00
- Post Title: XMA 360 file format?

uhmmm why not trying the xWMAEncode.exe utility which comes in the DirectX SDK?
it allows to encode and decode the xma files as far as I have seen and tested (quick test, so I could be wrong)

*ps*: anyway for who is interested towav uses the libraries of Microsoft
## Post #14
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-12T16:29:06+00:00
- Post Title: XMA 360 file format?

Why don't you ask the author? Maybe he gives you some details.
## Post #15
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-12T23:51:42+00:00
- Post Title: XMA 360 file format?

> Reply from Rheini
>
> Why don't you ask the author? Maybe he gives you some details.Well, I would like to, but the entire site is in Russian. I can use Google translate, but I don't like it very much. I don't see Xplorer's e-mail address directly on the site, either. Well, anyways, I'll try that utility from the DX SDK.
## Post #16
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-05-13T00:05:48+00:00
- Post Title: Re: XMA 360 file format?

I know I can only use Google too (the only Russian word I can read by now is download )
You may try to register in the forum and write him a PM, or use the Feedback form or the guestbook or...

> All comments and suggestions please, support@ctpax-x.ru
## Post #17
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-05-15T01:16:42+00:00
- Post Title: Re: XMA 360 file format?

I thought the xmaencode was from the XDK only?
## Post #18
- Username: Zench
- Rank: VIP member
- Number of posts: 209
- Joined date: Mon May 05, 2008 4:11 am
- Post datetime: 2009-05-21T19:07:25+00:00
- Post Title: Re: XMA 360 file format?

> Reply from Bugtest
>
> uhmmm why not trying the xWMAEncode.exe utility which comes in the DirectX SDK?
it allows to encode and decode the xma files as far as I have seen and tested (quick test, so I could be wrong)Nope, it didn't work for me with the March SDK. I think I will register for that Russian forum and ask the creator.

Edit: I'm not so sure now that I found this thread: [http://www.hcs64.com/mboard/forum.php?s ... showpage=0](http://www.hcs64.com/mboard/forum.php?showthread=14818&showpage=0)
## Post #19
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-10-25T19:43:24+00:00
- Post Title: Re: XMA 360 file format?

Yeah I know, this thread is quite old, but: I came across this topic through Google while searching for info on the XMA format.
I just tested the ToWav program on Forza Motorsport 3 and it works!
You can download the program at this URL: [http://www.ctpax-x.ru/index.php?goto=files&show=24](http://www.ctpax-x.ru/index.php?goto=files&show=24)
## Post #20
- Username: DvT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 15, 2009 9:09 pm
- Post datetime: 2009-11-28T23:13:27+00:00
- Post Title: Re: XMA 360 file format?

Or just download the XMAencode.exe :

[http://www.filefactory.com/file/a1e8efa/n/xmaencode.rar](http://www.filefactory.com/file/a1e8efa/n/xmaencode.rar)
## Post #21
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2009-11-28T23:38:28+00:00
- Post Title: Re: XMA 360 file format?

Oh wow, that was a weird surprise. cant believe someone leaked it.

EDIT: Seems to be not decoding any of the xma's i have. gives me an unsupported format error.
## Post #22
- Username: pietastesgood
- Rank: advanced
- Number of posts: 72
- Joined date: Sun Oct 26, 2008 9:41 am
- Post datetime: 2009-11-29T00:18:50+00:00
- Post Title: Re: XMA 360 file format?

The contents of this post was deleted because of possible forum rules violation.
## Post #23
- Username: hcs
- Rank: mega-veteran
- Number of posts: 263
- Joined date: Mon Oct 19, 2009 4:41 am
- Post datetime: 2009-11-30T07:18:31+00:00
- Post Title: Re: XMA 360 file format?

The contents of this post was deleted because of possible forum rules violation.
## Post #24
- Username: DvT
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sun Nov 15, 2009 9:09 pm
- Post datetime: 2009-12-02T17:51:04+00:00
- Post Title: Re: XMA 360 file format?

The contents of this post was deleted because of possible forum rules violation.

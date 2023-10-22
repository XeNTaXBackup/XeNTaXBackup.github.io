## Post #1
- Username: Indoorsman
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-13T12:42:53+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

HI all,

I have made a tool which can repack ba2 files from Fallout 4, it is still work in progress 

Details:
This games has 2 different formats of BA2 files.
1 - GNRL = general format archive
2 - DX10 = texture format archive

My tool can, so far extract all formats.
Also my tool can repack files with format GNRL only, also with compression.

Still gonna work on repacker for DX10 archives.. 

M
[F4 Tools V7.0.rar](https://xentaxbackup.github.io/file/10008_F4 Tools V7.0.rar)
## Post #2
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-13T17:33:25+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from michalss
>
> HI all,

I have made a tool which can repack ba2 files from Fallout 4, it is still work in progress 

Details:
This games has 2 different formats of BA2 files.
1 - GNRL = general format archive
2 - DX10 = texture format archive

My tool can, so far extract all formats.
Also my tool can repack files with format GNRL only, also with compression.

Still gonna work on repacker for DX10 archives.. 

M

Awesome, can you please somehow write command-line tools as well if possible ?
## Post #3
- Username: TheRanger
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-13T18:50:33+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from TheRanger
>
> michalss wrote:HI all,

I have made a tool which can repack ba2 files from Fallout 4, it is still work in progress 

Details:
This games has 2 different formats of BA2 files.
1 - GNRL = general format archive
2 - DX10 = texture format archive

My tool can, so far extract all formats.
Also my tool can repack files with format GNRL only, also with compression.

Still gonna work on repacker for DX10 archives.. 

M

Awesome, can you please somehow write command-line tools as well if possible ?

Why do you need it for? Its ok just extractor?
## Post #4
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2015-11-13T22:39:05+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

Any idea how to view or convert the Normal and Specular maps? IrfanView just shows black, and any other DDS viewers I've found won't load them.
## Post #5
- Username: TheRanger
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-13T23:09:10+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from AchillesPDX
>
> Any idea how to view or convert the Normal and Specular maps? IrfanView just shows black, and any other DDS viewers I've found won't load them.

 they are DX10 textures, try Xnview  im also not 100% sure if all textures are right, very complicated format im affraid...
## Post #6
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2015-11-13T23:19:41+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

XnView displays something at least - they look pretty scrambled though. Something's clearly not quite right. If you can look into it at some point, that'd be awesome, but as it is, your utility is still very useful. Thanks!
## Post #7
- Username: TheRanger
- Rank: beginner
- Number of posts: 23
- Joined date: Tue Aug 25, 2015 2:11 am
- Post datetime: 2015-11-14T08:49:37+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from michalss
>
> Why do you need it for? Its ok just extractor?

Forget that, its not much necessary, just waiting for your DX10 ba2 archives repacker
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-14T10:18:22+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from AchillesPDX
>
> XnView displays something at least - they look pretty scrambled though. Something's clearly not quite right. If you can look into it at some point, that'd be awesome, but as it is, your utility is still very useful. Thanks!

Found correct headers and now it should be fixed  Enjoy
## Post #9
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-14T10:18:56+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

added new version where all texture headers are know.. version V7.0 will do it
## Post #10
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2015-11-14T17:17:47+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from michalss
>
> AchillesPDX wrote:XnView displays something at least - they look pretty scrambled though. Something's clearly not quite right. If you can look into it at some point, that'd be awesome, but as it is, your utility is still very useful. Thanks!

Found correct headers and now it should be fixed  Enjoy

Just snagged V7 and it seems like the normal and specular maps are more screwed up now than they were before. XnView sort of opened them with V6 and now it refuses to open them at all.

Thanks for the effort anyway!
## Post #11
- Username: Savage
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-14T17:42:56+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from AchillesPDX
>
> michalss wrote:AchillesPDX wrote:XnView displays something at least - they look pretty scrambled though. Something's clearly not quite right. If you can look into it at some point, that'd be awesome, but as it is, your utility is still very useful. Thanks!

Found correct headers and now it should be fixed  Enjoy

Just snagged V7 and it seems like the normal and specular maps are more screwed up now than they were before. XnView sort of opened them with V6 and now it refuses to open them at all.

Thanks for the effort anyway!

They are 100% correct. XNview cannot open it, you have to use PS or GIMP but they are 100% correct..
## Post #12
- Username: AchillesPDX
- Rank: beginner
- Number of posts: 34
- Joined date: Sat Mar 17, 2012 1:02 am
- Post datetime: 2015-11-14T18:17:22+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

Excellent. Photoshop is my software of choice - which plugin would you suggest? And will GIMP open them natively? I've never used it before.

Ideally I'd find something to batch convert everything to PNGs or TIFs.

Thanks again!
## Post #13
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2015-11-18T21:04:35+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

Thanks! michalss
## Post #14
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2015-11-19T13:17:02+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

@michalss

It is possible to make a command-line version?
## Post #15
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-19T14:10:10+00:00
- Post Title: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from Savage
>
> @michalss

It is possible to make a command-line version?

Im sorry but no, i drop it, i have done what was need it, not more time for it..
## Post #16
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2015-11-19T16:06:06+00:00
- Post Title: Re: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

Well, thanks for the tool anyway, nice work
## Post #17
- Username: Monument
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Nov 30, 2015 4:08 am
- Post datetime: 2015-11-29T20:13:06+00:00
- Post Title: Re: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

Hey, Not sure as of why. But when trying to open the program it just loads beside my mouse and does not open. Any help would be appreciated.
## Post #18
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2015-11-29T20:51:49+00:00
- Post Title: Re: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from Monument
>
> Hey, Not sure as of why. But when trying to open the program it just loads beside my mouse and does not open. Any help would be appreciated.

No idea mate, try diff PC, it works ok for all others..
## Post #19
- Username: relight
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Aug 16, 2010 10:52 am
- Post datetime: 2016-05-02T01:05:49+00:00
- Post Title: Re: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

Metadefender.com detects Worm.Allaple.Win32.29564 in this tool, is it a false positive?
## Post #20
- Username: mono24
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2016-05-02T05:19:20+00:00
- Post Title: Re: Fallout 4 [BA2] Repacker (GNRL,TEXTURE)

> Reply from relight
>
> Metadefender.com detects Worm.Allaple.Win32.29564 in this tool, is it a false positive?

What ?  WTF is metadefender crap , of course it is false positive. Pls use proper antivirus next time...

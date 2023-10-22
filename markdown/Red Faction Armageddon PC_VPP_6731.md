## Post #1
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-05T23:43:41+00:00
- Post Title: Red Faction Armageddon PC_VPP

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-06T08:27:50+00:00
- Post Title: Red Faction Armageddon PC_VPP

The code on my repository should be able to unpack it. I won't be providing binaries though, sorry. Game unlocks in 20 hours for me.
## Post #3
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-06T12:00:47+00:00
- Post Title: Red Faction Armageddon PC_VPP

A link to your repository please?
## Post #4
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2011-06-06T17:36:36+00:00
- Post Title: Red Faction Armageddon PC_VPP

[http://svn.gib.me/public/volition/trunk/](http://svn.gib.me/public/volition/trunk/)

It works fine on the *.vpp_pc files which have no compression but crashes on the ones that do like misc.vpp_pc
## Post #5
- Username: OrangeC
- Rank: double-veteran
- Number of posts: 868
- Joined date: Sun Apr 20, 2008 9:58 am
- Post datetime: 2011-06-06T18:26:18+00:00
- Post Title: Red Faction Armageddon PC_VPP

Thanks, works great!
## Post #6
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-06-06T19:57:18+00:00
- Post Title: Red Faction Armageddon PC_VPP

> Reply from Rick
>
> The code on my repository should be able to unpack it. I won't be providing binaries though, sorry. Game unlocks in 20 hours for me.

Unpack it only or also repack ? thx
## Post #7
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-07T01:01:41+00:00
- Post Title: Red Faction Armageddon PC_VPP

> Reply from twisted
>
> http://svn.gib.me/public/volition/trunk/

It works fine on the *.vpp_pc files which have no compression but crashes on the ones that do like misc.vpp_pcYeah, I can't handle any peculiarities until the game is out. 

> Reply from michalss
>
> Unpack it only or also repack ? thxI have not implemented packing yet, will do that when I have the game and can test stuff.
## Post #8
- Username: Nexus Elite
- Rank: n00b
- Number of posts: 17
- Joined date: Sat Apr 16, 2011 1:36 am
- Post datetime: 2011-06-07T03:04:14+00:00
- Post Title: Red Faction Armageddon PC_VPP

Any chance on checking mesh?
## Post #9
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-07T10:19:46+00:00
- Post Title: Red Faction Armageddon PC_VPP

> Reply from twisted
>
> http://svn.gib.me/public/volition/trunk/

It works fine on the *.vpp_pc files which have no compression but crashes on the ones that do like misc.vpp_pcMy code unpacks misc.vpp_pc just fine.
## Post #10
- Username: twisted
- Rank: veteran
- Number of posts: 100
- Joined date: Tue Apr 24, 2007 6:25 am
- Post datetime: 2011-06-09T15:53:19+00:00
- Post Title: Red Faction Armageddon PC_VPP

> Reply from Rick
>
> twisted wrote:http://svn.gib.me/public/volition/trunk/

It works fine on the *.vpp_pc files which have no compression but crashes on the ones that do like misc.vpp_pcMy code unpacks misc.vpp_pc just fine.

Works fine now, didn't realise steam needed to decrypt the vpp files first.
## Post #11
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2011-06-09T16:06:48+00:00
- Post Title: Red Faction Armageddon PC_VPP

can anybody share compiled Rick's tools?
## Post #12
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-09T19:40:11+00:00
- Post Title: Red Faction Armageddon PC_VPP

Gibbed.Volition.Pack.exe works but the game does not run with the modified file. I noted that the package version is 6 and not 3 of the Guerrilla.
Any ideas?
## Post #13
- Username: srredfire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 19, 2011 2:22 pm
- Post datetime: 2011-06-10T08:54:48+00:00
- Post Title: Red Faction Armageddon PC_VPP

Can anyone post compiled binaries for the unpacking tools? Would be much appreciated.
## Post #14
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-10T11:50:43+00:00
- Post Title: Red Faction Armageddon PC_VPP

Committed revision 28, now supports packing version 6 VPPs. Use -p 6 (or --version=6) when packing.
## Post #15
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-10T15:02:37+00:00
- Post Title: Red Faction Armageddon PC_VPP

Thanks Rick! Worked perfectly.
## Post #16
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-06-10T21:41:28+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Binaries of revision 28 attached below.
[Gibbed.Volition.7z](https://xentaxbackup.github.io/file/4314_Gibbed.Volition.7z)
## Post #17
- Username: srredfire
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Jan 19, 2011 2:22 pm
- Post datetime: 2011-06-11T04:42:44+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Thanks Herdell.

Also if anyone could help me with this ( RFA related ) it'd be great:

[viewtopic.php?f=17&t=6764](http://forum.xentax.com/viewtopic.php?f=17&t=6764)
## Post #18
- Username: Kane
- Rank: n00b
- Number of posts: 13
- Joined date: Tue Dec 28, 2010 5:50 pm
- Post datetime: 2011-06-11T08:58:27+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

The world_l0.vpp_pc is 2.83 GB, but your program only extracts 2 GBs.
## Post #19
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2011-06-11T20:32:00+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

> Reply from Herdell
>
> Binaries of revision 28 attached below.
Thank you

> Reply from Kane
>
> The world_l0.vpp_pc is 2.83 GB, but your program only extracts 2 GBs.confirmed
Crash at 1h_c0913.str2_pc

P.S. Please upload binaries of new revision
## Post #20
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-11T21:26:34+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Mbi2010, check your MP.
## Post #21
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-11T21:49:41+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Revision 32: Fix offset handling with large (2GB+) VPP archives.
## Post #22
- Username: Herdell
- Rank: veteran
- Number of posts: 103
- Joined date: Mon Dec 14, 2009 3:35 am
- Post datetime: 2011-06-13T16:35:49+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Updated revision binaries. Enjoy!
[Gibbed.Volition.Rev32.7z](https://xentaxbackup.github.io/file/4329_Gibbed.Volition.Rev32.7z)
## Post #23
- Username: delutto
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Apr 16, 2011 12:20 pm
- Post datetime: 2011-06-13T18:16:50+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Tanks Herdell.
## Post #24
- Username: Crinkle
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 14, 2011 2:35 am
- Post datetime: 2011-06-13T18:40:49+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

<ninja edit for stupidity win>

I'm hoping to get a version of my "Your Faction Geurrilla" (Edits over 600 RFG settings!) tool going for RFA.

Plus i dont want to play the game "zoomed in"
## Post #25
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-06-13T19:40:30+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Should be trivial to adjust FOV, look at camera.xtbl or get that trainer that's on the official forums.
## Post #26
- Username: Crinkle
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Jun 14, 2011 2:35 am
- Post datetime: 2011-06-13T20:35:22+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Already done. But i'll leave explosions, salvage, upgrade prices, health, weapons etc till after my first runthrough!
## Post #27
- Username: Mbi2010
- Rank: Banned
- Number of posts: 15
- Joined date: Fri Sep 03, 2010 2:12 pm
- Post datetime: 2011-08-03T17:41:35+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

please compile new binaries (rev33)
[http://svn.gib.me/public/volition/trunk/](http://svn.gib.me/public/volition/trunk/)
## Post #28
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2011-10-16T09:11:21+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

> please compile new binaries (rev33)
>
> http://svn.gib.me/public/volition/trunk/
Here is
[redfactiontoolsv33.7z](https://xentaxbackup.github.io/file/4777_redfactiontoolsv33.7z)
## Post #29
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2011-10-18T04:31:09+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Does it also work with X360 version please ?
## Post #30
- Username: lostprophet
- Rank: mega-veteran
- Number of posts: 202
- Joined date: Thu Apr 08, 2010 2:38 am
- Post datetime: 2013-04-05T19:48:17+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

Could somebody please compile the latest revision for Red Faction: Armageddon vpp_pc unpack/pack?
[http://svn.gib.me/public/volition/trunk/](http://svn.gib.me/public/volition/trunk/)
## Post #31
- Username: Ekey
- Rank: M-M-M-Monster veteran
- Number of posts: 1823
- Joined date: Wed Mar 31, 2010 1:54 pm
- Post datetime: 2013-04-06T08:41:19+00:00
- Post Title: Re: Red Faction Armageddon PC_VPP

> Reply from lostprophet
>
> Could somebody please compile the latest revision for Red Faction: Armageddon vpp_pc unpack/pack?
http://svn.gib.me/public/volition/trunk/
[http://svn.gib.me/builds/volition/volition-r91_b74.zip](http://svn.gib.me/builds/volition/volition-r91_b74.zip)

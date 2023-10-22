## Post #1
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2015-07-03T19:34:28+00:00
- Post Title: [PC] Run And Fire MMOFPS

Hi,
There is new MMOFPS game on Steam - RUN AND FIRE : [http://store.steampowered.com/app/360760/](http://store.steampowered.com/app/360760/)
I'd downloaded and found that game's archive is .ARCH00, familiar with FEAR, Repulse.
I'd tried some Aluigi's script : 
- FEAR/FEAR2 ARCH00 : Didn't work
- Repulse ARCH00 : Didn't work

Anybody help me on this? thank you very much 
Sample File: [https://www.mediafire.com/?zyy30zxm6jdurdt](https://www.mediafire.com/?zyy30zxm6jdurdt)
## Post #2
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2015-07-15T21:16:06+00:00
- Post Title: [PC] Run And Fire MMOFPS

anybody help me about .bms on this game
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-15T22:09:05+00:00
- Post Title: [PC] Run And Fire MMOFPS

the arch00 archive starts with the signature "PTAR" while the bms scripts you mentioned check for "LTAR".

You could use TextureFinder to check for contained textures (there are some)

You could check the filetable at archive's end ("characters\AI\Mat\Bumper.Mat00G" etc.)

You could try a comtype_scan (search "Quickbms" for more infos):
[viewtopic.php?f=10&t=12632&p=104305&hil ... an#p104305](http://forum.xentax.com/viewtopic.php?f=10&t=12632&p=104305&hilit=comtype_scan#p104305)

good luck.
## Post #4
- Username: merlinsvk
- Rank: ultra-veteran
- Number of posts: 411
- Joined date: Mon Oct 27, 2008 7:11 am
- Post datetime: 2015-07-16T09:10:49+00:00
- Post Title: [PC] Run And Fire MMOFPS

[FEAR / FEAR2 / ARCH00 archives (script 0.6)](http://aluigi.altervista.org/papers/bms/fear.bms) works. It extracts 132 files.
## Post #5
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2015-07-16T12:00:41+00:00
- Post Title: [PC] Run And Fire MMOFPS

> Reply from shakotay2
>
> the arch00 archive starts with the signature "PTAR" while the bms scripts you mentioned check for "LTAR".

You could use TextureFinder to check for contained textures (there are some)

You could check the filetable at archive's end ("characters\AI\Mat\Bumper.Mat00G" etc.)

You could try a comtype_scan (search "Quickbms" for more infos):
viewtopic.php?f=10&t=12632&p=104305&hil ... an#p104305

good luck.

Thanks for your help    i didn't know how to check

> Reply from merlinsvk
>
> FEAR / FEAR2 / ARCH00 archives (script 0.6) works. It extracts 132 files.

Thanks for your help, i just realized i had used old version of QuickBMS
## Post #6
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2016-08-07T02:01:49+00:00
- Post Title: [PC] Run And Fire MMOFPS

even after extracting the files from the Arch00 archive it looks like
there is an additional layer of compression on the *.Model00p files
or maybe they didn't extract properly to begin with
## Post #7
- Username: onelove1210
- Rank: advanced
- Number of posts: 75
- Joined date: Thu Apr 07, 2011 7:06 pm
- Post datetime: 2016-08-07T03:48:39+00:00
- Post Title: [PC] Run And Fire MMOFPS

> Reply from AceWell
>
> even after extracting the files from the Arch00 archive it looks like
there is an additional layer of compression on the *.Model00p files
or maybe they didn't extract properly to begin with

Yes, that's why I have FEAR tools but it's useless    I will install and check again that file

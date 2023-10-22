## Post #1
- Username: CVMe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 11, 2011 5:57 am
- Post datetime: 2011-09-13T23:24:10+00:00
- Post Title: Another CVM!!!

I was browsing through the contents of yakuza 2, and i noticed that some of the files were cvm. I tried to open using the atlus extraction method on a hex editor, example: removing 0000x1800. It did not work, then I tried noesis and the format could not be recognized. I even managed to stumble upon a program known as ROFS2ISO, it is used to convert Sega CVM files that were not encrypted. No luck so far, does anyone have an idea?

Heres some pictures of hex. It stops at 1005
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-09-13T23:34:28+00:00
- Post Title: Another CVM!!!

yakuza files are compressed no one knows the compression they use so extracting the cvm wont help.
## Post #3
- Username: CVMe
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Sep 11, 2011 5:57 am
- Post datetime: 2011-09-13T23:39:57+00:00
- Post Title: Another CVM!!!

ok thanks
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-09-14T01:27:11+00:00
- Post Title: Another CVM!!!

Have you tried cvm_div? Some japanese program.
## Post #5
- Username: DOTAPRINCE
- Rank: veteran
- Number of posts: 133
- Joined date: Tue May 17, 2011 1:17 pm
- Post datetime: 2011-09-14T15:34:11+00:00
- Post Title: Another CVM!!!

Have you tried naruto shippuden ultimate ninja 5 cvm too?
I think it's compressed too since I can't extract with the same method..
## Post #6
- Username: Satoh
- Rank: mega-veteran
- Number of posts: 194
- Joined date: Sat May 09, 2009 10:07 pm
- Post datetime: 2011-09-14T18:23:38+00:00
- Post Title: Another CVM!!!

Have you tried Hackstract on it to see if it uses the same CVM format hackstract recognizes?

I vaguely recall there being another program that extracts CVM but I can't remember what it is.

If you can open it in hackstract, you should be able to dump the folders it finds.
## Post #7
- Username: McCuñao
- Rank: veteran
- Number of posts: 101
- Joined date: Sat Apr 22, 2006 8:49 pm
- Post datetime: 2014-02-15T10:44:06+00:00
- Post Title: Another CVM!!!

> Reply from chrrox
>
> yakuza files are compressed no one knows the compression they use so extracting the cvm wont help.

Sorry for the necropost, but, they're compressed inside the CVM, which is also encrypted? Some friends of mine found the password for both games (In order to use the cvm_tool), and we're trying to repack it with no luck (Probably because we're using mkisofs and not something that can mimic the original header).

EDIT: We'll, we've managed to repack files but only when we do not change filesizes. Everything goes Boom if we do so. I suspect it's related to the fact that the CVMs are paired to *DIR*.BINs, which seem to be a table of contents of the ISO. Problem is, the folders are visible, but the filenames are not. Seems to be compressed with something, with the header AVLZ. Anyone can help?

Also, the OGREs are file containers so this should go into the proper section.
## Post #8
- Username: Panzah
- Rank: advanced
- Number of posts: 62
- Joined date: Thu Jul 22, 2010 5:11 am
- Post datetime: 2014-12-07T23:09:08+00:00
- Post Title: Another CVM!!!

Necropost, but does anyone know the password for Yakuza 1 CVMs?
## Post #9
- Username: zetper
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Aug 23, 2014 2:39 am
- Post datetime: 2015-01-24T12:42:01+00:00
- Post Title: Another CVM!!!

> Reply from Panzah
>
> Necropost, but does anyone know the password for Yakuza 1 CVMs?
Нello Panzah password qi2o@9a! for Yakuza 1 and 2 CVM
cvm_tool.exe split -p qi2o@9a! OGRE4.CVM OGRE4.iso OGRE4.hdr
## Post #10
- Username: BL4CK0UT
- Rank: beginner
- Number of posts: 25
- Joined date: Mon Jul 13, 2015 7:08 am
- Post datetime: 2018-10-01T04:08:16+00:00
- Post Title: Another CVM!!!

> Reply from zetper
>
> Panzah wrote:Necropost, but does anyone know the password for Yakuza 1 CVMs?
Нello Panzah password qi2o@9a! for Yakuza 1 and 2 CVM
cvm_tool.exe split -p qi2o@9a! OGRE4.CVM OGRE4.iso OGRE4.hdr

Error opening 'data.cvm for reading..

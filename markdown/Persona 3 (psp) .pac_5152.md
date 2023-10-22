## Post #1
- Username: darkluap
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Oct 04, 2010 8:04 am
- Post datetime: 2010-10-07T06:11:36+00:00
- Post Title: Persona 3 (psp) *.pac

Hi, I unpacked the iso and many find the files to achieve
3d models, but I could not unzip files pac format.

in those files are the gmo, someone help me or guide to accomplish this, it would be very grateful.

thanks for reading, bye!
## Post #2
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2011-04-21T14:09:05+00:00
- Post Title: Persona 3 (psp) *.pac

> Reply from darkluap
>
> Hi, I unpacked the iso and many find the files to achieve
3d models, but I could not unzip files pac format.

in those files are the gmo, someone help me or guide to accomplish this, it would be very grateful.

thanks for reading, bye!
Seems we got the same problem  dude, but where're your samples?
## Post #3
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-07T09:17:55+00:00
- Post Title: Persona 3 (psp) *.pac

I could not unzip files *.pac too.
attached sample.
<sorry, It deleted.>
## Post #4
- Username: Rick
- Rank: Moderator
- Number of posts: 388
- Joined date: Wed Aug 10, 2005 5:10 am
- Post datetime: 2011-07-07T09:45:09+00:00
- Post Title: Persona 3 (psp) *.pac

Code to unpack is available on my Atlus repository: [http://svn.gib.me/public/atlus/trunk/](http://svn.gib.me/public/atlus/trunk/)
## Post #5
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-08T03:39:43+00:00
- Post Title: Persona 3 (psp) *.pac

Thanks,Rick!!
But.. I have no idea what to do.
I tried open your files at MS Visual Studio 2010.
but dialoged "cannot open,because different version".
I have no idea what to do.

and I could some model(GMO files) rip with gitMO from *.pac files. but they have no textures...
I want to extract textures. 

Sorry for my poor English.　I hope you'll understand.
[model-pack-bc063.pac-preview.jpg](https://xentaxbackup.github.io/file/4454_model-pack-bc063.pac-preview.jpg)
## Post #6
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-11T07:10:49+00:00
- Post Title: Persona 3 (psp) *.pac

YATTA!!
I learned extractable file type from reading Rick's code.
Fortunately,I can found tm2(headed "TIM2") file from pac.

Thanks a million, Rick.  
[bc063_textured.jpg](https://xentaxbackup.github.io/file/4467_bc063_textured.jpg)
## Post #7
- Username: szfzafa
- Rank: advanced
- Number of posts: 56
- Joined date: Sun Feb 27, 2011 6:46 pm
- Post datetime: 2011-07-23T15:17:37+00:00
- Post Title: Persona 3 (psp) *.pac

Thanks to Rick's code and thanks to porimac's hint.
I'd never learnt C# but I wanted the models, and I almost made it through.
But they look..sort of..sniffy.. in MS3d.



pppppppppp.jpg (15.77 KiB) Viewed 376 times


Hi, porimac, u must be using Metaseq to import .GMO and .tm2.
Did u wrote an importer plugin for Metaseq on ur own?
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-07-23T15:42:33+00:00
- Post Title: Persona 3 (psp) *.pac

noesis can convert these formats.
## Post #9
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-07-23T17:08:28+00:00
- Post Title: Persona 3 (psp) *.pac

Hi,szfzafa!

> Did u wrote an importer plugin for Metaseq on ur own?
As Mr.chrrox say,I use Noesis.

> But they look..sort of..sniffy..
It's so hard...
I used this tool to extract *.tm2 files.

[http://www.geocities.jp/noretales/tool.html](http://www.geocities.jp/noretales/tool.html)

..This Tool made by Japanese, myself included.
I hope this isn't too awkward for you.

How To use it,
1. drug and drop .pac file to edamame_aru.exe
2. type TIM2(header word)
3. type tm2(extension name)

look my attachments picture!   

thanks.
[edamame_aru.jpg](https://xentaxbackup.github.io/file/4531_edamame_aru.jpg)
## Post #10
- Username: butT
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Aug 01, 2011 1:21 pm
- Post datetime: 2011-08-02T04:08:08+00:00
- Post Title: Persona 3 (psp) *.pac

How extactly are you suppose to read the code on unpacking the pac? Ive been able to extract the tm2s but that is it.
## Post #11
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-02T04:23:56+00:00
- Post Title: Persona 3 (psp) *.pac

I used GitMO for extract GMO files.
[http://www.richwhitehouse.com/index.php ... nary/Media](http://www.richwhitehouse.com/index.php?content=inc_projects.php&showcat=Binary/Media)
Noesis supported GMO,TM2.
[http://oasis.xentax.com/](http://oasis.xentax.com/)
You can convert any formats!
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2011-08-02T08:17:59+00:00
- Post Title: Persona 3 (psp) *.pac

Noesis is a beautiful piece of work like that, it simplifies a lot of these matters. It also intrigues me that they use GMO instead of a proprietary format. Lately Atlus has been using NIF and GMO it seems.
## Post #13
- Username: porimac
- Rank: VIP member
- Number of posts: 109
- Joined date: Wed Sep 08, 2010 11:46 pm
- Post datetime: 2011-08-02T10:03:33+00:00
- Post Title: Persona 3 (psp) *.pac

> Reply from Darkfox
>
> It also intrigues me that they use GMO instead of a proprietary format. Lately Atlus has been using NIF and GMO it seems.
I think there might be convenience of the "Subcontract developer".
They were using RMD in the former work,"Persona 3 (PS2)".

## Post #1
- Username: xFlasH
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-04-25T09:07:59+00:00
- Post Title: Westwood

Hi all.

I had been searching such a tool for a long time. What a great one!
However, I would appreciate the Westwood .PAK format file would be included by your software.
It's mainly used in the good old from the 90's : Lands of Lore, Kyrandia 1,2, 3, C&C, RedAlert....
I know there are some differences in the format between the games.
But I don't know more 

Thanks a lot for your help.

xFlasH
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T10:54:37+00:00
- Post Title: Westwood

Noted. I will see if I can get hold of a plugin that will enable access to those. There are, I guess, already quite a few extractors for those.
## Post #3
- Username: xFlash
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 25, 2005 8:59 pm
- Post datetime: 2005-04-25T13:06:59+00:00
- Post Title: Westwood

> Reply from Mr.Mouse
>
> Noted. I will see if I can get hold of a plugin that will enable access to those. There are, I guess, already quite a few extractors for those.

Yes.   It's a pity.
I've just found one of them (Dragon Unpacker), but it doesn't do the complete extraction job.
And more, the picture it extract are in a specific westwood format that it couldn't parse. 

Do you need some sample file ?

Thanks for your help.

xf
## Post #4
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-25T13:26:19+00:00
- Post Title: Westwood

Hey,

Yes, if you could supply us with some archives it will help us out.

Thanks.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T14:04:11+00:00
- Post Title: Westwood

Yes, that would be great. Some nice, juicy sample files.
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T14:23:08+00:00
- Post Title: Westwood

Also: 

check 

[http://xccu.sourceforge.net/](http://xccu.sourceforge.net/)

This may just be what you are looking for.
## Post #7
- Username: xFlash
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 25, 2005 8:59 pm
- Post datetime: 2005-04-25T21:59:19+00:00
- Post Title: Westwood

Thanks for your fast answers ^_^
I already knew XCCMixer. It can do some extraction, but not all, and some of the files include aren't extractable. And some other make the soft crash ....
XCCMixer has be done for softwares as the C&C series C&C 1, 2 RA 1, 2 ... but not for the older ones as "Lands of Lore" or "Kyrandia"

You can download [here](http://burnsclub.free.fr/misc/CHAPTER1.zip) a .PAK file sample. You can easily extract its contents with XCC. But some of the results files are unreadible and it's where your science could greatly help me ;p

xf

PS: xcuses for my poor english. I'am french :-'
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-25T22:13:57+00:00
- Post Title: Westwood

I have no problem with the French, two Frenchmen play in my band (bass and solo-guitar).     Just make sure you forget about party-politics and still vote a 'Yes'  for Europe, in the coming referendum.   

Thanks for the file.  

And here's a BMS script you can use to extract the contents of that PAK file. 

Just "Use Custom BMS" in MultiEx Commander.

The script itself:

```
SavePos ST 0 ;
GoTo EOF 0 ;
SavePos E 0 ;
Math E += 1 ;
GoTo ST 0 ;
Do ;
SavePos FOO 0 ;
Get FO Long 0 ;
Get FN String 0 ;
SavePos NE 0 ;
Get FE Long 0 ;
Set D Long FE ;
Math FE -= FO ;
Log FN FO FE FOO 0 ;
GoTo NE 0 ;
While D <> E ;

```

[pak.zip](https://xentaxbackup.github.io/file/188_pak.zip)
## Post #9
- Username: xFlash
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 25, 2005 8:59 pm
- Post datetime: 2005-04-25T23:45:19+00:00
- Post Title: Westwood

OK The PAK extraction part has been done, but what about the gfx/sfx files read?
My goal is to grab from those .PAK file some of the original GFX files.
In this .PAK (chap1) you can find :
CPS : Apparently a GFX format. XCCMixer is able to read them.
FRE : French string table. XCCMixer is able to read it but in a compressed way. How to inflate it ?
SHP: GFX File, but i've never find a software which can read it 
WSA: Animation GFX File. XCC Mixer is sometimes able to read it
ADL : ???
C55/TIM : ??? Always begin with a "FORM" string in hexa
DAT : ???
DAT : ???
C55 : ???
VCN : ???
VMP : ???
XMI : ??? Musics ?
XXX : ???
INF :  ???  
...

A great "Merci" for your help so !!!

xf
## Post #10
- Username: xFlash
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Apr 25, 2005 8:59 pm
- Post datetime: 2005-04-27T17:30:17+00:00
- Post Title: Westwood

Hi

Any idea how to read the 
SHP and WSA files. I think it's here where the GFX are stored

xFlasH
## Post #11
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-04-28T02:48:18+00:00
- Post Title: Westwood

Um, not really, I did take a bit of a look at them but didn't notice anything that would suggest any compression or whatever was used. There is a good chance though that the SHP files used in these older games are the same or similar to the SHP files in more recent games such as Simcity4 - I will try to take a look at it.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-04-28T06:10:21+00:00
- Post Title: Westwood

They are different from the standard RA2+ SHPs used by Westwood. 

Are compressed pictures. But not like the others.
## Post #13
- Username: DK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 04, 2005 3:54 pm
- Post datetime: 2005-07-04T14:47:02+00:00
- Post Title: Westwood

Hello,
interesting forum,
lot of informations here,
hope to give my little contribute 

For now, you can try my "test" version of a tool to explore (edit? maybe in the future...) the old Westwood games (EoB, LoL, Kyrandia, Dune)
[http://www.pollodigomma.net/iagtg/westpak2.exe](http://www.pollodigomma.net/iagtg/westpak2.exe)

I've other specs (VCN, EMC, INF, ecc.) but need more work.

See ya,
DK
## Post #14
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-04T14:51:25+00:00
- Post Title: Westwood

> Reply from DK
>
> Hello,
interesting forum,
lot of informations here,
hope to give my little contribute 

For now, you can try my "test" version of a tool to explore (edit? maybe in the future...) the old Westwood games (EoB, LoL, Kyrandia, Dune)
http://www.pollodigomma.net/iagtg/westpak2.exe

I've other specs (VCN, EMC, INF, ecc.) but need more work.

See ya,
DK

Nice! You know, why not include it at the WIKI? We can also host the file for you. 

[http://wiki.xentax.com/index.php/Game_Tools](http://wiki.xentax.com/index.php/Game_Tools)

You can edit those pages, as it's a WIKI. If you need a host, just let me know and I will update any link you put in there to the tool.

PS. Love the Blue Tentacle avatar
## Post #15
- Username: DK
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Jul 04, 2005 3:54 pm
- Post datetime: 2005-07-04T20:14:50+00:00
- Post Title: Westwood

> Nice! You know, why not include it at the WIKI? We can also host the file for you.
Thanks, but the tool isn't ready yet; I must fix/change something and write some little help/docs 
Hope to add it soon to the WIKI, and maybe add some files spec I have.

For the hosting, I already have it and prefer to put a link here, so I can update only in one place 

Bye,
DK
## Post #16
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-07-04T20:49:50+00:00
- Post Title: 

> Reply from DK
>
> 
Thanks, but the tool isn't ready yet; I must fix/change something and write some little help/docs 
Hope to add it soon to the WIKI, and maybe add some files spec I have.

For the hosting, I already have it and prefer to put a link here, so I can update only in one place 

Bye,
DK

Yep, good to have it at one place, so you have full control! Allright, the community eagerly awaits the entry at the WIKI    !

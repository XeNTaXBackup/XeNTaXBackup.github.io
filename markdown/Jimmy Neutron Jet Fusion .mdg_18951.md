## Post #1
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2018-10-19T15:48:07+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

This game is made by Krome Studios and uses a similar format to games like Blade Kitten, Star Wars: The Force Unleashed and Hellboy: Science of Evil, three games I've seen people make tools for.

[https://puu.sh/BKpQp.zip](https://puu.sh/BKpQp.zip)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-20T09:36:52+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

> Reply from lemurboy12
>
> This game is made by Krome Studios and uses a similar format to games like Blade Kitten, Star Wars: The Force Unleashed and Hellboy: Science of Evil, three games I've seen people make tools for.dunno, which guys you're talking of. The one I remember dealing with PS2 models is furryfan, creator of worldfamous Wildarms3  bms script which noone could read except himself (and me  ). Anyways, he knew what he did, I'm very sure, but sadly the wiki he used, is gone but his knowledges remain, partially, so I can present a point cloud at least (where the face indices are hard to track with this format; in some cases auto created triangle strips would do):



Calamibot.jpg (28.83 KiB) Viewed 143 times


But, is that a Calamibot, that's the question.
## Post #3
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2018-10-20T15:36:16+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

> Reply from shakotay2
>
> lemurboy12 wrote:This game is made by Krome Studios and uses a similar format to games like Blade Kitten, Star Wars: The Force Unleashed and Hellboy: Science of Evil, three games I've seen people make tools for.dunno, which guys you're talking of.
[viewtopic.php?f=16&t=15853](http://forum.xentax.com/viewtopic.php?f=16&t=15853)
[viewtopic.php?f=16&t=14903](http://forum.xentax.com/viewtopic.php?f=16&t=14903)
[viewtopic.php?f=16&t=5098](http://forum.xentax.com/viewtopic.php?f=16&t=5098)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-20T16:14:57+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

> Reply from lemurboy12
>
> viewtopic.php?f=16&t=15853
viewtopic.php?f=16&t=14903
viewtopic.php?f=16&t=5098Thanks!
The last link is useless for our needs here, since it's Blade Kitten for PC, isn't it?
The format in the first linked thread Hellboy: SoE is from PS3, face indices are easy to track as can be seen by AceWell's extraction.

SW Force Unleashed uses WII, MDG formats, they seem to be similar to PS2, will have a look at.

A format that is indeed nearly the same is from SotC:
[viewtopic.php?f=16&t=18905](http://forum.xentax.com/viewtopic.php?f=16&t=18905)
## Post #5
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-20T17:12:48+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

well. to bad it's ps2 only. for pc you'd have a load of choices which mdl/mdg extractor you wanna use.

it sure looks like sotc format. 0x[count] and 0x6[datatype] flags on the strip data.
## Post #6
- Username: lemurboy12
- Rank: veteran
- Number of posts: 119
- Joined date: Fri Mar 30, 2012 11:56 pm
- Post datetime: 2018-10-20T18:36:14+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

There's also a GameCube version, here's some samples from that:
[https://puu.sh/BOcUM.zip](https://puu.sh/BOcUM.zip)
## Post #7
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-20T19:33:24+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

> Reply from lemurboy12
>
> There's also a GameCube version, here's some samples from that:
https://puu.sh/BOcUM.zip

I would say 'forget about that'.  that seems packed. i don't like figuring out compression algos. and... isn't the cube a big endi? i'm not gonna try to read that. float maybe but pointers get confusing. ugh.
## Post #8
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-20T20:19:37+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

well, result on a quickhack (had to delete dozens of infinite floats and QNANs):



a_Calamibot_Gamecube.png (13.58 KiB) Viewed 117 times


Looks more like a bot.
(big endian floats, yes)
here's the code from my Make_obj project (very ugly, I know, just to show the principle):

```
{
	char *pFBuf, pTmp[4] ;
	int i, l ;			//, nValue[12]
	DWORD j, k ;
    float *pFloat, *pFloatBE ;
	float fData = 0.0f ;    // , XYZPos

	pFBuf = (char *) lpFBuf ;
	pFBuf += dwStart ;	j= dwStart ;

	pFloatBE= &fData ; pFloat= &fData ;
    if (bBigE)
    for (k=0;k < dwVertsCnt;k++) {
		fprintf( stream, "v ") ;
        for (i=0;i<3;i++) {
            for (l=0;l<4;l++) pTmp[3-l]= *(pFBuf+l) ;
            pFloatBE= (float*) pTmp ;
			fprintf( stream, "%f ", *pFloatBE) ; pFBuf += 4 ; j+= 4 ;
		}
		fprintf( stream, "\n") ;
		pFBuf += vStride-12 ; j += vStride-12 ;
	}
	else for (k=0;k < dwVertsCnt;k++) {
		fprintf( stream, "v ") ;
        for (i=0;i<3;i++) {
			pFloat = (float*) pFBuf ;
			fprintf( stream, "%f ", *pFloat) ; pFBuf += 4 ; j+= 4 ;
		}
		fprintf( stream, "\n") ;
		pFBuf += vStride-12 ; j += vStride-12 ;     // this line was missing in releases prior to 7-3-2018
	}
}
```
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-20T21:02:47+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

some slight modification to the code and adding of tri stripped face indices (2 meshes at the right side of pic) results in this:



autocreated_ugly_versa_cool.png (109.13 KiB) Viewed 115 times


Some extra faces to be deleted manually.

(infinites and QNANs resulted from "random(?) zeroes" not being skipped)
## Post #10
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-10-20T23:30:24+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

good things. is this based on the ps2 or cube data tho? if you do the cube, i'm out. fine to me. have at it.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-21T08:05:12+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

it's the Gamecube data but for PS2 it's similar.

@lemurboy12: very good idea to provide the Gamecube samples!  
The code to convert it to obj gave me the idea to try PS2 again. Though, for PS2 I've got 5761 vertices only (Gamecube: 6119).
Dunno why there's a difference?

calamibot, PS2:



a_calamibot-PS2.png (38.26 KiB) Viewed 100 times


(need to find uvs for Gamecube before I can upload the tool)
## Post #12
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-21T14:24:30+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

uvs for gamecube mdg; not perfect (the ones of  the  main body are awful) but maybe a starting point:



a_calamibot_Gamecube-uvs.png (140.09 KiB) Viewed 95 times
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-10-21T20:40:15+00:00
- Post Title: Jimmy Neutron Jet Fusion .mdg

Using Acewell's links to Zheneq's Noesis script from here
[viewtopic.php?f=10&t=17614&p=137391&hil ... eq#p137391](http://forum.xentax.com/viewtopic.php?f=10&t=17614&p=137391&hilit=+Zheneq#p137391)
I got the GameCube tex loaded with some slight header modification:



JimmyNeutron-GameCube-tex.png (76.08 KiB) Viewed 86 times

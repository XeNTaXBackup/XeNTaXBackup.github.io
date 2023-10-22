## Post #1
- Username: kalil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2011 10:18 am
- Post datetime: 2011-04-17T02:33:44+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-04-17T07:05:57+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

No point, the game use UE3, just wait till 19 or after and gildor will update his uModel and you can get it. Hes not going to update the app till the official release date.
## Post #3
- Username: kalil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2011 10:18 am
- Post datetime: 2011-04-20T21:01:54+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

Okay  
and Today is 20 *w*
## Post #4
- Username: CMihai
- Rank: veteran
- Number of posts: 131
- Joined date: Sun Jul 05, 2009 7:58 pm
- Post datetime: 2011-04-20T22:44:25+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

[http://www.gildor.org/smf/index.php/top ... 1.html#new](http://www.gildor.org/smf/index.php/topic,775.msg6981.html#new)

Looks like gildor is having some problems   He only got the textures by now...
## Post #5
- Username: brienj
- Rank: VIP member
- Number of posts: 288
- Joined date: Mon May 02, 2005 8:48 pm
- Post datetime: 2011-04-20T22:46:32+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

Well thanks for the model regardless, so I can make it playable on the 360.
## Post #6
- Username: firsak
- Rank: advanced
- Number of posts: 64
- Joined date: Wed Dec 16, 2009 7:32 pm
- Post datetime: 2011-04-21T08:32:37+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

Gildor reversed the format. 
No skeletal mesh support for PS3, unfortunately.
## Post #7
- Username: logansan25
- Rank: veteran
- Number of posts: 138
- Joined date: Mon Oct 04, 2010 8:15 am
- Post datetime: 2011-04-21T12:02:47+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

> Reply from firsak
>
> Gildor reversed the format. 
No skeletal mesh support for PS3, unfortunately.

Kratosssssssss!!!!!!! Nooooooooooooooooooooo!!!!!!!!!!!!!
## Post #8
- Username: kalil
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sun Apr 17, 2011 10:18 am
- Post datetime: 2011-04-21T14:43:39+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

X_X 
OMg The Textures 
i have a kratos from god of war 2 but im not have the textures x_x(and its not very good for the textures u.u)
mmm
The model can´t be extracted? (for other games or others things )
(sorry for my english x_x)
## Post #9
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-04-23T06:55:39+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

Kalil,


I have every file from the Kratos.XXX archive with thanks to gildor's Unreal Package Extractor. I believe kratos's model is in a file called CHAR_Kratos-a9de1b13.Package.


it is in .Package format apparently and i have no idea how to convert it.
## Post #10
- Username: shadowmoy
- Rank: veteran
- Number of posts: 153
- Joined date: Sat Feb 21, 2009 9:29 pm
- Post datetime: 2011-04-25T13:40:43+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

this is not unreal skeletalmesh but a custom ps3 viftag format , just like ps2 vifinfos, each mesh part is splitted in a rendercall block to push a certain amount of vertices to the vertex unit just like in this bleach soul ignition ps3 game :


so the vertex don't use any indices here, they just come in order, i will try to do a quick export of it   

each block section start with :

```
then you got 2 word :
datacount
unknow
then the data array ...

```


also i noticed  quickly the vertex size is 23 bytes each :
xyz as sshort
etc...
## Post #11
- Username: CodeMan89
- Rank: advanced
- Number of posts: 70
- Joined date: Wed Jun 16, 2010 8:04 pm
- Post datetime: 2011-05-06T03:00:09+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

does anyone know how to convert .package files within the .XXX file? I too am trying to get the model of kratos.
## Post #12
- Username: plodtrew
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Wed Jul 18, 2007 2:14 pm
- Post datetime: 2011-05-16T14:57:34+00:00
- Post Title: Kratos(God of war 3) from Mortal Kombat 9 (PS3)

At the moment only Gildor know hows to import psa/psk model files using his actorx plugin for 3dsm. The ps3 version of the models are not supported in his app at this stage. 

The formats are also different between consoles, tried putting kratos into the 360 version but the game doesn't load the model.

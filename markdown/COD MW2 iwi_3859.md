## Post #1
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-11-11T19:13:18+00:00
- Post Title: COD MW2 iwi

hm, i have tested the old converter from cod4, but they changed the file, ive played a little with the file like replace the first 27 bytes with the bytes from a file of cod4, so the coverter works but the output file is a little strange, the pic looks not bad but i think the size is not optimized, like inputfile 6xx kb and my output is 4 mb

[http://www.xup.in/dl,28283119/smith_inst_col.iwi/](http://www.xup.in/dl,28283119/smith_inst_col.iwi/)
## Post #2
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2009-11-12T11:34:24+00:00
- Post Title: COD MW2 iwi

They don't like modding textures or maps, like: 
[http://bashandslash.com/index.php?optio ... Itemid=111](http://bashandslash.com/index.php?option=com_content&task=view&id=739&Itemid=111)

> The lack of dedi servers would be a death blow to our modding community. You cannot have matchmaking AND run different mods, it just wouldn't work
..

> Matchmaking Benefits:
>
> 
>
>         * Locking down the game would keep IW in firm control over its own intellectual property and artistic direction. Benefit would be all Activision/IW.
>
>         * Preventing game modding could prepare us for a subscription model and would IW to charge for PC DLC, given that everyone is running the same game and they would have essentially killed off the PC modding community. Benefit would be all Activision/IW.
>
>         * One PC game would mean one (albeit, still small) community...right now PC Call of Duty means many games and very tiny communities.
## Post #3
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2009-11-12T23:17:48+00:00
- Post Title: COD MW2 iwi

remove the second DWORD (5th to 8th byte) and use the old iwi2dds utility

they added 4 bytes, not sure what they are for. values i found often:

40 03 00 00
40 01 00 00
41 01 00 00

73 01 00 00
70 03 00 00

03 03 00 00
00 00 04 00


you might be interested into this:

Quote: Gagarin @ RGN Forums

> my friend sERGE-002 create somethink like plugin for standart iwi2dds.exe which allowing u to convert .iwi to .dds for MW2
>
> 
>
> it's a plugin so both files must be in one folder. it's simply worked with drag&drop method (like iwi2dds) but can be used with console :
>
> 
>
> iwimw2dds <iwi> [<out_dir>]
>
> 
>
> <iwi> - .iwi file name or file mask 
>
> [<out_dir>] - ouput file directory. If not set, converted file goes to same folder with iwi2dds
>
> 
>
> examples :
>
> 
>
> iwimw2dds weapon_commando_knife_col.iwi
>
> iwimw2dds *.iwi d:\dds
>
> 
>
> 
>
> DOWNLOAD
>
> 
>
> surely it's temporary tool. I hope someone create more practical tool. We need dds2iwi for MW2 too :wink2:
>
> 
>
> Enjoy !
## Post #4
- Username: Cryptonia
- Rank: advanced
- Number of posts: 46
- Joined date: Thu Aug 20, 2009 12:11 am
- Post datetime: 2009-11-13T23:59:11+00:00
- Post Title: COD MW2 iwi

> Reply from CoDEmanX
>
> remove the second DWORD (5th to 8th byte) and use the old iwi2dds utility

they added 4 bytes, not sure what they are for. values i found often:

40 03 00 00
40 01 00 00
41 01 00 00

73 01 00 00
70 03 00 00

03 03 00 00
00 00 04 00


you might be interested into this:

Quote: Gagarin @ RGN Forums
my friend sERGE-002 create somethink like plugin for standart iwi2dds.exe which allowing u to convert .iwi to .dds for MW2

it's a plugin so both files must be in one folder. it's simply worked with drag&drop method (like iwi2dds) but can be used with console :

iwimw2dds <iwi> [<out_dir>]

<iwi> - .iwi file name or file mask 
[<out_dir>] - ouput file directory. If not set, converted file goes to same folder with iwi2dds

examples :

iwimw2dds weapon_commando_knife_col.iwi
iwimw2dds *.iwi d:\dds


DOWNLOAD

surely it's temporary tool. I hope someone create more practical tool. We need dds2iwi for MW2 too :wink2:

Enjoy !

cool works but a problem, normal does the tool only a header change, but why is inout iwi 10 mb, output dds only 8 mb?


and a file who cant be convertet

[http://www.xup.in/dl,15847026/loadscree ... hrise.iwi/](http://www.xup.in/dl,15847026/loadscreen_mp_highrise.iwi/)
## Post #5
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2009-11-15T21:15:09+00:00
- Post Title: COD MW2 iwi

well I use a tool by a friend to remove the second dword, but you can also use any hex editor. afterwards i convert the iwi using Regolith's latest IWI_X_DDS.

loadscreen_mp_highrise:
2,764,828 byte - iwi (in)
2,764,928 byte - dds (out)

[http://www.xup.in/dl,18960454/loadscree ... hrise.dds/](http://www.xup.in/dl,18960454/loadscreen_mp_highrise.dds/)

works fine for me
## Post #6
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2009-11-22T22:25:14+00:00
- Post Title: COD MW2 iwi

Hello people,

I'm skin modder and i would like to change the camo pattern from Ghost roach soap etc...

I saw here that you can get the iwi converted to dds.

But could you explain me how you remove dword or with the hex editor cause i don't understand how you do it ?

Please
## Post #7
- Username: ulukai
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Mon Nov 23, 2009 2:59 am
- Post datetime: 2009-11-28T17:09:41+00:00
- Post Title: COD MW2 iwi

somebody know a little prog like iwi_x_dds but for inverse processus ?

iwi_x_dds work for modern warfare 2 but now just need the inverse   

Any idea ?
## Post #8
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2009-12-08T00:06:15+00:00
- Post Title: COD MW2 iwi

you can't really mod mw2 anyway, so why bother with dds to iwi conversion?
## Post #9
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2009-12-10T18:22:25+00:00
- Post Title: COD MW2 iwi

The contents of this post was deleted because of possible forum rules violation.
## Post #10
- Username: tigershop
- Rank: beginner
- Number of posts: 20
- Joined date: Wed Nov 25, 2009 9:03 pm
- Post datetime: 2009-12-10T22:41:48+00:00
- Post Title: COD MW2 iwi

PLS Heeeeeeeeeeeelp Me !

Program -----------> dds->iwi
## Post #11
- Username: CoDEmanX
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 12, 2009 1:39 pm
- Post datetime: 2009-12-21T00:38:56+00:00
- Post Title: COD MW2 iwi

the game rejects custom content (tested by the most active CoD modders, RGN community), so what you need a dds2iwi tool for if you can't use the result? It might work if you modify the stock IWDs, but you can't play MP with altered IWD archives. And idk what a SP texture mod would be good for honestly :/

Unless IW releases some sort of mod tools we are screwed
## Post #12
- Username: evilpie
- Rank: beginner
- Number of posts: 23
- Joined date: Mon Nov 30, 2009 5:13 am
- Post datetime: 2010-01-21T17:34:37+00:00
- Post Title: COD MW2 iwi

Got CoD4 this week, so i will extend my work on that fileformat.
I've already edited the wiki last month, [http://wiki.xentax.com/index.php/Call_Of_Duty_2_IWI](http://wiki.xentax.com/index.php/Call_Of_Duty_2_IWI).

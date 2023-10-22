## Post #1
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2017-10-25T03:46:19+00:00
- Post Title: Resident Evil Dead Aim

Hi Everyone 

We were checking some days ago the files from this game all 3D stuff its on a File called "Image.bin" i managed to unpack that file 
with a fkp tool ones you do that you get "bin, dat snd and hlz files using the same tool over the first bin file wich its the one from
Bruce you get more bin files of them its called "pc01a.zone.bin#002.omm" that one have textures inside but not sure wich one its
the model data so will leave some samples from the files if its  required will upload more. 

[http://www.mediafire.com/file/jc4fi7ae7 ... amples.rar](http://www.mediafire.com/file/jc4fi7ae7embpe7/Samples.rar)
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-25T11:53:27+00:00
- Post Title: Resident Evil Dead Aim

looks familiar. cavia game. you could extract further til you get csf files and try those tools.

[https://ps23dformat.wikispaces.com/Ghos ... ne+Complex](https://ps23dformat.wikispaces.com/Ghost+in+the+Shell+Stand+Alone+Complex)

it's a later iteration of their files. i haven't tested them yet. will do later. 

edit: found my old tool stuff. i'd not mind if you could share this fpktool you use. it may be easier to use. and... we got some rubbish and a gun. all without textures coordinates tho.



is this lowpoly RE stuff worth looking further into this? something special you need?

i'd be all in rebooting this gitsac sp campaign. or master it. undub ofc.  /offtopic
## Post #3
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2017-10-26T02:45:40+00:00
- Post Title: Resident Evil Dead Aim

Hi

Thanks for the reply yea did test that ghost in the shell tool but i end with a lot of 3ds files wich have tons of missing stuff =/
for example model of bruce (like the screen above) its missing parts of his body same with fong ling of course all weapons are 
there but not uvs.

Sure this is the one i use [http://www.mediafire.com/file/yfumw375jzi9d1q/FPK.rar](http://www.mediafire.com/file/yfumw375jzi9d1q/FPK.rar)

Well will like to get all stuff from this game but heard that may have some cut scene models wich are better than the ingame ones.
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-26T13:46:09+00:00
- Post Title: Resident Evil Dead Aim

yeh. i'm on it. seems the submeshes fail right now. i dunno how to get the uvs yet. variable buffers. those may be flagged to reposition the reader. this bogus face array sure is a weirdo.

edit1: we gettin' there. slowly. i'm no daemon. it shoulda extracted everything but now blender spews some importer errors. excuse me that i got no idea how the 3ds format works. maybe it's stupid messing with that bms script.  but it's a lil progress.



now... a round of tv.

edit2: got the full body. the files are wonky. i noticed it contains more vertexbuffers then it said in the header. i did it manually. that's wrong tho. i'm sure there's some magic routine involved to get the correct count. that complicates things. i got the script pretty much translated and nailed tho. 



now... time for the bed.
## Post #5
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2017-10-27T03:25:43+00:00
- Post Title: Resident Evil Dead Aim

Oh man thats a nice progress you did there i wish i could help you more but only can help with samples and testing.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-27T15:43:03+00:00
- Post Title: Resident Evil Dead Aim

np. nice puzzle. and i'm sorta bored. tho... maybe you could find some sorta 'static prop' from this game. you could read the hex of the 1st image#xxx.bin at around offset 0x240 to figure path or file names. or if there's no skeleton, this CJF (c joint file) 'chunk' should be missing. i'd just like to verify the buffer format. means figuring out if i gotta implement a second code path for potentially boneless models. i don't wanna check with gits files. dunno why. differences possible?

i'll continue with 3ds then. gotta get the format and prepare for the uv disassembly and face array rearrangemant. good stuff. 

almost there. i'm can already sniff on the barrel.



i gotta recode to c and mangle this. it's a short bitch.
## Post #7
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-29T14:37:46+00:00
- Post Title: Resident Evil Dead Aim

done fuxed with bms.

you can * batch the csf folder. it outputs blender sorta nice. you gotta scale the uvs / 1024 and remove doubles to seperate the mesh parts, but works. maybe i'll tinker with it and recode it to c. i could try the skeleton too. but, for now...

have this temporary script. all i could get out of this one.

for posterity. lowpo snap mod added. i'd replace or retexture/remodel her head even further.


[RE_deadaim_3ds.rar](https://xentaxbackup.github.io/file/13503_RE_deadaim_3ds.rar)
## Post #8
- Username: CaxUchiha
- Rank: n00b
- Number of posts: 14
- Joined date: Tue Feb 23, 2016 5:57 pm
- Post datetime: 2017-10-31T11:37:41+00:00
- Post Title: Resident Evil Dead Aim

Thanks for your script episoder! It works well  Will you try the skeleton in the future? xD
## Post #9
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2017-10-31T12:15:41+00:00
- Post Title: Resident Evil Dead Aim

> Reply from CaxUchiha
>
> Thanks for your script episoder! It works well  Will you try the skeleton in the future? xD

i think not. it doesn't have alot of bones. just arms and legs. no fingers. a bit of jaw and no eyes. can and should be easy to rig this way, or better from scratch.
## Post #10
- Username: The Chief
- Rank: veteran
- Number of posts: 101
- Joined date: Fri Oct 09, 2009 10:44 am
- Post datetime: 2018-01-23T01:47:28+00:00
- Post Title: Resident Evil Dead Aim

Hi again espisoder, I managed to get more models from the game (like zombies and monsters) but seems the script didn't work with those.. Could you take a look at some of them please? Here are some samples:

[http://www.mediafire.com/file/e13r8b7by ... amples.rar](http://www.mediafire.com/file/e13r8b7by93av9g/Samples.rar)
## Post #11
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-01-23T05:43:56+00:00
- Post Title: Resident Evil Dead Aim

- snipped -
## Post #12
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2018-01-23T16:12:13+00:00
- Post Title: Resident Evil Dead Aim

hell yeah. the proper head loop wasn't that hard. the fpass are crisscross spaghetti conditions. i could barely assemble the reverse logic. sorta magic stuff. it's nice and compact tho. awesome sauce. 

enjoy your zombie 
[reda_csf23ds_v2.rar](https://xentaxbackup.github.io/file/13837_reda_csf23ds_v2.rar)

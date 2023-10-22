## Post #1
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2020-03-17T22:17:33+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

Hey everyone! 

I'm hoping someone might be able to help me out here, and possibly point me in the right direction to tools for the files in this game. 
Apparently it's running on the Orochi 3 Engine, which I couldn't find particularly much on in the usual places. At least not much useful. 
The array of giant monster models as well as character and environmental pieces is great so hopefully someone can help out. 

I've attached a link to the files I'm pretty sure are from Eva-01, from Neon Genesis Evangelion, but the game includes monsters from Godzilla, Gamera, Ultraman, Patlabor and so many more! 

Anyway, hopefully someone can take a look. I know there are meshes and textures in here using the .mdl and .tex formats but I'm unsure as to how to view them or get them into some sort of exportable state to mod into other games or use in Blender for renders.

Thanks for taking a look, hopefully someone can come up with something...

[https://mega.nz/#!jFATRSyI!5Z0gEOdeO6gU ... iQQlQYmFtE](https://mega.nz/#!jFATRSyI!5Z0gEOdeO6gU0UVN_S4agburRJ9mAb5tkiQQlQYmFtE)
## Post #2
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-18T00:00:22+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

Try RandomTBush's maxscript for World of Final Fantasy. It was also Orochi 3 if I remember correctly.
## Post #3
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2020-03-18T01:11:42+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

Thanks man! I will check it out!
## Post #4
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2020-03-18T02:00:40+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

Okay, so it looks like the textures work for the most part, but the .mdl files don't convert using using that script.
## Post #5
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-03-18T07:39:17+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

I believe you have decompressed them before trying, right? If not here is the script : [https://mega.nz/#!ft4X2CJI!FQUzhbEddKl3 ... P-KuRCX-r4](https://mega.nz/#!ft4X2CJI!FQUzhbEddKl312ELfUsC_4BT2fERwivbvP-KuRCX-r4)

I can't test the maxscript, but chrrox's noesis script seems to handle your samples well : [viewtopic.php?t=12688](https://forum.xentax.com/viewtopic.php?t=12688)
## Post #6
- Username: trexjones
- Rank: veteran
- Number of posts: 113
- Joined date: Mon Oct 13, 2014 1:54 pm
- Post datetime: 2020-03-18T22:08:15+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

Far out, I'm an idiot! Thank you!
## Post #7
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-07-31T18:20:08+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

The noesis script only works for a small number of models, most have index and overflow errors, same for the max script.

Additionally on some textures the WoF bms script seems to miss parts of the texture.


Full game samples [https://mega.nz/folder/rOAVEaLb#RqitpUM5oPg2d1gDGh0Iaw](https://mega.nz/folder/rOAVEaLb#RqitpUM5oPg2d1gDGh0Iaw)
E010 seems to be a good example of both issues.

Bunch of models that convert [https://mega.nz/folder/3PhAkapC#PkTLCYOq_TV3bkdp0fnpXw](https://mega.nz/folder/3PhAkapC#PkTLCYOq_TV3bkdp0fnpXw)
## Post #8
- Username: akderebur
- Rank: double-veteran
- Number of posts: 640
- Joined date: Fri Jul 08, 2011 5:36 pm
- Post datetime: 2020-08-01T14:23:49+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

> Reply from 09williamsad ↑Sat Aug 01, 2020 2:20 am at Sat Aug 01, 2020 2:20 am
>
> 
E010 seems to be a good example of both issues.

The attached script should work for that sample and possibly others too. Only problem is that it will probably produce lots of split meshes, but better than not splitting at all  Delete/remove other ".mdl" scripts before using this one.


[fmt_CITY_SHROUDED_IN_SHADOW_mdl.rar](https://xentaxbackup.github.io/file/18551_fmt_CITY_SHROUDED_IN_SHADOW_mdl.rar)
## Post #9
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-08-02T20:18:45+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

> Reply from akderebur ↑Sat Aug 01, 2020 10:23 pm at Sat Aug 01, 2020 10:23 pm
>
> 

The attached script should work for that sample and possibly others too. Only problem is that it will probably produce lots of split meshes, but better than not splitting at all  Delete/remove other ".mdl" scripts before using this one.

Thanks, I am reconverting now and it seems that the majority now convert, I will post a link with the converted models once they are done.
## Post #10
- Username: 09williamsad
- Rank: veteran
- Number of posts: 104
- Joined date: Sun Mar 13, 2016 9:09 pm
- Post datetime: 2020-08-03T19:08:31+00:00
- Post Title: CITY SHROUDED IN SHADOW (2018 - PS4)

Most of the games character models converted to FBX <Link removed due to site policy>

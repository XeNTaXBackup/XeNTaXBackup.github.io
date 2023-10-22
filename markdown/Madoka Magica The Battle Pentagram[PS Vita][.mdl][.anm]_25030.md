## Post #1
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-02-09T18:25:53+00:00
- Post Title: Madoka Magica: The Battle Pentagram[PS Vita][.mdl][.anm]

Noesis plugin for Madoka Magica: The Battle Pentagram[PS Vita]
opens models [.mdl] and animations [.anm]
During creation, was found a [plugin for blender 2.49](https://forum.xentax.com/viewtopic.php?f=16&t=17012&p=135953#p135953),which helped a lot.
Unpack .apk archive with using [this qbms script](http://aluigi.altervista.org/bms/dragon_ball_z_boz.bms) 

by default searchs  textures in the path: "..\texture\name.gxt"
(change it, edit line 251)
by default searchs  all animations in the path: "..\motions\name.anm"
(to change the path dir, edit line 124)

or to change method load animations:
(uncommentthe desired method and comment out all the others)
(if animations are not needed, comment out everything)

```
    line 114, "openAnim(animPath, animList, mdl.skeleton)"
-open one anim (Open File Dialog):
    line 117, "openDialogFile(animList, mdl.skeleton)"
-open all anim from dir (Open Folder Dialog):
    line 121, "openDialogFolder(animList, mdl.skeleton)"
-open all anim from dir:
    line 125, "openAllAnimFromFolder(animList, mdl.skeleton, animDir)"

```


judging by the *.tbl file, the game uses "ragdoll". so cloaks, cloth and hair are static.
[fmt_Madoka_PSVita.py](https://github.com/Durik256/Noesis-Plugins/blob/master/fmt_Madoka_PSVita.py)
[fmt_Madoka_PSVita.zip](https://xentaxbackup.github.io/file/21753_fmt_Madoka_PSVita.zip)
## Post #2
- Username: reh
- Rank: veteran
- Number of posts: 102
- Joined date: Tue Nov 17, 2015 6:18 am
- Post datetime: 2022-02-09T21:36:04+00:00
- Post Title: Madoka Magica: The Battle Pentagram[PS Vita][.mdl][.anm]

The script also works for Gundam Seed Battle Destiny PSVITA
## Post #3
- Username: kikiyiko
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun May 15, 2022 8:40 am
- Post datetime: 2022-05-15T01:42:49+00:00
- Post Title: Madoka Magica: The Battle Pentagram[PS Vita][.mdl][.anm]

Can you show me a guide on how to export the mdl's and anm's correctly? Sorry for asking
## Post #4
- Username: olivergray
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Nov 30, 2022 2:33 pm
- Post datetime: 2022-11-30T06:40:23+00:00
- Post Title: Madoka Magica: The Battle Pentagram[PS Vita][.mdl][.anm]

> Reply from reh ↑Thu Feb 10, 2022 5:36 am at Thu Feb 10, 2022 5:36 am
>
> 
The script also works for Gundam Seed Battle Destiny PSVITA

That's right, it works.[mapquest directions](https://mapquestdirectionss.com)
## Post #5
- Username: noblekeon
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Aug 24, 2023 9:47 am
- Post datetime: 2023-08-25T09:43:43+00:00
- Post Title: Madoka Magica: The Battle Pentagram[PS Vita][.mdl][.anm]

> Reply from reh ↑Thu Feb 10, 2022 5:36 am at Thu Feb 10, 2022 5:36 am
>
> 
The script also works for Gundam Seed Battle Destiny PSVITA

How do I properly export the mdls and anms, and do you have a tutorial to do so? My apologies for the intrusion

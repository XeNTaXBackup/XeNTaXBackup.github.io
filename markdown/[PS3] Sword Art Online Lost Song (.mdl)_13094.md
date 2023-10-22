## Post #1
- Username: ValarMorghulis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 23, 2015 9:07 pm
- Post datetime: 2015-07-23T13:55:20+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Hi everyone!
I need your help to rip SAO: Lost Song's models. I managed to extract files from *.apk using Dragon Ball Z: Battle of Z script for QuickBMS.
Textures are *.gtf - You can convert them to *.dds with [this program](http://forum.xentax.com/viewtopic.php?f=18&t=5164&start=15) (download JU57FL1P's RAR archive). Here there are Kirito's textures I converted: [click me](http://imgur.com/ZBzmIHy,2tIyFNo,I9mgvTz,oinO2jS,N6WObgB,5mpEl6b,bpI5lwk,pNshLXE)
Models are *.mdl - I tried some scripts for Noesis, but without success...

P.S. I'm not a programmer/scripter. I don't know anything about these things, so I can't contribute 

If you need samples, here you go: [SAO Lost Song samples.rar](http://www.mediafire.com/download/k7h5ml869hyh9gg/SAO+-+Lost+Song+samples.rar)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-07-23T19:05:08+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

the mesh format is not too hard but will take some time to build the submeshes automatically
so you'll need to find someone willing to do it



ch_asu_mdl_tex.JPG (79.11 KiB) Viewed 896 times
## Post #3
- Username: ValarMorghulis
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Thu Jul 23, 2015 9:07 pm
- Post datetime: 2015-07-23T21:36:27+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

> Reply from shakotay2
>
> the mesh format is not too hard but will take some time to build the submeshes automatically
so you'll need to find someone willing to do it
ch_asu_mdl_tex.JPG
 Woah, so cool!
Waiting for someone who's willing to do this
## Post #4
- Username: Cheshire1012
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 11, 2014 11:31 am
- Post datetime: 2015-08-10T11:37:28+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

I can extract models with using this tool.
[http://zenhax.com/viewtopic.php?f=9&t=4 ... ball#p2286](http://zenhax.com/viewtopic.php?f=9&t=426&hilit=dragon+ball#p2286)
but I miss some UVs of the image(especially an image of body and eyes). It is hard to remap these UVs.
Could anyone fix the problem?
[xx1_1.png](https://xentaxbackup.github.io/file/9505_xx1_1.png)
## Post #5
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2015-08-10T13:20:40+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Hi,
I just happened to find a solution for the missing/zeroed UVs today.

If you take a look at the MaxScript on line 504 you'll see, that the UVs are set to 0, because the script author did not find the UVs addresses

After some trial and error, I found out that the UV section starts 36 bytes after the vertices(0x24) for the "3c" type submodels.

* this does not fix the zeroed UVs for the eyes though( they are easy enough to be fixed by hand)


I've attached the fixed script.

One additional note, some models like Hildisvini or Heidrun can't be opened though.( They use some other submodel structure, than the rest, that isn't supported by the script)
There is a bug with the wing's UVs as well, where some UVs are only half the size( I have only found this bug with Cait Sith wings, so far) and other wings have horizontally inverted UVs(once again applies to Cait Sith, but also to Undine). Those bugs need to be fixed by hand for now.
[battle of godz_sao_ls_fix.zip](https://xentaxbackup.github.io/file/9506_battle of godz_sao_ls_fix.zip)
## Post #6
- Username: Cheshire1012
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 11, 2014 11:31 am
- Post datetime: 2015-08-10T15:38:44+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

> Reply from kurainooni
>
> Hi,
I just happened to find a solution for the missing/zeroed UVs today.

If you take a look at the MaxScript on line 504 you'll see, that the UVs are set to 0, because the script author did not find the UVs addresses

After some trial and error, I found out that the UV section starts 36 bytes after the vertices(0x24) for the "3c" type submodels.
* this does not fix the zeroed UVs for the eyes though( they are easy enough to be fixed by hand)


I've attached the fixed script.

One additional note, some models like Hildisvini or Heidrun can't be opened though.( They use some other submodel structure, than the rest, that isn't supported by the script)
There is a bug with the wing's UVs as well, where some UVs are only half the size( I have only found this bug with Cait Sith wings, so far) and other wings have horizontally inverted UVs(once again applies to Cait Sith, but also to Undine). Those bugs need to be fixed by hand for now.
Though it is easy to fix UVs for eyes,it is not perfect for art:(
guy u know some mismatches by hands would happen.
I cant actually make my lovely yuuki perfect.It seems to have some mismatches with anime:( 
If u could do little,I would be grateful.Is it possible to use your way to fix UVs for eyes?
I will try my hard too.
[xx2.png](https://xentaxbackup.github.io/file/9508_xx2.png)
## Post #7
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2015-08-10T18:06:48+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

It seems I was successfull again.



I honestly don't know, why the UVs for Sinons(Gun Gale Outfit) are making the eyes that large( could still be a bug, or the wrong offset), but the UVs for Yuuki's eyes look pretty decent. Other models should look alright.
Report back, if you found other problems with the script, other than the wings, and the integer bug that randomly occurs when starting up the script.
[battle of godz_sao_ls_fix_v1.1.zip](https://xentaxbackup.github.io/file/9509_battle of godz_sao_ls_fix_v1.1.zip)
## Post #8
- Username: Cheshire1012
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 11, 2014 11:31 am
- Post datetime: 2015-08-11T10:58:54+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Thank guys!:D
Finally I fix some coordinates of UVs and use some PS skills to match the original.
Another problem is that when I import weapons started with w letter in rom data,they have zero UV.
[xx3.png](https://xentaxbackup.github.io/file/9516_xx3.png)
## Post #9
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2015-08-11T13:00:40+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Hi there,

here is the next update.

So far the weapons are using the 0x34 structures, where the UVs were quick to find(the last 4 bytes of the structure)

If you find weapons with other structures( you'll notice the names for the models in 3ds Max are exactly the same as the Structure name without the "0x") it would help if you could state the structure name or at least the mesh name.

The common structure I've found are:
0x20( commonly used by the wings)
0x24( commonly used by the face and the hair)
0x28( used by the eyes)
0x34( for the weapons)
0x3c( commonly for clothing and other models with specular maps, like the monsters)

There are possibly more, but I couldn't find other ones yet, aside of Heidrun and Hildisvini, which are yet to be analyzed.
[battle of godz_sao_ls_fix_v1.2.zip](https://xentaxbackup.github.io/file/9517_battle of godz_sao_ls_fix_v1.2.zip)
## Post #10
- Username: anime663
- Rank: veteran
- Number of posts: 111
- Joined date: Mon Jun 04, 2012 8:45 am
- Post datetime: 2015-09-04T23:43:15+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Does anyone know where Lux's model files are? Can't seem to find em...
## Post #11
- Username: Trishty
- Rank: advanced
- Number of posts: 63
- Joined date: Mon Jul 05, 2010 9:37 pm
- Post datetime: 2015-09-08T17:15:08+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

I try Black Lotus in update 1.03, her body and eyes are missing UVs @@
[](http://s771.photobucket.com/user/trishty/media/Untitled7.png.html)
## Post #12
- Username: Xr79
- Rank: veteran
- Number of posts: 91
- Joined date: Sun Oct 06, 2013 6:45 am
- Post datetime: 2015-09-25T19:43:53+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

okay triple never mind. it is in the data rom.apk file, now I am at the uploading to blender part, I don't know how to use the .MS file, I have used .py scripts with blender before but not .ms, can you elaborate on how to use the importer?
## Post #13
- Username: Darko
- Rank: double-veteran
- Number of posts: 723
- Joined date: Tue Jul 14, 2009 1:16 am
- Post datetime: 2015-09-25T22:30:39+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

> Reply from Xr79
>
> okay triple never mind. it is in the data rom.apk file, now I am at the uploading to blender part, I don't know how to use the .MS file, I have used .py scripts with blender before but not .ms, can you elaborate on how to use the importer?

Maxscript??, open the script in 3dsmax (maxscript menu, go to maxscript editor, open the script and once is opened just press ctr+e or go to tools evaluate all).
## Post #14
- Username: kurainooni
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Mon May 21, 2012 10:37 pm
- Post datetime: 2015-10-07T16:43:21+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Hi, sorry for not posting for quite a while. I'm still trying to figure out how to fix the bug with Kuroyukihime's wings( the inlines to be precise).
Anyways, here is the updated script.
[battle of godz_sao_ls_fix_v1.4_pre.zip](https://xentaxbackup.github.io/file/9840_battle of godz_sao_ls_fix_v1.4_pre.zip)
## Post #15
- Username: Demonslayerx8
- Rank: veteran
- Number of posts: 99
- Joined date: Mon Jul 06, 2015 7:48 am
- Post datetime: 2015-12-04T05:16:40+00:00
- Post Title: [PS3] Sword Art Online: Lost Song (*.mdl)

Has anyone figured out how to get the bones yet? It would be pretty nice for posing and stuff.

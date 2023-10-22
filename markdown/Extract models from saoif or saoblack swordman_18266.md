## Post #1
- Username: bigsamaa
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Jun 21, 2018 5:32 pm
- Post datetime: 2018-06-21T09:43:13+00:00
- Post Title: Extract models from sao:if or sao:black swordman

how i extract models from Sword Art Online: Integral Factor or Sword Art Online: Black Swordsman

I try to extract model from SAO: BS but i got this files.



someone can help me ?

Example files : [https://drive.google.com/open?id=14QSmY ... ITf_aVJp7Z](https://drive.google.com/open?id=14QSmY-Gy_ae8Wc15dx_hc1ITf_aVJp7Z)

Sword Art Online: Integral Factor Link : [https://play.google.com/store/apps/deta ... nt.saoifww](https://play.google.com/store/apps/details?id=com.bandainamcoent.saoifww)

Sword Art Online: Black Swordsman Link : [http://www.9game.cn/game/downs_683560_2.html](http://www.9game.cn/game/downs_683560_2.html)

ps. sorry for my bad english
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-21T16:15:48+00:00
- Post Title: Extract models from sao:if or sao:black swordman

the signature in files is UnityFS so try Unity Assets Bundle Extractor (UABE) on ain_rabbit_001 for example (decompress).

Then load uncompressed file and in "Assets info" window choose a mesh for example and use "Export Raw" button.
Use hex2obj to get the mesh in the created .dat file displayed:



ain_rabbit_001.jpg (137.71 KiB) Viewed 171 times


(There may be simpler ways but I don't have the time to check.)

(mesh is type 43 in UnityEx)
## Post #3
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-06-21T19:42:28+00:00
- Post Title: Extract models from sao:if or sao:black swordman

instead of using "Export Raw" from UABE press "Plugins">"Export to .obj"
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2018-06-22T06:59:17+00:00
- Post Title: Extract models from sao:if or sao:black swordman

which version of UABE do you use?
v 1.0 exports negative faceindices:

# Faces (1 to 235)
f -233/-233/-233 -234/-234/-234 -235/-235/-235
f -235/-235/-235 -231/-231/-231 -232/-232/-232
f -231/-231/-231 -230/-230/-230 -232/-232/-232
f -229/-229/-229 -232/-232/-232 -230/-230/-230
f -235/-235/-235 -232/-232/-232 -228/-228/-228

luckily the blender wavefront importer seems to ignore the minus
## Post #5
- Username: riccochet
- Rank: advanced
- Number of posts: 47
- Joined date: Mon Aug 11, 2014 9:55 pm
- Post datetime: 2018-06-22T08:24:11+00:00
- Post Title: Extract models from sao:if or sao:black swordman

I've used Unity Studio on Integral Factor before and the models exported fine. Pretty sure it should work with the other game as well
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2018-06-22T08:35:07+00:00
- Post Title: Extract models from sao:if or sao:black swordman

> Reply from shakotay2
>
> 
v 1.0 exports negative faceindices...luckily the blender wavefront importer seems to ignore the minus
Negative indices are allowed in obj format. It's just referring from the last vertex before current line, though people don't usually use this method.
## Post #7
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2018-06-22T18:38:42+00:00
- Post Title: Extract models from sao:if or sao:black swordman

> Reply from shakotay2
>
> which version of UABE do you use?
version 2.2

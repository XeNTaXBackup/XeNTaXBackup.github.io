## Post #1
- Username: teoma
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 11, 2009 5:22 pm
- Post datetime: 2015-04-16T21:08:33+00:00
- Post Title: Aion cgf to Collada(remake script)

i dont want to bump old topic [viewtopic.php?t=3999&f=16](http://forum.xentax.com/viewtopic.php?t=3999&f=16) ,cause its too old noone is there anyway,
but the problem still remain unfixed - its impossible to convert all files in folder, as per each .cgf == .dae, cause now if you select all files in folder, and turn them in a loop(for), you get every single file .cgf(In folder) will be attached in new .dae, for example there is x1.cgf; x2.cgf;x3.cgf; when you make a loop like this

```
	for name in os.listdir("."):
		#if name.endswith(".cgf"):
		converter.AddMesh(name), r"%s\%s.cgf" % (meshPath,name))

```


all you get is x1.dae(normal), but x2=x1.cgf+x2.cgf = x2.dae, means mesh from first model is attach with second model(mesh) and thats not what should be !
I dont rly know python that much to be able to find where is that damn loop that makes that, and even if i find where it is i have no idea of how it could possibly be fixed, so please if someone can fix this ! please.
## Post #2
- Username: teoma
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Mar 11, 2009 5:22 pm
- Post datetime: 2015-04-17T12:36:45+00:00
- Post Title: Aion cgf to Collada(remake script)

anyway BIG thx to the Chrrox i finnaly maded that damn script!

if anyone wants i can share it, or if not just thx Chrrox!
## Post #3
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-04-17T20:59:03+00:00
- Post Title: Aion cgf to Collada(remake script)

> Reply from teoma
>
> anyway BIG thx to the Chrrox i finnaly maded that damn script!

if anyone wants i can share it, or if not just thx Chrrox!so good job dude, share it
## Post #4
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-10-31T11:41:40+00:00
- Post Title: Aion cgf to Collada(remake script)

we still waiting for your modification in script? why don't share it? ask for help and no help others?

## Post #1
- Username: nosuit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 18, 2015 10:16 am
- Post datetime: 2015-10-18T02:53:26+00:00
- Post Title: [HELP] Hitman (.weightedprim) Maxscript

I've been looking at the Hex for about a month now and I have no clue what i'm doing.
Help on writing a maxscript/converter for import/conversion of .prim models would be awesome.

Here's a simple box mesh, unweighted. 
[http://www.mediafire.com/download/k74sx ... im.pc_prim](http://www.mediafire.com/download/k74sxic14sfs30o/mockupgeom_box_a.prim.pc_prim)

Here's a more complex weighted mesh.
I can provide a .bonerig file on request, but it doesn't really matter about Weights and or Rigging.
[http://www.mediafire.com/download/8ctlu ... ightedprim](http://www.mediafire.com/download/8ctlu8ln3hzcmyc/head.pc_weightedprim)

Any help would be great, thanks!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2015-10-18T07:11:49+00:00
- Post Title: [HELP] Hitman (.weightedprim) Maxscript

> Reply from nosuit
>
> I've been looking at the Hex for about a month now and I have no clue what i'm doing.yeah, made my day!  Welcome to the club. 

> Help on writing a maxscript/converter for import/conversion of .prim models would be awesome.I'm always in trouble understanding the term "help on writing a script". Do you know maxscript?

> Here's a simple box mesh, unweighted. 
>
> http://www.mediafire.com/download/k74sx ... im.pc_primOnce you've understood that there's other data formats than floats such as shorts for example it's pretty simple:



mockupgeom_box.JPG (37.43 KiB) Viewed 97 times


The hard part is to get the uvs - all I get is 0.5 0.5
or 1.0 1.0
I pray to the mighty god of hex reversing that I don't have to rewrite my damned code 'cause it
looks like I'll have to introduce signed shorts for uvs. (I really hate sunday mornings...)

Hey, wait. Why "signed"? The uv range is 0.0 to 1.0, isn't it?
Or do they use signed uvs with an offset?
## Post #3
- Username: nosuit
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 18, 2015 10:16 am
- Post datetime: 2015-10-18T10:05:31+00:00
- Post Title: [HELP] Hitman (.weightedprim) Maxscript

Ohk, so faces start at 0x10? that's cool.

Sweet lord have mercy, the Hex god has given us meshes.
## Post #4
- Username: TGE
- Rank: veteran
- Number of posts: 109
- Joined date: Thu Jun 05, 2014 2:48 am
- Post datetime: 2015-10-19T09:34:52+00:00
- Post Title: [HELP] Hitman (.weightedprim) Maxscript

Those weighted prim files are just raw data dumps, you can't automatically extract from it that way. 
There's got to be a header file somewhere.

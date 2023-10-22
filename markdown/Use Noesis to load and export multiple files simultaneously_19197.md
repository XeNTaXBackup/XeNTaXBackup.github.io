## Post #1
- Username: Maphesdus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 12, 2016 3:53 am
- Post datetime: 2018-12-16T00:39:09+00:00
- Post Title: Use Noesis to load and export multiple files simultaneously?

I already know that it's possible to load multiple files into Noesis simultaneously by creating a Noesis scene file, but I can't figure out how to export multiple files simultaneously. Whenever I try to export from a Noesis scene file with multiple objects, Noesis only ever exports the first object. For example, consider the following generic template of a Noesis scene file:

```
version 1
physicslib ""
defaultAxis "0"

object {
	name "Mesh_A"
	model "Mesh_0001.dat"
	loadOptions ""
}


object {
	name "Mesh_B"
	model "Mesh_0002.dat"
	loadOptions ""
}

object {
	name "Mesh_C"
	model "Mesh_0003.dat"
	loadOptions ""
}

object {
	name "Mesh_D"
	model "Mesh_0004.dat"
	loadOptions ""
}
```


By creating a Noesis scene that follows the above format, I can load as many objects into Noesis as I want. But Noesis only ever wants to export the very first object. Is there some way around this? Like a batch export, or something?
## Post #2
- Username: Vuze
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 11, 2018 4:33 am
- Post datetime: 2019-02-19T15:58:20+00:00
- Post Title: Use Noesis to load and export multiple files simultaneously?

Did you find a solution to this?

In my case I'm trying to export a model with multiple sub meshes but the export only ever contains a single model.
I found the -modelindex # paramter, which works but you can't chain multiple together, so still, only the first specified model.
## Post #3
- Username: HeliosAI
- Rank: mega-veteran
- Number of posts: 166
- Joined date: Wed Nov 17, 2010 9:57 pm
- Post datetime: 2019-02-26T08:33:42+00:00
- Post Title: Use Noesis to load and export multiple files simultaneously?

Instead of Export chose Export from Preview, that will save all imported models as one.
## Post #4
- Username: Maphesdus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 12, 2016 3:53 am
- Post datetime: 2019-04-05T22:08:05+00:00
- Post Title: Use Noesis to load and export multiple files simultaneously?

> Reply from o0Crofty0o ↑Tue Feb 26, 2019 4:33 pm at Tue Feb 26, 2019 4:33 pm
>
> 
Instead of Export chose Export from Preview, that will save all imported models as one.
Tried that. Didn't work.
## Post #5
- Username: TBarbe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Dec 31, 2021 10:17 pm
- Post datetime: 2022-02-08T22:41:27+00:00
- Post Title: Use Noesis to load and export multiple files simultaneously?

Hey, I have the same problem.  Did you manage to find an alternative solution?

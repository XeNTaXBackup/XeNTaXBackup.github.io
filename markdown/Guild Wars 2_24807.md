## Post #1
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-05T22:05:36+00:00
- Post Title: Guild Wars 2

Having issues with the python script for these .pf models. If anyone can explain whats up. 
[](https://ibb.co/q0y6Jnf)


Samples
[https://drive.google.com/file/d/1MrY2WL ... sp=sharing](https://drive.google.com/file/d/1MrY2WLtsT47MRpPsaMt0al3_Ezeh86_Z/view?usp=sharing)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-06T09:03:41+00:00
- Post Title: Guild Wars 2

The script you uploaded is from Demonsangel, afaics, but you might read here, too (6 years old thread!  ):

> Reply from zaramot ↑Tue Apr 07, 2015 2:31 am at Tue Apr 07, 2015 2:31 am
>
> 
.
btw. you'll need to give the file a structure before you can step into animation data. As simple as this.
.
Here's a part of the mesh (someone needs to care for the skeleton...):



00139774-pf.png (128.3 KiB) Viewed 82 times

(that's not eyeballs, I think  )
## Post #3
- Username: Sharppy
- Rank: mega-veteran
- Number of posts: 163
- Joined date: Thu Jun 07, 2018 3:09 pm
- Post datetime: 2021-12-06T22:12:39+00:00
- Post Title: Guild Wars 2

Thanks for the reply Shakotay. Yes the title and tools are rather old but dont seem to work on all meshes. You say "give the file a structure" what you mean by that ?  Is the script not able to parse models correctly ?. I seen one did work of a dragon. 2nd to the end. But all others fail. I could do the mesh manually too but i was hoping this script could be updated or fixed. I'm kind of lost here on why this wont work and why nobody has looked into this in so long. Thank you for your help. I truly don't know how to make edits to scripts or know what the issue is.
[](https://ibb.co/1TzLyS0)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2021-12-06T22:28:14+00:00
- Post Title: Guild Wars 2

> Reply from Sharppy ↑Tue Dec 07, 2021 6:12 am at Tue Dec 07, 2021 6:12 am
>
> You say "give the file a structure" what you mean by that ?Hard work.  (It's "to understand which data belongs to mesh, skeleton, animation".)

> Is the script not able to parse models correctly ?Because the model format has changed, didn't it? 

> I seen one did work of a dragon.A working sample could help a lot.

> and why nobody has looked into this in so long.See my answer to LogicalEvil from 6 years ago:

> Reply from shakotay2 ↑Thu May 28, 2015 4:22 pm at Thu May 28, 2015 4:22 pm
>
> 
It could be helpful if someone sent me an old pf (skeleton) file which is loaded correctly by Demonsangle's script.
Otherwise I don't think that I'll waste more time on this.

## Post #1
- Username: ximplosionx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 10, 2015 11:23 am
- Post datetime: 2015-01-10T03:48:43+00:00
- Post Title: Help with Phoenix Wright: Dual Destinies

Hey all,

I'm interested in reverse engineering the Ace Attorney: Dual Destinies .MOD file format and was hoping to come here for some guidance. It looks like the models were made using a mobile version of the MT Framework and does not seemingly align with the RER/RE6 format. I've began to parse the header of these files ([script here](https://gist.github.com/anonymous/631dd098ea7376cfa1be)), but I'm clueless where to go from here. I've written a parser for game files in the past, but never a 3D Model format. Does anyone have any documentation on the .mod format? Would anyone be interested in helping if I could get you samples to look at?

Some notes:
The headers of the RE6/RER file format seemed to be using 64 bit integers to store things like vertex counts. In the mobile version those seem to be kept as 32 bit integers.

Thanks!
## Post #2
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-01-10T07:44:01+00:00
- Post Title: Help with Phoenix Wright: Dual Destinies

Provide some samples, please.
## Post #3
- Username: ximplosionx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 10, 2015 11:23 am
- Post datetime: 2015-01-10T09:19:31+00:00
- Post Title: Help with Phoenix Wright: Dual Destinies

You can grab some models [here](https://mega.co.nz/#!i8ZTmIIL!EDaRQ6NspShU_qI3El6Gj9OGZ5QmAG0g_usiXV8Tt4E). They also have their .tex files and .mrl (unsure of that format. Thought 'material' for a moment, but that should be in the model's data, no?)

Thanks for looking.
## Post #4
- Username: zaramot
- Rank: double-veteran
- Number of posts: 783
- Joined date: Wed Jan 05, 2011 7:41 pm
- Post datetime: 2015-01-10T09:51:34+00:00
- Post Title: Help with Phoenix Wright: Dual Destinies

As I thought it's similar to Monster Hunter 4 MT mobile format. You can get most models using my script from here [viewtopic.php?f=16&t=11910&hilit=monster+hunter](http://forum.xentax.com/viewtopic.php?f=16&t=11910&hilit=monster+hunter) (fell free to edit or finish it)
## Post #5
- Username: ximplosionx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jan 10, 2015 11:23 am
- Post datetime: 2015-01-10T22:09:58+00:00
- Post Title: Help with Phoenix Wright: Dual Destinies

> Reply from zaramot
>
> As I thought it's similar to Monster Hunter 4 MT mobile format. You can get most models using my script from here viewtopic.php?f=16&t=11910&hilit=monster+hunter (fell free to edit or finish it)

Fantastic.

Say, do you have any samples of MH4's MT models? On the PW:AA models the bone weights seem to be thrown off so I wanted to take a look.

Also any word on the tex format used in MT Mobile? I'd love some documentation there, or if you can point me to someone who may know.

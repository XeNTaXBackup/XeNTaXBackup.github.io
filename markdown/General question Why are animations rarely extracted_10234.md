## Post #1
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-03-19T17:54:57+00:00
- Post Title: General question: Why are animations rarely extracted?

With the exception of unreal games (some unity too). One never sees animation data even when skeletal information is available.
Are there any specific difficulties with it?
Some of them clearly say *.bip referring to 3dsmax

I am currently doing my very first tool (Real soccer 2012) but half way through (after thinking i have learn the file structure) I was hit with this random chunk of data that changes size in every file with no obvious pattern. Are these the kind of problems you face?

PS: what do people do with these models anyway? Custom rendering and Machinima?

I am sure animation helps with machinima.
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-03-20T00:13:40+00:00
- Post Title: General question: Why are animations rarely extracted?

Animation formats are much more likely to use custom bit-level delta compression schemes and other interesting/unique storage techniques that vary on a per-game basis. Sometimes it's easy to spot animation data and sometimes it isn't. When it isn't, it's often the case that guessing will get you nowhere, so you either gamble on guessing right (potentially wasting a lot of your time), or you endeavor to disassemble the game to figure it out, which is much more time-consuming than just sifting through some obvious hex. It's almost always easy to spot model geometry as raw data, and developers typically don't bother compressing skeletons themselves because they're relatively tiny so they're usually easy enough to spot too.
## Post #3
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-20T06:14:41+00:00
- Post Title: General question: Why are animations rarely extracted?

here are the problems i have faced. 

#1 games use joints. modelers use bones (albiet maya). most games do not include the extra joints at the end of the chain that do not transform vertices. partial solution is to take ibm and create a mini-end bone. however this is assuming you have perfect computation of ibm. in rise of guardians, i got skeleton but when i multplied matrices and extracted joint local coordinate system only 90% of mini bones were pointing the right way. always there was one or two bones pointing opposite direction should. tried everything. said fuck it .

#2 same problem as number one. a game can have one joint n multiple children. you transform joint it moves all child joints. in modeler you create two bones in v-shape the bones are independant. ie. there are two parent joints at same position. its a pain in the ass to name name bones and vertex maps (weight maps) because of this.

so even if animation data is easy to extract (like in hyperdimension neptunia), unless your skeleton is friggenly perfectly setup, animation data is useless anyways.

#3 you have to know your modeler extremely well. in blender bones need a head, tail, and roll angle. wtf is a roll angle? if you look at blender source, you need to know how they compute this roll angle given the bones local coordinate system. looking at blender source code just gives me a frigging headache lol!

as for what people do with the models i just extract them and delete them lol. i need the image of a real woman in order to fap to lol. i think the biggest audience are the dA barbie doll users, who like to take the extracted models and pose them, creating their own fan comics and stuff like that. some of the stuff is interesting but its also full of weird stuff like vanille being groped by teenage mutant ninja turtles and monsters swallowing doa5 characters lol.
## Post #4
- Username: michalss
- Rank: Moderator
- Number of posts: 955
- Joined date: Mon Mar 28, 2011 3:42 am
- Post datetime: 2013-03-20T06:56:39+00:00
- Post Title: General question: Why are animations rarely extracted?

for sure wrong section mate
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-03-20T14:04:43+00:00
- Post Title: General question: Why are animations rarely extracted?

howfie: That typically isn't an actual issue. Models will often only animate bones that are weighted and will flatten the rest of the skeleton, or they'll flatten certain hierarchies to make natural posing in the baked hierarchy impossible, but this is always compensated for in their baked anim data. You just need to make sure the base pose matrices correctly reflect the same coordinate system as your transformed anim matrices and you should be all set. Of course, this discounts the pains in the ass you might face getting it into the right space for your modeler of choice. Noesis doesn't care, as long as your anim matrices are localspace. That was a lot of shit to type on a phone, I should have just gone downstairs.
## Post #6
- Username: howfie
- Rank: double-veteran
- Number of posts: 929
- Joined date: Fri Jul 08, 2011 7:06 pm
- Post datetime: 2013-03-20T15:58:42+00:00
- Post Title: General question: Why are animations rarely extracted?

ha ha ha ha. really hmmm? i guess i might give it a go one day on neptunia then and see what kind of junk pops out. so that's what they call it (flattening the hierarchy) when they remove the joint tips?
## Post #7
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-03-20T23:13:29+00:00
- Post Title: General question: Why are animations rarely extracted?

#1 is actually how all animations work. They are stored in local space and the skeleton is a Directed Acrylic graph.

Compression is usally employed when the cpu can handle it there for everything but mobile.
I think the compression algorithms are pretty standard to a level.  The unreal engine source code that was stolen shows a few of them (maybe that's why gildor is so successful).

Thanks for the replies.
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-03-21T01:15:22+00:00
- Post Title: General question: Why are animations rarely extracted?

Plenty of games store animated joints in modelspace, Noesis supports a couple. Especially older games that wanted weighted vertex transforms but didn't want the expense of hierarchical transforms.

The cost of most delta compression methods is negligible, and will actually benefit performance quite often by reducing memory bandwidth and/or reads from slow RAM. This is especially true for quite a few mobile architectures where most of your time is spent waiting on the memory bus.
## Post #9
- Username: JohnHudeski
- Rank: mega-veteran
- Number of posts: 177
- Joined date: Thu Mar 03, 2011 5:38 am
- Post datetime: 2013-03-21T09:31:02+00:00
- Post Title: General question: Why are animations rarely extracted?

I did not think mobile cpus were that powerful.
I have been told if you have to chose to commit work, give cpu more over ram.
## Post #10
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-03-21T13:00:35+00:00
- Post Title: General question: Why are animations rarely extracted?

There's nothing inherently expensive about delta compression, and it can save in both memory bandwidth and computational expense. Global animation standards (when they exist) for just about every embedded platform use delta compression. PSP's GMO and Dreamcast's Ninja Motion included. However, everyone has their own way of implementing and expressing it, sometimes at bit level and sometimes not.

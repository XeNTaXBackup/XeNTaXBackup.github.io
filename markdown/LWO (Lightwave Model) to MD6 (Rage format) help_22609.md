## Post #1
- Username: Duskortym
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jul 07, 2020 1:55 pm
- Post datetime: 2020-08-28T09:40:09+00:00
- Post Title: LWO (Lightwave Model) to MD6 (Rage format) help

Hello. I am making a total conversion mod for Rage. Luckily, Rage comes with a toolkit with most of the features enabled. I've played around with it for a few months now, and I've made a lot of progress, but one thing I'm having trouble with is making md6 models. While Rage uses LWO (Lightwave object files) for many of the static models, for things like characters, weapons, or dynamic models (things that use skeletons and animations), it uses a proprietary format called MD6. From looking into the game, what I've figured out is that MD6 files are meshes, animations, and skeletons. The mesh is the model, though, and if you open the file in notepad, you will notice that it lists locations of joints, and then all of the locations of vertexes and what it calls tris (what I assume would be triples in Lightwave). I've put some notes in this script, and I've shortened the tris and verts sections to save space:

MD6Version 2 //Version of the program they're using to export to MD6

init { //initialize
	commandLine "-ex mesh -meshes -skeletons  {sticky; } -minExpand ( -16 -16 -16 ) -maxExpand ( 16 16 16 ) -remapForSkinning 1 -morphMap " //meshes, morph map, and remap it for skinning, initialize skeletons
	sourceFile	"animation/weapons/grenades/sticky_grenade.mb" //????
	numMeshes 1 //lists the number of meshes
	numJoints 2 //number of joints
	numUserChannels 0
	numWeightSets 8 //???
	minExpand ( -16 -16 -16 ) //????
	maxExpand ( 16 16 16 ) //????
	remapForSkinning 1 //Set it to be remapped for skinning as true
	morphMap "" //morphmap
}

joints {
	"test"	-1 ( 1 0 0 0 0 0 0 0 ) ( 0 0 0 1 ) ( 1 1 1 ) ( 0 0 0 )	// locations of joint
	"test1"	0 ( 1 0 0 0 0 0 0 0 ) ( 0 0 0 1 ) ( 1 1 1 ) ( 0 0 0 )	// origin
}

mesh { //initialize mesh
	name "emp" //name
	shader "models/weapons/grenades/emp_grenade" //location of texture or uvmap
	verts 343 {
		vert 0 ( 1.7315030098 0.7459070086 -5.9852466583 ) ( 0.4663890004 0.4424340129 ) ( 1 -1 -1 -1 1 0 0 0 )

etc...

then

tris 476 {
		tri 0		2 1 0
		tri 1		5 4 3
}
}

etc..

I've randomly tried to change the values and it says that the model is offset, but if I copy out sections from other models it works fine. This means that I should be able to create a type of script that converts a model into the above format and file.

If you take a look at a Doom 3 Md5mesh file, it is very similar, but there are differences. I attempted to copy an md5def and try and translate things over to an md6, but unfortunately, there are whole sections missing in the verts compared to the MD6. Take a look at this example:

MD5Version 10
commandline "mesh maps/fred/monorail/crash.mb -dest models/md5/cinematics/monorail/crash_debris.md5mesh -game Doom -prefix ENV_"

numJoints 1
numMeshes 2

joints {
	"origin"	-1 ( 0 0 0 ) ( -0.8752637506 0.366555661 0.2916583121 )		// 
}

mesh {
	// meshes: crashgeo_m232
	shader "textures/outside/tram1tex2"

	numverts 53
	vert 0 ( 0.9023230076 0.9980000257 ) 2 1
	vert 1 ( 0.7835739851 0.9476000071 ) 1 1
etc..

The tris are in the same format...


In any case, my question is.. this seems like something viable. How would I create a script? I know that someone created a script in an engine modification for Doom 3 called IcedTech: [https://github.com/jmarshall23/IcedTech ... MayaImport](https://github.com/jmarshall23/IcedTech/tree/master/code/Engine/MayaImport)  but I have tried to export the source code using CMAKE and Visual Studio 2019 with no luck (I'm a level designer and artist, not a programmer).

What I'd really like to do is figure out a way to create a script that would translate LWO (Lightwave Object) files into MD6 files. How would I go about doing this? What kind of extra material should I be reading to understand how to create scripts like this?

Thank-you.

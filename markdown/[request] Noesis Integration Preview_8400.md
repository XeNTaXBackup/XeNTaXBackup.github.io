## Post #1
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-24T18:52:36+00:00
- Post Title: [request] Noesis Integration Preview

First of all, Thanks to finale for inject life to the 3D/2D models section and support the users working with this incredible Tool Developed by Mr. Adults, same time thanks to Fatduck by the True Amazing Fat importer script.

Now the Question, in the RF models finale made a .py plugin, this load a fully model with all parts (helm, glove, pants, shoes, chest) this 5 parts its a standard in MMORPG Games, in the beginin finale tell this its a error coz he cant separte the parts, but really this its a greath think, how its posible made a butom or develop the same think for all the scripts? Load all parts of one set armor, and see this fully in Noesis preview its the best way to show a full Model, how its posible made a standard do this? one sample its DK online, not have Texture preview and only can see parts individual, its posible i can put 5 parts off this sets in folder and put textures too, and noesis load fully the set? this can ve very nice and advance.
## Post #2
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-24T21:26:11+00:00
- Post Title: [request] Noesis Integration Preview

I use a standardized set of functions for loading models. Currently it loads all of the models in the same folder. You can use noesis scene files to determine what to load as well. For rf online it is convenient because all parts are stored in the file. For others, it works for just meshes, but what if skeletons were added? Might be more difficult.
## Post #3
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-25T00:07:18+00:00
- Post Title: [request] Noesis Integration Preview

noesis scene files? where its this option?. i dont see  , Btw i load .xac files in model data folder and cant see the textured, model and texture its in this folder.
## Post #4
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-02-25T00:16:49+00:00
- Post Title: [request] Noesis Integration Preview

I don't remember the details but someone was asking about wanting to load FF9 models with their weapons since they were stored separately, so MrAdults gave an example of how to do it in the Noesis thread.

Might be some place to start.
It was basically a text file where you specified which models you want to load and some other properties.
## Post #5
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-02-25T04:49:14+00:00
- Post Title: [request] Noesis Integration Preview

Well, i read the 53 pages of Noesis treadh, i found in wath version Mr. Adults include this, but i not found how its posible, wath i need edith or where the .txt with textures and meshes format go to load all parts in one single.
Any tip?
## Post #6
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-03-01T00:20:13+00:00
- Post Title: [request] Noesis Integration Preview

Look at the .noesis files in the Scene folder.

It is pretty straightforward.
## Post #7
- Username: Rimbros
- Rank: ultra-veteran
- Number of posts: 495
- Joined date: Fri Jul 09, 2010 7:23 am
- Post datetime: 2012-03-06T23:32:15+00:00
- Post Title: [request] Noesis Integration Preview

> Reply from finale00
>
> Look at the .noesis files in the Scene folder.

It is pretty straightforward.

I already take view, i found this info.

NOESIS_SCENE_FILE
version 1
physicslib		""
defaultAxis		"1"

object
{
	model		"sample_boxroom.dae"
	offset		"(0 0 0)"
	rotate		"(0 0 0)"
}
object
{
	model		"sample_ball.dae"
	offset		"(0 90 250)"
	rotate		"(0 0 0)"
}
object
{
	model		"sample_block.dae"
	offset		"(0 -100 45)"
	rotate		"(0 0 0)"
}
object
{
	model		"sample_spike.dae"
	offset		"(0 100 0)"
	rotate		"(0 0 0)"
}
object
{
	model		"sample_guy.dae"
	offset		"(100 200 0)"
	rotate		"(0 0 0)"
}


But here i see predefine object position captured.
Some idea how to made this easy?

Like load a .txt file
and txt file have this info

mesh01
mesh = Helm0122.obj
texture = Helm0122.dds
---------------------------
mesh02
mesh = Chest0122.obj
texture = Chest0122.dds
----------------------------
mesh01
mesh = Boot0122.obj
texture = Boot0122.dds
----------------------------

Finale you already can do this, in RF you load all the parts in folder only with load one .msh piece.
its this posible?.
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2012-03-06T23:41:38+00:00
- Post Title: [request] Noesis Integration Preview

I posted some FF8 .noesis files that were pretty simplified and worked to let the user view FF8 character+weapon models and play the anims in sync. An example:

```
version 1
physicslib		""
defaultAxis		"0"
sharedAnims		"1"

object
{
	model		"d0c000.dat"
	offset		"(0 0 0)"
	rotate		"(0 0 0)"
}
object
{
	model		"d0w000.dat"
	offset		"(0 0 0)"
	rotate		"(0 0 0)"
}

```


Basically you just define as many objects as you want by specifying model files in the objects. (you can use any format that Noesis supports) You can also offset/rotate them if you want, but most games with models broken into multiple meshes will tend to have all of the geometry oriented around a single root, so in that case (0 0 0) works fine as seen with FF8. There's also a "scale" field and a "disableSurf" field that allows you to disable surfaces on that model by index. There's no material/texture override though, that is dictated by the model itself.

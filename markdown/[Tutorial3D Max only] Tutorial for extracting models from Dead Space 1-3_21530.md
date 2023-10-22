## Post #1
- Username: MaZTeR
- Rank: mega-veteran
- Number of posts: 248
- Joined date: Sat Jul 09, 2016 11:06 pm
- Post datetime: 2019-12-25T22:28:47+00:00
- Post Title: [Tutorial/3D Max only] Tutorial for extracting models from Dead Space 1-3

To save your time, this tutorial works ONLY on 3D Max. Not Blender, not anything else. So if you came looking for something else, then sorry but this won't help you.

Yeah so, I got tired of people asking me every now and then how I got access to the models from the main Dead Space games, so I figured out I'll make this guide since nobody in the last 11 years since the first game was released actually has done so. I had one tutorial in Facepunch couple of years ago made but that site has been reduced to atoms.

First off, here is a folder containing required tools for getting the models:

[https://www.mediafire.com/file/1m1i9j6d ... s.zip/file](https://www.mediafire.com/file/1m1i9j6d3qjy8oj/3D_Max_Dead_Space_.geo_.RCB_scripts.zip/file)
[https://www.mediafire.com/file/4xb3s1ff ... t.zip/file](https://www.mediafire.com/file/4xb3s1ffy28pqbw/dead_space_noesis_textures_script.zip/file)
[https://www.mediafire.com/file/vh3kgpjv ... s.zip/file](https://www.mediafire.com/file/vh3kgpjvqikv7db/dead_spaec_1-3_samples.zip/file)
[https://www.mediafire.com/file/tnisaj3e ... v.rar/file](https://www.mediafire.com/file/tnisaj3elv77ajy/ds1_.snu_to_wav.rar/file)
[https://www.mediafire.com/file/tt61elv4 ... e.rar/file](https://www.mediafire.com/file/tt61elv4u4sr0ca/ds1_xas_decode.rar/file)
[https://www.mediafire.com/file/240allqy ... 3.zip/file](https://www.mediafire.com/file/240allqyd7a6eck/DS2_EXA_to_mp3.zip/file)
[https://www.mediafire.com/file/gg10lwpe ... r.rar/file](https://www.mediafire.com/file/gg10lwpe0i6blla/ds3_ealayer.rar/file)
[https://www.mediafire.com/file/vmgh564i ... 3.zip/file](https://www.mediafire.com/file/vmgh564ita25wqz/RickVisceral110423.zip/file)
[https://www.mediafire.com/file/fdr8f6y5 ... 3.rar/file](https://www.mediafire.com/file/fdr8f6y5mpxf9gt/SBK_unpacker_DS1-3.rar/file)

Visceral viewer (RickVisceral110423)
SBK unpacker DS1-3
ds1 xas_decode
dead space noesis textures script (model script is included in the same bunch)
3D Max Dead Space .geo .RCB scripts

Obviously, what you are going to unfortunatly require is the actual games (I know, how shocking): Dead Space, Dead Space 2 and Dead Space 3. If you are too poor to pay 5 bucks for what those games are worth these days, cracked versions work just fine as well, however, I do not promote piracy so I recommend buying them. Allkeystore offers great prices for any games, so check that site out if you are short on cash.

And if you still didn't get it, 3D Max, tested on versions 2017 to this date. Probably works on older versions since all you do is open up the models with a Max script.

Note that this is not a tutorial on setting up 3D Max or using Noesis. Only to explaining how you get the models. I assume you know how or can figure out other tutorials on doing exactly the things first mentioned.

Important: Any of the scripts in this tutorial can ONLY be used to extract anything that aren't LOD models of level geometry. Well, with the Max scripts, you can get both, but the UVs are completely broken. As for the Dead Space Noesis script, level geometry models are completely broken. If you know how to fix these, feel free to post the fixed scripts here.

Enough talk, let's get to business. Also, as I wrote this, I had not installed the games on my system so this is based on my memory of how things approximately go.

For this tutorial, we'll extract one of the Slasher Necromorphs.

Dead Space 2-3:
1. Open up Visceral viewer and open up one of the big archive files until you come across something which has global_assets sub-folders. Open the folders up until you come across the char folder and see something related to the Slashers. Pick one of them and extract the str file to somewhere safe.
2. Unpack the str file with the str unpacker included with the Visceral viewer folder.
3. Open up Max and go to the scripts section and open up the batch extractor. Once it's open, select the .GEO folder within the unpacked Slasher folder. It will open up the Slasher model in default T-pose to the editor (Note: It doesn't include the gibs or any small models which might be included with some models, these can only be extracted with the other script which does not have the batch feature)
4. There's your model, but it is untextured.

Dead Space:
1. Install Noesis and place the scripts to the proper locations
2. Find the Slasher model from the game files of the first game (It's the same as in Dead Space 2 and 3 without the compressed archive file)
3. Unpack the str file
4. Open up Noesis and convert the files into fbx or something you can manipulate with 3D Max. To save time, use the batch feature and convert everything at once. If I remember correctly, the tool is a bit iffy with the sizing so you might have to apply rescaling to the model, I am not 100% sure though. Keep in mind that the gibs and other small models are included.
5. Open up the files in Max, I suggest installing a batch opener for FBX or whatever format you chose to convert the geo files into.
6. There's your model, but it's untextured.

Note that the models are inserted backwards with the 3D Max script meanwhile they are facing forward with Noesis.

Textures.
1. Open up Noesis (place the scripts to the proper places).
2. Find the textures (located in the tg4h/d folders, one of which contains the UV data so only either of the two contains the material you need).
3. Convert to TGA or whatever you want. Use the batch feature to convert all the textures at once.
4. Open up Max. Apply textures.

Skeleton:
1. Once you have your model, open up the RCB script
2. Open up the RCB folder with the script
3. Skeleton(s) should appear in the editor as yellow nodes, not bones.
Note that the models do not have any skin data so you have to rig them from the beginning. Use the skeletons as a reference if you are making 1:1 scale recreation with new rigs.

Credits to every person behind the scripts I linked, I have not made a single one. I take credit for only making this tutorial.
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2019-12-25T23:55:03+00:00
- Post Title: [Tutorial/3D Max only] Tutorial for extracting models from Dead Space 1-3

Very helpful. Thank you.

Dead Space has a lot of good Mocap animations and I'm glad if someone reverses it.
Especially the reload motion of this game is unique and wonderful.

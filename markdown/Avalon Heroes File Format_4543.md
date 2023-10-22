## Post #1
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2010-06-01T15:26:42+00:00
- Post Title: Avalon Heroes File Format

So I had already posted this on the Game Archive Research a few days ago, and so far, it went well, thanks to Zazz' QuickBMS script I was able to extract the archives.
Now since that was already solved, I think this is the proper place where I should post my next request.

Could anyone please take a look at the format of game's model files?
Here is my original thread from the Game Archive Research forum: [viewtopic.php?p=38712#p38712](http://forum.xentax.com/viewtopic.php?p=38712#p38712) (More info found here on my last post).

Here is the sample file link (same file link from the original post above): [http://www.mediafire.com/?lmmwnzwmtyn](http://www.mediafire.com/?lmmwnzwmtyn)
This includes a semi-complete hero model file set from the game. (Mesh [.msh], Skeleton [.skl], Animation [.ani], Texture [.tex], and some other files [.mdl, .pkg]) (Sound file was not included since it could easily be opened using Audacity's import raw data, Cool Edit Pro or Adobe Audition).

As for the Game Website: [http://avalonheroes.en.alaplaya.net/](http://avalonheroes.en.alaplaya.net/)
## Post #2
- Username: FurryFan
- Rank: mega-veteran
- Number of posts: 190
- Joined date: Sun Jan 10, 2010 4:37 am
- Post datetime: 2010-06-01T17:20:41+00:00
- Post Title: Avalon Heroes File Format

Okay here is the format of the .msh files
at offset 0h14 there is a 4ByteIntegerVariable #NumVertexes
followed by
{4ByteFloatVertexes(X,Y,Z) + 4ByteFloatNormalMappings(X,Y,Z)}
then: 01 00 00 00 4ByteInteger(#NumTextureMappings)
{4ByteFloatTextureMappings(U,V)}
then: 4ByteInteger(#BoneStuff)
{8ByteArrayBoneStrings}
then: 4ByteInteger(#FacesSection1)
{2ByteVertex#1, 2ByteVertex#2, 2ByteVertex#3}
(Here is where things get strange)
4ByteMagicString (LRTM)
03 00 00 00 01 00 00 00
4ByteInteger(#Tex characters in Texture File name)
{Texture File Name)
??????
4ByteInteger(# Tex characters in shader)
{Shader name}
?????? Beginning of section 2
4ByteInteger(#FacesSection2)
{2ByteVertex#1, 2ByteVertex#2, 2ByteVertex#3}
LRTM....Texture for section 2.....

Now the .tex textures are really just DDS textures with a different heading (The 341KB size was a dead give away)
I pasted the hex from the .tex file from offset 0h28 until what looked like the end of the file (but was not), into a saber-tooth tiger dds texture from everquest 2 at offset 0h80


[http://ps23dformat.wikispaces.com/file/ ... kech.blend](http://ps23dformat.wikispaces.com/file/view/drakech.blend)
Note you must export the model from blender into another program, because my models never display textures in Blender for some reason even though the UV Mappings are present
[http://ps23dformat.wikispaces.com/file/view/drakech.dds](http://ps23dformat.wikispaces.com/file/view/drakech.dds)
[http://ps23dformat.wikispaces.com/file/ ... hSHELL.dds](http://ps23dformat.wikispaces.com/file/view/sabertoothSHELL.dds)
## Post #3
- Username: windfury
- Rank: beginner
- Number of posts: 23
- Joined date: Sun May 23, 2010 2:54 pm
- Post datetime: 2010-06-01T18:23:51+00:00
- Post Title: Avalon Heroes File Format

Whoa, that is awesome, mine displays properly. This is much appreciated.  



You know what? I think we just unlocked a secret content of Avalon Heroes. That texture we got is actually not the one that is shown in the game. Back then, I wondered why they have two of each files for each hero, I guess this answers my question. This is probably going to be used for some kind of campaign mission, or maybe just an alternate costume, evil forms of the original Heroes, could be something they would add as cash in game.

Anyway, going back on topic. I'm really a noob when it comes to stuff like this, I see that you have posted the format, but I do not know what to do with it, I guess I would have to research first.  If these (Mesh, Skeleton [This is already Biped] and Animation) could be imported into 3DS Max [Preferably 8], I would really be happy, I really want to export them for other games. This would also be a great addition to the list of games that we could extract models with animations from here on XeNTaX.
## Post #4
- Username: Karpati
- Rank: ultra-veteran
- Number of posts: 467
- Joined date: Fri Dec 08, 2006 6:25 am
- Post datetime: 2010-08-31T18:08:09+00:00
- Post Title: Avalon Heroes File Format

windfury,

I added the compressed (like _npc.msh) and the uncompressed .msh and the uncompressed .tex loader module to the 3D Object Converter and I released the v4.422 now.

You can install or use the portable v4.40.
[http://web.t-online.hu/karpo](http://web.t-online.hu/karpo)

After that you can update your installed (or portable) application (version>=4.0) quickly and easily using the auto-update function (Help/Check for updates…) to get the latest version of the 3D O. C.

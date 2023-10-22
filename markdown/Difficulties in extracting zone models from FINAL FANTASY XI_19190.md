## Post #1
- Username: Maphesdus
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jan 12, 2016 3:53 am
- Post datetime: 2018-12-15T07:55:31+00:00
- Post Title: Difficulties in extracting zone models from FINAL FANTASY XI

Hey all, I'm working on a project to extract zones/areas from FFXI and import them into Unreal Engine 4. You can check out my YouTube channel below to see some of the work I've done:
YouTube: FFXI: Unreal -- Ru'Aun Gardens in Unreal Engine 4

I've been using Noesis as my primary extraction tool, and Autodesk Maya as an intermediary step to fix the models up a bit before importing them into UE4.  I feel I've made some pretty good progress, but I'm just not satisfied with the results, and the more I learn, the more I realize how little I know.

For example, one thing that's been really confusing to me is that when I load an FFXI zone model into Noesis and then open up the Data Viewer tool from the Tools menu, I notice that each material seems to have four different versions:
Explicit Shiny (tag: _explicitshiny)
Explicit Soft Blend (tag: _explicitsoftblend)
Explicit No Blend (tag: _explicitnoblend)
Standard? (No special tag. I'm assuming this is the standard version of the material.)

The "shiny" tag seems pretty self-explanatory, but I don't know what the difference is between what I assume is the standard material and the "no blend" material. And I think "soft blend" means the material is supposed to have transparency, but I'm not sure. Also, what does the keyword "explicit" mean in the context of these tags? Why not just use "soft blend" as a tag? Why does it have to be "explicit soft blend"? Are these categorizations unique to FFXI, or are they part of how Noesis parses the material information it's reading? Could anyone explain all of this to me, please?

Anyway, the biggest problem I'm having is that most zones in FFXI have what appear to be special "decal" materials that provide additional layers of texture on top of the primary or base layer. However, this seems to be done by having overlapping pieces of geometry that occupy the same space as each other, with certain blending options enabled for the decal layers. I think this is somehow related to the different material blend types above, but I don't really understand the specific details of how it works, exactly. Does anybody here have any idea? And is there a way for Noesis to automatically detect which pieces of geometry are supposed to be the decal layers and which are supposed to be the base layers?

Another issue I've been having with the materials is that even though the Data Viewer tool in Noesis says there are four types of material for each texture, whenever I export an FFXI zone model and open it up in some other 3D modeling program (such as Maya), I only ever get one or two materials per texture. Why is that? What's going on here? Shouldn't I be getting four materials per texture? Where are the other two?

Aside from textures and materials, loading unreferenced geometry using the -ff11rederunref command produces a convoluted mess of objects in the center of the zone, and trying to pull all of them apart in some other 3D modeling program (I personally prefer Maya) is a huge pain in the ass, especially for zones that happen to have a lot of unreferenced geometry. The problem is compounded by the fact that many pieces of unreferenced geometry are actually comprised of several smaller sub-pieces, and it is often very difficult to tell which pieces are supposed to be part of which object when all the objects are directly on top of each other. I know this is just how Noesis was programmed to work with FFXI, but is it possible to create a plugin for Noesis that automatically places the unreferenced geometry where it's actually supposed to go? If not, would it at least be possible to have Noesis arrange the unreferenced geometry in a grid layout so at least the pieces aren't all on top of each other? Also, is it possible to load only the unreferenced geometry? I feel that would make it easier to separate it out from the regular geometry.

There is also an issue with Level of Detail (LOD) geometry in that FFXI zone models will often have both high-poly and low-poly versions of the same object. This wouldn't normally be a problem (LOD objects are to be expected in any game), but whenever I export an FFXI zone model using Noesis, the regular high-poly meshes and low-poly LOD meshes both get placed right on top of each other, thus making it so that I have to pull apart even the regular geometry in addition to the unreferenced geometry. Ru'Aun Gardens in particular is a zone that seems to have an unusually high number of low-poly LOD objects. Is there some kind of flag that can be parsed to automatically determine whether any particular mesh in a given scene is supposed to be an LOD object or not?

Furthermore, several zones in FFXI pull information from multiple DAT files at once. All of the major cities do this, as do many of the more elaborate outdoor areas, such as Ru'Aun Gardens (seen in the video above). I managed to get all of the various DAT files for Ru'Aun Gardens to display in Noesis by creating a scene file (which I've shared below), but when I tried to export that scene file as an FBX object, Noesis only exported the first mesh in the list. Am I doing something wrong? Did I write the scene file correctly? Somebody help me out here, please.

Also, I don't know if this is the case with other zones, but in the case of Ru'Aun Gardens, only the base DAT file actually has any textures in it, and so I assume the other DAT files are just supposed to reference the textures in that base file. Unfortunately, Noesis doesn't seem to pick up on this, and so the models in the other DAT files just load into Noesis without any textures. Again, not sure if this is because of the way I wrote the scene file, or because Noesis just isn't programmed to parse data from multiple zone files in this way.

I've attached my scene file of all the combined DAT files for Ru'Aun Gardens below. Could someone who understands Noesis better than I do take a look at it please and make sure I'm doing this correctly?


Noesis Scene File for FINAL FANTASY XI -- Ru'Aun Guardens (All DAT Files Combined):


 Ru'Aun Guardens - All DAT Files Combined.zip
(678 Bytes) Downloaded 10 times


I realize most people here probably don't have FFXI installed on their machines, so here's a DropBox link to download the relevant DAT files for Ru'Aun Gardens:
DropBox: FFXI Ru'Aun Gardens DAT files.zip [16.8 MB]

Oh, and ones last thing... As far as I can tell, Noesis does not currently have the ability to load, preview, or export the animation effects for spells and abilities in FFXI, which is a real shame because some of the spell effects are pretty frickin' sweet. Is there anything that can be done about this?

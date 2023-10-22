## Post #1
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2013-12-24T14:06:06+00:00
- Post Title: [Question] Star Citizen Cryengine 3 files

Hi everyone,

The Star Citizen modding community is looking for a little help!

Star Citizen is built on Cryengine 3, so there are a lot of tools we have available to help create user generated content, and CIG has been very supportive of this.  They have even discussed creating a custom SDK for us, but... I guess game development comes first.  So until then we're left to our own devices, and there are some oddities in these game files that are causing fits.

Specifically, when we look at game objects in Noesis, the separate objects tend to be exploded all over the place.  Allow me to demonstrate:



It's tough to see in that picture, but this is the MISC_Freelancer cga file (renamed to .cgf so that Noesis can import/export).  The picture doesn't show it clearly but basically the 500+ objects that make up the ship are scattered all over the universe.  Here is a better shot in Blender, with the file converted to .obj and imported:



Here is the interesting thing:  The origins for the points are all at 0,0,0, but the geometry is spread out.  The pieces are in the proper relative rotation and scale, but the transform from the origin is off by (a rough estimate) a factor of 1000.  In other words, you can move the pieces to the origin by roughly that factor while keeping the same scale and rotation, and they'll be in the right place relative to the origin.  However, doing this 500+ times with no guidance on if you have the right factor (or if it's even constant) is just too daunting.

In MechWarrior Online (also a Cryengine 3 game), they come with handy .cdf file that has info we can correct transform for, but there is no equivalent information in Star Citizen.

So my question is:  Any ideas on how to fix the transform issues for these files?  Thank you for your time!
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-25T00:09:32+00:00
- Post Title: [Question] Star Citizen Cryengine 3 files

don't understand what you mean by "factor". It's the submeshes that have different position offsets to the origin, isn't it?

Since the Noesis plugin is a dll only revelation can help you with this, I guess.

If you are capable of blender python script you might patch the obj importer.

On the other hand it is rather simple to change the vertex data of the obj by adding an offset to vx for example using any coding language.

In blender select a submesh and drag it to the origin, then export the whole scene as obj keeping the vertex order.

Compare the two objs using WinMerge for example and you'll see which coords to change.
## Post #3
- Username: Markemp
- Rank: veteran
- Number of posts: 116
- Joined date: Tue Dec 24, 2013 9:42 am
- Post datetime: 2013-12-25T16:03:38+00:00
- Post Title: [Question] Star Citizen Cryengine 3 files

That is correct; the offset is weird.  And it happens before the obj importer in Blender, since Noesis shows the models all exploded as well.  There is something goofy with the .cga and .cgf files, so I probably need to start by digging through there.  Maybe @MrAdults will see this thread and figure out if Noesis can place the objects in the correct place.  I'm perusing xml and cdf files to see if I can find offset information, but no luck so far.  The game has to know where to place these objects, so the information has to be *somewhere*.

Here's another oddity.  It's not a fixed offset, as some pieces are placed properly.  For example, the P-52 file has about 40 objects, and about half of them are correctly positioned.  The rest are scattered about.  They are in the proper relative position, but too far away from the origin.



What a tricky, tricky thing this is.

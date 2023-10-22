## Post #1
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-10-16T13:17:56+00:00
- Post Title: Extract FFX/FFX-2 models withought bones resetting to 0,0,0

so as we all knoe these models can be extracted with theyre animations which play fine and the skeleton looks good in specialised viewers, but when the exported file (usually dae or smd) is imported in 3ds max or milkshape, the skeletal positions reset to 0,0,0 and the rigging is unassigned from the mesh.

doesn anyone have any insight on whats going on here or even how to stop it as of yet?
## Post #2
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2011-10-16T18:08:23+00:00
- Post Title: Extract FFX/FFX-2 models withought bones resetting to 0,0,0

That doesn't happen. Use an OpenCOLLADA plugin to import the dae produced by Noesis. (if you don't select OpenCOLLADA from the filetype dropdown when importing, Max will use its Autodesk DAE importer which is not compatible)
## Post #3
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-10-16T19:03:39+00:00
- Post Title: Extract FFX/FFX-2 models withought bones resetting to 0,0,0

thank you for the info, im gonna go google it now and get it in my 3ds max install now!
## Post #4
- Username: flarespire
- Rank: veteran
- Number of posts: 99
- Joined date: Sun Jul 24, 2011 7:30 am
- Post datetime: 2011-10-17T15:34:22+00:00
- Post Title: Extract FFX/FFX-2 models withought bones resetting to 0,0,0

it worked, thanks for all the help!

## Post #1
- Username: Murdock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 17, 2015 7:59 am
- Post datetime: 2015-09-15T19:29:02+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

Hello, maybe someone allready figured this out, but I can't find a solution. Alot of models I import with the mesh importer script have broken smoothing groups... The same happens when I import the mesh via the hex2obj method. 
Does somebody know a way to get the models with proper smoothing groups?
## Post #2
- Username: MichaelDarkAngel
- Rank: mega-veteran
- Number of posts: 267
- Joined date: Fri Nov 05, 2010 6:25 am
- Post datetime: 2015-09-15T19:38:33+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

Smoothing may be done in the game engine and not saved as part of the model file.

--MDA
## Post #3
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2015-09-15T19:49:35+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

From what i remember when looking at the mesh files:

The 3ds max script and hex2obj are not reading the original normals so the tool tries to autogenerate them, causing some odd issues. When i get some time i will make a updated importer for Maya with normals and everything.
## Post #4
- Username: Murdock
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Aug 17, 2015 7:59 am
- Post datetime: 2015-09-15T20:43:01+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

thanks for the fast replies! 
@Highflex: that would be very appreciated!
## Post #5
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2015-09-24T16:12:28+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

Just edited the bf4 max script to import correct normals 

Grab a copy from here:

[https://github.com/Highflex/frostbite_3dsmax_scripts](https://github.com/Highflex/frostbite_3dsmax_scripts)

Probably adding the other scripts too ( bf3, battlefront ) 

though i need to finish my maya plugin which will support everything plus the benefit of native code speed

comparison pictures:

[https://www.dropbox.com/s/hwxya4upecc5s ... 2.PNG?dl=0](https://www.dropbox.com/s/hwxya4upecc5su0/bf4_mesh_normals_02.PNG?dl=0)
[https://www.dropbox.com/s/rjbyf1mimc7j9 ... s.PNG?dl=0](https://www.dropbox.com/s/rjbyf1mimc7j9ie/bf4_mesh_normals.PNG?dl=0)
## Post #6
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-09-24T18:51:35+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

I hope your planned maya plugin will have a better way of exporting of head meshes without making them look like melted wax sculptures.
## Post #7
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2015-09-24T22:41:58+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

> Reply from artworkplay
>
> I hope your planned maya plugin will have a better way of exporting of head meshes without making them look like melted wax sculptures.

Ah i think that was a issue with how they exported stuff, like guns are all seperated and then its put together ingame using the animation. I will see if i can parse any animation data to easily solve this, i believe there are a lot of tpose anim dummys around.
## Post #8
- Username: Highflex
- Rank: beginner
- Number of posts: 34
- Joined date: Wed Jul 23, 2014 12:41 am
- Post datetime: 2015-09-27T23:27:20+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

Just updated the scripts, reading skeleton files is now fully fixed and everything works with max 2016, ( i should make a new thread for this soon )
## Post #9
- Username: artworkplay
- Rank: veteran
- Number of posts: 116
- Joined date: Thu Oct 06, 2011 4:40 am
- Post datetime: 2015-09-29T01:20:20+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

> Reply from Highflex
>
> Just updated the scripts, reading skeleton files is now fully fixed and everything works with max 2016, ( i should make a new thread for this soon )

Had a chance to try it with Max 2012 but got this while trying to import the skeleton
Error occurred in i loop; filename: C:\Program Files\Autodesk\3ds Max 2012\Scripts\bf4_skeleton_import_H2.ms; position: 2061; line: 94
## Post #10
- Username: JakeGreen
- Rank: mega-veteran
- Number of posts: 164
- Joined date: Mon Aug 23, 2010 5:14 am
- Post datetime: 2015-09-29T06:17:42+00:00
- Post Title: Battlefield 4 mesh importer - smoothing groups

> Reply from Highflex
>
> Just updated the scripts, reading skeleton files is now fully fixed and everything works with max 2016, ( i should make a new thread for this soon )

Do you think you could fix the SWBF importer as it seems to not work with the AT-AT and a few other small models like the very detailed main menu models.

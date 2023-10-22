## Post #1
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2016-07-21T00:32:27+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

Hello i hope someone can help me with that . 
i have tested all the scripts related to maya 2015 and maya 2012 and blender and Noesis 
and what i am facing is a problem with the animations 
i believe there is something wrong with the maya 2015 script and the way it imports the animation and the joints 
at first here what i tried to do : 
i tried to install the maya 2015 plugin and import league of legends 3d models and animations and everything seems to work great .
but after i export it to fbx and import it to a game engine (Unity 3D) i start getting some faces problems :

but the animations works fine and great .

and then i tried another thing is that i improted the SKN file to noesis and then convert to obj or fbx and import back to maya 2015 and that seems to work great no face problems but what i faced is that the model that i exported from noesis is fliped and not the same as how the animation joints are built :
here is the maya 2015 plugin with the face problem :


but thats what happens when i export from noesis to obj and then import again to maya to apply the animation :



as u can see here its flipped (mirrored) .

can someone help me with that ? here is akali SKN file and SKL file (2016 new files)
[https://mega.nz/#F!ZpRw0TZa!3DQRI_XppQqjLrpp3O3-eg](https://mega.nz/#F!ZpRw0TZa!3DQRI_XppQqjLrpp3O3-eg)

akali skn and skl for animation and model 
and the plugin i use 

if the plugin needs alot of money or alot of work i am willing to pay for it .

thanks
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-07-21T07:33:59+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

MEGA says: Enter decryption key
To access this folder/file, you will need its Decryption key.
If you do not have the key, contact the creator of the link.
## Post #3
- Username: lol2k12
- Rank: n00b
- Number of posts: 11
- Joined date: Sun Oct 27, 2013 11:47 pm
- Post datetime: 2016-07-21T22:39:26+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

i have updated the link and now it works
## Post #4
- Username: finalfantasix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 03, 2016 12:49 am
- Post datetime: 2016-07-26T05:51:36+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

same problem with animations import to maya 2015,
incorrect animation (New files 2016)
## Post #5
- Username: godskin
- Rank: veteran
- Number of posts: 98
- Joined date: Thu Nov 05, 2015 9:45 pm
- Post datetime: 2016-07-26T06:50:46+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

solve
## Post #6
- Username: finalfantasix
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 03, 2016 12:49 am
- Post datetime: 2016-07-26T07:27:09+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

as solve? help godskin pls bro...
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-07-27T16:23:25+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

> Reply from lol2k12
>
> but thats what happens when i export from noesis to obj and then import again to maya to apply the animationI don't have maya, but what I don't get: why don't you mirror the mesh in maya to get it matched to the skeleton again?
## Post #8
- Username: Slozhny
- Rank: beginner
- Number of posts: 26
- Joined date: Mon Aug 31, 2009 6:03 am
- Post datetime: 2016-08-29T23:23:05+00:00
- Post Title: League Of Legends 3D Models And Animation Flipped Help me

> Reply from lol2k12
>
> i have updated the link and now it works
Your main trouble is doble reconvert. So your model (skeletal mesh) has double damaged. U must reset mesh (reset Xform for 3DS Max) and reskin model again.

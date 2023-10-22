## Post #1
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2017-08-31T13:56:20+00:00
- Post Title: Trouble finding Faces data (Model researcher)

Hi, i'm using this tool to train myself in extracting 3D meshes from binary file format ([http://lazov.ru/mr/tutorial.php](http://lazov.ru/mr/tutorial.php))... but i have trouble finding faces data... i have followed the tutorial and reproduced it without problem but doing this for another format is difficult since it's the 1st time i'm doing it alone ! (haven't even tried to find UV at this moment...) i got the help from someone a year ago and i want to follow the work myself... here are the models i am training on actually : [https://www.mediafire.com/file/gv3y573c ... format.rar](https://www.mediafire.com/file/gv3y573cokbj2cg/3D%20binary%20file%20format.rar) for the 2 dancers i have already found the vertices [http://imgur.com/3m8bRpY](http://imgur.com/3m8bRpY) but the faces are another story... the format seems to always store vertices 1st (just after the header informations) and then faces and textures coordinates... 
My goal is to update the maxscript he made for me (if i can) to be able to import stages, avatars, animations on 3ds in the future, but i don't have the knowledge for this... so i'm starting with the "basis" and learning by myself...
anyway if someone want to help me to find the faces data i will really appreciate it, if any of you want to take a look at the stage sample and animations feel free to do it if you want.
Thank you for reading !
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-08-31T22:21:38+00:00
- Post Title: Trouble finding Faces data (Model researcher)

> Reply from Loginoux
>
> ... but i have trouble finding faces data...I wouldn't know, why. Search for 0000 0100 0200 and you're done (more or less):



discoclub_dancer1-rgm.jpg (180.88 KiB) Viewed 152 times


since it's a simple format with floats the FVB block is expected to consist of vx,vy,vz, nx,ny,nz, tx,ty, where
v: vertex, n: normals, t: texture coords. So 8 "float elements", one float has 4 bytes, so FVF size= 8x4=32 bytes.
## Post #3
- Username: Loginoux
- Rank: beginner
- Number of posts: 25
- Joined date: Tue Oct 13, 2015 5:25 pm
- Post datetime: 2017-09-01T11:42:36+00:00
- Post Title: Trouble finding Faces data (Model researcher)

Hi, thank you for your reply ! so now thanks to you i am able to find the faces and vertices data.
I tried with the disco dancer 2 file and i was able to extract the model ! 
[](https://www.hostingpics.net/viewer.php?id=537443bandicam20170901133548602.jpg)
The only thing that bothers me is UV pos, how did you find that value ? and i didn't understand that much the VB size thing... maybe if i read again it will be better idk...
Anyway i will try with the other samples i have and write here if i have trouble. 
Have a nice day !

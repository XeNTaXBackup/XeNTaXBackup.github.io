## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-14T09:25:09+00:00
- Post Title: FIFA 15 Bones [Problem again :P]

I guess i am not the luckiest when its about bones 
Anyway new problem, new questions, new topic 

I've been searching for bone definitions since the release of FIFA 14. But just yesterday while working on some FIFA 15 PC Demo files i made some progress.

Now let me explain first what is going on in FIFA model file concerning the bones.
There are 2 sections defined which are probably related to bones, and i can assume this because i have completely understood what the rest of the sections do and they have absolutely NOTHING to do with animations (Except the indices and weights assignments in vertex definitions).

Now about those 2 sections, the first one is a short one consisting of 200 to 300 bytes and i have no idea what its about. I have not found any repeated pattern or any value that makes sense with the rest of the model.

The second one is the one i worked on. It clearly contains transformation matrices. And it contains a lot of them. So i assumed that those are each bone's transformation matrices. I tried to exctract some the head and tail positions from the matrices, but the end result does not work for all bones. To be more precise the bone head position is calculated directly by extracting the translation Vector from the transformation matrix.

[](http://imgur.com/07JwXf2)

The head positions of the face bones seem correct, ALL THE REST ARE WRONG  
To be more specific the bones that appear right below the body, are the leg bones and they only need a -1 scale on Z axis and an 180 degrees rotation over Z to get into place.

The tail positions seem to be wrong as well, i guess that they should have been positioned near the surface of the model and not just below the bone head.


My biggets concern though is that i have not found any bone hierarchy. Is this possible that all bones have no parents? Is there any possibility that the skeleton is defined in a different "general" file?

If anybody needs the convertion code to get the bone head and tail locations just tell me i'll provide anything needed, as well as raw files for further investigation.

Thanks in advance
## Post #2
- Username: cra0
- Rank: ultra-veteran
- Number of posts: 438
- Joined date: Fri Apr 27, 2012 4:37 pm
- Post datetime: 2014-09-15T03:08:43+00:00
- Post Title: FIFA 15 Bones [Problem again :P]

Been interested in FIFA 15 myself, what's the structure for the bones look like though ? Is there a 3x4 matrix ? 

Did you try multiplying a child by its parents inverse?
## Post #3
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-15T06:29:19+00:00
- Post Title: FIFA 15 Bones [Problem again :P]

> Reply from cra0
>
> Been interested in FIFA 15 myself, what's the structure for the bones look like though ? Is there a 3x4 matrix ? 

Did you try multiplying a child by its parents inverse?

Its a 4x4 matrix, and that is what i am talking about, there is no hierarchy somewhere... There are just raw transformation matrices more than 200 the one after the other.

I really believe that the main skeleton with the bone hierachy is defined in an other file rather than the same mesh model file.

I've located some RIGAMATE files (thats the file header) have you ever encountered any of them? These also have some matrices in them but there seems to be some kind of linking between the bones. I had not the time to play around with this file yet, if you want to do so i can send it to you to check it
## Post #4
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-19T14:49:29+00:00
- Post Title: FIFA 15 Bones [Problem again :P]

I'm attaching some files containing two sample models (face and boot models) that contain bones and i've also attached separate hex workshop bookmarks, if anyone wants to see for which sections i am talking about.
[shoe.7z](https://xentaxbackup.github.io/file/7838_shoe.7z)

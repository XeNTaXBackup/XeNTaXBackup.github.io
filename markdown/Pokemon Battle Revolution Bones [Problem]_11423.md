## Post #1
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-15T22:05:01+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

Howdy everyone.

At the moment i am working on an importer for the Pokemon Battle Revolution game of 2007 (in Blender of course).

I had no problems with the model information, nor with the textures. What i am struggling with though are the bones.

All the sections contained in the file are defined in blocks and they are starting with some kind of id which i use for now to distinguish the sections for the models and the bone sections. Now for those bone sections there is a 3 float value contained which is probably the bone tail position and some offsets which lead to the children and sibling bones. In some sections there are some matrices contained in the sections but i can't figure out how to use them. I tried to apply them by multiplying it with the bone tail, but the result was literally shit  There is also another 3 float rotation defined which i also tried to apply on the bone tails and it seems like a rotation leading to a posing stance. 

So what i am thinking in the end is that i don't need neither the matrix nor the rotation, to simply visualize the bones in their default stance to match the model skin. There are still problems though. The closest i managed to get is here:



I can't figure out why the heck the legs and the arms are aligned like this, while the tail is in its place.
This is happening with other models as well. None of them gets its bones correctly aligned.

What has possibly gone wrong? Is there anything i am missing?
## Post #2
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-17T21:23:17+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

Update: I played around with some more models, and one of them got imported correctly


I can't explain why it is not working with the rest :S:S

Any clue about bone investigation in game models is highly appreciated.
## Post #3
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-20T12:43:46+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

*bump* anyone???
## Post #4
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-22T18:43:57+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

I think i need to generalize the question in order to get some opinions, so i want to know is:

Is there any possibility that the bone matrices and rotations i've found should be used in order to calculate the default bone position? For what i've searched so far, i see that the matrices are used in order to apply an animation or a specific pose. Could it be that the default bone position is thought as a special pose?


Please guys, i'm getting really desperate for some help. I'm totally stuck.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-22T19:29:43+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

Guess without samples and without the script noone will dig into this.
## Post #6
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-22T20:39:32+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2
>
> Guess without samples and without the script noone will dig into this.

Sorry for that 

So here is some more info about it 

first of all a typical bone header:
[](http://imgur.com/57AetmW)

And my python code:

```
    bpy.ops.object.add(type='ARMATURE',enter_editmode=True,location=(0,0,0))
    ob=bpy.context.object
    ob.name=pokemon_name
    amt = ob.data
    amt.name = pokemon_name+'Amt'
    #amt.show_axes = True
    print('Importing '+str(len(bone_positions_vectors)) +' Bones')
    
    for i in range(len(bone_positions_vectors)):
        bpy.ops.object.mode_set(mode='EDIT')
        bone=amt.edit_bones.new(bone_positions_names[i])
        bone.use_local_location=True
        bone.use_inherit_rotation=True
        bone.tail=Vector(bone_positions_vectors[i])
        mat=bone_positions_matrices[i]    
        
        if bone_positions_parents[i] in amt.edit_bones:
            
            #mat=bone_positions_matrices[bone_positions_parents.index(bone_positions_parents[i])]
            #bone_positions_matrices[i]=mat*bone_positions_matrices[i]
            parent=amt.edit_bones[bone_positions_parents[i]]
            bone.parent=parent
            bone.head=parent.tail
            bone.use_connect=True
        else:
            bone.head=Vector((0,0,0))
            
        
        bone.tail=bone.head+bone.tail
        
        #Final Check
        if bone.tail==bone.head:
            bone.tail+=Vector((0,0,0.1))
        
        bpy.ops.object.mode_set(mode='OBJECT')

```


If there is something more needed please tell me so that i can provide it
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-23T09:12:06+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

the model file which is imported correctly and one or two model samples which are not would be required.
## Post #8
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-23T09:46:35+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2
>
> the model file which is imported correctly and one or two model samples which are not would be required.

Okay
So this is mew which is imported correctly...
[https://www.dropbox.com/s/5zhedpnsd0qauw6/150_test_0](https://www.dropbox.com/s/5zhedpnsd0qauw6/150_test_0)
This is mewtwo which sucks...
[https://www.dropbox.com/s/hwbhiim3b4l5nx3/151_test_0](https://www.dropbox.com/s/hwbhiim3b4l5nx3/151_test_0)

This is a stripped version of the script that imports the bones to the scene. I've just stripped off the model and texture imports. Its much faster as well.
[https://www.dropbox.com/s/rnw4x22bqj6tw ... n_bones.py](https://www.dropbox.com/s/rnw4x22bqj6twuf/pokemon_bones.py)

With a bit tweaking on the script you can print the bone header offsets, for further investigation of the file. If you are not comfortable with that tell me and i'll fix it for you 


Unfortunately i don't know any other model whose bones are ok, but i can provide you a lot that do not get imported correctly
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-23T10:31:44+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

Seems it's 151_test_0 which is imported correctly, isn't it?

Thanx for sharing. Since I'm a "bones apprentice" I'm not sure whether I can help
but I'll try my very best. 

From a first glance on 150_test_0 I would guess it's a problem with trigonometric functions
(0° instead of 180° or vice versa which should be related to a 'minus' in matrix operations).

If you don't mind could you upload a picture of this model to get a clue how the bones should be orientated?
## Post #10
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-23T11:13:50+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2
>
> Seems it's 151_test_0 which is imported correctly, isn't it?

Thanx for sharing. Since I'm a "bones apprentice" I'm not sure whether I can help
but I'll try my very best. 

From a first glance on 150_test_0 I would guess it's a problem with trigonometric functions
(0° instead of 180° or vice versa which should be related to a 'minus' in matrix operations).

If you don't mind could you upload a picture of this model to get a clue how the bones should be orientated?

Yes i made a mistake with the names. 151_test_0 is mew and 150_test_0 is mewtwo.

Thanks a lot for your help :D I am a bones apprentice's apprentice so you probably know much more than i do, so your help is more than important.

Now for the pics, you can see them on the first two posts, these are the models. If its not that clear i can send you a blend file containing both models.

As for the actual problem, it is probably something like that, but the difficult part for me is to differentiate the bone headers. If it is something like a minus one that should be multiplied with the matrix components, where the heck is it defined, or set?

Also keep in mind that the vertices are in a -X Z Y format. I've made various experimentations so please check the parts where the matrices and the locations are saved for the applied axis order.
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-23T12:29:04+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from gregkwaste
>
> I am a bones apprentice's apprenticeAre you kidding? From what I see in your script, you're not.

> so you probably know much more than i doMaybe I understand 33% of your script...

> Now for the pics, you can see them on the first two posts, these are the models.Ah, ok, well, the "shadows". Seems my monitor's brightness (50%) is too low.

> As for the actual problem, it is probably something like that, but the difficult part for me is to differentiate the bone headers. If it is something like a minus one that should be multiplied with the matrix components, where the heck is it defined, or set?I would try to narrow down the problem to bone groups that seem to be correct (right arm for example) versa those that are not (right leg for ex.)

So there's obviously an additional 90° rotation
between upLegR - legR
and footR - toeR.

Atm I don't know how to apply a 90°s rotation to a single bone by script.
(All I achieved was turning a whole skeleton.)



wrong_bones.jpg (106.8 KiB) Viewed 206 times
## Post #12
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-23T12:52:24+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2
>
> gregkwaste wrote:I am a bones apprentice's apprentice Are you kidding? From what I see in your script, you're not.
Screw the script, this script is based on another one i found on blender artists, that introduced me on how blender controls the bones, the rest is just my way of importing the bones.

Feel free to ask me if you have any questions on any part of the script because its normal that you don't understand other sections. (Like the get_children function, this function is just the best function i've written )


> Reply from shakotay2
>
> 
so you probably know much more than i doMaybe I understand 33% of your script...
I may know how to write scripts but i have no idea about bones and stuff like that, that's why i asked for help, i do not know what i should expect to find in the file, and more important i don't know how to apply it.


> As for the actual problem, it is probably something like that, but the difficult part for me is to differentiate the bone headers. If it is something like a minus one that should be multiplied with the matrix components, where the heck is it defined, or set?

> I would try to narrow down the problem to bone groups that seem to be correct (right arm for example) versa those that are not (right leg for ex.)
>
> 
>
> So there's obviously an additional 90° rotation
>
> between upLegR - legR
>
> and footR - toeR.
>
> 
>
> Atm I don't know how to apply a 90°s rotation to a single bone by script.
>
> (All I achieved was turning a whole skeleton.)
>
> wrong_bones.jpg

first of all the bone parent is fixed, so you don't need to mess around with it. It draws its position from the parent or the 0,0,0 so you want to play with the tail.

Now in order to rotate the bone.tail, you can do it in various ways.
The easiest one is using Vectors rotate function. Bone.tail is a vector type. So i expect that by writing bone.tail.rotate(euler object). I assume that you know how to create an Euler object.

Its very easy:

```
eu.x,y,z= radian rotation
or all in one eu.rotate_axis('X' or 'Y' or 'Z',radians)

```


Btw those bones whose names start with ef or ct, should be different from the others. I don't know what could they be, joints? clusters? I have no idea. The only thing i can tell you is that those bones headers have a section id equal to 0x0 rather than the 0x2 of the rest of the bones.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-23T14:06:43+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from gregkwaste
>
> Its very easy:
Code: Select alleu=Euler()
eu.x,y,z= radian rotation
or all in one eu.rotate_axis('X' or 'Y' or 'Z',radians)
Thx - long forgotten memories arise...
In the
for i in range(len(bone_positions_vectors)):
loop I tried
        if i==51: bone.tail.rotate(eul)
but seems it's not the index for legR.
Also I've to hide dozens of bones manually again to get a better overview.
Have to think about it tomorrow.
(Doing the 90° z-rotation manually via the blender gui worked.)

> Btw those bones whose names start with ef or ct, should be different from the others. I don't know what could they be, joints? clusters? I have no idea.Me, too. But with some luck we can ignore them so far.
## Post #14
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-23T14:19:16+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2
>
> gregkwaste wrote:Its very easy:
Code: Select alleu=Euler()
eu.x,y,z= radian rotation
or all in one eu.rotate_axis('X' or 'Y' or 'Z',radians)

Thx - long forgotten memories arise...
In the
for i in range(len(bone_positions_vectors)):
loop I tried
        if i==51: bone.tail.rotate(eul)
but seems it's not the index for legR.
Also I've to hide dozens of bones manually again to get a better overview.
Have to think about it tomorrow.
(Doing the 90° z-rotation manually via the blender gui worked.)
Btw those bones whose names start with ef or ct, should be different from the others. I don't know what could they be, joints? clusters? I have no idea.Me, too. But with some luck we can ignore them so far.

Its really difficult to get the correct id manually, you better use this:

if bone.name=='legR'
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-04-24T14:48:57+00:00
- Post Title: Pokemon Battle Revolution Bones [Problem]

Thx - though it doesn't seem to make sense trying to correct the rotations manually.

In your opening post you wrote "There is also another 3 float rotation defined".
(I supposed them to be angles in radians and converted them into degrees.)
Shouldn't the values be identical or mirrored for left/right leg for example? 
As is for 151_test but not for 150_test:

150_test
upLegL   3.5557192153936525 -55.68430907653912 -88.53523428602308
upLegR   -0.728983155268552 16.08990565610301 -80.32057943162708

151_test
leg_b   0.47448000814926894 39.99999883637168 0.12653000142642667
leg_bb   0.47448000814926894 -39.99999883637168 0.0
## Post #16
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-04-24T15:14:10+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2
>
> Thx - though it doesn't seem to make sense trying to correct the rotations manually.

In your opening post you wrote "There is also another 3 float rotation defined".
(I supposed them to be angles in radians and converted them into degrees.)
Shouldn't the values be identical or mirrored for left/right leg for example? 
As is for 151_test but not for 150_test:

150_test
upLegL   3.5557192153936525 -55.68430907653912 -88.53523428602308
upLegR   -0.728983155268552 16.08990565610301 -80.32057943162708

151_test
leg_b   0.47448000814926894 39.99999883637168 0.12653000142642667
leg_bb   0.47448000814926894 -39.99999883637168 0.0

I'd also recommend that we start our searches with the head. It should be easier to handle, because there are no left and right sides.
Well the real analogue of upLegL and upLegR are leg_a and leg_aa
I'll try to print the values right now and check again what you are saying here. I do agree that there should be some sort of relation on them.

Edit:
Just printed them

leg_a 7.19137981860678 0.0 -5.6742202072362895
leg_aa 10.909899581075448 0.0 6.247180017272918

The last component has the same relation. But how should we apply that rotation? I remember trying to apply that on the bone tail but the result was still not good.
I am also thinking if the parent bone has any relation as well. Maybe its rotation should be applied on all its children.
## Post #17
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-05-16T16:17:51+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from gregkwaste
>
> shakotay2 wrote:Thx - though it doesn't seem to make sense trying to correct the rotations manually.

In your opening post you wrote "There is also another 3 float rotation defined".
(I supposed them to be angles in radians and converted them into degrees.)
Shouldn't the values be identical or mirrored for left/right leg for example? 
As is for 151_test but not for 150_test:

150_test
upLegL   3.5557192153936525 -55.68430907653912 -88.53523428602308
upLegR   -0.728983155268552 16.08990565610301 -80.32057943162708

151_test
leg_b   0.47448000814926894 39.99999883637168 0.12653000142642667
leg_bb   0.47448000814926894 -39.99999883637168 0.0

I'd also recommend that we start our searches with the head. It should be easier to handle, because there are no left and right sides.
Well the real analogue of upLegL and upLegR are leg_a and leg_aa
I'll try to print the values right now and check again what you are saying here. I do agree that there should be some sort of relation on them.

Edit:
Just printed them

leg_a 7.19137981860678 0.0 -5.6742202072362895
leg_aa 10.909899581075448 0.0 6.247180017272918

The last component has the same relation. But how should we apply that rotation? I remember trying to apply that on the bone tail but the result was still not good.
I am also thinking if the parent bone has any relation as well. Maybe its rotation should be applied on all its children.
Has anyone tried importing Giratina's bones into Blender?
## Post #18
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-05-17T12:41:49+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from Escope12
>
> gregkwaste wrote:shakotay2 wrote:Thx - though it doesn't seem to make sense trying to correct the rotations manually.

In your opening post you wrote "There is also another 3 float rotation defined".
(I supposed them to be angles in radians and converted them into degrees.)
Shouldn't the values be identical or mirrored for left/right leg for example? 
As is for 151_test but not for 150_test:

150_test
upLegL   3.5557192153936525 -55.68430907653912 -88.53523428602308
upLegR   -0.728983155268552 16.08990565610301 -80.32057943162708

151_test
leg_b   0.47448000814926894 39.99999883637168 0.12653000142642667
leg_bb   0.47448000814926894 -39.99999883637168 0.0

I'd also recommend that we start our searches with the head. It should be easier to handle, because there are no left and right sides.
Well the real analogue of upLegL and upLegR are leg_a and leg_aa
I'll try to print the values right now and check again what you are saying here. I do agree that there should be some sort of relation on them.

Edit:
Just printed them

leg_a 7.19137981860678 0.0 -5.6742202072362895
leg_aa 10.909899581075448 0.0 6.247180017272918

The last component has the same relation. But how should we apply that rotation? I remember trying to apply that on the bone tail but the result was still not good.
I am also thinking if the parent bone has any relation as well. Maybe its rotation should be applied on all its children.
Has anyone tried importing Giratina's bones into Blender?

Did not try to, but i can do it now. I don't guarantee for the result though  99% they are going to be completely out of place 

Edit:
Here you are :


There are a lot of bones in there, seems really detailed, but out of place :(
## Post #19
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-05-17T20:40:25+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

Do you think you can fix that?
## Post #20
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-05-18T07:32:15+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from Escope12
>
> Do you think you can fix that?
Well i was busy with other stuff, but when i imported the giratina model to check the bones, i started working on the bones again, trying to find out what is missing and how i can fix it.
I decided to NOT apply any kind of matrix. Mew bones did not need a matrix to show up correctly, and the same should stand for every model. So i tried imposing custom rotations on the bones and i ended up in something like this :

[](http://imgur.com/8hpwsAI)


The rotations i implied were on magnitude 90 or 180 degrees but i needed to apply them in different axes. unfortunately this does not seem to apply everywhere, because as you can see there is no rotation of 90 or 180 or -90 degrees that will get the wing bones aligned.  So there should be something more in the file that i am missing right now. I am working on some values that i found, i hope i can fix it once and for all this time.
## Post #21
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-05-19T16:57:02+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

OK Thank you. Did you also know that some of the models don't show how the game shows when they are textured? Can you also fix that?
## Post #22
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-05-19T22:16:32+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from Escope12
>
> OK Thank you. Did you also know that some of the models don't show how the game shows when they are textured? Can you also fix that?

I tried a completely different way of reading and storing the bones, thinking that this was the cause of the mistakes, but again i ended up on a failure. I guess i'll have to wait until someone more experienced offers to help me, or to think of something new to apply 


I did not understand your question to be honest. Do you have any pics to show me? I do not own the game, i've also never played it xD i am just messing around with the files so i don't know how they show up ingame.
## Post #23
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-06-05T12:40:40+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from gregkwaste
>
> Escope12 wrote:OK Thank you. Did you also know that some of the models don't show how the game shows when they are textured? Can you also fix that?

I tried a completely different way of reading and storing the bones, thinking that this was the cause of the mistakes, but again i ended up on a failure. I guess i'll have to wait until someone more experienced offers to help me, or to think of something new to apply 


I did not understand your question to be honest. Do you have any pics to show me? I do not own the game, i've also never played it xD i am just messing around with the files so i don't know how they show up ingame.

Here is a picture to prove it.
[palkia side.jpg](https://xentaxbackup.github.io/file/7434_palkia side.jpg)
## Post #24
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-06-09T15:54:26+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from Escope12
>
> gregkwaste wrote:Escope12 wrote:OK Thank you. Did you also know that some of the models don't show how the game shows when they are textured? Can you also fix that?

I tried a completely different way of reading and storing the bones, thinking that this was the cause of the mistakes, but again i ended up on a failure. I guess i'll have to wait until someone more experienced offers to help me, or to think of something new to apply 


I did not understand your question to be honest. Do you have any pics to show me? I do not own the game, i've also never played it xD i am just messing around with the files so i don't know how they show up ingame.

Here is a picture to prove it.

This is a blender screenshot mate, i see how it looks like in there. Post an ingame screenshot so i can see the difference.
## Post #25
- Username: Escope12
- Rank: mega-veteran
- Number of posts: 171
- Joined date: Tue Feb 28, 2012 7:42 am
- Post datetime: 2014-06-09T16:38:24+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

Hare is a ingame picture
[palkia.jpg](https://xentaxbackup.github.io/file/7454_palkia.jpg)
## Post #26
- Username: gregkwaste
- Rank: advanced
- Number of posts: 69
- Joined date: Wed Apr 16, 2014 5:17 am
- Post datetime: 2014-09-06T20:31:51+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from Escope12
>
> Hare is a ingame picture

sorry for the late response,

i don't see something wrong. Its just the lighting effects that are applied from the game engine. If you notice, all model textures are as mate as hell. There are minor details on them.
## Post #27
- Username: DahniMae
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 19, 2023 4:18 am
- Post datetime: 2023-06-18T09:28:45+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

"Btw those bones whose names start with ef or ct, should be different from the others. I don't know what could they be, joints? clusters? I have no idea. The only thing i can tell you is that those bones headers have a section id equal to 0x0 rather than the 0x2 of the rest of the bones."

i can answer this! these bones starting with EF or CT (Effect or Control) are just sort of Positional that are used by the pokemon battkle engine to place effects such as where bubble beam comes out of when in battle when they use moves or do stuff, they dont ever hold any animation or bone weight data for the model itself and can even be safely left out of the model if need be 

their only purpose is to do stuff inside the game engine rather than control any part of the model
## Post #28
- Username: DahniMae
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sun Mar 19, 2023 4:18 am
- Post datetime: 2023-06-18T09:30:57+00:00
- Post Title: Re: Pokemon Battle Revolution Bones [Problem]

> Reply from shakotay2 ↑Wed Apr 23, 2014 8:29 pm at Wed Apr 23, 2014 8:29 pm
>
> 
gregkwaste wrote:I am a bones apprentice's apprentice Are you kidding? From what I see in your script, you're not.
so you probably know much more than i doMaybe I understand 33% of your script...
Now for the pics, you can see them on the first two posts, these are the models. Ah, ok, well, the "shadows". Seems my monitor's brightness (50%) is too low.
As for the actual problem, it is probably something like that, but the difficult part for me is to differentiate the bone headers. If it is something like a minus one that should be multiplied with the matrix components, where the heck is it defined, or set?I would try to narrow down the problem to bone groups that seem to be correct (right arm for example) versa those that are not (right leg for ex.)

So there's obviously an additional 90° rotation
between upLegR - legR
and footR - toeR.

Atm I don't know how to apply a 90°s rotation to a single bone by script.
(All I achieved was turning a whole skeleton.)

wrong_bones.jpg

so following what ive said in the post above, this "ef_knee" bone isnt actually a knee and isnt controlling any part of the model, its just a placer for an effect that comes out of the Knee or such when the mon is using some sort of move in battle

it wont hold any weights or move the model itself or anything, its just a marker placed on the rig

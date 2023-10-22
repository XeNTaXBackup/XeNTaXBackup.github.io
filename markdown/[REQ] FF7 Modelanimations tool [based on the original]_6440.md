## Post #1
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-16T16:01:59+00:00
- Post Title: [REQ] FF7 Model/animations tool [based on the original]

I hope I did not get the wrong section but this one seems to be the most suitable.

I would like to request a new, improved tool for FF7 that somehow expands on the original bread-and-butter tool, Kimera. But, this time, with the proper focus on animations. Kimera's interface is rather unfriendly in this task and somewhat limited (all tutorials, like [this](http://ff7modhd.yolasite.com/resources/files/Simple%20Battle%20Editing.pdf), . I think it is required a program that gives modders more power over animation editing, bone number increasing, and also by supporting import/export of the animations themselves in programs like Milkshape for even easier editing, maybe also by importing other formats -Collada, etc- for referencing/modeling after those; and especially that does not corrupt the models edited in loco. I hope I was clear  

I wanted to upload the editor itself and a sample file but apparently I can't.

> Could not upload attachment to ./files/30075_55afe99d310369428787a98aab72ad91.
[here](http://www.megaupload.com/?d=ISEKDDQX) is the editor megaupload link. However, even if it's the latest version it still has a tendency to corrupt edited models, so please be careful.

[This](http://www.megaupload.com/?d=JHACAJNX) is the sourcecode, freely available to edit. It requires OpenGL Visual Basic 6 to be edited, found [here](http://home.pacific.net.hk/~edx/tlb.htm).

This is a brief explanation of FF7 anims, not done by me.

> -- FF7 .A animation files --
>
> --- brief info written by mirex --
>
> 
>
> Each animation file holds one character animation ( run, walk or some other).
>
> Some characters have more animation files. Animation is set of frames,
>
> in each frame are stored bone rotations.
>
> 
>
> -- animation file contents --
>
> name        size in bytes
>
> header      24
>
> unknown     12
>
> frames      frames_count * frame
>
> 
>
> -- one frame, size is ( bones * 12 + 24 ) --
>
> unknown     24 bytes = 6 floats
>
> rotations   bones * 12 bytes = bones * 3 floats
>
> 
>
> 
>
> // header structure, 24 bytes
>
> struct {
>
>     unsigned long   x1;
>
>     unsigned long   frames_count;
>
>     unsigned long   bones_count;
>
>     unsigned long   x2, x3, x4;
>
> } anim_head;
>
> 
>
> I understand only two values from the header, 'frames_count' which is number
>
> of animation frames and 'bones_count' which is suprisingly number of animated
>
> bones. 
>
> 
>
> If you want to load all possible animations for the model (even anims
>
> of different models) then check if animation file has same number of bones
>
> as current model.
>
> 
>
> After header there is 12 bytes of data that are unknown to me. It could
>
> be some center of coord system or anything.
>
> 
>
> Frame starts with 6 floats (unknown), followed by rotations for each bone.
>
> Rotations are stored as 3 floats (float is 4byte floating-point number).
Is there a good soul willing to spend his or her time to fulfill this task? 
Thank you/Merci/Grazie/Danke/おかげで
## Post #2
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-04-30T07:19:14+00:00
- Post Title: [REQ] FF7 Model/animations tool [based on the original]

what can I do to make someone more interested in this? a paypal donation for the spent time, maybe?
## Post #3
- Username: Chev
- Rank: beginner
- Number of posts: 24
- Joined date: Sat Mar 19, 2011 1:06 am
- Post datetime: 2011-04-30T10:18:21+00:00
- Post Title: [REQ] FF7 Model/animations tool [based on the original]

Well, you're asking for a whole animation authoring tool, which is a bit of a tall order to put it mildly and quite outside of the scope of what usually gets made here (viewers, at best exporters), so the odds are slim. Well, the complete tool you'll never get, reducing the scope to an exporter/importer pair of programs for a format usable in existing modeling packages would be more realistic.
## Post #4
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-05-01T06:59:34+00:00
- Post Title: [REQ] FF7 Model/animations tool [based on the original]

importer/exporter for animation files? that would be very nice, unless said animation files are more complicated than the editor itself
## Post #5
- Username: Devilot
- Rank: ultra-veteran
- Number of posts: 443
- Joined date: Tue Sep 07, 2010 5:12 pm
- Post datetime: 2011-05-07T18:59:17+00:00
- Post Title: [REQ] FF7 Model/animations tool [based on the original]

> Reply from Chev
>
> Well, you're asking for a whole animation authoring tool, which is a bit of a tall order to put it mildly and quite outside of the scope of what usually gets made here (viewers, at best exporters), so the odds are slim. Well, the complete tool you'll never get, reducing the scope to an exporter/importer pair of programs for a format usable in existing modeling packages would be more realistic.

I second this idea. anyone willing to do it?
## Post #6
- Username: xman2000
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Sep 26, 2019 2:23 pm
- Post datetime: 2019-09-29T05:06:32+00:00
- Post Title: [REQ] FF7 Model/animations tool [based on the original]

> Reply from Devilot ↑Sun Apr 17, 2011 12:01 am at Sun Apr 17, 2011 12:01 am
>
> 
I hope I did not get the wrong section but this one seems to be the most suitable.

I would like to request a new, improved tool for FF7 that somehow expands on the original bread-and-butter tool, Kimera. But, this time, with the proper focus on animations. Kimera's interface is rather unfriendly in this task and somewhat limited (all tutorials, like this, . I think it is required a program that gives modders more power over animation editing, bone number increasing, and also by supporting import/export of the animations themselves in programs like Milkshape for even easier editing, maybe also by importing other formats -Collada, etc- for referencing/modeling after those; and especially that does not corrupt the models edited in loco. I hope I was clear  

I wanted to upload the editor itself and a sample file but apparently I can't.

Could not upload attachment to ./files/30075_55afe99d310369428787a98aab72ad91.
here is the editor megaupload link. However, even if it's the latest version it still has a tendency to corrupt edited models, so please be careful.

This is the sourcecode, freely available to edit. It requires OpenGL Visual Basic 6 to be edited, found here.


Hi someone have this software written in VB6 (broken link) ?  
important to me.  thanks.

## Post #1
- Username: snail
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 27, 2019 8:01 pm
- Post datetime: 2019-04-27T12:08:12+00:00
- Post Title: Finding out what 3Dfile it is.

Hello Xentax

I have a file and really want to change it to a different model i have uploaded the file,
maybe you guys can help me with it.

[https://drive.google.com/open?id=1ReSKd ... Lh0DDx2hCC](https://drive.google.com/open?id=1ReSKdkDsNIRP7QrAlypKEmLh0DDx2hCC)

Greetings Snail
## Post #2
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-27T13:38:12+00:00
- Post Title: Finding out what 3Dfile it is.

not sure what you asking for. you wanna know which game it potentially belongs too? you can google that. it's whether everquest or a gta vice city file. in terms of content, we could code a noesis script to load and view it. there's no easy way backwards into the game file tho. not sure if this is any game file either tho. it's only positions and colors. nothing else.
## Post #3
- Username: snail
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 27, 2019 8:01 pm
- Post datetime: 2019-04-27T13:59:30+00:00
- Post Title: Finding out what 3Dfile it is.

Thank you for helping me out i have got it from the TomTom mobile application and want to change it if possible.
So if you can help me with that would be awesome tried many programs to open it but seems not the file from those games or applications.
also tried kompas 3d but also wont open it.
Cant we find out with the header what program made it ?
## Post #4
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-27T14:57:13+00:00
- Post Title: Finding out what 3Dfile it is.

again... changing this is not really easy. you gotta 'compile' the new data somehow and recreate the header in some way. there are 40-44 bytes that gotta be correct and tested. so... you got a lil bit of stuff todo yourself. i'm working on the noesis script rn, but it's the usual buffer recast mess or missing feature piss. i can't generate a dummy index list, casue the list data type can't be set, nor does noesis support a plain unindexed triangle list. ugh... not very nice. 

edit: got it. the geometry is not culling tho. and i just noticed what i think you're trying to do. a custom car model in your navi app? 

well you'd need a simple exporter for a modelling program (just like blender). i'm certain somebody with more experience then me, could write that for you. the header copy paste aside, it's a pretty simple format. the model could potentially be done in a single part, what i guessed are the parts and count.
[fmt_tomtom_m3d.rar](https://xentaxbackup.github.io/file/16126_fmt_tomtom_m3d.rar)
## Post #5
- Username: snail
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 27, 2019 8:01 pm
- Post datetime: 2019-04-27T16:12:00+00:00
- Post Title: Finding out what 3Dfile it is.

Thank you indeed that is what i wanted to do.
Now only need to find out how to modify the model haha but big thx.
## Post #6
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-27T17:21:41+00:00
- Post Title: Finding out what 3Dfile it is.

i'm messing with blender py rn. maybe i'll have an exporter done later. or maybe in a couple hours (tomorrow). 

(i need to learn it anyway. gonna need an exporter for my own engine model format at a later point)
## Post #7
- Username: snail
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sat Apr 27, 2019 8:01 pm
- Post datetime: 2019-04-27T17:35:11+00:00
- Post Title: Finding out what 3Dfile it is.

Cool thank you haha your awesome.
## Post #8
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-04-28T19:25:55+00:00
- Post Title: Finding out what 3Dfile it is.

i throw it.  been working on this all day. blender doesn't give out correct raw triangles. neither correct colors. the indices are all over the place. i got correct colors when splitting (really splitting) the polys/triangles on a test quad. pretty blah. it may work when you get to seperate all polys on bigger models. unfortunetaly there is no automatic function for that. so... manual it is. it can export multiple part files tho. maybe you find somebody who understands blender's data layout better to make the de-indexing work correct. 

[https://www.mediafire.com/file/qq3xcu8u ... tomtom.rar](https://www.mediafire.com/file/qq3xcu8uyo5o6he/tomtom.rar)

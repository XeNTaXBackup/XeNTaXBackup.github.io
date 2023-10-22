## Post #1
- Username: Roman
- Rank: advanced
- Number of posts: 55
- Joined date: Wed Aug 19, 2015 2:54 pm
- Post datetime: 2016-09-06T13:16:18+00:00
- Post Title: 3d maxscript load for bones animation data.

I have animation data for bones.
Data like this: int32 time1, float32 quat1(x,y,z,w) and float32 pose1(x,y,z) 
                   int32 time2, float32 quat2(x,y,z,w) and float32 pose2(x,y,z)
Maxscript load(import) this data and apply to bones.
Question how right apply to bones animation data ?

Model have 14 bones.

I get first bone then do $.transform = quat1 x y z w 
Then i get second bone and do $.transform = quat2 x y z w 
And do like this for all bones.
But animation look wrong.

May be i not right transform bones in maxscript or my algorithm wrong ?

Maxscript load data correct from file. 
Good if say me algorithm, how right transform bones in maxscript.
Step by step.

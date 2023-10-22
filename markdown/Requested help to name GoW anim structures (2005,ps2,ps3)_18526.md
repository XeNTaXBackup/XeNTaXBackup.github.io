## Post #1
- Username: MogAika
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Aug 01, 2018 5:12 am
- Post datetime: 2018-07-31T23:25:03+00:00
- Post Title: Requested help to name GoW anim structures (2005,ps2,ps3)

Hi folks! I working on a tool that allows to extract/modify "god of war (2005)" resources. I plan to extrapolate this tool to gow2 and then gow3 engine.
[https://github.com/mogaika/god_of_war_b ... ow_2_minor](https://github.com/mogaika/god_of_war_browser/tree/gow_2_minor) (currently I work in gow_2_minor branch, master a little outdated)
Currently, I working on animation parsing and have some success
Video of buggy proof of concept of rotation anims to proof my ambitions (do not look at broken vertex<=>boneId mapping): [https://youtu.be/dgRNge0cBSo](https://youtu.be/dgRNge0cBSo)

Sooo, I'm totally dumb in animation terminology and need your help to name resources structs.
Much better if you can link this structs below to maya animation workflow (Almost all game was created in Maya)
Below is simplified version of structs format inside anim resource:

```
|= []DataType             # describe target type of animation, every Act has array of States that represent act State for cooresponding DataType
|                         # example: texture U, skeletal, particles
|                         
|= []Group                # has multiple Acts, has name, examples: bClimb, bwalk, balWalk, what remind me of blend groups
| |                       # (in case of balWalk its obvious because there are only 5 animations that
| |                       # represent different Kratos angles when he walks on beam.
| |                       # Can has external flag, that means that this anim group will be loaded from different resource (cutscenes and specific smash anims)
| |                       
| |= []Act                # has array of States, every state represents animation data for corresponding DataType, represents one animation, has Name (like walkBlend0, runLand, wallGrubL, ropeSlide)
| | |                     
| | |= []State            # has single or multiple Chunks, also contain float that used to convert from frames/samples-time to time in seconds.
| | | |                   
| | | |= []Chunk          # has 1 main Interval and possible array of sub Intervals, also has DataBitMap to explain wich parts of resources must be animated.
| | | | |                 # for example, if in animation something moves only first 3 and last 3 frames, then main Interval will have length==0 and
| | | | |                 # for animation purposes we will use sub Intervals (in our example case there will be 2 sub intervals for first 3 and last 3 frames).
| | | | |                 # chunks constructed in way to reduce number of dummy samples of data (unite changes that must happen in close time periods).
| | | | |                 # different type of animations (joint pos, joint rot, joint scale) stored in different chunks
| | | | |                 
| | | | |= DataBitMap     # shows which elements will be animated in this chunk (example: Xpos of 1 bone, Yrot of 3 bone and Zscale for 2bone)
| | | | |                 
| | | | |= Interval       # main Interval, has framesCount, startFrameOffset, lengthInFramesTime and offsetToIntervalData
| | | | |= []Interval     # possible array of sub Interval's, same struct as above, exists in case explained above (when main Interval framesCount == 0)
| | | | | |            
| | | | | | = SamplesData # not a struct, real data array, can vary from type to type. possible variants for joint pos/rot/scale intervals:
| | | | | | | - raw samples         # float32/fixedPoint15.8
| | | | | | | - compressed samples  # int16, int8, must be multiplyed by 2^n where n specified in special separated array
| | | | | | | - additive samples    # int16, must be added to prev frame value to get next frame value (multiplyed by 2^n too)
| | | | | | |                       # also we cannot skip such frames to get next frame (in case anim is too fast)

```


And, as always, sorry for my english

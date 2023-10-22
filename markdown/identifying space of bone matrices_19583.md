## Post #1
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2019-03-02T17:19:53+00:00
- Post Title: identifying space of bone matrices

I am trying to analyze bone information. Weirdly this format stores 5 matrices for each bone. I know that the 1st matrix is the inverse modelspace bind pose. I also know that the 2nd matrix is the modelspace bind pose. Now I'm stuck trying to identify the last 3 matrices. My guess is one of it is the localspace and inverse localspace bind pose. I have no idea on what the 5th one could be.

Here are some of the data: (taken through Noesis)

```

((0.0, -0.0, -1.0), (-0.0, 1.0, -0.0), (1.0, -0.0, 0.0), (-0.7449899911880493, -19.03723907470703, -0.0)) // inverse modelspace bindpose
((0.0, 0.0, 1.0), (0.0, 1.0, 0.0), (-1.0, 0.0, 0.0), (0.0, 19.03723907470703, -0.7449899911880493)) // modelspace bindpose
((1.0, 0.0, 0.0), (0.0, 1.0, 0.0), (0.0, 0.0, 1.0), (0.0, 0.0, 0.0)) // unknown
((0.0, 0.0, 1.0), (0.0, 1.0, 0.0), (-1.0, 0.0, 0.0), (0.0, 19.03723907470703, -0.7449899911880493)) // unknown
((0.04737327992916107, -0.022383077070116997, 0.9986264109611511), (0.007453800644725561, 0.9997289776802063, 0.02205418422818184), (-0.9988494515419006, 0.006398778408765793, 0.04752727970480919), (-0.06532999873161316, 17.62476921081543, 4.6052398681640625)) // unknown

bone_1 | parent: root_bone
((1.0, -0.0, 0.0), (-0.0, 1.0, -0.0), (0.0, -0.0, 1.0), (-0.0, -0.06299000233411789, 0.7449899911880493))
((1.0, 0.0, 0.0), (0.0, 1.0, 0.0), (0.0, 0.0, 1.0), (0.0, 0.06299000233411789, -0.7449899911880493))
((1.0, 0.0, 0.0), (0.0, 1.0, 0.0), (0.0, 0.0, 1.0), (0.0, 0.0, 0.0))
((0.0, 0.0, -1.0), (0.0, 1.0, 0.0), (1.0, 0.0, 0.0), (0.0, -18.9742488861084, 0.0))
((0.9999999403953552, -1.8884044266087585e-06, -6.035664682713104e-06), (1.8795659570969292e-06, 1.0, -1.4686231679661432e-06), (6.036471859260928e-06, 1.4666445622424362e-06, 1.0), (-0.0653049498796463, 0.06299915909767151, 4.6053595542907715))

bone_2 | parent: root_bone

((-0.0, 1.0, 0.0), (1.0, 0.0, 0.0), (0.0, -0.0, -1.0), (-19.03723907470703, -0.0, -0.30254000425338745))
((-0.0, 1.0, 0.0), (1.0, 0.0, 0.0), (-0.0, 0.0, -1.0), (0.0, 19.03723907470703, -0.30254000425338745))
((1.0, 0.0, 0.0), (0.0, 1.0, 0.0), (0.0, 0.0, 1.0), (0.0, 0.0, 0.0))
((0.0, 0.0, 1.0), (1.0, 0.0, 0.0), (0.0, 1.0, 0.0), (-0.44244998693466187, 0.0, 0.0))
((-0.022383077070116997, 0.9986264109611511, 0.04737327992916107), (0.9997289776802063, 0.02205418422818184, 0.007453800644725561), (0.006398778408765793, 0.04752727970480919, -0.9988494515419006), (-0.08629030734300613, 17.621471405029297, 5.047180652618408))

bone_3 | parent: bone_2

((0.0, 0.9936618804931641, 0.11241021752357483), (1.0, 0.0, -0.0), (-0.0, 0.11241021752357483, -0.9936618804931641), (-21.186338424682617, -0.0, -2.9292166233062744))
((-0.0, 1.0, -0.0), (0.9936618804931641, 0.0, 0.11241021752357483), (0.11241021752357483, -0.0, -0.9936618804931641), (-0.0, 21.381330490112305, -0.5290899872779846))
((1.0, 0.0, 0.0), (0.0, 0.9999980926513672, 2.9190516670496436e-10), (0.0, -2.9190516670496436e-10, 0.9999980926513672), (0.0, 4.077511766809039e-05, -1.0092104503200972e-06))
((0.9936618804931641, 0.0, 0.11241021752357483), (0.0, 1.0, 0.0), (-0.11241021752357483, 0.0, 0.9936618804931641), (2.3440914154052734, 0.0, 0.22654998302459717))
((-0.0023906442802399397, 0.9987384080886841, 0.05015873908996582), (0.9899377822875977, 0.00946025736629963, -0.14118656516075134), (-0.14148297905921936, 0.04931650310754776, -0.9887115359306335), (-0.1280258744955063, 19.966615676879883, 4.835890769958496))

...

```


Once I do find out what those last 3 matrices are I'll also need to find out how to convert my modelspace bones to that space. 

Thank you.
## Post #2
- Username: Lynix
- Rank: advanced
- Number of posts: 42
- Joined date: Wed Jul 01, 2015 10:11 pm
- Post datetime: 2019-03-02T17:39:42+00:00
- Post Title: identifying space of bone matrices

You can try for each matrix to make a skeleton and See if it is a Skeleton maybe so you can figure out what the matrixes are
## Post #3
- Username: episoder
- Rank: mega-veteran
- Number of posts: 162
- Joined date: Sat Oct 17, 2015 3:05 am
- Post datetime: 2019-03-02T18:07:31+00:00
- Post Title: identifying space of bone matrices

The 3rd seems an "identity" aka "normal zero" or scale matrix. The slightly off 1.0 and low (exponential notation) numbers indicate some numerical errors as far as i can estimate. The 4th could be the parent orientation or ik or something, same as the 5th. Local space or not. To be sure you should output all of those matrices as seperate bones to identify and debug the locations and rotations. That's all i can think of.
## Post #4
- Username: majidemo
- Rank: advanced
- Number of posts: 71
- Joined date: Sun Aug 21, 2016 7:00 am
- Post datetime: 2019-03-02T18:34:28+00:00
- Post Title: identifying space of bone matrices

> Reply from episoder ↑Sun Mar 03, 2019 2:07 am at Sun Mar 03, 2019 2:07 am
>
> 
The 3rd seems an "identity" aka "normal zero" or scale matrix. The slightly off 1.0 and low (exponential notation) numbers indicate some numerical errors as far as i can estimate. The 4th could be the parent orientation or ik or something, same as the 5th. Local space or not. To be sure you should output all of those matrices as seperate bones to identify and debug the locations and rotations. That's all i can think of.

Thank you. I'll try to investigate based on your suggestions.

At one point this all didn't matter as all I needed was to extract the data and display it in 3D. Now I have to convert it back to this format and it's starting to get complicated.

I think based on the game there is really no point in keep IK data. Unless they just didn't care for file size and space and just dumped even unrelevant information into their custom files. (game is from 2001)

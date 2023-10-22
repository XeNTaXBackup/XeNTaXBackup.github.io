## Post #1
- Username: Cheshire1012
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 11, 2014 11:31 am
- Post datetime: 2023-05-24T05:23:16+00:00
- Post Title: [Mobile]Yu-Gi-Oh Cross Duel (*.bundle)

Hi everyone!
I have tried to rip this mobile game with existed tools but I still failed to extract the model with correct uv mapping.
I could figure the 3d assets by guessing the random *.bundle file by using UABEA and extract the model by using UABE.
But the problem was that the mapping was not correct after using UABE. Maybe the plugin was something wrong. The situation was below:



sameple.jpg (90.09 KiB) Viewed 110 times


Hence, I want to know if there is better way to extract it normally.
The sample was below:
[sample file](https://www.mediafire.com/file/e0e4zttru3wk9py/12cee350a2974733df813833be99b36a.bundle/file)
## Post #2
- Username: fajNYgosciu1234
- Rank: veteran
- Number of posts: 145
- Joined date: Fri Oct 30, 2020 9:31 pm
- Post datetime: 2023-05-29T17:53:39+00:00
- Post Title: [Mobile]Yu-Gi-Oh Cross Duel (*.bundle)

i have tested your sample and looks like you need to use assetstudio, but you need to put the version of the bundle in the specify unity version option, for me the uv's worked perfectly, my guess is that the cause of this is uabe doesn't export uvs correctly with meshes
## Post #3
- Username: Cheshire1012
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Nov 11, 2014 11:31 am
- Post datetime: 2023-06-06T14:00:17+00:00
- Post Title: [Mobile]Yu-Gi-Oh Cross Duel (*.bundle)

> Reply from fajNYgosciu1234 ↑Tue May 30, 2023 1:53 am at Tue May 30, 2023 1:53 am
>
> 
i have tested your sample and looks like you need to use assetstudio, but you need to put the version of the bundle in the specify unity version option, for me the uv's worked perfectly, my guess is that the cause of this is uabe doesn't export uvs correctly with meshes

which specify  unity version do you use?

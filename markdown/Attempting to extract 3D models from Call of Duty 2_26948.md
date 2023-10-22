## Post #1
- Username: BillyMartin
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jun 05, 2023 7:59 pm
- Post datetime: 2023-07-07T02:02:59+00:00
- Post Title: Attempting to extract 3D models from Call of Duty 2

Hello there, everyone. I'm attempting to extract 3D models from Call of Duty 2: Big Red One using hex2obj or model researcher, but I'm getting no results. I've attempted to study hex but it's just too difficult to grasp, therefore I was wondering if someone had made a script or knows how to convert.To obj, convert xboxmesh.Luxox18 tried something similar with Call of Duty 3.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-07-07T07:04:24+00:00
- Post Title: Attempting to extract 3D models from Call of Duty 2

> Reply from BillyMartin ↑Fri Jul 07, 2023 10:02 am at Fri Jul 07, 2023 10:02 am
>
> 
... but I'm getting no results. I've attempted to study hex but it's just too difficult to grasp
What attempts had you made and what information/tutorials had you read for reference?

> Reply from BillyMartin ↑Fri Jul 07, 2023 10:02 am at Fri Jul 07, 2023 10:02 am
>
> 
... therefore I was wondering if someone had made a script or knows how to convert
That's really a dramatic transition. Don't give up so quickly.  
If there were any scripts you should have used the forum search or google first before creating this thread, yet why bother struggling to learn in the first place if so?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-07-07T10:08:15+00:00
- Post Title: Attempting to extract 3D models from Call of Duty 2

> Reply from BillyMartin ↑Fri Jul 07, 2023 10:02 am at Fri Jul 07, 2023 10:02 am
>
> ... using hex2obj or model researcher, but I'm getting no results. I've attempted to study hex but it's just too difficult to grasp, therefore I was wondering if someone had made a script or knows how to convert.Since you didn't provide a sample I checked xbmesh from here:

> Reply from braveplayer50 ↑Wed Nov 10, 2021 4:42 pm at Wed Nov 10, 2021 4:42 pm
>
> And yes, seems to be hard to handle. The vertices don't arrange to a meaningful point cloud, no matter which FVFsize I used: 12, 16, and so on up to 48, which was the most promissing candidate.

Maybe you'll need to collect the last float of each 16 bytes block to create a face of 3 of them, dunno. Too tired for fiddling around...

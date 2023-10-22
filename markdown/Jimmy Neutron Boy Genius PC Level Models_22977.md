## Post #1
- Username: trussive
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 06, 2019 5:51 am
- Post datetime: 2020-11-08T00:08:17+00:00
- Post Title: Jimmy Neutron Boy Genius PC Level Models

Hi, how's it going? I'm messing around with this game again, but level models aren't easily found... at all.

I suspect they might either be in the level OMT archives, or in the GAM files (though GAM seems to tell the game what to load and where, rather than the map itself.)

I would settle for Ninja Ripper, but UV maps are broken, and some tris don't get ripped.

Here's some miscellaneous files from the game that I think might have level models. I would just send the whole game, but I doubt I can.

[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/117acpmMNk4wdTDml3v2qbLYglAXRSKl7?usp=sharing)
## Post #2
- Username: trussive
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 06, 2019 5:51 am
- Post datetime: 2020-12-08T04:51:23+00:00
- Post Title: Jimmy Neutron Boy Genius PC Level Models

Alright, after some digging through the OMT files, I found level models, and materials. Now, my only issue is figuring out how to load them in, say, Blender.

Here's some samples.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1FDl8BefNvghaoZZwLT0ljPEiqTcyXWCt?usp=sharing)
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-08T17:26:47+00:00
- Post Title: Jimmy Neutron Boy Genius PC Level Models

"birdhouse" looks like a birdhouse using faked face indices - don't have the time to get the correct ones:
.



birdhouse.png (10.17 KiB) Viewed 87 times


(FIs seem to be contained in the "3DMa" blocks. Well, couldn't resist... see right part of picture)
## Post #4
- Username: trussive
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Mar 06, 2019 5:51 am
- Post datetime: 2020-12-10T21:18:25+00:00
- Post Title: Jimmy Neutron Boy Genius PC Level Models

Thanks for figuring it out. Do you mind telling me the settings? I have no clue how to use hex2obj, even with the tutorial.
## Post #5
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2020-12-11T10:27:20+00:00
- Post Title: Jimmy Neutron Boy Genius PC Level Models

Here you go:
.



birdhouse_point_cloud.png (20.25 KiB) Viewed 67 times


Hex2obj will give you a point cloud only. Getting the face indices requires additional coding which I did "on the fly":

```
f 1 5 4 
f 2 3 6 
f 2 6 5 
f 3 2 1 
f 6 4 5 
f 7 8 12 
f 12 11 7 
f 8 10 14 
f 14 12 8 
f 10 9 13 
f 13 14 10 
f 9 7 11 
f 11 13 9 
f 15 17 18 
f 18 16 15 
f 19 20 22 
f 22 21 19 
f 15 16 20 
f 20 19 15 
f 16 18 22 
f 22 20 16 
f 18 17 21 
f 21 22 18 
f 17 15 19 
f 19 21 17 
f 23 24 28 
f 28 27 23 
#f 24 26 30 
#f 30 28 24 
#f 26 25 29 
#f 29 30 26 
f 25 23 27 
#f 27 29 25 

```

You can copy/paste them into the test.obj file which is being created when pressing the 'mesh' button.

If you know 'C' you could use my Make_obj project for such:

> Reply from shakotay2 ↑Mon Mar 06, 2017 6:01 pm at Mon Mar 06, 2017 6:01 pm
>
> 

btw: there's a good chance that it's 30 vertices - didn't check that.

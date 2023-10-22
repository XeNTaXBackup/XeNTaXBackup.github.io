## Post #1
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-10-29T17:02:57+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

Extracted from an .AFS Archive, this is the standard model type for this game for cars/courses (.PAC) and I know it's been covered before with many other games but i've had no luck using the same tools on these. Can someone give me a hand? I'm sure this will be pretty quick compared to other things.

Sample course file (full size 2MB, not a large download, smallest one):

[https://www.dropbox.com/s/elqkfwgnh8gzt ... Y.PAC?dl=0](https://www.dropbox.com/s/elqkfwgnh8gztqp/MYOUGI0_DAY.PAC?dl=0)


And a sample car file (1MB):
[https://www.dropbox.com/s/6gwyb6hk02cb2bt/FC3S.PAC?dl=0](https://www.dropbox.com/s/6gwyb6hk02cb2bt/FC3S.PAC?dl=0)

Thanks!
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-05T23:07:17+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

This QuickBMS script unpacks content from the PAC files:

```
get FILES long
get DUMMY long
get SSIZE long
getdstring FOLDERNAME 16

for i = 0 < FILES
    getdstring NAME 16
    get OFFSET long
    get SIZE   long
    get FOLDER long
    get DUMMY  long

    savepos TMP
    goto OFFSET
    getdstring SIGN 3
    if SIGN == "GIM"
	string NAME p= "%s.%s" NAME SIGN
    elif SIGN == "CMD"
        string NAME p= "%s.%s" NAME SIGN
    else
        string NAME += ".DAT"
    endif
    goto TMP

    log NAME OFFSET SIZE
next i
```


CMD files are models, and GIM files are textures. I can't find a program that can read them though.
## Post #3
- Username: barti
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2014-11-06T01:52:14+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

the cmd looks like a modified version of folklore's model format.
## Post #4
- Username: Argonaut
- Rank: beginner
- Number of posts: 22
- Joined date: Fri Sep 12, 2014 3:19 am
- Post datetime: 2014-11-07T00:30:54+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

> Reply from chrrox
>
> the cmd looks like a modified version of folklore's model format.

Cheers for both of your replies guys, didn't expect this to take off so quickly  That script functions perfectly on the car Models but only creates .dats and .gims on the Course. All the dats feature the same header here: (It also produces correct file names IE lodxx and named objects, which is nice I guess)

 

With a few pointers to a program which could read folklore's model format (to be used on these if the modifications aren't too extensive), I could get the car models and textures working just fine.

Here's a sample .dat LOD file just incase you can identify the file's header. Thanks for your input!  

[https://www.dropbox.com/s/mj4aybneigehx ... 1.DAT?dl=0](https://www.dropbox.com/s/mj4aybneigehx7f/crslod01.DAT?dl=0)

EDIT: In addition, Noesis won't read the produced .gim files for either car or course model. Hmm.
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-11-07T13:37:07+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

The .dat file looks like it might be encrypted - "SMD" could be a garbled version of "CMD" and "KINA_NI˙T254_000" looks like it might be some kind of a model or material name.
## Post #6
- Username: KarinFutoGT
- Rank: advanced
- Number of posts: 51
- Joined date: Sat Apr 07, 2012 1:04 am
- Post datetime: 2015-04-08T18:11:24+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

So you can open the car models and textures? And how extract the .afs?
## Post #7
- Username: Neitancrost
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed May 29, 2019 7:21 pm
- Post datetime: 2021-09-12T19:43:00+00:00
- Post Title: Initial D Special Stage .PAC 3D Files

Hi there. So, I was able to decompress these course files and I tried to create a Noesis script to read them, but I found 2 problems : faces seem to be stored as vif tags (something idk how to handle) and some submeshes have broken and inconsistent data (what seems to be vif tags in the middle of vertices content and some incomprehensible amounts of data).

Samples and script:
[https://www.mediafire.com/file/s3xm6pjl ... t.rar/file](https://www.mediafire.com/file/s3xm6pjldfb7ayh/ID_Special_Stage_samples_%252B_script.rar/file)
-crs00: it has a bunch of broken submeshes, for instance the meshes at 0x0310d0 and 0x03ad80
-crs44: it has no broken submeshes
-treeLrg_L01: simple file with 1 mesh

Note: I had better results with autogenerated Quads than auto tristrip. Also, I noticed that every submesh has a type of content that I couldn't find out what it is, like the one at 0x01b4 in treeLrg_L01.
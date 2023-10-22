## Post #1
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-06-27T18:35:53+00:00
- Post Title: South Park Rally PC model files

Hello, I'm trying to figure out what this rbh file it's all about.

I think it has the model of the character of this game but I would like to open or something so I can mess with and edit it.


I give here the link for the model file (.rbh) and the texture file (.vram):

[https://drive.google.com/file/d/0By_Xs8 ... 04S2M/view](https://drive.google.com/file/d/0By_Xs884e-hxNkFzZUtLbW04S2M/view)~



The vram file can be open using this little tool herbert3000 created, VramExtractor1.1:
[viewtopic.php?f=18&t=14469](http://forum.xentax.com/viewtopic.php?f=18&t=14469)


Any help will be very appreciated. Thanks.
## Post #2
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-07-04T00:07:57+00:00
- Post Title: South Park Rally PC model files

So far I was able to extract the vertices, texture coordinates, faces + texture indices of a very simple model:



model.png (175.38 KiB) Viewed 431 times
## Post #3
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-07-05T08:21:25+00:00
- Post Title: South Park Rally PC model files

That's good work over there, hope you find about the "matrix" on the index numbers.
## Post #4
- Username: herbert3000
- Rank: veteran
- Number of posts: 145
- Joined date: Wed Jun 02, 2010 11:53 am
- Post datetime: 2016-07-09T16:18:31+00:00
- Post Title: South Park Rally PC model files

Here's a tool that converts a rbh file to obj (only works with the big map rbh files).
And there are also no textures.
[http://www.mediafire.com/download/jboz7 ... bh2obj.zip](http://www.mediafire.com/download/jboz7czva9f2fem/rbh2obj.zip)



farm.png (240.11 KiB) Viewed 396 times


There are too many unknown chunks and values in the rbh files, so I stopped working on that.
If someone's interested in doing further research, here are the single chunks of the the file cartjeep.rbh and a Word document in which I tried to structure the chunks:
[http://www.mediafire.com/download/dhks8 ... h.dump.zip](http://www.mediafire.com/download/dhks8148n801vgh/cartjeep.rbh.dump.zip)
## Post #5
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2016-08-30T15:49:00+00:00
- Post Title: South Park Rally PC model files

Still hoping for someone to find out about to export and import models!
## Post #6
- Username: PhillipGamer3264
- Rank: advanced
- Number of posts: 45
- Joined date: Sun Aug 14, 2016 11:32 am
- Post datetime: 2016-08-30T18:56:10+00:00
- Post Title: South Park Rally PC model files

in N64 Version, you can export .VRML model file, using Meshlab
## Post #7
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2017-03-21T02:11:32+00:00
- Post Title: South Park Rally PC model files

That's on N64 but that's good to know that.

But here I don't want just to export, I want to import too so I can make custom cars and also edit the characters models and animation too.

Still hoping for someone to find out about it.


Just some information about the .RBH: [http://rewiki.regengedanken.de/wiki/.RBH](http://rewiki.regengedanken.de/wiki/.RBH)
## Post #8
- Username: Wallace
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2018 12:41 pm
- Post datetime: 2019-01-25T07:05:59+00:00
- Post Title: South Park Rally PC model files

How do you extract the meshes for characters?
## Post #9
- Username: rubinho146
- Rank: advanced
- Number of posts: 44
- Joined date: Tue Jun 14, 2016 10:13 pm
- Post datetime: 2019-01-25T11:42:02+00:00
- Post Title: South Park Rally PC model files

Hi!

 Extracting the models for the character isn't yet possible, no one found out how to do yet! There is a source code that helps on how to get into extracting the .rbh file.
## Post #10
- Username: Wallace
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Jul 29, 2018 12:41 pm
- Post datetime: 2019-04-29T17:10:41+00:00
- Post Title: South Park Rally PC model files

Is there a way to actually use the source files?

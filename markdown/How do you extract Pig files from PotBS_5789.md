## Post #1
- Username: Piraticus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 15, 2011 11:02 am
- Post datetime: 2011-01-15T03:08:36+00:00
- Post Title: How do you extract Pig files from PotBS?

Hello there.  I would like to export the textures found within Pirates of the Burning Sea, which I believe are contained within files that have the .pig extension.  I am willing to pay for software that can do this, but thus far have been unsuccessful in finding any information on this and any software that can actually open and manipulate the potbs .pig files.

Now, I am not a 3d modeler.  I simply want to export the textures inside the game to make tiles that I can use in Photoshop with which to create battlemaps for online tabletop roleplaying games.

I attempted to export the pig files with the trial version of MultiEx Commander and it did not work.

Any help would be greatly appreciated.  Thank you.
## Post #2
- Username: Piraticus
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Jan 15, 2011 11:02 am
- Post datetime: 2011-01-18T00:08:36+00:00
- Post Title: How do you extract Pig files from PotBS?

Any help here would be greatly appreciate.  Thanks.
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-19T12:45:47+00:00
- Post Title: How do you extract Pig files from PotBS?

do you expect us to already have the pig files ?  
upload a sample!
## Post #4
- Username: verthul
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Feb 07, 2011 6:02 pm
- Post datetime: 2011-02-07T10:09:47+00:00
- Post Title: How do you extract Pig files from PotBS?

Hi,
Iam also interessted in opening this file type.
I uploaded some sample data.
It would be nice, if you can test it.

[http://www.verthnet.de/piggs.rar](http://www.verthnet.de/piggs.rar)
## Post #5
- Username: Teancum
- Rank: veteran
- Number of posts: 99
- Joined date: Wed Nov 28, 2007 3:30 am
- Post datetime: 2012-04-30T01:05:20+00:00
- Post Title: How do you extract Pig files from PotBS?

Sorry for the bump, but I took a quick look at this. There's a general header, the first 8 bytes of which are identical. The next 8 bytes vary, while the third 8 bytes are always the same. Then there's padding until 041C (hex). After that there's a table of contents, which I'd assume also have the positions and file sizes as well.

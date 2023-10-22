## Post #1
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-07T23:35:48+00:00
- Post Title: Unpack .AIA animation files

Please help me understand the .AIA/ASO file format common with YS series PC games. I want to get at the .DDS files contained within.

I have placed a sample here:
[https://www.dropbox.com/s/4oakt5h929ao2ze/C_400.zip](https://www.dropbox.com/s/4oakt5h929ao2ze/C_400.zip)

Thank you.
## Post #2
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-12T22:32:17+00:00
- Post Title: Unpack .AIA animation files

Can anyone help with this or hazard a guess?
## Post #3
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-12T23:27:29+00:00
- Post Title: Unpack .AIA animation files

most people don't like to start from scratch. So do I.

The more infos you provide the more likely you'll get a reply.

A hexdump screenshot of the formats first 1024 bytes for example would be helpful.
## Post #4
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-13T01:48:08+00:00
- Post Title: Unpack .AIA animation files

Sure. As requested,
[aia_1.png](https://xentaxbackup.github.io/file/6835_aia_1.png)
## Post #5
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-13T01:48:59+00:00
- Post Title: Unpack .AIA animation files

continued
[aia_2.png](https://xentaxbackup.github.io/file/6836_aia_2.png)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-12-13T07:59:22+00:00
- Post Title: Unpack .AIA animation files

hmm, TextureFinder doesn't reveal too mucch:
[](http://www.pic-upload.de/view-21611327/C_400_AIA.jpg.html)
## Post #7
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-13T15:25:43+00:00
- Post Title: Unpack .AIA animation files

I believe the textures are obscured in some way - either compressed or encrypted. When extracting the YS Origin data (data.ni) archives, the enemy and player sprite sheets are not present in the file structure where other textures are located. However, there is a ANI folder containing many large .AIA files... I am certain the sprite sheets are located here.
## Post #8
- Username: aspire
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-12-21T22:26:08+00:00
- Post Title: Unpack .AIA animation files

This format is supported in Noesis 4.093. 

The pixel data was compressed using a custom variable-sized RLE algorithm.
## Post #9
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-22T16:21:17+00:00
- Post Title: Unpack .AIA animation files

Thanks a bunch for this...

I downloaded version V4.093, but when I load any .AIA file, it says "Preview mode is not available but would you like to export". When I select yes, no files get created. I ran Noesis as administrator on two different win7  boxes and tried various .aia files but no luck. Am I doing it wrong?
## Post #10
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-22T16:34:34+00:00
- Post Title: Unpack .AIA animation files

Please disregard my previous post. I figured out what was happening.

I verified the .AIA files from "Ys: Oath in Felghana" load fine in Noesis, however, the .AIA files from "Ys Origin" do not. I guess the format is a bit different.  The very first post of this thread has a downloadable example of an .AIA file from YS Origin.

Thanks so much!
## Post #11
- Username: aspire
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-12-22T17:57:42+00:00
- Post Title: Unpack .AIA animation files

Oh, I just assumed Ys Origin was the same. Looks like they made some minor changes to the header. Update to 4.094 and they'll work.
## Post #12
- Username: aspire
- Rank: n00b
- Number of posts: 18
- Joined date: Sun Sep 09, 2012 11:28 pm
- Post datetime: 2013-12-22T20:58:59+00:00
- Post Title: Unpack .AIA animation files

Fantastic! Thanks again for this.

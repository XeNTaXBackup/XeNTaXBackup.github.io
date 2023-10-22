## Post #1
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-03T05:38:13+00:00
- Post Title: dreamcast .NJ cord problem.

hey i have problems with this ninja chunk model
even in noesis look bad.

i have a sample 

 sample.rar
(192.76 KiB) Downloaded 40 times



the games is Tomoyo no Daisakusen card captor.
thanks
## Post #2
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-03T06:36:55+00:00
- Post Title: dreamcast .NJ cord problem.

again.
image samples here
                          


image.jpg (15.86 KiB) Viewed 141 times
## Post #3
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-05-04T14:36:30+00:00
- Post Title: dreamcast .NJ cord problem.

I dunno, data just looks screwed. The transform data looks clean but it's broken, and so are the vertex weights. Lots of 0-weight entries and verts that get lots of 0-weights added to them.
## Post #4
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-04T22:08:57+00:00
- Post Title: dreamcast .NJ cord problem.

yeah i tried in othes viewer and same too.

also i use an program name EXMLDNet,but just create an unknown file that not preview.
this say is for sega dreamcast but i dont get it.

PD(sorry bout the bad english write)
## Post #5
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-05-04T23:56:35+00:00
- Post Title: dreamcast .NJ cord problem.

I guess it has something to do with the fact that it has like 250 nodes in the file. They're probably out of order. It might have something to do with the 2 bits that are set in the top 8 bits of the node's evaluation bits. It's probably actually multiple models, so the vertex buffers from the nodes in different models are stomping on each other.
## Post #6
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-05T00:54:47+00:00
- Post Title: dreamcast .NJ cord problem.

i think this tool can do the trick,but i don't know how use it
i guess than you could make it where i fail
image 



Captura.JPG (80.83 KiB) Viewed 104 times


sorry but can´t upload 2 file at same time
the next will be the tool.
## Post #7
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-05T01:18:22+00:00
- Post Title: dreamcast .NJ cord problem.

i post an reply in EXMLDNet page but no answer.
sorry seems to big for uploading here is the URL [http://kryslin.silvite.com/exmldnet.html](http://kryslin.silvite.com/exmldnet.html)
## Post #8
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-05-05T01:43:21+00:00
- Post Title: dreamcast .NJ cord problem.

I don't think you're going to have any luck with exmdlnet, its NJCM support is pretty primitive.

Anyway, turns out it used an interesting trick that I haven't seen in any other NJCM files.

The next version of Noesis will support it.
## Post #9
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-05T02:04:43+00:00
- Post Title: dreamcast .NJ cord problem.

ok i see...thanks!
and also i think i have another model format that noesis could be have problems open it
i ' m happy to help to noesis to grown even more this tools is excellent...and waiting the next release.bye
## Post #10
- Username: Crisfer
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 12, 2011 12:36 pm
- Post datetime: 2013-05-05T08:02:53+00:00
- Post Title: dreamcast .NJ cord problem.

yeah.. looks great and the animation too..
image



Cardcaptor.png (207.1 KiB) Viewed 89 times


even some files look like 1° pic, the rest is fine. 
is a shame they can't convert in "T" pose for autodesk sketching.
anyway was a great job,thanks MrAdults.
## Post #11
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2013-05-05T15:12:42+00:00
- Post Title: dreamcast .NJ cord problem.

I'm guessing the first one will be fixed in 4.08. I didn't check though. But it's probably the same issue that was making Maken X models look screwed up, which is fixed now.

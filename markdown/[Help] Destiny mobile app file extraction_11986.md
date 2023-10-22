## Post #1
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2014-09-21T02:24:55+00:00
- Post Title: [Help] Destiny mobile app file extraction

Heya people,

Wondering... I'm attempting to extract the 3D models from the Destiny android app.
While I've experience with PC game ripping etc etc unfortunately I've never messed with anything within android.

There are a series of .TGXM and .JSON files within the app that are around 600KB, I'm assuming that they may be low-poly versions of the in-game avatar but as of yet I've had no luck extracting the file type to anything I could use as a model.

Here's a link to everything I pulled from the app.
[https://onedrive.live.com/redir?resid=1 ... 2693%21363](https://onedrive.live.com/redir?resid=1262FCAFC252693%21363)

So, any advice or nudges in the correct direction would be much appreciated!
## Post #2
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-21T12:15:43+00:00
- Post Title: [Help] Destiny mobile app file extraction

.TGXM is a container format. It can store models as well as textures. Here's a QuickBMS script for extraction:

```
get DUMMY long
get DUMMY long # first file name offset?
get FILES long

getdstring FOLDERNAME 256

for i = 0 < FILES
	getdstring FILENAME 256
	get OFFSET long
	get DUMMY  long
	get SIZE   long
	get DUMMY  long
	
	string NAME p= "%s/%s" FOLDERNAME FILENAME
	log NAME OFFSET SIZE
next i
```


I'll look into the model data in a bit.
## Post #3
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2014-09-22T03:47:42+00:00
- Post Title: [Help] Destiny mobile app file extraction

Danke comrade!

Hmm. Ok, I'll have to learn how to execute scripts...
## Post #4
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2014-09-24T08:48:08+00:00
- Post Title: [Help] Destiny mobile app file extraction

Ok! Worked out how to use quickBSM, pulled out all the texture folder files to usable files.
However the geometry folders files came out as .TGX, so I'm assuming there's another process needed to convert those to some form of mesh file? .obj etc etc.
## Post #5
- Username: barti
- Rank: veteran
- Number of posts: 148
- Joined date: Sun Apr 01, 2012 7:44 pm
- Post datetime: 2014-09-24T19:42:17+00:00
- Post Title: [Help] Destiny mobile app file extraction

That's correct. The .tgx files store some of the model data, while the .js file "ties" the whole model together. Unfortunately I don't have the time to make a converter right now.
## Post #6
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2014-09-24T23:33:12+00:00
- Post Title: [Help] Destiny mobile app file extraction

No worries, Barti.
I wouldn't expect anyone to waste time on something like this without being paid for said time.

Off to the internets I go to attempt to work out how to do it myself...
## Post #7
- Username: TheLynx
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Sep 27, 2014 4:52 pm
- Post datetime: 2014-09-27T08:56:14+00:00
- Post Title: [Help] Destiny mobile app file extraction

> Reply from Spartan019
>
> No worries, Barti.
I wouldn't expect anyone to waste time on something like this without being paid for said time.

Off to the internets I go to attempt to work out how to do it myself...

it's not payment that's the issue. Lots of people don't mind helping others out. It's just sometimes people are busy. Hopefully someone else will jump in to help. I'm not capable of such things but many are and lots of the time they get bored or want to take on new projects.

I still highly recommend going and learning how to do this on your own. Quite frankly it's why I am here, and I might even take  a crack at it.
## Post #8
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2014-09-27T23:04:13+00:00
- Post Title: [Help] Destiny mobile app file extraction

Yeah, wasn't suggesting it was, just thought such an endeavour would warrant some form of compensation is all.

I've looked around, haven't found anything useful in terms of instructional information.
Pretty sure I just don't know where to look
## Post #9
- Username: Spartan019
- Rank: n00b
- Number of posts: 17
- Joined date: Sun Sep 21, 2014 9:46 am
- Post datetime: 2014-10-06T01:00:57+00:00
- Post Title: [Help] Destiny mobile app file extraction

Ok.
Stuck.

Could anyone point me in the direction of something that could explain how to combine the above file types into some form of usable model?
## Post #10
- Username: Shiroleinchen
- Rank: n00b
- Number of posts: 17
- Joined date: Fri Feb 19, 2016 1:01 am
- Post datetime: 2016-06-02T15:50:00+00:00
- Post Title: [Help] Destiny mobile app file extraction

have anyone a script to convert the tgx files?
## Post #11
- Username: lyhtem
- Rank: n00b
- Number of posts: 18
- Joined date: Wed Dec 21, 2016 4:04 am
- Post datetime: 2017-06-21T08:08:55+00:00
- Post Title: [Help] Destiny mobile app file extraction

Sorry to unbury the thread, was there any progress made?

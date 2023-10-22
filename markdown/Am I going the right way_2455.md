## Post #1
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-05T16:26:54+00:00
- Post Title: Am I going the right way?

Well, I wanted to learn this BMS scripting, because it seemed pretty good (Didn't buy the program, so can't really tes), But I was wondering, I dont know what to do after this, Talking about Halo

```
Get Version Long 0;
Get FDO Long 0;
Get DO Long 0;
Get FC Long 0;
For T = 1 to FC;
Goto FDO 0;
Get FN String 0;
SavePos NS 0;
Goto DO 0;
Get UK Long 0;
Get FS Long 0;
Get FP Long 0;
SavePos ND 0;
Next T;

```

I can be REALLY off, according to really large scripts, for an easy format specification, but mkay.
Also, I don't really understand how you can use this "Log" function. Could someone clearify that ? 

Thanks, 
Matsy

[/code]
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-05T18:59:59+00:00
- Post Title: Am I going the right way?

Let me take you through your code, you're going strong I think, just some issues: 
The Log statement you must use to save the relevant info about each resource in the archive, so MultiEx Commander knows where to find what. 

Ok, first your code:

```

# Okay, so you tell MexCom that importation is standard. That means that you have info about : The offset of the Offset variable in the archive for each resource, plus the Offset of the Size variable for each resource. 

Get Version Long 0;
#  Ok, so you get the version number (4bytes) and store it in Version. 

Get FDO Long 0;

# You store the next variable in FDO. 

Get DO Long 0;

# You store the next 32-bit variable in DO

Get FC Long 0;

# You store the number of resource (I assume) in FC
 
For T = 1 to FC;

# Good you start the loop
# This is the same as saying "for each resource do" ;)

Goto FDO 0;

# Okay, the first thing in the loop: you go to FDO. 

Get FN String 0;

# This is apparently where all the filenames are stored, so you get a string (FN). Note that you get a null-terminated string. This Get statement assumes that the string is null-terminated. 

SavePos NS 0;

#Okay, so after this null-terminated string, you save the location in the file and store this in NS. 

Goto DO 0;

#Alrightey, now jump to DO (you loaded that from the header). 

Get UK Long 0;

# I assume you load UnKompressed size or something ?

Get FS Long 0;

# Then you load the (compressed) filesize of this resource?

Get FP Long 0;

# Then you load the Offset of this resource ? ("FilePointer"?)

SavePos ND 0;

# Okay, very well, but you now save the current location in the file and store this in ND .  
# This would be a great place to Log what you found for this resource. 
# Assuming resources are not compressed:

Log FN FP FS 0 0 ;

# Note: you should save the position of the FP and FS variable as well to make use of the ImpType Standard you defined! You can do this by adding a SavePos FSO 0 ; before the Get FS Long 0 ; and SavePos FOO 0 ; before the Get FP Long 0 ; 
# The Log statement should have to be then:

Log FN FP FS FOO FSO ;

#Anyway, now you will do all the same for the next resource. 
# But there's a problem here. Where to jump?
# In your loop you will jump to FDO again. That's not right, is it? You will now get the same filename AGAIN. Should you not jump to NS instead? The Savepos you did just after you loaded the Filename in FN? 
# And the same goes for the other jump in the loop: DO. You Savepos the location in the other table in ND, should you not jump there instead? 
# So if I'm right, should you not simply change the FDO and DO variable names in NS and ND? 

 
Next T;

```


Hope this helps.
## Post #3
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-05T19:31:32+00:00
- Post Title: Am I going the right way?

Well, In that way, I wouldnt be doing something with the data(I think I should, or I'm seeing this program all wrong)

And, to explain the variables for a bit

Version = Version
FDO = FilenameDirectoryOffset
DO = DirectoryOffset
FC = FileCount
NS = NextString
UK = UnKnown (It wasnt really sure what it was, but isnt needed for the extraction I guess)
FS = FileSize
FP = FilePosition
ND = NextDirectory

Won't I have to do something with the FileSize / FilePosition, so I get the data of every file in it?

But, that's where I hang. How do I copy / get data?

Can't I jump to the FP, and just
Get FileInfo FS 0;
Or anything like that?, Or isnt that the intention of this BMS, that it only does logging?

Thanks for replying ,it helped me out a lot 

Edit, I think this is the final script(If I'm correct):

```
Get Version Long 0;
Get FDO Long 0;
Get DO Long 0;
Get FC Long 0;
For T = 1 to FC;
Goto FDO 0;
Get FN String 0;
SavePos FDO 0;
Goto DO 0;
Get UK Long 0;
SavePos FSO 0;
Get FS Long 0;
SavePos FOO 0;
Get FP Long 0;
SavePos DO 0;
Log FN FP FS FOO FSO;
Next T;

```
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-05T20:15:44+00:00
- Post Title: Am I going the right way?

Nope,the script is just intended for logging. multiex.dll does the processing of the script and only logs what the author of the script logs. This log is then picked up by MexCom to do actual data extraction etc. The script is not intended for actual extraction.
## Post #5
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-05T20:22:33+00:00
- Post Title: Am I going the right way?

I was wondering, I think the latest script of mine, Has to work.
Is there any possibility of me, to check?
## Post #6
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-05T21:02:08+00:00
- Post Title: Am I going the right way?

Well, technically, I could test it for you, if you have an example map.
## Post #7
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-06T06:11:18+00:00
- Post Title: Am I going the right way?

Well, The Bitmaps.map and the Sounds.map are both 300 MB / 200 MB.
I'll upload them anyway, Replying with the link within ~5 hours >_>
## Post #8
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2007-02-06T22:21:53+00:00
- Post Title: Am I going the right way?

No need, I've got them. I tested it and it seems to work, I had to first remove your entry into the wiki. MultiEx is very picky,and you had some trailing system characters after the ; signs, and it didn't work.  Now it does! Good job!!
## Post #9
- Username: Matsy
- Rank: beginner
- Number of posts: 20
- Joined date: Mon Aug 21, 2006 3:12 pm
- Post datetime: 2007-02-07T06:29:30+00:00
- Post Title: Am I going the right way?

Whoa. I'm so glad it actually works! 
Yay ^_^

Thanks for helping me out Mr.Mouse, and testing the script, cheers for you 

~Matsy

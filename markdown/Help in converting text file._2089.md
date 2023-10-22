## Post #1
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-14T16:28:31+00:00
- Post Title: Help in converting text file.

Here is another request for help or advice I submit to this community. I am trying to addopt 3rd party utylity program for one major flight simulator to needs of  another. Here is the sample of output and input required. 

> OUTPUT FROM  1st PROGRAM
>
> 
>
> [Macro] 
>
> Name=BoxBuilding1 
>
> X=6.4 
>
> Y=7 
>
> Rotation=180 
>
> File=D:\Leung Software\FS Scenery Creator\Macros\PARKING.API 
>
> V1=10000 
>
> V2=100 
>
> Param0=1.92 
>
> Param1=1.92 
>
> 
>
> [Macro] 
>
> Name=BoxBuilding2 
>
> X=110 
>
> Y=37 
>
> Rotation=180 
>
> File=D:\Leung Software\FS Scenery Creator\Macros\PARKING.API 
>
> V1=10000 
>
> V2=100 
>
> Param0=2.56 
>
> Param1=2.56 
>
> 
>
> [Macro] 
>
> Name=BoxBuilding3 
>
> X=114 
>
> Y=37 
>
> Rotation=180 
>
> File=D:\Leung Software\FS Scenery Creator\Macros\PARKING.API 
>
> V1=10000 
>
> V2=100 
>
> Param0=2.56 
>
> Param1=2.56 
>
> 
>
> ************************************************************* 
>
> INPUT FOR 2ndPROGRAM 
>
> 
>
> [city1.bmp] 
>
> ObjectCount=3 
>
> 
>
> Object000.TypeName=BoxBuilding1 
>
> Object000.MapClass=0 
>
> Object000.Chance=100 
>
> Object000.PositionX=6.400000 
>
> Object000.PositionY=7.000000 
>
> Object000.Angle=180.000000 
>
> 
>
> Object001.TypeName=BoxBuilding2 
>
> Object001.MapClass=0 
>
> Object001.Chance=100 
>
> Object001.PositionX=110.000000 
>
> Object001.PositionY=37.000000 
>
> Object001.Angle=180.000000 
>
> 
>
> Object002.TypeName=BoxBuilding3 
>
> Object002.MapClass=0 
>
> Object002.Chance=100 
>
> Object002.PositionX=114.000000 
>
> Object002.PositionY=37.000000 
>
> Object002.Angle=180.000000

Some of the lines are simply redundant, some needs to be reformated and slightly changed, or added. All can be done with "find and replace " of any word processor, however I was wondering if more automatic approach could be devised. I can write line by line required changes.
## Post #2
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-14T18:29:59+00:00
- Post Title: Help in converting text file.

If the number of files you want to convert is big enough to justify the effort, you could always write a lexer/parser combination that reads the data structures of the first file and outputs the reformatted information to the second file.

Judging from what you posted, this should not be very hard to do -- the format is line-based and doesn't seem to be nested in any difficult way.

Can you specify exactly what needs to be converted to what? And from where do you get the additional information that is not stored in the first file?
## Post #3
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-14T20:11:43+00:00
- Post Title: Help in converting text file.

Something like this.......

```


ADD:[name of texture.bmp]
ADD:ObjectCount=total number of lines /6
[Macro]	DELETE this line
Name=BoxBuilding1		                REPLACE: Name with Object%.TypeName  
ADD:Object%.MapClass=0
ADD:Object%.Chance=100
X=6.4				REPLACE: X with Object%.PositionX  
Y=7				REPLACE: Y with Object%.PositionY  
Rotation=180			REPLACE: Rotation with Object%Angle  
File=D:\Leung Softwre\FSâ€¦â€¦â€¦	                DELETE this line
V1=10000			                DELETE this line
V2=100				DELETE this line
Param0=1.92			DELETE this line
Param1=1.92			DELETE this line


[Macro]				DELETE this line
Name=BoxBuilding2		                REPLACE: Name with Object%.TypeName  
ADD:Object%.MapClass=0
ADD:Object%.Chance=100
X=110				REPLACE: X with Object%.PositionX  
Y=37				REPLACE: Y with Object%.PositionY  
Rotation=180			REPLACE: Rotation with Object%Angle  
File=D:\Leung Softwre\FSâ€¦â€¦â€¦	                DELETE this line
V1=10000			                DELETE this line
V2=100				DELETE this line
Param0=2.56			DELETE this line
Param1=2.56			DELETE this line


[Macro]				DELETE this line
Name=BoxBuilding3		                REPLACE: Name with Object%.TypeName  
ADD:Object%.MapClass=0
ADD:Object%.Chance=100
X=114				REPLACE: X with Object%.PositionX  
Y=37				REPLACE: Y with Object%.PositionY  
Rotation=180			REPLACE: Rotation with Object%Angle  
File=D:\Leung Softwre\FSâ€¦â€¦â€¦	                DELETE this line
V1=10000			                DELETE this line
V2=100				DELETE this line
Param0=2.56			DELETE this line
Param1=2.56			DELETE this line
	




DESIRED INPUT	
[city1.bmp]	
ObjectCount=3	

Object000.TypeName=BoxBuilding1	
Object000.MapClass=0
Object000.Chance=100
Object000.PositionX=6.400000
Object000.PositionY=7.000000
Object000.Angle=180.000000

Object001.TypeName=BoxBuilding2
Object001.MapClass=0
Object001.Chance=100
Object001.PositionX=110.000000
Object001.PositionY=37.000000
Object001.Angle=180.000000

Object002.TypeName=BoxBuilding3
Object002.MapClass=0
Object002.Chance=100
Object002.PositionX=114.000000
Object002.PositionY=37.000000
Object002.Angle=180.000000

```


Sorry for this little chaotic format.
## Post #4
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-14T23:12:50+00:00
- Post Title: Help in converting text file.

I've created a quick and dirty parser for you. I'll mail it to your hotmail....
## Post #5
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-14T23:21:11+00:00
- Post Title: Help in converting text file.

Well, this program is not pretty ... but it should hopefully work.

I've assumed there are no negative values as positions given; else a slight change might be necessary.

[Edit: Well, the change would only be cosmetical. There might be odd warnings if a value is equal to -1.0, but the file will nevertheless be converted correctly.]
[ConvertSomething.zip](https://xentaxbackup.github.io/file/853_ConvertSomething.zip)
## Post #6
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T00:29:36+00:00
- Post Title: Help in converting text file.

Thank you BOTH very, very much. As soon as I can catch some time I will try those converter/parsers.
## Post #7
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-15T08:08:37+00:00
- Post Title: Help in converting text file.

You're welcome. Don't forget to post your results.
## Post #8
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T11:47:44+00:00
- Post Title: Help in converting text file.

Thank you for your quick assistance.Thanks a milion.   
The results are in: PERFECT  I understand that this works only in DOS box, but NP. 

I will play with it little more, but so far so good. Perhaps just this one: in converted file there are empty lines separating each entry. My fault - but can they be deleted?
## Post #9
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-15T14:14:54+00:00
- Post Title: Help in converting text file.

> Reply from Xela
>
> Thank you for your quick assistance.Thanks a milion.   
The results are in: PERFECT

Nice to hear that it works. 

> Reply from Xela
>
> I understand that this works only in DOS box, but NP.
A command-line version was the easiest thing to do -- however, adding a simple GUI would be no problem. If you tell me what you need ...

> Reply from Xela
>
> I will play with it little more, but so far so good. Perhaps just this one: in converted file there are empty lines separating each entry. My fault - but can they be deleted?
Sure, no problem. Try the attachment ...

[Edit: trying once again to attach this file ...]
[ConvertSomething.zip](https://xentaxbackup.github.io/file/860_ConvertSomething.zip)
## Post #10
- Username: bored
- Rank: beginner
- Number of posts: 28
- Joined date: Mon Mar 13, 2006 4:03 am
- Post datetime: 2006-09-15T20:58:08+00:00
- Post Title: Help in converting text file.

Wow Xela...What are the chances of finding two people to help you within a couple of hours?

Anyway, I've downloaded Deniz's solution and it's far more elegant than mine..so please delete all traces of the file I sent you... preferably without trying it out.
## Post #11
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-15T21:24:13+00:00
- Post Title: Help in converting text file.

It is pretty unbelievable that what I thought was quite a task, was so promptly and kindly attended by BOTH of you. And both with exactly same result - WORKING and exactly ehat I wanted. Many , many thanks.
## Post #12
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-09-15T23:20:27+00:00
- Post Title: Help in converting text file.

You really need to get rid of Win9x,  Dos boxes are so 1990 .  Live in the now, with NT's command prompts.
## Post #13
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-09-15T23:21:34+00:00
- Post Title: Help in converting text file.

You really need to get away from Win9x, Dos boxes are so 1990s.  Installed w2k or xp, and get the superb command prompt.
## Post #14
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2006-09-15T23:22:43+00:00
- Post Title: Help in converting text file.

You really need to get away from Win9x, Dos boxes are so 1990s.  Installed w2k or xp, and get the superb command prompt.
## Post #15
- Username: Xela
- Rank: VIP member
- Number of posts: 225
- Joined date: Sun Jul 31, 2005 11:12 am
- Post datetime: 2006-09-16T00:20:14+00:00
- Post Title: Help in converting text file.

> Dos boxes are so 1990
You cannot imagine how much I would give to be able to move time back and live again in 1990. Wouldn't you?
## Post #16
- Username: Deniz Oezmen
- Rank: VIP member
- Number of posts: 185
- Joined date: Mon Aug 28, 2006 9:07 pm
- Post datetime: 2006-09-16T15:15:46+00:00
- Post Title: 

> Reply from bored
>
> Anyway, I've downloaded Deniz's solution and it's far more elegant than mine..so please delete all traces of the file I sent you... preferably without trying it out.

Hey, programs don't have to look nice on the inside ... they just have to work. 

Concerning Xela: I have finally managed to attach the updated program to my previous post. Now the empty lines should be gone.

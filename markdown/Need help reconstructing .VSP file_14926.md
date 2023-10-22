## Post #1
- Username: goldenboy78
- Rank: n00b
- Number of posts: 16
- Joined date: Sun Nov 23, 2014 9:07 am
- Post datetime: 2016-08-23T18:27:34+00:00
- Post Title: Need help reconstructing .VSP file

Hi, the mentioned file in the subject is a project file from a video editing software called Corel Video Studio.

I opened that project file with the standard Microsoft editor, because i wanted to edit the drive letter of the root path from a certain video file, 
due to a relink problem with that video file in the Video Studio software.
After I saved it, it won't open anymore in Video Studio because the text editor replaced all hexadecimal 00's with 20's in that project file...



The thing is, that it's a very big file. It's about 5mb, and as I said all 00's were replaced 

What I tried to do, to "repair" that file was to replace all 20's with 00's again
and then to find out the specific offsets where any 20's were needed, in order Video Studio to load that project file again..

I found that offsets through comparison with an older save of that project file.

I partially had success after all that 00 replacements with the 20's, Video Studio loads the project file again but it gets stuck at 68%.

I have a guess at which offset it get's stuck, but the bytes at that offset seem ok to me if I indicate the pattern right..

It should be got stuck at offset 0x0D5600:


If someone could help me, giving me some advice if there's any pointers or sth. else important to know in that specific byte block where that pattern is visible, I really would appreciate it.

Thx very much in advice.

edit:

Well, the project file loads up again now. There was a nullbyte at 0x3f05fd that had to be replaced also with "20".



But unfortunalley, I guess there have to be replaced some more nullbytes with "20"'s, because if you press the play button 
yout get the error message "It has been detected a wrong argument"..



Any advice, which bytes are responible for passing this or these arguments would be very apreciated...
## Post #2
- Username: robertjjr
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jun 28, 2017 11:48 pm
- Post datetime: 2017-06-28T15:56:39+00:00
- Post Title: Need help reconstructing .VSP file

VSP It is using about 19gb of space and looking at the client that this file resides. ... If you'd like assistance with disabling or restricting the size of future VSP files,

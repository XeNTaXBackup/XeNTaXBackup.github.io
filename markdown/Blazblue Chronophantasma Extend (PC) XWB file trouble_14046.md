## Post #1
- Username: BBPlayer
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Mar 04, 2016 1:36 pm
- Post datetime: 2016-03-04T05:50:18+00:00
- Post Title: Blazblue Chronophantasma Extend (PC) XWB file trouble

Hi there, I'm trying to change some music in Blazblue:CPE but when I try to create new XWB files and add them in the game throws an error at me and one of two things will happen

-If I gave it both a new XWB and XSB, I will only get one error box and the match will start but with no music
-If I only gave it a new XWB file and NO XSB, then it will give me one error, than another and crash

I've checked the original XWB and XSB files against ones I'm making and they seem to be from the exact same version of XACT (46/44 for XWB, 46/43 for XSB), I have used xactxtract to compare them and I can't figure out what is wrong, pls help

here is a link to the files [https://www.dropbox.com/s/ksuj0j80o5322 ... s.zip?dl=0](https://www.dropbox.com/s/ksuj0j80o5322fo/XWB%20and%20XSB%20files.zip?dl=0)
"022_btl_az2".xwb and .xsb are the new ones I'm trying to put in 
"022_btl_az" .xwb and .xsb are the old files

I know it only has one piece of music in it and I just want to change it, older blazblue games just used .ogg files why must it now be such a bore :S
## Post #2
- Username: Liandril
- Rank: advanced
- Number of posts: 55
- Joined date: Mon Aug 02, 2010 11:11 pm
- Post datetime: 2016-03-05T23:47:08+00:00
- Post Title: Blazblue Chronophantasma Extend (PC) XWB file trouble

Hi BBPlayer,

the sound section in your xsb differs from the original one, so creating a new xsb is probably not the best approach. 

Just to be sure:  'If I only gave it a new XWB file and NO XSB...' does NOT mean that there was no xsb at all, but means that you tried the OLD xsb together with your new xwb, right? Actually this should work. Did you create the xwb as "in memory" or as "streaming" (I remember that I had a problem because of this when replacing the xwb in another game)?

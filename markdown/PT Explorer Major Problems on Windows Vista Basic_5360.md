## Post #1
- Username: batmanass47
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Nov 03, 2010 7:56 am
- Post datetime: 2010-11-07T04:08:30+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

Today i downloaded the PTexplorer 1.6 and 1.7 i get error that says this MSCOMCTL.OCX i have windows vista basic 32 bit 


then I Tryied right-clicking and Troubleshoot compatibility, then select XP SP2 mode but it seems it is already highlighted i grey 









When you download ptexplorer does all your files or am am i missing something look like this and what version do you have 



ptexplorer 1.6 [blog/?p=28](http://forum.xentax.com/blog/?p=28) 







ptexplorer 1.7 [blog/?p=141](http://forum.xentax.com/blog/?p=141)




is this where i download MSCOMCTL.OCX 

But even when i downloaded MSCOMCTL.OCX it still did not work 
http://www.ocxdump.c...2/download.html 




1. Will  PT Explorer Run on windows vista basic for  Smackdown vs Raw  2011
## Post #2
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-07T12:39:21+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

You must  first actually CHECK the option to run it in compatibility mode, and then select which one from the drop down menu.
## Post #3
- Username: batmanass47
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Nov 03, 2010 7:56 am
- Post datetime: 2010-11-07T19:31:50+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

I CHECKed the option and ran it in compatibility mode, and then select which one from the drop down menu, and hit apply on each one this this is what i got
## Post #4
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-07T20:25:54+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

Try running it as Administrator. Right click on the .exe and select Run as Administrator. I downloaded it, unpacked it on a Vista machine and did that, it worked.
## Post #5
- Username: batmanass47
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Nov 03, 2010 7:56 am
- Post datetime: 2010-11-07T20:59:23+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

I unpacked it from the i have winrar and ran it is Administrator. I Right-clicked on the exe and select Run as Administrator. and i still got the same error can we do a remote desktop to see what is wrong please 

i use use team viewer for remote desktop

[http://www.teamviewer.com/download/index.aspx](http://www.teamviewer.com/download/index.aspx)
## Post #6
- Username: batmanass47
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Nov 03, 2010 7:56 am
- Post datetime: 2010-11-08T15:14:11+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

this helped 

[http://www.ascentive.com/support/new/libraryfiles.exe](http://www.ascentive.com/support/new/libraryfiles.exe)

but then i got this error comdlg32.ocx 


how am i getting all of these errors i just crashed and installed a fresh copy of windows
## Post #7
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-08T15:21:58+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

try this: [http://windowsxp.mvps.org/comdlg32.htm](http://windowsxp.mvps.org/comdlg32.htm) read the box about Vista, you need an elevated command prompt.
## Post #8
- Username: batmanass47
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Nov 03, 2010 7:56 am
- Post datetime: 2010-11-08T16:03:51+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

I went to the website like you told me to do and this came up

I clicked Start, click All Programs, click Accessories, right-click Command Prompt, and then click Run as administrator.
## Post #9
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-08T16:35:45+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

You should read that site again, because you made a mistake.

You must open an Elevated command prompt as dictated. 
and then type :

```
regsvr32  %Systemroot%\System32\comdlg32.ocx
```


Make sure you saved the ocx file in your windows/system32 folder first.
## Post #10
- Username: batmanass47
- Rank: beginner
- Number of posts: 22
- Joined date: Wed Nov 03, 2010 7:56 am
- Post datetime: 2010-11-08T16:47:49+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

MR Mouse thankxs buddy it is working now 

1. Missing comdlg32.ocx for vista   go here [http://www.ehow.com/how_6854266_registe ... vista.html](http://www.ehow.com/how_6854266_register-comdlg32_ocx-vista.html)

Enter the command regsvr32 %Systemroot%\System32\comdlg32.ocx


2. Missing MSCOMCTL.OCX  Download this [http://www.ascentive.com/support/new/libraryfiles.exe](http://www.ascentive.com/support/new/libraryfiles.exe)



3. MR Mouse have you figured out when you are able to do PT Explorer for Smackdown vs Raw 2011 when will it be released excited
## Post #11
- Username: mono24
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-11-08T17:29:13+00:00
- Post Title: PT Explorer Major Problems on Windows Vista Basic

> Reply from batmanass47
>
> MR Mouse thankxs buddy it is working now 

1. Missing comdlg32.ocx for vista   go here http://www.ehow.com/how_6854266_registe ... vista.html

Enter the command regsvr32 %Systemroot%\System32\comdlg32.ocx


2. Missing MSCOMCTL.OCX  Download this http://www.ascentive.com/support/new/libraryfiles.exe



3. MR Mouse have you figured out when you are able to do PT Explorer for Smackdown vs Raw 2011 when will it be released excited

Excellent! I'm glad it works now! For all you folks that have the same problem, the total solution is in batmanass47's post. 

No, I have no idea when and if I can do a 2011 update. I'm too busy with other stuff at the moment.

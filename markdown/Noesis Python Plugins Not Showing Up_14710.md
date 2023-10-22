## Post #1
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-02T04:53:21+00:00
- Post Title: Noesis Python Plugins Not Showing Up

Hope this is the right place to put this.  Should be a simple fix, but for some reason Noesis is convinced that I have no Python plugins (including the ones that came preinstalled.)  I've tried reloading already to no avail.  Any suggestions?
## Post #2
- Username: Gh0stBlade
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2016-08-02T14:39:50+00:00
- Post Title: Noesis Python Plugins Not Showing Up

You could try deleting everything then reinstalling Noesis. Or maybe updating to the latest version, ensuring that the folder path Noesis is in, isn't complex or too long.
## Post #3
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-02T17:25:45+00:00
- Post Title: Noesis Python Plugins Not Showing Up

> Reply from Gh0stBlade
>
> You could try deleting everything then reinstalling Noesis. Or maybe updating to the latest version, ensuring that the folder path Noesis is in, isn't complex or too long.

Still nothing, and I just uninstalled and reinstalled the most recent version.  Only issues I can think of are that I installed it on my D: drive, or that I have the Python 2.7 IDE installed.  Could either of those be the issue?
## Post #4
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-03T00:08:51+00:00
- Post Title: Noesis Python Plugins Not Showing Up

the only thing i can think of is your file path contains weird characters.
## Post #5
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-03T00:47:52+00:00
- Post Title: Noesis Python Plugins Not Showing Up

No, just on my D: drive in a folder called D:\Noesis. But my Python IDE is installed to the C: drive
## Post #6
- Username: MrAdults
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-08-04T03:56:05+00:00
- Post Title: Noesis Python Plugins Not Showing Up

Try DependencyWalker on NoesisPython.dll to make sure it's actually loadable.
## Post #7
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-04T23:42:55+00:00
- Post Title: Noesis Python Plugins Not Showing Up

> Reply from MrAdults
>
> Try DependencyWalker on NoesisPython.dll to make sure it's actually loadable.

Apparently I'm missing a whole bunch of Windows DLLs I've never heard of: API-MS-WIN-CORE-LOCALIZATION-OBSOLETE-L1-2-0.DLL, API-MS-WIN-CORE-PROCESSENVIRONMENT-L1-2-0.DLL, API-MS-WIN-CORE-PSM-APPNOTIFY-L1-1-0.DLL, etc.  Error include the following:

Error: At least one required implicit or forwarded dependency was not found.
Error: At least one module has an unresolved import due to a missing export function in an implicitly dependent module.
Error: Modules with different CPU types were found.
Warning: At least one delay-load dependency module was not found.
Warning: At least one module has an unresolved import due to a missing export function in a delay-load dependent module.
## Post #8
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2016-08-05T22:11:11+00:00
- Post Title: Noesis Python Plugins Not Showing Up

put your windows install in your pc drive and run sfc.exe /scannow
## Post #9
- Username: IAmTheClayman
- Rank: n00b
- Number of posts: 17
- Joined date: Mon Aug 01, 2016 8:46 am
- Post datetime: 2016-08-08T00:45:37+00:00
- Post Title: Noesis Python Plugins Not Showing Up

> Reply from chrrox
>
> put your windows install in your pc drive and run sfc.exe /scannow

Not sure where my Windows install is, but I ran scannow and it didn't come back with any errors

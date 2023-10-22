## Post #1
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-06T14:28:47+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

I can't start my MultiEx Commander on my system (Win XP SP1), it gives me an error message: "Run-time error '429'. ActiveX component can't create object"
Does anybody know how to repair it, please??? Thanks very much!
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-07T11:10:55+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Try to install the latest service packs. It is also important to note specifically what the installer says, which version you downloaded and stuff like that. Your information is just too undetailed.
## Post #3
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-07T13:24:27+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

I had this problem in version 3.7b, so I downloaded the latest version 3.9.69, but it's the same now. The installation succesfuly ended, but if I want to run the program it gives me that message. I've tried to download the newest windows update, but it still continues. I really don't know if the problem is in my computer, windows or in MultiEx... 
I am sorry to interrupt you, but I think that MultiEx is great and I would like to use it soon.
Thank you very much for your reply. Orgic.
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-07T15:35:38+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Try to run the attached mc32trial.exe instead of mc32.exe and note/copy any and all error logs. You can find a debug.log (if possible) in the data directory,and perhaps other logs.
[mc32trial.zip](https://xentaxbackup.github.io/file/8_mc32trial.zip)
## Post #5
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-07T16:55:53+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

So, I've run the mc32trial.exe, but it brings the same message like mc32.exe; it behaves like mc32.exe. There is no log file in data directory...
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-10T20:35:46+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Okay, perhaps if you install this patch 
[viewtopic.php?t=576](http://forum.xentax.com/viewtopic.php?t=576)
## Post #7
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-12T18:57:02+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

I've installed that patch, but the only difference is that now there is a new window with the error message "ERROR: 429-ActiveX component can't create object". What can I do with it?
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-12T21:58:38+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Is that the only message in that window, or are there more, please copy the contents of the text window and post it.
## Post #9
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-13T10:30:47+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

This is the only one message in the window, nothing more. 
"ERROR: 429-ActiveX component can't create object" 
That's all.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-13T19:46:03+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Okay there's a new patch available at [http://multiex.xentax.com](http://multiex.xentax.com) Please try that one , it should report more.
## Post #11
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-14T09:05:06+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

OK, these are new messages in the window:
MODMAIN: Initializing MC
INITMC: Loading Splash
INITMC: Creating FS-Object
ERROR: 429-ActiveX component can't create object
## Post #12
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-14T09:40:44+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Right, the program is trying to run a Microsoft filesystem script from scrun.dll, and wants to create an object so it can manipulate filenames etc. 

Possible cause: If you have Norton Anti-Virus installed, disable script blocking and try again.
## Post #13
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-14T20:51:55+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

I've tried to disable script blocking, but it still doesn't work. I've also tried to disable the whole anti-virus control, but still the same. Shall I do anything else with the anti-virus or with the system?
## Post #14
- Username: afterforever
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Mar 24, 2004 7:20 am
- Post datetime: 2004-03-23T23:22:47+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

I got this error

MODMAIN: Initializing MC
INITMC: Loading Splash
INITMC: Creating FS-Object
ERROR: -2147024770-Automation error
The specified module could not be found.
## Post #15
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-23T23:43:12+00:00
- Post Title: HELP ME PLEASE! Problem with starting MultiEx Commander!!!

Okay, please go to your Windows directory and to the System32 directory in there. Find the scrrun.dll and right-click it to select "properties". 
Note the version down and please post it here.
## Post #16
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-24T17:34:52+00:00
- Post Title: 

My version is 5.6.0.6626
Thanks
## Post #17
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-24T20:24:31+00:00
- Post Title: 

That's my version too.   

Okay, well, try registering it. 
To do that, go to start->run

Then type

regsvr32.exe c:\windows\system32\scrrun.dll

(or wherever your windows directory is).

Please check if that helps, because then the file was not registered by the installer maybe.
## Post #18
- Username: Orgic
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Sat Mar 06, 2004 10:16 pm
- Post datetime: 2004-03-25T18:19:29+00:00
- Post Title: 

Oh, it works now.  
I'm very happy, I must enjoy it soon.
Thank you very much for your goodwill and for passing your time with my problem.
So, thanks.
## Post #19
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-03-25T18:36:10+00:00
- Post Title: 

Excellent! Hope you enjoy it!
## Post #20
- Username: paulus
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-12T07:51:36+00:00
- Post Title: 

Hi, i have the same error mesage and version of scrunn on win98, but when i try and register the file, i get this:

LoadLibrary "path to scrunn.dll" failed.
GetLastError returns 0x00000485.



i'd love to be able to get multi ex working, but just cant seem to get any luck 

btw i have a p2 333, 196 ram and a 16meg vodoo 3 3dfx card. (in case it helps)
## Post #21
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2004-05-12T07:58:16+00:00
- Post Title: 

Well, do a search in your windows directory for the file scrunn.dll. 
And use the path to that file in the command. 

Note: you must use YOUR path to the file, e.g. if you have windows installed on another drive than C:, that must also change in the command.
## Post #22
- Username: paulus
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2004-05-12T21:36:52+00:00
- Post Title: 

LOL - silly me

thanks for that  - i have now successfully regged it, and it works now

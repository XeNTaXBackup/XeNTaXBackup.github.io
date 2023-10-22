## Post #1
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2015-06-17T15:04:37+00:00
- Post Title: How Unpack Themida 2.x.x

Hello everybody,

Today I will be showing you all how you can unpack a sample which is packed with Themida. This tutorial will show you how to do the process without requiring to manually use a debugger yourself.

What you will learn in this thread:
- What Themida is
- A bit about how Themida works
- Why packers/obfuscators may be used with not only malicious software but safe, legitmate software
- Why unpacking is useful to Malware Analysis
- How you can unpack samples packed by Themida without requring knowledge of how to use a Debugger yourself manually

1). What Themida is
Themida is software specifically engineered to help software stay better protected from becoming cracked and/or it's source code was being stolen.

If someone comes along and they can read the code you wrote for your software, if you have not made the software opensource and did not wish the code to be given out and/or read by someone, would you be happy about them having found a way to read your source code? I don't think you would.

The purpose of Themida is to help prevent the protected software from becoming vulnerable to reverse engineering attempts. It can also help against piracy.

2). A bit about how Themida works
Themida will pack the executable. When you execute the packed sample, it will unpack the executable in memory and use that to continue executing to perform and do what it's meant to do. If the unpacking of the packed executable into memory fails for whatever reason, then the program will not work.

3). Why packers may be used in legitimate software
Packers may be used in legitimate software so the developer's software is better protected against attacks. If someone can read your code, or use Disassembly to understand how it works, they can try to find vulnerabilities and then use them to create zero-day exploits.

Packers are also quite frequent with malware. Your Antivirus product may pickup detections for software packed in a certain way/type of packer used.

4). Why unpacking is useful in Malware Analysis
If the sample is packed, then this essentially protects against Disassembly. We won't be able to understand how the program works, we'll just be reading the instructions from the packer wrapper. For example, the process of the unpacking. However, we want the original executable (unpacked executable) and we want to perform Disassembly with that executable so we can try to make sense of and understand how the program works to know if it's malicious or not.

5). How we can actually identify and unpack Themida packed executables
To start off, you'll need a few things: 

Tools
ProtectionID 6.6.7
OllyDBG 1.10

OllyDBG Plugins

ODBGScript v1.82.6
StrongOD 0.4.8.892
PhantOm 1.79
ARImpRec.dll


Script

Themida - Winlicense Ultra Unpacker 1.4


Ok the first thing we need do is set path in the Themida - Winlicense Ultra Unpacker 1.4.txt for your "ARImpRec.dl", so we open the txt with notepad and search it.

> HERE_ENTER_YOUR_DLL_PATH_TO_ARIMPREC_DLL:
>
> mov ARIMPREC_PATH, "C:\Documents and Settings\Admin\Desktop\OllyDBG\plugin\ARImpRec.dll"

Open up ProtectionID and as can see first icon like a paper with a pencil, press there and drop your executable. It should process the information (if it can). As we can see in the below screenshot, it detects the Themida packing:



Ok after checked that we unpack ollydbg in a path we want, a example mine is in Desktop: C:\Documents and Settings\Admin\Desktop\OllyDBG.

So now we gonna create inside ollydbg folder a folder called plugin and inside we extract all plugins we download, so this need be look like that.




PS: delete PSAPI.DLL from main folder of OllyDBG.

Ok so now we are ready to start with it.

1. First time we open Olly we need set the plugin directory because is not configured, for do it we go to --> Option-Appareance, in the tab Directories we can set where we stored plugins, so do it, press ok and restart Olly.



2.So now the next time we open Olly we see plugins loaded.



3. Ok now we go open the target to unpack or just press F3, after opened we got a pop up, just press Yes and the file continue Analysing, just wait to finish.



4.Now press F9 to run it and as you can see, we got a pop up, don't worry just press ok and the debug is terminated.




5. Good the next move is run script, so for this we go can do it via plugin menu-ODBGScript-Run Script and we search for "Themida - Winlicense Ultra Unpacker 1.4.txt" download before.

6.Ok after we load nothing happen becase we terminated the debug before, so what we need do is reopen the target, just press in the X to close target.

7.After reopened target run script again or if you get this pop up asking for begin unpacking process we press Yes.



Ok next one we press No.



So now the unpacking process has begun, we can check status in the down bar as the right side of screen, after some seconds, we got pause, now to resume and continue unpacking maximize main thread windows and press right click and go to -> Script Functions-Script Windows, so now we have a Window of Script opened, right click there and press Resume.



8. So now we got a pop up telling us about we need modify some values into "ollydbg.ini", after that we need restart Olly and resume script.



9. So now we repeat steps do before, open target and run script,etc, after we finish we got this at the end.



PS: remember close OllyDBG after open .ini.

10. Ok we press Yes and in the Script Execution press right click and Resume.

11. Good now this part is very important, if we running a VMWare, we need set Yes, if we running normal SO just press No.



12. Now we got another pop up, really in my case I select Moddern Scan no Simple, it uses more checks.



13. Ok in this one we select No.



14. Ok after finished we got a new pop, there I press Yes.



15. Finally the job is done, as you can see there, now we can see dumped file, so we press Yes for use this data.



16. As script say, we choose first time no, if we got any problem after press no, repeat the process and the next time just press Yes, just in case.



17. Ok this pop ask for compress the dumped file, but in this case we won't do it because is a good size, is not a file of 120MB or 200MB so I think is fine press No.



18. Ok after all this we finally have dumped file in the folder where stored exe.



Press ok and we are done.







PS: Ok I hope this guide help us to unpack in future your themida protections, so well have fun and sorry if my english is to bad.

Credits: LCF-AT, Nacho_dj and me for write this guide.
## Post #2
- Username: eriger777
- Rank: beginner
- Number of posts: 26
- Joined date: Thu Sep 25, 2014 5:30 am
- Post datetime: 2015-07-22T21:44:21+00:00
- Post Title: How Unpack Themida 2.x.x

Wow.. I was looking for this. Could you do a guide on vmprotect? LFC's tutorials are hard to understand.
## Post #3
- Username: Adolfok3
- Rank: n00b
- Number of posts: 11
- Joined date: Mon Aug 11, 2014 2:13 am
- Post datetime: 2015-08-31T17:47:16+00:00
- Post Title: How Unpack Themida 2.x.x

Wowww! Perfect!! Thx!!

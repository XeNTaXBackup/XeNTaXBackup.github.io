## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-09-26T14:24:23+00:00
- Post Title: PSA: Update your Noesis version!

Hello my beloved and occasionally deplorable Noesis users,

The Noesis crash data site receives a high volume of crashes from extremely old versions of Noesis that have been fixed for years. I would think that when you crash, and you get the option to click "Yes" to submit a crash report, it would occur to you to see if the program has been updated to fix your particular crash already. But apparently not. 99% of crash reports come from extremely old versions, I even see a good volume of 3.x ones.

But on top of that, I've included some more useful crash diagnostic info in 4.202, so please make sure you're using at least version 4.202. Although I obviously can't do anything about crashes happening within third party plugin binaries (which many are), I'd like to make Noesis completely crash-free.

You can update to the latest version of Noesis by using the "Check for Updates" option in the program's "Tools" menu. If you're using a version that's so old that it doesn't have the "Check for Updates" feature (I think that would be 4+ years now), you can download the latest version [here](http://richwhitehouse.com/index.php?content=inc_projects.php).

If you're being diligent about updating and submitting the same crash over and over again, feel free to contact me and provide the circumstance and data you're using to get the crash. There's one in particular I've been trying to track that doesn't make a lot of sense from the dump, and seems to indicate some stack corruption (due to a register state that's just been read off of the stack having what appears to be a bad address), but I've been unable to determine where that corruption could've occurred in my offline analysis.

Yours,
D
## Post #2
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-09-27T00:08:44+00:00
- Post Title: PSA: Update your Noesis version!

Hey MrAdults,

I'm one of the deplorable users. 
For a while now, I'm getting crashes when opening Noesis - I wasn't sure if I was the only one.

I just downloaded the latest version, unzipped (did not add plugins) and boom. Crash.
I mean, not really  crashed, the message appears, but nothing weird happens. Noesis seems to keep running fine, but I can't use it.
I'm only able to use it when I open it using Sandboxie, then it works 100%.

And yeah.. Just thought I would let you know!
## Post #3
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-09-27T00:14:27+00:00
- Post Title: PSA: Update your Noesis version!

> Reply from lolwatt
>
> Hey MrAdults,

I'm one of the deplorable users. 
For a while now, I'm getting crashes when opening Noesis - I wasn't sure if I was the only one.

I just downloaded the latest version, unzipped (did not add plugins) and boom. Crash.
I mean, not really  crashed, the message appears, but nothing weird happens. Noesis seems to keep running fine, but I can't use it.
I'm only able to use it when I open it using Sandboxie, then it works 100%.

And yeah.. Just thought I would let you know!
Thanks. Are you able to submit reports when it crashes? If so, what is your IP? I used to be able to see a user's posting IP list with my moderator powers on here, but that list has disappeared. I think it got fucked up with a forum upgrade or something.

Is this you?

NOESIS_VER		"4.052"
EXCEPTION_CODE		"c0000005"
EXCEPTION_ADDR		"00000000"
EXCEPTION_EIP		"00000000"
EXCEPTION_LFL		""
EXCEPTION_LCF		""
NOESIS_MODULE		"D:\cabal arquivos\noesisv4202\Noesis.exe" "00110000" "003a9000" "00260f77"

If so, your install is super-fucked. The internal version is 4.052, which is ancient, yet it's in a 4.202 directory. Something on your system is probably flushing it out with an old copy of the executable somehow, which would crash for many reasons. Maybe your antivirus has gone haywire.
## Post #4
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-09-27T01:18:41+00:00
- Post Title: PSA: Update your Noesis version!

> Reply from MrAdults
>
> 
Thanks. Are you able to submit reports when it crashes? If so, what is your IP? I used to be able to see a user's posting IP list with my moderator powers on here, but that list has disappeared. I think it got fucked up with a forum upgrade or something.

Is this you?

NOESIS_VER		"4.052"
EXCEPTION_CODE		"c0000005"
EXCEPTION_ADDR		"00000000"
EXCEPTION_EIP		"00000000"
EXCEPTION_LFL		""
EXCEPTION_LCF		""
NOESIS_MODULE		"D:\cabal arquivos\noesisv4202\Noesis.exe" "00110000" "003a9000" "00260f77"

If so, your install is super-fucked. The internal version is 4.052, which is ancient, yet it's in a 4.202 directory. Something on your system is probably flushing it out with an old copy of the executable somehow, which would crash for many reasons. Maybe your antivirus has gone haywire.

Hey there!

No, this isn't me. I just submitted one crash report with the version 4.202 (clean install). 
My IP is 186.xxx.72.90.

Thanks.
## Post #5
- Username: mono24
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2016-09-27T03:09:11+00:00
- Post Title: PSA: Update your Noesis version!

Your crash is in:

0x708a1a37 (<unknown>@0x00000000, offset 0xf1a37) - C:\Program Files (x86)\GbPlugin\gbiehuni.dll

This isn't a part of Noesis, and is loading into the process as part of the shell view, meaning it's also active for any process on your machine with shell hooks including Explorer itself. Noesis just happens to be the one doing something it doesn't like, probably owing to the fact that it doesn't expect to be pulled in by the application's shell view.

It looks like this file is commonly malware and is the cause of many MSIE crash/freeze reports. It's possible that this file's been modified by a virus or something. Your copy of the module is 5,275,648 bytes (at least based on the in-process memory usage, not necessarily matching the file size) which isn't in line with any legitimate copy I can find by googling. You should probably scorch the earth.
## Post #6
- Username: lolwatt
- Rank: veteran
- Number of posts: 143
- Joined date: Mon Sep 22, 2014 8:23 am
- Post datetime: 2016-09-27T05:58:28+00:00
- Post Title: PSA: Update your Noesis version!

I cannot thank you enough!

After googling around, I found out about that.
It's actually from GBuster Security, it's an antifraud solution that banks here in Brazil use.
Before logging in with a bank account on their website, you must install that crap. Yeah. No other option.
It seems very unpopular among users and a true headache to get rid of it.
I'll have to remove it and find another way to deal with online banking.

Thank you again!

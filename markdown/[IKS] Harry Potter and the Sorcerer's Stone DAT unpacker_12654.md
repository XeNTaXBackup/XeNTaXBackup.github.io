## Post #1
- Username: SILENTpavel
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-02-27T23:01:30+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

Hello. I want to share with you my tool for unpacking DAT container from Harry Potter and the Sorcerer's Stone (PS1).

Source code available!
You need python to run this!
Usage: <script.py> POTTER.DIR

Enjoy 
[Potter DAT unpack.zip](https://xentaxbackup.github.io/file/8771_Potter DAT unpack.zip)
## Post #2
- Username: SILENTpavel
- Rank: advanced
- Number of posts: 54
- Joined date: Fri Aug 05, 2011 12:53 pm
- Post datetime: 2015-07-20T03:51:37+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

> Reply from ikskoks
>
> Usage: <script.py> POTTER.DIRWhat i did wrong? Did i need to install python 2.7.10? I've installed 3.4.3 on my Win7. Sorry for possibly "python-noob" question.

>sciezka zapisywanego pliku
>path of the saved file
## Post #3
- Username: SILENTpavel
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2015-07-20T13:00:29+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

> Did i need to install python 2.7.10?
This program was made on Python 2.7.5
You shopuld propably download and install it.

Or you can edit source code by adding bracets to all print functions like print("hello world")
## Post #4
- Username: Leminur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 21, 2017 11:37 am
- Post datetime: 2017-06-21T03:46:05+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

Hello there! I am having trouble trying to extract the POTTER files, I want to find the 3d Models from the game, but I am having a bit of trouble in order to do so.

Here is how I am opening with CMD (I am going to show it without the directories):

> python.exe PotterDATunpack.py POTTER.DIR

I do not know Polish or Python, but I do know programming and I debugged the script you made once I successfully ran the script.
I managed to have the successful output message (Wypakowywanie zakonczone sukcesem.) But it did not generate or extracted any files. I have debugged the script and I found out that it's not getting into the 'for' condition:

```
for i in range(liczba_plikow):
```


Can I have some help with it? Thanks a bunch for doing such script!
## Post #5
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-06-21T06:37:28+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

I have tested on SLUS_014.15 and it worked fine.

This script creates "WYPAKOWANE" folder next to the POTTER.DIR and POTTER.DAT file.

Execute like this: C:\Users\User>python "C:\TEMP\Potter DAT unpack.py" C:\TEMP\POTTER.DIR

Folder should look like this:


And output in cmd should look like this:
## Post #6
- Username: Leminur
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Jun 21, 2017 11:37 am
- Post datetime: 2017-06-21T18:17:40+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

> Reply from ikskoks
>
> I have tested on SLUS_014.15 and it worked fine.

This script creates "WYPAKOWANE" folder next to the POTTER.DIR and POTTER.DAT file.

Execute like this: C:\Users\User>python "C:\TEMP\Potter DAT unpack.py" C:\TEMP\POTTER.DIR

I have tried to do the same as you did, but I am still having the same problem.

I did place the POTTER files into a TEMP folder right next to C:\ as you can see on the image below, but I am still having the same problem.



Captura de tela 2017-06-21 15.11.05.png (17.17 KiB) Viewed 176 times



I am using the SLUS-01415 that I had found on emuparadise, but I am not sure why I can't execute it correctly! 
Do you have any idea what may cause this problem?
## Post #7
- Username: ikskoks
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2017-06-21T20:43:31+00:00
- Post Title: [IKS] Harry Potter and the Sorcerer's Stone DAT unpacker

I have answered by PM.
It was game version related problem.

## Post #1
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-07T22:57:27+00:00
- Post Title: EARC archive (FFXV PC)

Hi,

I have made an archiver to extract and rebuild EARC archives. Compressed files don't have to be smaller.


Edit: It works with the FULL version of the game.

Tested on playable demo version of the game, I have imported changed texts and fonts succesfully to the game.
First, you need to set the folder to extract files from EARC archives. After set, it saves this path to ini file.

If something is not working correctly, PM me.

PS. Sorry about app design, didn't have time to do it better.

Edit 2018-07-21:
Next version, allows to reinsert only one file in the EARC archive: [Link removed]

Edit 2018-12-30:
Next version, allows to extract all EARC archives from the selected folder, rebuild all EARC archives based on a list, and make a batch file to extract DDS from all found BTEX files: [Hammerhead 1.5](http://www.balamb.pl/down/Hammerhead_v1.5.zip)
## Post #2
- Username: Katkat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 14, 2015 2:22 am
- Post datetime: 2018-03-07T23:13:47+00:00
- Post Title: EARC archive (FFXV PC)

Unable to extract audio content

```
juste-à-temps (JIT) à la place de cette boîte de dialogue.

************** Texte de l'exception **************
System.OverflowException: L'opération arithmétique a provoqué un dépassement de capacité.
   à EARC.Form1.bLoadEARC_Click(Object sender, EventArgs e)
   à System.Windows.Forms.Control.OnClick(EventArgs e)
   à System.Windows.Forms.Button.OnClick(EventArgs e)
   à System.Windows.Forms.Button.OnMouseUp(MouseEventArgs mevent)
   à System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   à System.Windows.Forms.Control.WndProc(Message& m)
   à System.Windows.Forms.ButtonBase.WndProc(Message& m)
   à System.Windows.Forms.Button.WndProc(Message& m)
   à System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Assemblys chargés **************
mscorlib
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2600.0 built by: NET471REL1LAST
    CodeBase : file:///C:/Windows/Microsoft.NET/Framework64/v4.0.30319/mscorlib.dll
----------------------------------------
EARC
    Version de l'assembly : 1.0.0.0
    Version Win32 : 1.0.0.0
    CodeBase : file:///C:/Users/KatKat/Desktop/test/Hammerhead.exe
----------------------------------------
System.Windows.Forms
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Configuration
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Core
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2600.0 built by: NET471REL1LAST
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System.Xml
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2612.0 built by: NET471REL1LAST_B
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
Microsoft.VisualBasic.Compatibility
    Version de l'assembly : 10.0.0.0
    Version Win32 : 14.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualBasic.Compatibility/v4.0_10.0.0.0__b03f5f7f11d50a3a/Microsoft.VisualBasic.Compatibility.dll
----------------------------------------
Microsoft.VisualBasic
    Version de l'assembly : 10.0.0.0
    Version Win32 : 14.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualBasic/v4.0_10.0.0.0__b03f5f7f11d50a3a/Microsoft.VisualBasic.dll
----------------------------------------
Microsoft.VisualBasic.Compatibility.resources
    Version de l'assembly : 10.0.0.0
    Version Win32 : 14.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualBasic.Compatibility.resources/v4.0_10.0.0.0_fr_b03f5f7f11d50a3a/Microsoft.VisualBasic.Compatibility.resources.dll
----------------------------------------
mscorlib.resources
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/mscorlib.resources/v4.0_4.0.0.0_fr_b77a5c561934e089/mscorlib.resources.dll
----------------------------------------
System.Windows.Forms.resources
    Version de l'assembly : 4.0.0.0
    Version Win32 : 4.7.2556.0 built by: NET471REL1
    CodeBase : file:///C:/WINDOWS/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms.resources/v4.0_4.0.0.0_fr_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------

************** Débogage JIT **************
Pour activer le débogage juste-à-temps (JIT), le fichier de configuration pour cette
application ou cet ordinateur (machine.config) doit avoir la valeur
jitDebugging définie dans la section system.windows.forms.
L'application doit également être compilée avec le débogage
activé.

Par exemple :

<configuration>
    <system.windows.forms jitDebugging="true" />
</configuration>

Lorsque le débogage juste-à-temps est activé, les exceptions non gérées
seront envoyées au débogueur JIT inscrit sur l'ordinateur
plutôt que d'être gérées par cette boîte de dialogue.


```

[log1.PNG](https://xentaxbackup.github.io/file/14009_log1.PNG)
## Post #3
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-08T19:30:04+00:00
- Post Title: EARC archive (FFXV PC)

I got an info that it's not working with EARC files of the full game. I'll be checking what SE changed in EARC format.
## Post #4
- Username: Katkat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 14, 2015 2:22 am
- Post datetime: 2018-03-08T23:50:16+00:00
- Post Title: EARC archive (FFXV PC)

> Reply from Robin
>
> I got an info that it's not working with EARC files of the full game. I'll be checking what SE changed in EARC format.

Okay, I had the full version, sorry for the inconvenience
## Post #5
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2018-03-10T21:20:01+00:00
- Post Title: EARC archive (FFXV PC)

Yeah, doesn't work for the main game, I can provide some earc files if need be.

Hope you figure it out, and thanks.
## Post #6
- Username: Katkat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 14, 2015 2:22 am
- Post datetime: 2018-03-10T22:09:10+00:00
- Post Title: EARC archive (FFXV PC)

> Reply from Andelx
>
> Yeah, doesn't work for the main game, I can provide some earc files if need be.

Hope you figure it out, and thanks.

I wanted to change the fighting music of the game, but I have a question, knowing that we can not extract the EARC file, can still create an EARC file with the content of a music of his choice?
## Post #7
- Username: Katkat
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Tue Jul 14, 2015 2:22 am
- Post datetime: 2018-03-11T15:20:47+00:00
- Post Title: EARC archive (FFXV PC)

[https://twitter.com/KupoOnToast/status/ ... 9994627074](https://twitter.com/KupoOnToast/status/972843469994627074)
[https://gamebanana.com/sounds/40797](https://gamebanana.com/sounds/40797)

A person apparently succeeded
## Post #8
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-11T16:45:46+00:00
- Post Title: EARC archive (FFXV PC)

It is/will be possible for sure. I'm working on encrypting EARC files during rebuilding.
## Post #9
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2018-03-12T13:29:21+00:00
- Post Title: EARC archive (FFXV PC)

Well, hope people figure it out soon. I look forward to looking through the files.
## Post #10
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-19T20:09:32+00:00
- Post Title: EARC archive (FFXV PC)

Next version, working with full version of the game: [Hammerhead 1.5](http://www.balamb.pl/down/Hammerhead_v1.5.zip) [Edited, 2018-12-30]

Important note: Archives from Steam Workshop are not supported. EARC archives inside EARC archives are also not supported.

If something is not working, let me know.
## Post #11
- Username: Andelx
- Rank: beginner
- Number of posts: 38
- Joined date: Tue May 03, 2016 1:44 am
- Post datetime: 2018-03-20T10:40:15+00:00
- Post Title: EARC archive (FFXV PC)

Thank you so much for this update. 

This is a great tool, I just hope there is a way to mass-extract the files, there are so many. o_o
## Post #12
- Username: ryudogaming
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Mar 11, 2018 11:08 pm
- Post datetime: 2018-03-20T17:36:41+00:00
- Post Title: EARC archive (FFXV PC)

there is a slight bug that if you could fix would be amazing.

Currently be it extracting or repacking it can only be done once on the same file. if you want to repack it again you have to close the software down and restart it as the repacker doesn't close or free the file after its done.

example: ive changed a file in fontandmessages.arc, but it didnt quite work so i want to edit the file again and repack it. but i can't i get a error saying its in use. so i have to close down the repacker open it again to repack the file.
## Post #13
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-03-20T18:18:47+00:00
- Post Title: EARC archive (FFXV PC)

@ryudogaming, you are right, I'll correct it for sure.
## Post #14
- Username: Amon Amarth
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue May 08, 2018 12:41 pm
- Post datetime: 2018-05-08T04:44:40+00:00
- Post Title: EARC archive (FFXV PC)

Hey there, I've been watching this thread for sometime and am hoping someone can use the data from your efforts to make a fix for the HUD for us Surround/Eyefinity users. Here's hoping.
## Post #15
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-07-14T20:59:42+00:00
- Post Title: EARC archive (FFXV PC)

I have just corrected this ridiculous bug spotted by ryudogaming: [Hammerhead 1.5](http://www.balamb.pl/down/Hammerhead_v1.5.zip) [Edited 2018-12-30]
## Post #16
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-07-21T15:14:35+00:00
- Post Title: Re: EARC archive (FFXV PC)

Another version, allows to reinsert only one file in the EARC archive: [Hammerhead 1.5](http://www.balamb.pl/down/Hammerhead_v1.5.zip)
Also, allows to reinsert more files in batch txt file.
## Post #17
- Username: Robin
- Rank: beginner
- Number of posts: 25
- Joined date: Wed Aug 12, 2015 3:44 am
- Post datetime: 2018-12-30T23:58:37+00:00
- Post Title: Re: EARC archive (FFXV PC)

New version: [Hammerhead 1.5](http://www.balamb.pl/down/Hammerhead_v1.5.zip)

- added option to extract from all EARC archives from the selected folder
- added option to rebuild all EARC archives from the list:
	1) When you extract EARC archive, it is being added to the list.
	2) This list is saved in earclist.txt, so you can edit it outside the application.
- added option to create a QBMS batch file for all BTEX files found in extraction folder and subfolders:
	1) You have to set a path to QuickBMS folder.
	2) Name of the ffxv_btex2dds.bms script is added automatically, but you can change it. This script has to be placed in QuickBMS folder.
	3) You have to set a path where you want to have extracted DDS files from BTEX files.
## Post #18
- Username: Critikal
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Thu Oct 20, 2022 7:47 am
- Post datetime: 2022-10-20T00:51:50+00:00
- Post Title: Re: EARC archive (FFXV PC)

Hey, are you still active?, i just started playing FF XV and i would love to edit some textures but i think the link is broken because im not able to get the app anywhere
## Post #19
- Username: Petrgold
- Rank: beginner
- Number of posts: 31
- Joined date: Thu Feb 27, 2020 6:46 pm
- Post datetime: 2022-10-21T14:37:52+00:00
- Post Title: Re: EARC archive (FFXV PC)

> Reply from Critikal ↑Thu Oct 20, 2022 8:51 am at Thu Oct 20, 2022 8:51 am
>
> 
Hey, are you still active?, i just started playing FF XV and i would love to edit some textures but i think the link is broken because im not able to get the app anywhere
[https://github.com/Kizari/Flagrum](https://github.com/Kizari/Flagrum)

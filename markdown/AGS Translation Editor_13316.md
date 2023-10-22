## Post #1
- Username: Takti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 05, 2015 5:42 pm
- Post datetime: 2015-09-12T17:44:09+00:00
- Post Title: AGS Translation Editor

Hello together i recently wrote a Editor application for "Adventure Game Studio" games to help me translate Technobabylon.

What can you do with AGS Translation Editor ?
Read, edit, convert and create TRS and TRA Translation Files for AGS Games then you can use winsetup.exe to choose the translation file.

Where do i get the script of a game ?
Unfortunatly i didn't found a proper way to get the scripts programmatically , however you can manually search for "__NEWSCRIPTSTART_" in the Game Exe and copy&paste the text into a new trs file it's only a bit tedious.
Maybe someone else does have already experience with it and could help .

TRS file format
A TRS file should look like this example

```
&1 Test translation1
&2 Original Text2
&2 Test translation2
...

```

Known Issues
there are problems with special characters like äöüßèà since Adventure Games Studio only supports the ASCII character (thought there are workarounds you can read more about it here [http://www.adventuregamestudio.co.uk/wi ... your_needs](http://www.adventuregamestudio.co.uk/wiki/Fonts#The_MOST_IMPORTANT_part:_define_your_needs)).

So usually you just edit the TRS files and create a TRA from it (Tools -> Create TRA).
Maybe someone else does find it usefull and i hope that is kind of understandable (english isn't my native language)

If you have still may have questions just ask 

Download
[AGS Translation Editor](https://bitbucket.org/Taktloss/ags_translationeditor/downloads/AGS_TranslationEditor.zip)
## Post #2
- Username: MiRiKan
- Rank: advanced
- Number of posts: 67
- Joined date: Fri Jul 25, 2014 1:28 pm
- Post datetime: 2015-09-13T23:32:06+00:00
- Post Title: AGS Translation Editor

WOW! can you share the source code? this looks like the powerful tool.
PM me if you can share
## Post #3
- Username: Takti
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jun 05, 2015 5:42 pm
- Post datetime: 2015-09-17T22:50:20+00:00
- Post Title: AGS Translation Editor

> Reply from MiRiKan
>
> WOW! can you share the source code? this looks like the powerful tool.
PM me if you can share

Sure the source code is here [https://bitbucket.org/Taktloss/ags_translationeditor](https://bitbucket.org/Taktloss/ags_translationeditor) everything open source 

PS: Any tips for improvments are appreciated .
## Post #4
- Username: ner0
- Rank: advanced
- Number of posts: 50
- Joined date: Sun Aug 28, 2011 11:47 pm
- Post datetime: 2016-02-11T00:28:22+00:00
- Post Title: AGS Translation Editor

Looks nice, unfortunately I can't seem to install this on my machine (Win10 x64), this is what I get: [http://i.imgur.com/yHu6TIr.png](http://i.imgur.com/yHu6TIr.png)
Also, please don't take this the wrong way but, you're introducing a translation tool entirely in German? Personally, English would have been a better choice for primary language.
Anyway, I hope to be able to use this... at some point.
## Post #5
- Username: dlyfreak
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Oct 11, 2016 8:57 pm
- Post datetime: 2016-10-11T13:22:17+00:00
- Post Title: AGS Translation Editor

i know its realy late to answer to this.

@ first, sorry 4 my bad english

@ second: try to install this:

[http://dl.cdn.chip.de/downloads/6890274 ... 820661.exe](http://dl.cdn.chip.de/downloads/6890274/aio-runtimes_v2.3.9.exe?cid=54450072&platform=chip&1476191796-1476199296-7590f-B-28e66d578cc9b9ade09acc3973820661.exe)


it should work after this.
## Post #6
- Username: hexaae
- Rank: advanced
- Number of posts: 44
- Joined date: Fri May 20, 2016 6:23 am
- Post datetime: 2018-02-11T16:45:48+00:00
- Post Title: AGS Translation Editor

> Reply from Takti
>
> 

Known Issues
there are problems with special characters like äöüßèà since Adventure Games Studio only supports the ASCII character (thought there are workarounds you can read more about it here http://www.adventuregamestudio.co.uk/wi ... your_needs).
I tried your tool with Maniac Mansion Deluxe [http://www.adventuregamestudio.co.uk/si ... /game/401/](http://www.adventuregamestudio.co.uk/site/games/game/401/) because I wanted to improve Italian translation adding accented vowels etc. but run into troubles with special chars.
When I import f.e. French .tra file, and save it as .trs all special char codes get lost (converted to "0xEFBF<non std hex single char code>"). If I now create a .tra starting from that saved .trs, in game I'll see wrong foreign char groups.
Can you correct this?

E.g. (French .tra)
"è" is imported as 0xEFBFA8, so when I save it as .trs and then use this .trs to generate the new .tra "è" will be replaced in game by something like "ï¿Ö"
Maybe this reference table can help understanding why: [http://www.i18nqa.com/debug/utf8-debug.html](http://www.i18nqa.com/debug/utf8-debug.html)
## Post #7
- Username: Jibun
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat May 16, 2020 11:07 pm
- Post datetime: 2020-05-24T17:42:45+00:00
- Post Title: AGS Translation Editor

AGS Translation Editor v2.0.0 available!

It's been some time, but I have continued the project and done several changes to it.
Special characters are now loaded and saved as expected and I have added some extra functionalities and fixed other minor bugs.

Here is the repository of the project: [https://github.com/Jibun/ags-translation-editor](https://github.com/Jibun/ags-translation-editor)
You can find and download the windows executable in the release tab of the repo.
## Post #8
- Username: jurandy007
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Wed Jan 20, 2021 11:26 pm
- Post datetime: 2021-01-20T15:38:27+00:00
- Post Title: AGS Translation Editor

I really liked the tool, congratulations but I'm having problems with it:

1 - When I try to convert to TRA the tool asks me to search for the EXE of itself and when I select it it says it is already in use.

2 - when I try to circumvent this by making a copy of the EXE and after choosing the name to save the TRA the error appears

" See the end of this message for details on how to call the
just-in-time (JIT) debugging instead of this dialog box.

************** Exception Text **************
System.NullReferenceException: Object reference not defined for an instance of an object.
   in AGS_TranslationEditor.AgsTranslation.CreateTraFile (Gameinfo info, String filename, Dictionary`2 entryList)
   in AGS_TranslationEditor.MainForm.createTraToolStripMenuItem_Click (Object sender, EventArgs e)
   in System.Windows.Forms.ToolStripItem.RaiseEvent (Object key, EventArgs e)
   in System.Windows.Forms.ToolStripMenuItem.OnClick (EventArgs e)
   in System.Windows.Forms.ToolStripItem.HandleClick (EventArgs e)
   in System.Windows.Forms.ToolStripItem.HandleMouseUp (MouseEventArgs e)
   in System.Windows.Forms.ToolStripItem.FireEventInteractive (EventArgs e, ToolStripItemEventType met)
   in System.Windows.Forms.ToolStripItem.FireEvent (EventArgs e, ToolStripItemEventType met)
   in System.Windows.Forms.ToolStrip.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.ToolStripDropDown.OnMouseUp (MouseEventArgs mea)
   in System.Windows.Forms.Control.WmMouseUp (Message & m, MouseButtons button, Int32 clicks)
   in System.Windows.Forms.Control.WndProc (Message & m)
   in System.Windows.Forms.ScrollableControl.WndProc (Message & m)
   in System.Windows.Forms.ToolStrip.WndProc (Message & m)
   in System.Windows.Forms.ToolStripDropDown.WndProc (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.OnMessage (Message & m)
   in System.Windows.Forms.Control.ControlNativeWindow.WndProc (Message & m)
   in System.Windows.Forms.NativeWindow.Callback (IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4300.0 built by: NET48REL1LAST_C
    Code Base: file: /// C: /Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
AGS_TranslationEditor
    Assembly version: 2.0.0.0
    Win32 version: 2.0.0.0
    Code Base: file: /// C: /Users/juran/Desktop/teste/AGS_TranslationEditor.exe
----------------------------------------
System.Windows.Forms
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4270.0 built by: NET48REL1LAST_C
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4300.0 built by: NET48REL1LAST_C
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Drawing
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4084.0 built by: NET48REL1
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Configuration
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4190.0 built by: NET48REL1LAST_B
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Core
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4300.0 built by: NET48REL1LAST_C
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System.Xml
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4084.0 built by: NET48REL1
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
System.Windows.Forms.resources
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4084.0 built by: NET48REL1
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms.resources/v4.0_4.0.0.0_pt-BR_b77a5c561934e089/System.Windows.Forms.resources.dll
----------------------------------------
Microsoft.VisualBasic
    Assembly version: 10.0.0.0
    Win32 version: 14.8.4084.0 built by: NET48REL1
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/Microsoft.VisualBasic/v4.0_10.0.0.0__b03f5f7f11d50a3a/Microsoft.VisualBasic.dll
----------------------------------------
mscorlib.resources
    Assembly version: 4.0.0.0
    Win32 version: 4.8.4084.0 built by: NET48REL1
    Code Base: file: /// C: /Windows/Microsoft.Net/assembly/GAC_MSIL/mscorlib.resources/v4.0_4.0.0.0_pt-BR_b77a5c561934e089/mscorlib.resources.dll
----------------------------------------

************** JIT Debugging **************
To enable just-in-time (JIT) debugging, the .config file for this
application or computer (machine.config) must have the value
jitDebugging defined in the system.windows section.

forms.
The application must also be compiled with debugging
enabled.

For example:

<configuration>
     <system.windows.forms jitDebugging = "true" />
</configuration>

When JIT debugging is enabled, any unhandled exception
will be sent to the JIT debugger registered on the computer,
instead of being dealt with in this dialog. "

3 - When I try to use GET GAME INFO in the game PRIMORDIA:

System.OutOfMemoryException: Exception of type 'System.OutOfMemoryException' was thrown.
## Post #9
- Username: muserigtc
- Rank: beginner
- Number of posts: 27
- Joined date: Sat Jul 16, 2016 9:44 pm
- Post datetime: 2023-04-11T08:01:15+00:00
- Post Title: AGS Translation Editor

Hey can you updated the AGS Version to 3.5.0

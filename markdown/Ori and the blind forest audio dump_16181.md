## Post #1
- Username: OtterDragon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 17, 2016 8:55 am
- Post datetime: 2017-04-22T02:30:07+00:00
- Post Title: Ori and the blind forest audio dump

Heya, as the title says, I am looking for a full audio dump, or a method of browsing the audio files of the game.

I go by Ori irl and most places, and I want the sound clip of Sein saying Ori to set as my text tone
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-04-22T04:17:58+00:00
- Post Title: Ori and the blind forest audio dump

You can use [Unity Studio](https://github.com/RaduMC/UnityStudio/releases) to extract the .fsb files

Use the [latest vgmstream](https://github.com/bnnm/vgmstream-builds) to listen/convert them into .wav files
## Post #3
- Username: OtterDragon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 17, 2016 8:55 am
- Post datetime: 2017-04-22T04:34:03+00:00
- Post Title: Ori and the blind forest audio dump

Thanks, Unity studio successfully allows me to view the files, but I am having trouble locating the fsb files


also no matter what file I click on, and when I try to extract, I get "unhandled exception has occured"
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-04-22T10:33:37+00:00
- Post Title: Ori and the blind forest audio dump

File > Load Folder > and open the "ori_data" or "oriDE_data" folder

Once it finishes loading all the files, go to the "Assets List" tab and sort them by type. Audio Clip should be near the top.

Highlight all the audio clips and go to Export > Selected assets and choose an output directory.

Playback / convert with vgmstream.
## Post #5
- Username: OtterDragon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 17, 2016 8:55 am
- Post datetime: 2017-04-22T17:16:29+00:00
- Post Title: Ori and the blind forest audio dump

> File > Load Folder > and open the "ori_data" or "oriDE_data" folder
>
> 
>
> Once it finishes loading all the files, go to the "Assets List" tab and sort them by type. Audio Clip should be near the top.
>
> 
>
> Highlight all the audio clips and go to Export > Selected assets and choose an output directory.

I tried this exactly, step by step, and when I first highlight the files, and when I start the export, I get "unhandled exception has occured". I can click continue or quit, and if I click continue, it just doesn't export any files... it creates the directory I want  them exported to, but it is empty 

This is the error I get when I try to export:

```
System.OverflowException: Arithmetic operation resulted in an overflow.
   at Unity_Studio.AudioClip..ctor(AssetPreloadData preloadData, Boolean readSwitch)
   at Unity_Studio.UnityStudioForm.ExportAsset(AssetPreloadData asset, String exportPath)
   at Unity_Studio.UnityStudioForm.ExportFiltered(List`1 filteredAssetList, String selectedPath, Int32 groupFiles)
   at Unity_Studio.UnityStudioForm.ExportAssets_Click(Object sender, EventArgs e)
   at System.Windows.Forms.ToolStripItem.RaiseEvent(Object key, EventArgs e)
   at System.Windows.Forms.ToolStripMenuItem.OnClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleClick(EventArgs e)
   at System.Windows.Forms.ToolStripItem.HandleMouseUp(MouseEventArgs e)
   at System.Windows.Forms.ToolStripItem.FireEventInteractive(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStripItem.FireEvent(EventArgs e, ToolStripItemEventType met)
   at System.Windows.Forms.ToolStrip.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.ToolStripDropDown.OnMouseUp(MouseEventArgs mea)
   at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
   at System.Windows.Forms.Control.WndProc(Message& m)
   at System.Windows.Forms.ScrollableControl.WndProc(Message& m)
   at System.Windows.Forms.ToolStrip.WndProc(Message& m)
   at System.Windows.Forms.ToolStripDropDown.WndProc(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.OnMessage(Message& m)
   at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
   at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, Int32 msg, IntPtr wparam, IntPtr lparam)


************** Loaded Assemblies **************
mscorlib
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.NET/Framework/v4.0.30319/mscorlib.dll
----------------------------------------
Unity Studio
    Assembly Version: 0.5.0.0
    Win32 Version: 0.0.0.0
    CodeBase: file:///C:/Users/OtterPop/Desktop/Unity%20Studio/Unity%20Studio.exe
----------------------------------------
System.Core
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Core/v4.0_4.0.0.0__b77a5c561934e089/System.Core.dll
----------------------------------------
System
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System/v4.0_4.0.0.0__b77a5c561934e089/System.dll
----------------------------------------
System.Windows.Forms
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Windows.Forms/v4.0_4.0.0.0__b77a5c561934e089/System.Windows.Forms.dll
----------------------------------------
System.Drawing
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Drawing/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Drawing.dll
----------------------------------------
System.Configuration
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Configuration/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Configuration.dll
----------------------------------------
System.Xml
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Xml/v4.0_4.0.0.0__b77a5c561934e089/System.Xml.dll
----------------------------------------
System.Web.Extensions
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_MSIL/System.Web.Extensions/v4.0_4.0.0.0__31bf3856ad364e35/System.Web.Extensions.dll
----------------------------------------
System.Web
    Assembly Version: 4.0.0.0
    Win32 Version: 4.6.81.0 built by: NETFXREL2
    CodeBase: file:///C:/Windows/Microsoft.Net/assembly/GAC_32/System.Web/v4.0_4.0.0.0__b03f5f7f11d50a3a/System.Web.dll
----------------------------------------
```
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2017-04-23T02:36:07+00:00
- Post Title: Ori and the blind forest audio dump

I'll just send you the audio files then. Might be the easiest way to do it.
## Post #7
- Username: OtterDragon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Wed Aug 17, 2016 8:55 am
- Post datetime: 2017-04-23T05:57:30+00:00
- Post Title: Ori and the blind forest audio dump

> Reply from brendan19
>
> I'll just send you the audio files then. Might be the easiest way to do it.

Thanks again man, also its funny that the specific file I was looking for was conveniently titled "oriSpeechOriSaysOriUrgentShortA #542092"

for anyone else doing stuff with Ori's sound files, Sein and Ori's names in the asset's are swapped, possibly implying that the game might have been called 'Sein and the blind forest' at one point.
## Post #8
- Username: ttu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 10, 2019 4:54 am
- Post datetime: 2019-09-09T20:57:40+00:00
- Post Title: Ori and the blind forest audio dump

Hi, I'd also like the audio dump files. I got all the .fsb files no prob, just not sure about the next step with vgmstream. Care to break that last part down? I extracted the latest version and click test.exe and nothing happens. The text says to download more files. I did. Put in the the same folder and still nothing. The text file goes on to mention winamp. Do I need that program too?

I tried half a dozen other fsb to audio extractors and nothing, total bummer
## Post #9
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2019-09-09T22:14:55+00:00
- Post Title: Ori and the blind forest audio dump

vgmstream has a plugin designed to work with Winamp so you can just playback audio formats and hear them without the need of converting them 

The test.exe is a command line only application. There is no Graphical User Interface (GUI) built in to the program. You can open it using command prompt. You can do this easily in any folder by holding down shift, right-clicking and selecting "Open command window here".

For batch converting do the following:
Copy the following text into a text editor like notepad and save it as "Test.bat" or something. The .bat file extension is the only important thing here as this will batch convert all files with the extension you want to convert.

For example, the following will work for Ori and the Blind forest as it uses FSB

```
FOR %%a IN (*.fsb) DO test.exe -l 2 -f 10 -o "%%a.wav" "%%a"
```


This .bat file will only work properly if the test.exe and your .fsb files are all in the same folder. You can specify the exact location of the test.exe if you want to though and just have the .bat file and the .fsb files in the same folder instead.

For example

```
FOR %%a IN (*.fsb) DO "C:\Program Files (x86)\Winamp\test.exe" -l 2 -f 10 -o "%%a.wav" "%%a"
```


Also, you can edit the (*.fsb) part to any file extension that vgmstream supports


Here is a breakdown of the functions

l = Loop count
In my example, the song will loops 2 times

f = Fade out time after loops
In my example, the song will fade out over 10 seconds after completing two loops

-o = Output file name
In my example, the converted .WAV file will use the exact same name as the .fsb file
## Post #10
- Username: ttu
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Sep 10, 2019 4:54 am
- Post datetime: 2019-09-10T05:06:32+00:00
- Post Title: Ori and the blind forest audio dump

This worked! Wow! Can't believe it worked and not really sure what I did in the end, just glad it did the trick after failing with so many other apps. I can't thank you enough!!

So, will this method ever not work, ie encrypted?

Do I simply change the .fsb in the .bat file when needed to correspond to any format?

Thanks again!!

P.S. I am a music producer and plan to use some of the samples and audio or ORI talking in a few tracks. It has a very happy, mysterious, elven like, vibe. Cheers
## Post #11
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2019-09-10T08:44:46+00:00
- Post Title: Ori and the blind forest audio dump

> Reply from ttu ↑Tue Sep 10, 2019 1:06 pm at Tue Sep 10, 2019 1:06 pm
>
> So, will this method ever not work, ie encrypted?Yes, if the file is encrypted it might not work.
Also, if the FSB is version 5 or above, they usually combine multiple FSB files into a singular file archive. It is advisable to split those type of files using a tool found on the ZenHAX forum (sister site to Xentax) which can split the FSB5 file into multiple audio files.

> Reply from ttu ↑Tue Sep 10, 2019 1:06 pm at Tue Sep 10, 2019 1:06 pm
>
> Do I simply change the .fsb in the .bat file when needed to correspond to any format?
Yes, if vgmstream supports the format, you can change the extension from FSB to anything it supports. Although file extensions don't always 100% guarantee a particular audio codec/format. For example FSB is really just a container format. The audio codec inside FSB can be many different types. It can be MP3, Vorbis, MS ADPCM, PCM or even XMA. In this case, Ori uses vorbis encoded audio inside FSB containers.
## Post #12
- Username: Xan the Dragon
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Aug 30, 2015 6:37 am
- Post datetime: 2019-10-10T05:23:51+00:00
- Post Title: Ori and the blind forest audio dump

Unity Asset Studio (note: this is NOT Unity Studio. Different app.) will automatically convert the FSB data and spit out ogg files for you. I've happened to do some audio ripping from Ori myself (lots of nice stuff there) and this tool makes it incredibly fast. [https://github.com/Perfare/AssetStudio/releases](https://github.com/Perfare/AssetStudio/releases)

Just go to the "Load file" option in the File menu and select every *.assets file in Ori DE_data. There will be an "Asset list" tab where you can see all of the assets and preview specific sounds (it's helpful if you sort by type). To export them all just go to Filter Type up top and click "AudioClip". Then select everything, go to Export => Selected assets.

No need to set up any extra applications or anything, this just works out of the box.

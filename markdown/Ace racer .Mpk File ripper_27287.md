## Post #1
- Username: gugugoo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 01, 2022 5:41 pm
- Post datetime: 2023-10-08T01:23:12+00:00
- Post Title: Ace racer .Mpk File ripper

This is a racing game developed by NetEase self-developed engine.which has a very beautiful car and clothing models.
can anyone take a look at these files and see if they can get 3d models & textures from them ?
thanks
It is stored in.mpk format.
dowload file:[https://drive.google.com/drive/folders/ ... drive_link](https://drive.google.com/drive/folders/1hj5HH6Xr2USBr0mrWIllbGfC-8cNqnJZ?usp=drive_link).
## Post #2
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-09T10:46:46+00:00
- Post Title: Ace racer .Mpk File ripper

@gugugoo: Use Netease scripts from here and read additional notes at the bottom of first post: [viewtopic.php?t=26884](https://forum.xentax.com/viewtopic.php?t=26884)
## Post #3
- Username: gugugoo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 01, 2022 5:41 pm
- Post datetime: 2023-10-09T13:24:26+00:00
- Post Title: Ace racer .Mpk File ripper

thank you very very much
## Post #4
- Username: gugugoo
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Aug 01, 2022 5:41 pm
- Post datetime: 2023-10-12T03:07:57+00:00
- Post Title: Ace racer .Mpk File ripper

> Reply from Spiritovod ↑Mon Oct 09, 2023 6:46 pm at Mon Oct 09, 2023 6:46 pm
>
> 
@gugugoo: Use Netease scripts from here and read additional notes at the bottom of first post: viewtopic.php?t=26884
I read and followed the script file you provided.  When I use NetEase (Messiah Engine) script to extract the MPK file, there is no success.  (I am using the Chinese version of the game. Does the script only support the international version?) Or there is something wrong with my operation method.  Can you help me take a look?  Thank you so much!
[9DB9O8KCAD][OLJST4$_IOR(2).png](https://xentaxbackup.github.io/file/24425_9DB9O8KCAD][OLJST4$_IOR(2).png)
## Post #5
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-12T11:27:58+00:00
- Post Title: Ace racer .Mpk File ripper

@gugugoo: It seems like you didn't fully download the game. The point is that mpkinfo is index for all possible containers of the same name (mpk files), regardless if they are already downloaded or not yet. If script is trying to process zero sized or incomplete container, it fails. I've just updated the script to ignore zero sized files, but if your download is incomplete or corrupted, it may crash anyway at some point.
## Post #6
- Username: Vlalchinanya
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 13, 2020 9:14 pm
- Post datetime: 2023-10-15T21:30:04+00:00
- Post Title: Ace racer .Mpk File ripper

> Reply from Spiritovod ↑Thu Oct 12, 2023 7:27 pm at Thu Oct 12, 2023 7:27 pm
>
> 
@gugugoo: It seems like you didn't fully download the game. The point is that mpkinfo is index for all possible containers of the same name (mpk files), regardless if they are already downloaded or not yet. If script is trying to process zero sized or incomplete container, it fails. I've just updated the script to ignore zero sized files, but if your download is incomplete or corrupted, it may crash anyway at some point.

Please tell me, will this script be able to unpack all existing meshes from files?  It’s just that Aluigi once made this script for me on the zenhax forum and it successfully decompressed .mpk files, but the result was raw files without an extension (or had the extension .4 and .9) Then Aluigi said that he had no idea how to decrypt these  files
## Post #7
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-16T00:24:48+00:00
- Post Title: Ace racer .Mpk File ripper

@Vlalchinanya: It's the same script, just with a few adjustments for newer container version and a fix for chunks size. There is additional script for converting textures, but for meshes you need to find some other tool, which could work with extracted files - they're not encrypted, but may be compressed (like textures). I guess it's worth to look for some Diablo Immortal tools, as it's using basically the same engine.
## Post #8
- Username: Vlalchinanya
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Mar 13, 2020 9:14 pm
- Post datetime: 2023-10-17T12:03:33+00:00
- Post Title: Ace racer .Mpk File ripper

> Reply from Spiritovod ↑Mon Oct 16, 2023 8:24 am at Mon Oct 16, 2023 8:24 am
>
> 
@Vlalchinanya: It's the same script, just with a few adjustments for newer container version and a fix for chunks size. There is additional script for converting textures, but for meshes you need to find some other tool, which could work with extracted files - they're not encrypted, but may be compressed (like textures). I guess it's worth to look for some Diablo Immortal tools, as it's using basically the same engine.

So, I unpacked the archives using your script, but I encountered a problem in the program for Diablo Immortal (DIDT). After unpacking the .mpk files, I now have a resource.repository file that the program requires for renaming and sorting files. But when I run it I get an error:

System.IO.EndOfStreamException: Unable to read beyond the end of the stream.
    at System.IO.BinaryReader.InternalRead(Int32 numBytes)
    at System.IO.BinaryReader.ReadUInt16()
    at DIDT.File..ctor(BinaryReader br) in E:\Projects\DIDT\DIDT\File.cs:line 45
    at DIDT.ResourceRepository..ctor(String repoPath) in E:\Projects\DIDT\DIDT\ResourceRepository.cs:line 81
    at DIDT.MainWindow.CreateResourceRepo() in E:\Projects\DIDT\DIDT\Form1.cs:line 329
    at DIDT.MainWindow.buttonSortFiles_Click(Object sender, EventArgs e) in E:\Projects\DIDT\DIDT\Form1.cs:line 336
    at System.Windows.Forms.Control.OnClick(EventArgs e)
    at System.Windows.Forms.Button.OnClick(EventArgs e)
    at System.Windows.Forms.Button.OnMouseUp(MouseEventArgs mevent)
    at DarkUI.Controls.DarkButton.OnMouseUp(MouseEventArgs e)
    at System.Windows.Forms.Control.WmMouseUp(Message& m, MouseButtons button, Int32 clicks)
    at System.Windows.Forms.Control.WndProc(Message& m)
    at System.Windows.Forms.ButtonBase.WndProc(Message& m)
    at System.Windows.Forms.Button.WndProc(Message& m)
    at System.Windows.Forms.Control.ControlNativeWindow.WndProc(Message& m)
    at System.Windows.Forms.NativeWindow.Callback(IntPtr hWnd, WM msg, IntPtr wparam, IntPtr lparam)

Please tell, what's wrong? If you have the opportunity to check the file itself, I attach it here: [https://mega.nz/file/HWZXVI7B#nxX3ePso6 ... wiOQOVtwkk](https://mega.nz/file/HWZXVI7B#nxX3ePso65DWhc0Hb3Ct1zLXBDgsOhLAQwiOQOVtwkk)
## Post #9
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-10-17T13:01:04+00:00
- Post Title: Ace racer .Mpk File ripper

@Vlalchinanya: This tool is for files extraction, at best you'll get the same output as from the script, but with filenames. Though from what I know, it doesn't support version 2 mpk with hashes. That suggestion was aimed for possible other tools / plugins, which could convert extracted meshes (which you should find manually), but I don't know if there are any around - it's just there are higher chances to find something for Diablo due to its popularity, rather than for random chinese game.

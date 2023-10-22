## Post #1
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2018-02-02T19:34:24+00:00
- Post Title: Final Fantasy XII TZA (PC)

Has anyone managed to extract the FFXII_TZA.vbf file \Steam\steamapps\common\FINAL FANTASY XII THE ZODIAC AGE\
?

Would like to do some research on cut content from the game and getting inside this file would be a major help.
Thanks.
## Post #2
- Username: ssringo
- Rank: veteran
- Number of posts: 98
- Joined date: Sat Apr 19, 2014 3:02 pm
- Post datetime: 2018-02-02T23:47:29+00:00
- Post Title: Final Fantasy XII TZA (PC)

I'd recommend also asking over on [zenhax](http://zenhax.com/viewforum.php?f=9&sid=266dd11ec59dfc0ddd3e584cf1bd8a11). You also need to upload samples. 

Download quickbms and the filecutter script from [here](http://aluigi.altervista.org/quickbms.htm). Run quickbms, choose the script and then the file you're looking to get extracted. It'll cut off parts of the main file. Upload those files and post them so people will have samples to work with.
## Post #3
- Username: Topher
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Oct 01, 2015 8:08 pm
- Post datetime: 2018-02-03T12:52:54+00:00
- Post Title: Final Fantasy XII TZA (PC)

VBFTool, a command line tool I created for FFX/FFX-2 VBF files, seems to work just fine with FFXII TZA.

[https://github.com/topher-au/VBFTool](https://github.com/topher-au/VBFTool)

You might need to compile from source, I'll get a newer release pushed out sometime in the near future.
## Post #4
- Username: zlksmlnu
- Rank: n00b
- Number of posts: 10
- Joined date: Wed Aug 10, 2016 6:27 am
- Post datetime: 2018-02-03T16:05:34+00:00
- Post Title: Final Fantasy XII TZA (PC)

> Reply from Topher
>
> VBFTool, a command line tool I created for FFX/FFX-2 VBF files, seems to work just fine with FFXII TZA.

https://github.com/topher-au/VBFTool

You might need to compile from source, I'll get a newer release pushed out sometime in the near future.

Hi, thanks I downloaded one of the older releases, when running it I have to pass a text file with file names? How do I get the file names in the first place if I cannot look inside the archive to get them?

Thanks again.

e;
If I try to just pass it an output directory it throws an error

```
VBF File Extractor v0.0.3 by Topher
------------------------------------


Unhandled Exception: System.IO.FileNotFoundException: Could not find file 'C:\Users\Localadmin\Downloads\vbfextract_0.0.3\AGE'.
   at System.IO.__Error.WinIOError(Int32 errorCode, String maybeFullPath)
   at System.IO.FileStream.Init(String path, FileMode mode, FileAccess access, Int32 rights, Boolean useRights, FileShare share, Int32 bufferSize, FileOptions options, SECURITY_ATTRIBUTES secAttrs, String msgPath, Boolean bFromProxy, Boolean useLongPath, Boolean checkHost)
   at System.IO.FileStream..ctor(String path, FileMode mode, FileAccess access, FileShare share)
   at VBFTool.VirtuosBigFileReader.LoadBigFileFile(String path)
   at vbfextract.Program.ExtractVBF(String vbfFile)
   at vbfextract.Program.Main(String[] args)
```

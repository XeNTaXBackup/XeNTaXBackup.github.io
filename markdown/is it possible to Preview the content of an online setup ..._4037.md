## Post #1
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-01-11T15:17:07+00:00
- Post Title: is it possible to Preview the content of an online setup ...

with this tool (ArchView) can  open an individal file without download the whole archive ...
[http://archview.sourceforge.net/](http://archview.sourceforge.net/)
is it possible to Preview the content of an online setup (or clients) before downloading of them ?
for example like this installer :
[http://cdn.ijjimax.com/nhnusa/games/com ... uncher.exe](http://cdn.ijjimax.com/nhnusa/games/common/firefox/SetupijjiFxLauncher.exe)
  appreciate , for improvement of knowledge about this subject ...
i just saw that most of anti virus softwares like nod32 can inspect content of an installer on hdd before unpacking it !
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2010-01-11T16:19:04+00:00
- Post Title: is it possible to Preview the content of an online setup ...

the trick is to download only the parts of the archive containing informations about the files.
so obviously is necessary to know the exact format of the archive for being able to download the needed parts in which are located the needed informations.

the zip archives are formats enough simples and indeed in the past I wrote a tool (zipweb) for doing this exact job of avoiding to download 2 gigabytes of zip only for viewing a file of some kilobytes in it.

the installers work enough similarly to a format but with some important differences because some of them have not been reversed yet (or not completely) or because their format doesn't allow the downloading of the file table (for example because they could have the information about each file followed by the compressed file and so making ugly the operation of seek&download through the hosting web server) or maybe because they are badly written or are encrypted or compressed and so is necessary to download them completely.

some types of installers supported by known programs (like 7-zip and innounp) are those of Inno-Setup, nsis installers, some versions of Install-shield with various limitations, possibly any executable containing a zip archive in its resources, the sfx installers (those created with 7-zip, winrar, winzip,...) and so on.

if I'm not in error exist some ways to mount remote http websites locally as disks so could be possible (ever theoretically) do use the pre-existent programs (like 7zip) for opening these files remotely but I have never tried it so I want only to show the info or the idea.

hope it helps
## Post #3
- Username: shekofte
- Rank: mega-veteran
- Number of posts: 221
- Joined date: Sun Jan 18, 2009 8:45 pm
- Post datetime: 2010-01-11T16:50:36+00:00
- Post Title: is it possible to Preview the content of an online setup ...

> if I'm not in error exist some ways to mount remote http websites locally as disks so could be possible (ever theoretically) do use the pre-existent programs (like 7zip) for opening these files remotely but I have never tried it so I want only to show the info or the idea.
nice tip thanks

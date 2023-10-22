## Post #1
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-06-09T10:28:33+00:00
- Post Title: XOR Tool for Multiple files

Hi!

Is there any XOR tool, where i can xor many files in one step.

I have a folder full of xored files, and it would be better if i can xor them in one step, and not selecting file by file.

Thx
## Post #2
- Username: Gocha
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-06-09T10:41:03+00:00
- Post Title: XOR Tool for Multiple files

Just use a batch file with the quickbms tool. also he has a plain xoring tool on his website 
[http://aluigi.altervista.org/mytoolz/xor.zip](http://aluigi.altervista.org/mytoolz/xor.zip)
that can also be used with a bat file.
if you need a bat file I can post one for you if you show me a screen shot of the folder.
## Post #3
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T10:44:00+00:00
- Post Title: XOR Tool for Multiple files

there is the find utility which does this job executing a specified executable and its parameters over any found file in a directory.

[http://gnuwin32.sourceforge.net/downlin ... in-zip.php](http://gnuwin32.sourceforge.net/downlinks/findutils-bin-zip.php)
[http://gnuwin32.sourceforge.net/downlin ... in-zip.php](http://gnuwin32.sourceforge.net/downlinks/libintl-bin-zip.php)
[http://gnuwin32.sourceforge.net/downlin ... in-zip.php](http://gnuwin32.sourceforge.net/downlinks/libiconv-bin-zip.php)

example:

```
find MYFOLDER -type f -exec c:\xor.exe "{}" "c:\NEWFOLDER\{}" 0x88 ;
```
in this example the find utility will scan the MYFOLDER directory (for example "c:\new folder") and for each file (-type f) will execute the xor utility.
each occurrence of {} will be substituited with the full name of the found file.
remember ever to add the final ';' as in the example.

P.S.: for more informations about the usage of find and all its various options (find can do really ANYTHING) it's enough to search "gnu find" on a search engine or [http://www.gnu.org/software/findutils/m ... index.html](http://www.gnu.org/software/findutils/manual/html_node/find_html/index.html)
## Post #4
- Username: Esidor
- Rank: beginner
- Number of posts: 21
- Joined date: Thu May 14, 2009 12:53 pm
- Post datetime: 2009-06-09T11:06:23+00:00
- Post Title: XOR Tool for Multiple files

Hmm seems i am too dumb to understand the syntax in my case.

Can you make a code example for maybe a folder C:\Test\images

In this folder are all the xored files by 0x01

That would help me to understand how it works.

Thx
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2009-06-09T12:08:09+00:00
- Post Title: XOR Tool for Multiple files

or try a batch like

```
pause
```

(replaces the files)
## Post #6
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2009-06-09T13:40:35+00:00
- Post Title: XOR Tool for Multiple files

create the folder c:\output and then:

```
find C:\Test\images -type f -exec c:\xor.exe "{}" "c:\output\{}" 0x01 ;
```
c:\output is needed because xor uses fopen(..., "wb") and reads 8kb of data each time (for using less resources) so the output file can NOT be the same of input
## Post #7
- Username: Rahly
- Rank: VVIP member
- Number of posts: 411
- Joined date: Thu Aug 05, 2004 5:17 pm
- Post datetime: 2009-06-10T11:22:34+00:00
- Post Title: XOR Tool for Multiple files

Need Unix tools for that.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2009-06-17T12:21:05+00:00
- Post Title: XOR Tool for Multiple files

Nice.

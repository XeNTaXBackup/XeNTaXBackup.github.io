## Post #1
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2013-10-24T13:44:07+00:00
- Post Title: Goodbye Deponia - Localisation hints

I'm starting this thread because there are few things changed in the third (and last) episode of the Deponia trilogy - Goodbye Deponia.

Originally the previous versions were using the following VIS3 file structure:

```
DWORD size_packed; // if  size_packed != size_unpacked entry is packed
DWORD size_unpacked;
DWORD type; // 0x00000000 = OGG; 0x00000008 = PNG; 0x00000003 = XML; 0x00000012 = CXML
```


The structure now is the same, BUT this "type" value is now always 0, so all files are considered to be OGGs.
The file holding the texts is always the last one, so you will be interested in 00002172.ogg (it's around five megabytes).

Now, the previous versions were using a XML file (compressed (XML) or compressed in chunks (CXML)), but now there's something called VBIN.
It's actually a pretty simple file, with it's own structure:

```
DWORD unknown;
DWORD size_unpacked;
DWORD size_packed;
byte data[size_packed];
```


So to get the texts out, you need to uncompress the "data" according to the given sizes, using zlib (or equal).
The easiest way to do this is using PHP and since it's designed to dynamically allocate the space needed, open the file, get rid of the header, the unknown DWORD, and the two sizes (in other words, trim the first 16 bytes), so the only thing you will left in there is the data.

Then just extract it like so (CMD):
php -r "echo gzuncompress(file_get_contents('00002172.ogg'))"; > localization.bin
and you will get the localization file.

Unfortunately it's not a XML file anymore (maybe some sort of compiled XML), so you will need to either HEX edit the texts or make some additional parsing tool for easier editing.

To sum it up:
1. Use Unpakke to get the files out of data.vis
2. Do the VBIN decompression kung-fu
3. Edit the texts
4. Do step 3 in reverse (compress, add the header, the unknown dword and the two updated sizes according to your changes)
5. use Unpakke to pack back the data.vis

I've probably didn't explain that very good, but I think that will be useful information if someone have the time (and the skills) to make some sort of tool.
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-10-30T20:57:07+00:00
- Post Title: Goodbye Deponia - Localisation hints

pm me a sample and we'll see what sort of format the xml is in
## Post #3
- Username: warwar
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Jun 04, 2011 3:36 pm
- Post datetime: 2013-11-04T08:13:25+00:00
- Post Title: Goodbye Deponia - Localisation hints

I use 16HEX and found 00002172.ogg is the only one with VBIN header, so I follow your instructions, remove the first 16 bytes and use php to convert, but then I got error message and failed to get xml. 
And I also got some files with RIFF header in the folder, if i unpack it again, it should be editable png file,  so how can I unpack and convert this kind of files?

There is the  00002172.ogg
[http://pan.baidu.com/s/1oYj7G](http://pan.baidu.com/s/1oYj7G)

And there is the RIFF header file Smaple.
[http://pan.baidu.com/s/1rFZhT](http://pan.baidu.com/s/1rFZhT)

Thanks
## Post #4
- Username: XpoZed
- Rank: veteran
- Number of posts: 144
- Joined date: Sun Oct 25, 2009 12:08 am
- Post datetime: 2013-11-04T08:36:48+00:00
- Post Title: Goodbye Deponia - Localisation hints

> Reply from warwar
>
> I use 16HEX and found 00002172.ogg is the only one with VBIN header, so I follow your instructions, remove the first 16 bytes and use php to convert, but then I got error message and failed to get xml. 
And I also got some files with RIFF header in the folder, if i unpack it again, it should be editable png file,  so how can I unpack and convert this kind of files?

There is the  00002172.ogg
http://pan.baidu.com/s/1oYj7G

And there is the RIFF header file Smaple.
http://pan.baidu.com/s/1rFZhT

Thanks
As i mention before, in this version they are no longer using XML, but something like compiled XML, so it's not ASCII file anymore.
## Post #5
- Username: Starnova
- Rank: n00b
- Number of posts: 18
- Joined date: Mon Feb 10, 2014 10:19 am
- Post datetime: 2014-05-11T23:39:49+00:00
- Post Title: Goodbye Deponia - Localisation hints

Hi, can anyone help me to extract the txt?? I used "VISExt" to unpack de Data.vis, but is there any tool for the ogg!!? The Help will be extremly apreciated...
## Post #6
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-05-19T18:31:29+00:00
- Post Title: Goodbye Deponia - Localisation hints

This quickbms script can export some texts. Use both script on the ogg.
Some subtitles are embedded in the video files, which are mkv files. You can use MKVToolnix to edit them.
[goodbyedeponia_text.7z](https://xentaxbackup.github.io/file/8467_goodbyedeponia_text.7z)
## Post #7
- Username: Beagle Boy
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Jun 29, 2011 11:01 pm
- Post datetime: 2014-11-29T14:12:53+00:00
- Post Title: Goodbye Deponia - Localisation hints

> Reply from swuforce
>
> This quickbms script can export some texts. Use both script on the ogg.
Some subtitles are embedded in the video files, which are mkv files. You can use MKVToolnix to edit them.

First of all, thanks for the script.

But recently, Visionaire updated the game files, and now your script do'nt work properly.
Your tool uncompressed the file normally, but is no longer converting to clean text.

If you can update it, I would be grateful for that.
I added the new file for you analyse in this link:
[https://dl.dropboxusercontent.com/u/957 ... 000c3f.vbi](https://dl.dropboxusercontent.com/u/95790699/00000c3f.vbi)

Thanks in advance.
## Post #8
- Username: swuforce
- Rank: veteran
- Number of posts: 121
- Joined date: Fri Nov 06, 2009 3:46 am
- Post datetime: 2014-12-14T10:02:07+00:00
- Post Title: Goodbye Deponia - Localisation hints

Updated script. Try. Use both on the vbi file.
[goodbyedeponia_text.7z](https://xentaxbackup.github.io/file/8270_goodbyedeponia_text.7z)
## Post #9
- Username: turusele
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Tue Feb 04, 2014 7:14 am
- Post datetime: 2015-09-10T11:03:43+00:00
- Post Title: Goodbye Deponia - Localisation hints

> Reply from Beagle Boy
>
> swuforce wrote:This quickbms script can export some texts. Use both script on the ogg.
Some subtitles are embedded in the video files, which are mkv files. You can use MKVToolnix to edit them.

First of all, thanks for the script.

But recently, Visionaire updated the game files, and now your script do'nt work properly.
Your tool uncompressed the file normally, but is no longer converting to clean text.

If you can update it, I would be grateful for that.
I added the new file for you analyse in this link:
https://dl.dropboxusercontent.com/u/957 ... 000c3f.vbi

Thanks in advance.
how to extract this file?

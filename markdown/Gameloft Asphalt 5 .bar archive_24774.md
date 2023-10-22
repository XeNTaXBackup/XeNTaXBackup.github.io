## Post #1
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-11-23T23:23:31+00:00
- Post Title: Gameloft Asphalt 5 .bar archive

Hello!

I've tried today to extract the audio files from Asphalt 5. In the .iPA file, there are multiple archives of the extensions .pak and .bar. All of their headers are in hex, no relevant chars.

The only program that I initially found to open these files without any modification is Ravioli Game Tools, but it extracts the files without specific file names and the headers are incorrectly distributed to the extracted files, meaning some files may end with another file's header and leave other files with no header.

DKDave, from the XeNTaX Discord server (don't ping on Discord, follow rule #7), spent some time analysing the archive and came up with a BMS script that extracts all files, with the headers properly aligned. No specific file names seem to be mentioned in the archive.

Note: The purpose of this post is to give information regarding an archive type that was previously completely undocumented. By posting the information on this forum, search engines will slowly index this link and will show up in relevant searches.

Replies that further document these archives are more than welcome. Inside are many proprietary formats, so the story is far from over!
[bar.zip](https://xentaxbackup.github.io/file/21269_bar.zip)

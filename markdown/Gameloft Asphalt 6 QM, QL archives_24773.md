## Post #1
- Username: antoniu200
- Rank: n00b
- Number of posts: 17
- Joined date: Sun May 09, 2021 7:40 pm
- Post datetime: 2021-11-23T23:12:41+00:00
- Post Title: Gameloft Asphalt 6 QM, QL archives

Hello!

I've tried today to extract the audio files from Asphalt 6. In the .iPA file, there are multiple archives of the extensions .dat and .bin. Their headers are QL, QM and other Q+letter headers.

The only program that I initially found to open these files without any modification is Ravioli Game Tools, but it extracts the files without specific file names and the headers are incorrectly distributed to the extracted files, meaning some files may end with another file's header and leave other files with no header.

DKDave, from the XeNTaX Discord server (don't ping on Discord, follow rule #7), mentioned that their version of 7-Zip opened one of these files, but only displayed the first file inside the archive. My version of 7-Zip wouldn't open it without changing the header to 
```
PK\x03\x04
```
, but only displayed the first file too.

Following their idea, I tried to extract the archive using QuickBMS with the zip.bms script. Low and behold, all the files were properly extracted, with their proper names and properly aligned headers.

Note: The purpose of this post is to give information regarding an archive type that was previously completely undocumented. By posting the information on this forum, search engines will slowly index this link and will show up in relevant searches.

Replies that further document these archives are more than welcome. Inside are many proprietary formats, so the story is far from over!

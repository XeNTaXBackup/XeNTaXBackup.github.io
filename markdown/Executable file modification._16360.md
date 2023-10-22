## Post #1
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2017-06-05T07:22:21+00:00
- Post Title: Executable file modification.

I'm working on making an editor for an old PC game. I have a import / exporter working, so I can create / modify the custom files to my liking, but I am now realizing a hole in my plan. The executable has a file inside of it with information on each file in the game. I figured since I could open the executable in 7zip I could just edit the file and drop the new file in there. Turns out, when I try to do that I get an "Unsupported Operation" error. I figure I can just have my editor modify the executable itself and replace the old data.

I have a few questions:
a) What potential problems could I come into doing this? I don't have any experience meddling with executables before.
b) Are there any better ways / tools of doing this?
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 719
- Joined date: Tue Jul 06, 2010 3:55 am
- Post datetime: 2017-06-05T16:36:20+00:00
- Post Title: Executable file modification.

You have to be more clear.

The data that is contained within the exe contains what exactly? Offsets into the main archive file hardcoded? checksums?
## Post #3
- Username: Kneesnap
- Rank: beginner
- Number of posts: 24
- Joined date: Thu Apr 06, 2017 4:01 am
- Post datetime: 2017-06-05T18:07:49+00:00
- Post Title: Executable file modification.

> Reply from Gh0stBlade
>
> You have to be more clear.

The data that is contained within the exe contains what exactly? Offsets into the main archive file hardcoded? checksums?

The file "104" in the exe (file in question) is structured like this:

For each file in the game archive,

int - nameOffset (Points below, to the name of this file.)
int - fileCategory (Unsure what the purpose of this is, but it appears to categorize file types.)
int - fileType (Determines what type of file this is)
int - offset (The offset in the main game archive where the file is found.)
int - zero
int - zero
int - Raw Size
int - Uncompressed Size (If applicable)

Then after all of this it has the filename of each file in the archive.

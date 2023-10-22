## Post #1
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2015-12-07T03:18:22+00:00
- Post Title: PS3 .at3 files

So recently, I've found a solution for those who had problems playing PS3 .at3 files at foobar2000(thanks to a tip I've got from someone at hcs64). That is because the PS3 .at3 file uses an different structure(at3plus), while the PSP .at3 file can be played back without any problems. Thus, all you will need is a hex editor of your choice - after that you're ready to go.
1. Open an hex-editor of your choice(I'm using 010 Editor) then open the PS3 .at3 file in it.
2. As you opened the PS3 .at3 file, you will realize there are extra bytes before the "RIFF".
3. Remove those bytes before the "RIFF" part. Before you can proceed, make another copy of the same file. This is important, since you will need it to compare both files.
4. After that, save that PS3 .at3 file you've just edited on your hex editor and close the program.
5. Try and test that modified file on foobar2000 or some at3 player. See if it works.

If you did play it, congratulations! Now you should be able to delete that copy you've just made out of the original file and you're good to go.

## Post #1
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-12-13T00:52:48+00:00
- Post Title: This War of Mine (language binary file)

Hi all,
I've written a tool to strip all languages except english in this game.
It is good when repacking to reduce size.
It also includes bin to text converter. I also included template of the file. Therefore,
some can easily code repacker.
I used "/n" for line breaks in a sentence.

I hope it would be usefull for you.

Edit: Tool requires 010Editor
[war_of_mine.7z](https://xentaxbackup.github.io/file/8267_war_of_mine.7z)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2014-12-13T03:15:16+00:00
- Post Title: This War of Mine (language binary file)

awesome work   

those widestrings look like the endian swaps half way though the format! it threw me off when i was investigating this format
## Post #3
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-13T15:11:15+00:00
- Post Title: This War of Mine (language binary file)

Please,if i want to translate into Asian Languages,need to add fonts？
& problem：
*ERROR Line 13: Template passed end of file at variable 'totalSize'. 
Sorry，I am a novice.
## Post #4
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-12-13T21:14:35+00:00
- Post Title: This War of Mine (language binary file)

> Reply from geraldhu
>
> Please,if i want to translate into Asian Languages,need to add fonts？
& problem：
*ERROR Line 13: Template passed end of file at variable 'totalSize'. 
Sorry，I am a novice.
make sure name of bin file is "l01n.bin"
and first run strip_lng.cmd then extract_lng.cmd.
## Post #5
- Username: geraldhu
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Dec 03, 2014 1:06 am
- Post datetime: 2014-12-14T06:22:46+00:00
- Post Title: This War of Mine (language binary file)

Thanks,merlinsvk's script is output "l10n.bin".
## Post #6
- Username: Taner038
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Sat Aug 23, 2014 1:14 am
- Post datetime: 2014-12-14T16:55:41+00:00
- Post Title: This War of Mine (language binary file)

> Reply from rengareng
>
> Hi all,
I've written a tool to strip all languages except english in this game.
It is good when repacking to reduce size.
It also includes bin to text converter. I also included template of the file. Therefore,
some can easily code repacker.
I used "/n" for line breaks in a sentence.

I hope it would be usefull for you.

Edit: Tool requires 010Editor

Error: A problem occurred writing the file 'I01.bin_stripped' to disk. The file maybe read-only or the disk may be full. (104) 

what should I do
## Post #7
- Username: rengareng
- Rank: veteran
- Number of posts: 131
- Joined date: Fri Feb 18, 2011 5:23 pm
- Post datetime: 2014-12-15T08:42:27+00:00
- Post Title: This War of Mine (language binary file)

> Reply from Taner038
>
> rengareng wrote:Hi all,
I've written a tool to strip all languages except english in this game.
It is good when repacking to reduce size.
It also includes bin to text converter. I also included template of the file. Therefore,
some can easily code repacker.
I used "/n" for line breaks in a sentence.

I hope it would be usefull for you.

Edit: Tool requires 010Editor

Error: A problem occurred writing the file 'I01.bin_stripped' to disk. The file maybe read-only or the disk may be full. (104) 

what should I do

Try running scripts in administrator mode.

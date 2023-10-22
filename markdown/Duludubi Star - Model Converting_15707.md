## Post #1
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2017-01-10T01:28:35+00:00
- Post Title: Duludubi Star - Model Converting?

[Before you ask, Duludubi Star was basically this Mario Galaxy knockoff made by Chinese theme park company Fantawild. It's been taken down from their site but a preserved download link still exist.](http://s4.zetaboards.com/PGC_Forums/topic/9478903/1/)

I got the guys on Zenhax to help with a script with decompiling the main resource file. Common file formats are used in the game like .DDS and .TGA, However as I tried to obtain the raw models - The name alone (skn) made me think programs for converting League of Legends models was the way to go but unfortunately this is actually different from those types of files. Just recently I decided to compile the binary .DLL's for the game as well as the main game's .exe without the resource package as that's what the game lives off of practically so this isn't anywhere near as bloated. I hex edited the game and found 1 result for .skn files but lacking actual coding knowledge I don't know what to do from there. Just remember the header seems to be different compared to the usual .skn format that games like LoL use. 

Binaries : [https://www.mediafire.com/?t3eae45m5plp005](https://www.mediafire.com/?t3eae45m5plp005)
Models I tried to convert : [http://www.mediafire.com/file/c2vrd834f ... ludubi.zip](http://www.mediafire.com/file/c2vrd834f90igcv/duludubi.zip)

Would be REALLY greatful if you could help me out here. I've tried NinjaRipper to rip the characters to no avail and getting very confusing bits and pieces of tiny polygons that honestly it just ends up looking like a jumbled mess. The HyRenderUnit and the main game .exe seem to be the only ones that mention the graphical formats when I looked in it through HxD. I'd really like to get my hands on the model of the main character, Duludubi more than anything right now.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-10T20:30:25+00:00
- Post Title: Duludubi Star - Model Converting?

guess using hex2obj (view link in my sig) will give you the fastest results.
I didn't bother searching for face indices though, used FIs autocreating instead.

So you'll need a version that's capable of that [viewtopic.php?f=29&t=10894&p=119417&hil ... ed#p119417](http://forum.xentax.com/viewtopic.php?f=29&t=10894&p=119417&hilit=+autocreated#p119417).



12-skn.JPG (96.28 KiB) Viewed 141 times
## Post #3
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2017-01-11T05:24:36+00:00
- Post Title: Duludubi Star - Model Converting?

Thank you very much, good sir. I do have to ask though, what's with making the UV maps .obj as well? And if so do they stay with the model or will I have to somehow load the UV model file into it? Sorry if I sound dumb. ^^;
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-01-11T18:35:58+00:00
- Post Title: Duludubi Star - Model Converting?

use File / saveAs mesh
to save the obj file with uvs included (so far you got a correct uv map displayed using the uvs button).
## Post #5
- Username: Mario123311
- Rank: beginner
- Number of posts: 28
- Joined date: Tue Jan 10, 2017 9:20 am
- Post datetime: 2017-04-04T16:59:07+00:00
- Post Title: Duludubi Star - Model Converting?

[https://www.mediafire.com/?4v6rc161nab0ana](https://www.mediafire.com/?4v6rc161nab0ana)

Really hate to be asking for help again but I'm having a bit of trouble. I have the start address but I have no idea how to get the "count" necessarily. (Next to the start address)
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2017-04-04T19:04:46+00:00
- Post Title: Duludubi Star - Model Converting?

for 12.skn it works like this:
from the vertex start address search for FFFFFFFF

After thousands of finds you'll experience a gap:



12_skn_gap.JPG (9.12 KiB) Viewed 77 times


Subtract the start address from the gap address; divide the result by the stride (48) and your done.

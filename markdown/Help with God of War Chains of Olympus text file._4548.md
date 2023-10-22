## Post #1
- Username: caws
- Rank: veteran
- Number of posts: 120
- Joined date: Sun Mar 02, 2008 2:57 am
- Post datetime: 2010-06-02T22:53:54+00:00
- Post Title: Help with God of War Chains of Olympus text file.

Well, i'm creating a editor (to translate the texts) for this kind of files, the problem is that i could't figure out the whole structure.

Here's what i've discovered so far (researching on the english file).

This is for the Pack file. (dx_persinveng.bin)

0x0c : Size of the file minus 4
0x44 : Pointer for the beginning of the first file.
0x48 : Size of the file
0x54 : Pointer for the beginning of the second file.
0x58 : Size of the second file.

After create a unpacker for the kind of file above, it extracts two files, one with unkown data for me
and the other with the texts, this is what i figured out so far about theses text files:

This is for the extractes file from Pack file. (dx_persinveng.bin0)

0x00 : Size of the file minus 4
0x24 : Unknown 
(I don't know what many values means, and a big part of the file is equal in every language. not the texts.)
0xdc : I find out that to point to the text this is the position where the text block begins (at 0x01e8) plus the value readead at this position.

I've attached both files from the english language.
(If someone needs, i can upload the same files but in spanish..)

Please help.

PS: Sorry for my weird english, i'm from Brazil...
[Files.rar](https://xentaxbackup.github.io/file/3100_Files.rar)
## Post #2
- Username: timartinelli
- Rank: mega-veteran
- Number of posts: 179
- Joined date: Thu Sep 30, 2010 4:52 pm
- Post datetime: 2012-11-27T14:34:58+00:00
- Post Title: Help with God of War Chains of Olympus text file.

Can someone help with the ps3 version of the files? I can upar files.

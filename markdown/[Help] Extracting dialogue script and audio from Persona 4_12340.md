## Post #1
- Username: Kaoru
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 07, 2014 6:47 am
- Post datetime: 2014-12-07T00:18:35+00:00
- Post Title: [Help] Extracting dialogue script and audio from Persona 4

So, I've been messing with the ISO for Persona 4 the last few days, trying to extract all the data I need. After hours of Googling, searching this forum and coding in Python, I've made very little progress, so I'm hoping someone here with more experience will be able to help me since this is my first attempt at ripping game assets.

What I want to do is extract all the dialogue scripts from both the Japanese and English versions of the game, as well as audio clips that match the script from the Japanese version. The end goal is to generate an [Anki](http://ankisrs.net/) deck for studying Japanese using these game assets.

Here's what I managed on my own so far:
- Extract the .cvm files, most notably DATA.cvm which contains most of the important stuff
- Found what seem like script files in DATA.cvm/EVENTS. They have file extensions .pm1, .pm2 and .pm3
- Found seemingly appropriate sound files by extracting .adx files from DATA.cvm/SOUNDS/COMMU.afs using ADX Encode Helper, and then converting them to .mp3

My biggest problem so far is that I don't know how the script files are encoded. I've had some limited success with parsing the English scripts by reading them byte by byte and trying to map bytes to ASCII characters, keeping the ones that match and discarding the rest. This produces files that are somewhat readable, but there's also a lot of gibberish(ie. non-dialogue) text left over. With some additional parsing I've managed to clean out some of it, but the bigger problem here is that this method won't work for the Japanese script at all, since Japanese characters don't map to ASCII. Knowing how the files are encoded and finding an easier way to read them would save me a lot of pain.

The second problem is the audio files. While I managed to extract and convert them all to a friendlier format, I have no idea how to map them to the matching lines of dialogue. The .pm* files don't seem to reference them, unless I'm missing something obvious.

Ideally, I'd also like to know:
- The in-game date for each line of dialogue
- The character using the line
- The specific character image associated with that line. These seem to be located in DATA.cvm/BUSTUP. I already managed to get the images in .png format, but I have the same problem I have with the audio files - I don't know how to map them to the matching lines of dialogue

I think a lot of my problems would be solved or at least way easier to deal with if I only knew how to properly decode the script files to something readable... I know I have a lot of work to do here to achieve what I want and I'm not asking to be spoon-fed, but since there's so little information about these file formats online I hope someone will be able to point me in the right direction. Any help is appreciated.

Sample script files:
[DATA.cvm/EVENTS/E100/E105_001.PM1 - Japanese](https://www.mediafire.com/?t6dxy3qwfcady8b)
[DATA.cvm/EVENTS/E100/E105_001.PM1 - English](https://www.mediafire.com/?ycuuk4pu4oodmvg)
[E105_001_PM1.txt - Parsed English](https://www.mediafire.com/?qjo07kgwn50kj6l)
## Post #2
- Username: RikuKH3
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 26, 2012 7:37 am
- Post datetime: 2014-12-08T18:02:00+00:00
- Post Title: [Help] Extracting dialogue script and audio from Persona 4

P4 Script Converter
[http://www.vector.co.jp/soft/dl/winnt/g ... 70648.html](http://www.vector.co.jp/soft/dl/winnt/game/se470648.html)
## Post #3
- Username: Kaoru
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Dec 07, 2014 6:47 am
- Post datetime: 2014-12-09T03:00:56+00:00
- Post Title: [Help] Extracting dialogue script and audio from Persona 4

Thank you, that was a huge help. 

I managed to extract all the data I need, I just have one last problem - the image references. The bustup image references that tool generates seem incomplete; they export as something like [BUSTUP(b2_1_x)], but how do I get the value of x? In this case, b2_1_ is the prefix for Yosuke's portraits, but x can be 1-4.

How do I know which one it is?

EDIT: Never mind, the last digit isn't that important for my needs, it seems to refer to different outfits. I worked around it by setting up a list of outfits for each character in the order I prefer them, and picking the first one that exists.

Thanks again for the help, who knows how much longer it would have took me on my own. Now that I'm done I'd like to share to share the results to give something back to the community and hopefully help someone in the future.

I dumped all the data to a sqlite table which is easier to work with than the raw files or .txt files generated by P4 Script Converter, and I fixed some common problems along the way(untranslated dialogue that was same in both the English and Japanese version, replacing placeholders like [名前]/[名字]/[主人公] with the protagonist's name, etc.). I also included all the needed images in .png format and all the audio in .mp3 format.

Get it [HERE](https://www.mediafire.com/?fi36jlahp811br8) (586.94 MB .zip file)

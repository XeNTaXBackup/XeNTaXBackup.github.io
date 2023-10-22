## Post #1
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-23T21:00:33+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

Hello! Good news from the Chrono Compendium, for those of you who have been following along. Thanks to Gemini and Ramsus at the forums over there, we've been able to decompress some files in which character models are *probably* stored. 

I say *probably* because Gemini said at one point there were only non-functioning copies of the models in the archives, yet we've got textures among these files that would be applied to the models in-game. 

I'm attaching three character file folders for the perusal of interested parties here. All the files in each folder are uncompressed to my knowledge. The "5" files and "4" files are definitely textures. "4" seems to be in the .TIM format and "5" is in an unknown format that can be viewed in graphics ripping programs like Tile Molester.

I'm extremely suspicious of the "3" files, which might contain model data. They certainly seem large enough in file size, but right now we're not sure how to view them, or even how to tell whether they are, indeed, models.

Anyone care to take a look at these?
[MainCharFiles.rar.rar](https://xentaxbackup.github.io/file/1384_MainCharFiles.rar.rar)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-24T02:19:32+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

At this point after looking at it some it would make sense that they would use their own kind of format for a 3D model.

It seems your suspicions are likely correct. Looking at some example TMDs then comparing them (in HEX) it does now seem you were right about them being models. The sad part is that is all I can say for now, I'm not good with 3D. >_<
## Post #3
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-24T19:11:21+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

Thanks for checking those out, Darkfox! Some files in Chrono Cross are LZSS compressed, I recently found out. I'm not sure whether these are still compressed or not, though. 

I'll do the TMD comparison with these files myself, now that you mention it. Is there anything that really stands out, like, do all model files have certain patterns when viewed in hex from your experience?
## Post #4
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-24T23:05:09+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

I've never worked much with 3D data. Really basic stuff on my part. I wouldn't put a whole lot of faith in my deductions here but I have looked it over and noted some similarities. I think this is a place for a more skilled person in the 3D field to figure out it's format.
## Post #5
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-25T16:02:28+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

We've also found what may be overworld models for the Chrono Cross characters, and I'm posting them here in case anyone wants to check 'em out.

Based on recent discussion at the Chrono Compendium, I believe everything I've posted here may be compressed after all.
[OMCM Examples.zip](https://xentaxbackup.github.io/file/1385_OMCM Examples.zip)
## Post #6
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-25T16:28:34+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

Everything? Would not the text be compressed as well. Of course not many games I've seen compress their text, and some compress their textures. But it is possible.
## Post #7
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-10-25T17:45:00+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

Ah, good point on the text and textures. Yes, that should be a qualified "everything." I actually don't think any of the textures are compressed in Chrono Cross (although some are in non-TIM formats that aren't easily viewed), and I know there's at least some text that isn't compressed, such as the character descriptions that go along with the "3", "4", "5", etc. files in the first archive I've posted above. 

I'm suspicious that the model data may be compressed, however. I started a thread in the compression forum, so I'll see if anyone can give me a confirmation or prove me wrong. I still have to do a .TMD comparison with these as well as take a look at the LZSS compression documentation on Qhimm's wiki to see if I can find clues as to whether this stuff is compressed.
## Post #8
- Username: FaustWolf
- Rank: advanced
- Number of posts: 41
- Joined date: Sat Aug 18, 2007 7:48 am
- Post datetime: 2007-11-06T19:12:06+00:00
- Post Title: Chrono Cross Models; Unknown Filetypes

Now for a report on more potential battle model / weapon model data.

[http://www.chronocompendium.com/Forums/ ... ttach=1950](http://www.chronocompendium.com/Forums/index.php?action=dlattach;topic=4770.0;attach=1950)

Firstly, the link is a zip containing a chunk of data from the CD image that I have named "ModelMine1." It's just raw hex data, and its beginning corresponds to a fresh sector (2048 bytes/sector as always) in the CD image. The data fall in this order: A header; Serge's battle model texture; Serge's eyeball texture; unknown data; Serge's first weapon model texture; unknown data; etc. Also inside the zip is a copy of my datamap for "ModelMine1," which I reproduce below. The chunk seems to be 11 sectors long exactly, if that means anything.

Also included in the zip are Serge's battle model texture, eyeball texture, and the seven weapon texture TIMs that occur within the ModelMine.

DATAMAP: All offsets given in hexadecimal notation. 

00000000 ~ 0000000F: 16 byte header 
00000010 ~ 0000823B: Serge Battle Texture
0000823C ~ 00009467: Serge Eyeball Blink Texture 
00009468 ~ 000097FF: 00 Buffer Bytes 
00009800 ~ 00014847: Unknown Data (Battle Model?)
00014848 ~ 00015DC7: Serge Weapon Texture 1
00015DC8 ~ 00016BE7: Unknown Data (Weapon Model?)
00016BE8 ~ 00018167: Serge Weapon Texture 2
00018168 ~ 00018C5F: Unknown Data (Weapon Model?)
00018C60 ~ 0001A1DF: Serge Weapon Texture 3
0001A1E0 ~ 0001AF0F: Unknown Data (Weapon Model?)
0001AF10 ~ 0001C48F: Serge Weapon Texture 4
0001C490 ~ 0001D2EF: Unkonown Data (Weapon Model?)
0001D2F0 ~ 0001E86F: Serge Weapon Texture 5
0001E870 ~ 0001F687: Unkknown Data (Weapon Model?)
0001F688 ~ 00020C07: Serge Weapon Texture 6
00020C08 ~ 00021897: Unknown Data (Weapon Model?)
00021898 ~ 00022E17: Serge Weapon Texture 7
00022E18 ~ 00023FFF: Unknown Data (Weapon Model?)

After this begins my ModelMine2 file, which contains Kid's suspected battle model and weapon model data. I'll post that later for comparison if anyone's interested.

SUSPECTED MODEL FILE INFO: The offsets and file lengths may actually be one byte too "short" depending on whether I'm interpreting the hex code correctly. For example, the First "Weapon Model" listed below is described as 3615 bytes long. If it makes more sense, feel free to interpret the file size as 3616 bytes.

First "Model" : 45127 bytes long. Header begins "06 00 00 00 20 00 00 00" 
First "Weapon Model" : 3615 bytes long. Header begins "01 00 00 80 48 00 5E 00"
Second "Weapon Model" : 2807 bytes long. Header begins "01 00 00 80 39 00 46 00"
Third "Weapon Model" : 3375 bytes long. Header begins "01 00 00 80 43 00 58 00"

The weapon "models" are consistent in their first 8 bytes, which may constitute a model file header; the first 8 bytes for the weapon "models" read:  01 00 00 80 xx 00 xx 00 (where "xx" represents a byte position that varies in value among the "models")

My notes on the data were hastily scribed, so if anyone wants clarification on any point, please ask. Once again, the "ModelMine" for Serge's (suspected) battle and weapon models and all the associated textures are in the attached zip if anyone would like to investigate.

BREAKING NEWS: We can now safely assume that the "Unknown Data" above represents 3D model data. Anyone have any ideas on how to decipher the format?

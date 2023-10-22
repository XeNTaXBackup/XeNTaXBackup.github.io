## Post #1
- Username: UnReAlMaCk!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-25T21:41:13+00:00
- Post Title: Forza .bin Files

Lots of people are modding forza textures with a tool, but they wont tell anyone where to find it or give anyone it, so i was thinking, why not MulitEx, it supports soooo much!   

so i have the file, plz help support this!

[](http://www.uploadhut.com/upload/128703.bin)
## Post #2
- Username: UnReAlMaCk!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-25T21:42:50+00:00
- Post Title: Forza .bin Files

sry, heres the link 

[http://uploadhut.com/view.php/128703.bin](http://uploadhut.com/view.php/128703.bin)

its normally called dodgechallenger.bin, but upload hut changes the name! lol
## Post #3
- Username: mrjkwik
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Wed Apr 06, 2005 11:55 am
- Post datetime: 2005-05-25T23:32:30+00:00
- Post Title: Forza .bin Files

could you also update any status on the files i pm'd you guys in this, or the other forza thread.  thank you.
## Post #4
- Username: UnReAlMaCk!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T01:01:03+00:00
- Post Title: Forza .bin Files

hello? mr. mouse? anyone can you support this asap? i wanna prove to these guys that not ony they can mod forza
## Post #5
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T01:09:19+00:00
- Post Title: Forza .bin Files

> Reply from UnReAlMaCk!
>
> hello? mr. mouse? anyone can you support this asap? i wanna prove to these guys that not ony they can mod forza

haha you are a funny one.. our texture editing has nothing to do with the bin or cab files.. so keep looking in the wrong places.. and one year you might find it
## Post #6
- Username: ForzaCustoms
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T01:11:18+00:00
- Post Title: Forza .bin Files

and look at you.. running to these people to do the work for you.. we did everything on our own.. including in house tools.. so your not exactly proving anybody wrong.. and you have the wrong files still
## Post #7
- Username: FoRzA SuX!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T02:23:14+00:00
- Post Title: Forza .bin Files

dude, what is you point exactly? we have no app to do this, except multiEx, so until its released or something, were gonna have multiEx support it!
## Post #8
- Username: UnReAlMaCk!
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T02:29:02+00:00
- Post Title: Forza .bin Files

wtf? come on, these ppl did such a good job making this program, y NOT use it?

you seriously want me to make my own program, stop talking before you emaress yourself, you didnt know about multiEx, so you HAD to make your own

multiEx is a DAMN good program, and until you tell us how to mod forza, were just gonna have to do it ourself.
## Post #9
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T02:38:02+00:00
- Post Title: Forza .bin Files

i think their correctly

.texture files should be a kind of .xpr file format what is include the textures saved on the cars. i'm not sure about this

but if mr.mouse can take a look on .texture files what we can found on savegame, for now i think we can edit the textures of car with multiex.

inside the .textures, we will found a .dds or .bmp formats or any other image format? maybe.. i really dunno because people who mod it first don't release ANY kind of usefull information.

so please, stop with this stupid kind of challenge for what is mod the forza better or first, its really ridiculous. the community lost with urs.
## Post #10
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T02:38:34+00:00
- Post Title: Forza .bin Files

> Reply from UnReAlMaCk!
>
> wtf? come on, these ppl did such a good job making this program, y NOT use it?

you seriously want me to make my own program, stop talking before you emaress yourself, you didnt know about multiEx, so you HAD to make your own

multiEx is a DAMN good program, and until you tell us how to mod forza, were just gonna have to do it ourself.

umm no.. we made our own programs because THEY WORK

unlike multiex.. it cant reinject a file into a forza cab properly.. and it gives some corrupt file error on every file i click on.. 

and embarrass my self? son we have custom paintjobs.. you dont.. 

us 1.. you 0
## Post #11
- Username: Guest
- Rank: N/A
- Number of posts: N/A
- Joined date: N/A
- Post datetime: 2005-05-26T02:39:01+00:00
- Post Title: Forza .bin Files

did i mention that multiex also costs money.. and our programs cost 20 minutes of time
## Post #12
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T03:34:07+00:00
- Post Title: Forza .bin Files

This is what I have so far on the file formats you sent us...

```
| Forza MotorSport (XBox) *.bin |
+-------------------------------+

// The entire archive is ZLib compressed - so you need to decompress it first.
// After decompression, it has the following format
// For some reason, the structure is not fixed like the format shown here.
// The first few files are jagged, but then the remaining files follow the
// consistent structure in the "//for each file" section.

4 - Version (1)
4 - First File Offset
4 - Length Of File Data? (not quite)
4 - Number Of Files
44 - null

// for each file
  44 - Filename (null)
  4 - 
  8 - 
  2 - Unknown (1)
  2 - Unknown (4)
  4 - Offset [+FirstFileOffset]
  4 - null
  4 - Unknown (73513)
  4 - 
  64 - null Padding to the next filename
  
X - File Data


+-------------------------------+
| Forza MotorSport (XBox) *.cab |
+-------------------------------+

// Uses ZLib compression for the files

4 - Header? (170 170 192 192)
4 - Unknown (15)
4 - Number Of Files
4 - Version (1)
4 - Archive Size
4 - Decompressed Archive Size?
4 - Filename Directory Length
4 - Filename Directory Length
16 - null
2 - Unknown (1)
256 - Archive Directory (null)

// for each file
  4 - File Offset
  4 - Compressed File Size
  4 - Decompressed File Size
  4 - Unknown
  4 - null
  4 - Unknown
  
// for each file
  X - Filename
  1 - null Filename Terminator
  
X - File Data


+-------------------------------+
| Forza MotorSport (XBox) *.ca2 |
+-------------------------------+

// The entire archive is ZLib compressed - so you need to decompress it first.
// After decompression, it has the same format as the *.cab files from this game.
// Each file is still compressed using ZLib aswell!

4 - Header? (170 170 192 192)
4 - Unknown (15)
4 - Number Of Files
4 - Version (1)
4 - Archive Size
4 - Decompressed Archive Size?
4 - Filename Directory Length
4 - Filename Directory Length
16 - null
2 - Unknown (1)
256 - Archive Directory (null)

// for each file
  4 - File Offset
  4 - Compressed File Size
  4 - Decompressed File Size
  4 - Unknown
  4 - null
  4 - Unknown
  
// for each file
  X - Filename
  1 - null Filename Terminator
  
X - File Data
```


I will work on a plugin for the *.cab and *.ca2 files, but I am still alittle stuck on the structure of the *.bin files.

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)

Mr Mouse - I will put these specs on the wiki later - I am just alittle too busy at the moment,
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-05-26T07:57:31+00:00
- Post Title: Forza .bin Files

Well, "Guest"/"ForzaCustoms", would you be so kind to stop trolling? 

In general, I do not remember asking for this bickering, people. 

If you have some feud to fight, please do that somewhere else. This is not the place. 

@Watto: That's okay, I have some formats to put in there still as well.
## Post #14
- Username: friendsofwatto
- Rank: VVIP member
- Number of posts: 532
- Joined date: Wed Jun 30, 2004 10:01 pm
- Post datetime: 2005-05-26T13:30:57+00:00
- Post Title: Forza .bin Files

OK well because of a bug in the Basic Version, I cannot add Game Extractor (Basic) support for the *.ca2 archives, but if you have the full version of Game Extractor then you can use the attached plugin. Unzip into your plugins/ directory (make the directory if it doesn't already exist). The attachment also does the *.cab archives for Full Version users.

No support for the *.bin files yet - there are still dome things which don't seem right 

WATTO
[watto@watto.org](mailto:watto@watto.org)
[http://www.watto.org](http://www.watto.org)
[Plugin_CAB.zip](https://xentaxbackup.github.io/file/258_Plugin_CAB.zip)
## Post #15
- Username: UnReAlMaCk
- Rank: VIP member
- Number of posts: 15
- Joined date: Thu May 05, 2005 5:46 am
- Post datetime: 2005-05-27T00:04:43+00:00
- Post Title: Forza .bin Files

game extracter is way to laggy, and uses "java"   

multiEx is already registered and all that, so ill just wait, i hate this game, and hated it more ever since these guys think their big and bad because they can paint a car in some crappy game, selfish pigs  

as for csx modding your program works perfectly
## Post #16
- Username: chesty
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun May 01, 2005 5:59 am
- Post datetime: 2005-05-28T23:50:20+00:00
- Post Title: 

Any news on this yet wanting to update my paintjobs
## Post #17
- Username: atarashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 04, 2005 9:38 pm
- Post datetime: 2005-06-07T18:10:56+00:00
- Post Title: 

Hi

I have the registered version and when I try to open a cab file to extract the ini files it contains, I get an error telling me "file info error" or something like this. I can extract some ini files but not all of them. I can not rebuild the cab files even when I extract successfuly the ini files. Can anyone check if it works?

regards
## Post #18
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-16T14:23:27+00:00
- Post Title: 

Ah I see, you posted here. Do you have an example of that CAB file?
## Post #19
- Username: atarashi
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Jun 04, 2005 9:38 pm
- Post datetime: 2005-08-20T15:51:44+00:00
- Post Title: 

Is there an email address I can use to send the cab file?
## Post #20
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2005-08-20T16:10:28+00:00
- Post Title: 

Yes, see [http://multiex.xentax.com](http://multiex.xentax.com)

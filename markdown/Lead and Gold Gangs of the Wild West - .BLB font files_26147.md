## Post #1
- Username: rayanm123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2022 10:35 am
- Post datetime: 2023-01-05T20:06:29+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

Hi 

There's this game called "Lead and gold gangs of the wild west" that I would like to edit it texts or translate it to Arabic .

The game runs at Diesel game engine i think it should be similar to bionic commando (payday too ) but payday seems different in almost everything.

please just give me any information you have even if it's not related to the game 

thanks in advance
## Post #2
- Username: rayanm123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2022 10:35 am
- Post datetime: 2023-02-02T13:25:34+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

Hi ,

I have a game called Lead and Gold gangs of the wild west.

and after opening the game files I noticed that the game uses fonts with .BLB extension  .

so is there anyway to edit them and add letters from another language for example Arabic , Persian , Polish etc...

the example files.
[https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1BoXNBj7yYJHsS6juHdQsiZ4NQr1Yyew_?usp=sharing)
## Post #3
- Username: rayanm123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2022 10:35 am
- Post datetime: 2023-06-30T16:00:57+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

Hi, 
BLB files are font files for this game and it seems for bionic commando 2009 as well anyway I tested them in the game by changing the hex to zeros at some places and some characters were effected thus I'm 100% sure that these are indeed the font files. 

The help I really need is getting the coordinates and replace them with my own so I can implement my own language. ikskoks.pl helped me to analyze the file format but I still  need more help to parse the file itself. 

I just don't understand what entry means nor how to work with bytes individually 

Here is the file format:
// BLB file format

// header
12 bytes (char) - signature + padding    // 73 D8 BD E5 00 00 00....
4 bytes (uint32) - font size
4 bytes (uint32) - number of characters in font
4 bytes (uint32) - header size (80)
4 bytes (uint32) - number of characters in font (repeated)
4 bytes (uint32) - characters list offset
4 bytes (uint32) - number of characters in font (repeated)
28 bytes - unknown
4 bytes (uint32) - DDS height
4 bytes (uint32) - DDS width
4 bytes (uint32) - unknown  // 45
4 bytes (uint32) - unknown  // 60


// coordinates
number_of_chars_in_DDS *
{
  10 bytes - entry
}

// characters list
number_of_ascii_chars *
{
   4 bytes (uint32) - character code
}


x bytes (char) - font name

Link to files and DDS : [https://drive.google.com/drive/folders/ ... sp=sharing](https://drive.google.com/drive/folders/1BoXNBj7yYJHsS6juHdQsiZ4NQr1Yyew_?usp=sharing)

Thanks ikskoks.pl for the format outline
## Post #4
- Username: rayanm123
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-07-01T08:41:54+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

I've checked your samples once again and I've updated the file format.
Now it is shared on the wiki [http://wiki.xentax.com/index.php/Lead_and_Gold_BLB](http://wiki.xentax.com/index.php/Lead_and_Gold_BLB)

So basically you have everything you want in coordinates table in which each
coordinate entry is 10 bytes in size. According to the wiki first byte of each entry is null,
then there is 1 unknown byte, then you have height and width, then 2 unknown bytes, then X coordinate and Y coordinate.
Having this info, you can edit coordinates as you wish.


As an example I will show you how to edit coordinates for "#" character in gmfont_eng_header.blb file.
Coordinates table begins right after header - it is offset 80.
Entry for "#" character is fourth entry in this table - it is offset 110, you should go there.
So you have 10 bytes for this entry, according to file format you can read this data:
char height - 66
char width - 51
char X coordinate - 694
char Y coordinate - 632

Now, if you open gmfont_eng_header.dds file in GIMP and choose selection tool and input this data there,
you will find out that it all matches your "#" character on DDS:
[https://i.imgur.com/VbyqeJP.png](https://i.imgur.com/VbyqeJP.png)

And now the only thing you should do is to edit those hex values and save BLB file to change your coordinates.
## Post #5
- Username: rayanm123
- Rank: ultra-n00b
- Number of posts: 6
- Joined date: Mon Nov 14, 2022 10:35 am
- Post datetime: 2023-09-09T19:47:24+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

Thanks for the response, for some reason xentax didn't give me a notification for your respond. Anyway, you're right! the coordinates are correct. the weird thing is that when I changed them to my liking. they didn't show or they showed in a weird way. 

Here I changed the char 'Y' coordinates to indicate for a letter I drew in the DDS but it doesn't show up something is maybe wrong, I tried to change the coordinates for the letter "P" with the letter "K" to test things up. Though K is shown It's not exactly how I wanted it to be. any reason? 

:: 
here the selected box is the coordinates I entered instead of the letter P, and blue is what was shown in the game? I tried to replace the height and width but no results unfortunately.

Thank you for looking it up
## Post #6
- Username: rayanm123
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2023-09-09T22:33:20+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

Well, you have to do more experiments with hex editing and try to adjust it to match expected result. 
That's the only advice I can give you after my research.
## Post #7
- Username: eprilx
- Rank: n00b
- Number of posts: 17
- Joined date: Tue Dec 08, 2020 12:05 pm
- Post datetime: 2023-09-10T07:32:34+00:00
- Post Title: Lead and Gold Gangs of the Wild West - .BLB font files

10 byte entry based on gmfont_eng_header.blb:
1 - Null
2 - Xadvance
3 - Width -> Height
4 - Height -> Width
5 int8 - Xoffset
6 int8 - Yoffset
7,8 - X
9,10 - Y

There are also about 5 tables:
1 - Char mapping (10 bytes each)
2 - Char id (4 bytes each)
3 - Id (4 bytes each)
4 - Kerning first, second (8 bytes each)
5 - Should be kerning amount but the data type is unknown (4 bytes each) (40 6A 58 80)

You can use BMFont to see what these values ​​mean. 
[https://www.angelcode.com/products/bmfo ... ormat.html](https://www.angelcode.com/products/bmfont/doc/file_format.html)

Update: width and height should swap in my old reply.

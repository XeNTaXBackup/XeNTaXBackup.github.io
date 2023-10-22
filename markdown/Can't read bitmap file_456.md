## Post #1
- Username: wolfmah
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 13, 2003 10:46 pm
- Post datetime: 2003-10-13T14:52:29+00:00
- Post Title: Can't read bitmap file

I have open the archive file of the Heroes of Might and Magic 1 (HEROES.AGG) in the hope of being able to alter the game to my liking, but I can't even open a freaking bitmap file on my system. Paint from XP and Photoshop 6 are all telling me the same thing, that the image can't be opened, but without any more detail. Is there anyone who could tell me if there's a way to see those images in a software?
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-13T17:53:48+00:00
- Post Title: Can't read bitmap file

Well, that's because it's not any of those fancy BMPs you know. In fact , it's a raw image. With a small header. The header is at the beginning of each image and comprises three integer values (2 bytes in lenght) :
- Number of colours??
- Heigth (e.g. 640)
- Width (e.g. 480)
- Then comes the image data. 

Open a file first with a hex ditor to see the heigth and width for each image. Then :
In Photoshop just select "raw" image when loading, specify the image heigth and width, channels : 1 and header size : 6. 
Now open it. 

Voila.   Example here :


Have fun.
## Post #3
- Username: wolfmah
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 13, 2003 10:46 pm
- Post datetime: 2003-10-14T00:03:29+00:00
- Post Title: Can't read bitmap file

Right on!   

But I still got a little question. Does the different shades of gray represent the color of the picture in the game or is it just a draw back of Photoshop?
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-14T08:31:32+00:00
- Post Title: Can't read bitmap file

No, a raw image is just a collection of colournumbers for each bit (ergo bitmap). Wat colour each number represents is written in a palette or color table. These pictures obviously have a colourresolution of 256. 
So, what you should do, and what I did, is look a bit further in the AGG file, to see if you find any .pal files, these are usually the palette files. 
if you do, you find two files : kb.pal and combat.pal. Well, the picture I showed is not from a combat scene, so we take the kb.pal. Now, this is a raw colour table, thus it is a series of Red Green Blue values, for 256 colours. Does this fit the size of that file? Yes, it does 256*3 = 768. 
Good, now we fire up photoshop, load the raw image again, and change the image->Mode to Indexed Colour (we tell it to use a fixed table). Now we have enabled the Colour Table option in Image->Mode.
Now open kb.pal (change it to kb.act first, that's the file extension photoshop likes for raw palette data) and load it as an Adobe Colour Table. 

Voila. Now you see the right colours.
## Post #5
- Username: wolfmah
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 13, 2003 10:46 pm
- Post datetime: 2003-10-14T19:18:35+00:00
- Post Title: Can't read bitmap file

Damn, I seem to be so far and so close at the same time. :/ I can see that the color are right if I turn the opacity a little down, but I can seem to be able to adjust the brightness to take out the blackness of the image to make it look right... No matter how close I get in caracter scale (btw, I'm using the same image as your exemple) the sky always turn out everything except blue   Is there anything to fix this to make everything as clear as the game?
## Post #6
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2003-10-15T13:26:32+00:00
- Post Title: Can't read bitmap file

This has to do with the original being in 640x480 VESA (Dos) mode. I don't know what brightness settings they used to show their pictures. Perhaps changing to 640x480 mode and choosing 65535 colours will show the pictures differently. Don't mess too much with the colours though, you should use their palette.
## Post #7
- Username: wolfmah
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Mon Oct 13, 2003 10:46 pm
- Post datetime: 2003-10-18T00:10:23+00:00
- Post Title: Can't read bitmap file

I got sick of the brightness and made my own palette base on the one the game use. For all of you who would like to modify the images of the game, just use this palette instead of the one in the game and their should be no problem   

[kb.pal.zip](ftp.wolfmahheaven.net/kb.pal.zip)

I still got a question though, have anyone found a way to "crack open" the different creature file (*.atk, *.std, *.wip, *.wlk) ?

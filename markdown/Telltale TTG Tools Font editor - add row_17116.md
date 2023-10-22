## Post #1
- Username: martanius
- Rank: advanced
- Number of posts: 42
- Joined date: Thu Aug 10, 2017 7:47 am
- Post datetime: 2017-10-08T14:05:11+00:00
- Post Title: Telltale TTG Tools Font editor - add row

Hello, I need to add some new characters into the game font, I can get the coordinates for each specific character in the DDS image of character set, but how the hell do I add a row in TTG Tool Font editor?

"Import" will only import characters up to a decimal value of 224. And show an error about index is out of array or something like that.

The game is Tales from the Borderlands.

I use TTG Tools from quckly - [http://file.quckly.ru/5k2galA276O4TUS](http://file.quckly.ru/5k2galA276O4TUS)

Please, can someone tell me how do I add a new row there?
Thank you.

EDIT
----------------------

Well, I figured it out. If someone have the same problem:

I used BMfont where in export options I choose export Font descriptor in XML format. It will export it in .fnt format anyway, but you can just change extension to .xml.
Now edit this file and remove everything except informations like:

<chars count="somenumber">
<char id="blah blah" x="blahblah" etc...
etc....
etc....
</chars>

And now go to Font editor in TTG Tools and open some FONT file and import this .xml file as "Import Coordinates from FontStudio".

Imported coords will need alot of adjusting as it is absolutely waaaay out of where it should be, but the important thing is that it importes correct decimal number of character and the rest you can edit there. Imported rows will be green highlighted.

Note it specifies char location differently, so it won't tell you info like kernings, Xend and Yend in the XML file. There is Xstart, Ystart, height and width (so you can calculate Xend and Yend from width and height). Kernings you either copy from similiar characters that already are there or test it or try to put there a number Offset number.

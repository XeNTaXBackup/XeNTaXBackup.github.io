## Post #1
- Username: zenox98
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-08-29T19:10:29+00:00
- Post Title: Spelunky HD modding tool (*.WAD files)

> This tool lets you extract and repack the .wad files with all the sound files and textures, letting you modify them and put them back into the game.
>
> 
>
> It's a command line utility. So you need to use it in a command prompt. Usage is pretty straightforward (remember to keep the wix file in the same directory):
>
> For extracting: spelunktool -x alltex.wad
>
> For recreating: spelunktool -c alltex
>
> 
>
> You can also use the batch files. Just drag and drop alltex.wad in windows explorer onto extract.bat or drag and drop the alltex folder onto repack.bat after extraction to repack it.
>
> 
>
> When recreating the wad file, it'll try to add everything in the alltex directory, if you add any extra file or directory which isn't supposed to be there, you're likely to get errors or a crash. I've tested the program a fair bit without encountering any bugs, but if anyone gets any problems, let me know. And as a general disclaimer, if something goes terribly wrong and my program sets your house on fire and eats all your food, I can not be held responsible.
>
> 
>
> One more thing, several files are duplicated when extracted. Only one of these will be added back when recreating. For instance book.png is in both tutorial and tutorialpics and it's the same file. If you edit any duplicate, just ensure each duplicate has been changed (my program will use the one which it finds first alphabetically).
>
> 
>
> Here's a quick example mod I did by replacing char_orange.png with char_slave.png:
>
> http://abload.de/img/spelunky2013-08-0919-9zu67.jpg

< link expired >
## Post #2
- Username: GDelscribe
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sat Aug 16, 2014 7:15 pm
- Post datetime: 2014-08-16T11:27:57+00:00
- Post Title: Spelunky HD modding tool (*.WAD files)

Sorry if this is foolish to ask but I assume this is not version specific to the game correct?

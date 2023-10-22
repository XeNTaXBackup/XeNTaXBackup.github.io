## Post #1
- Username: srcs34k
- Rank: n00b
- Number of posts: 14
- Joined date: Wed May 23, 2012 11:45 pm
- Post datetime: 2016-05-30T06:20:36+00:00
- Post Title: Ultima 9 Tool Suite 2000 David Churchill [.FLX]

[http://www.bursik.de/ultima/tools/downloads/u9tools.txt](http://www.bursik.de/ultima/tools/downloads/u9tools.txt)

> What's Included
>
> ---------------
>
> 
>
> u9xt.exe <filename.flx> <id number> <output file>
>
> 
>
> The flx files in static and sound are just lots of little files all globbed into
>
> one.  This program will extract the id'th (zero based) item from filename.flx
>
> and dump it info output file.
>
> 
>
> 
>
> u9books.exe <bookfile.flx>
>
> 
>
> The books file (eg. books-en.flx) contains all the books in the game, as well
>
> as the shops (ooh, I see some cheap goods in the near future), and journal entries
>
> for major items.  Running this will create a u9-books directory under the current
>
> directory and dump a heap of html files in it.  Once it's finished (takes a little
>
> time, be patient), simply open up index.html.  Note that the formatting codes
>
> in the books file aren't translated very well yet...
>
> 
>
> 
>
> u9snd.exe [-i] [-r <min>-<max>] -f <inputfile>
>
> 
>
> This program will extract all sounds except speech (type 2 encoded) from the sound
>
> files (music.flx, speech.flx, sfx.flx).  Use -i to make the program only create an
>
> index, -r to set the range of items to work on (get id numbers from the index), -f
>
> to set the filename.  Only -f is required, by default the program will extract 
>
> _all_ sounds in a particualar file.  Be sure you have a heap of space free!
>
> 
>
> 
>
> u9txv.exe <texturefilename>
>
> 
>
> This program will display the textures in a texture file (only texture8.* at the
>
> moment).  It requires 1024x768x16 to run, although this is easily changed if
>
> you can recompile it.  Use the '<' and '>' keys (well, actually ',' and '.') to
>
> move to new textures - it's probably better to use '>', as it currently displays
>
> the textures sequentially across the screen.  To exit simply hit escape.
>
> 
>
> 
>
> u9bmp.exe [gfx-mode-id]
>
> 
>
> This program will display the images contained in bitmap16.flx, which must be
>
> in the current directory.  gfx-mode-id is optional; to get a list of valid
>
> values run u9bmp with -? as a parameter.  A video card capable of a 16-bit 
>
> resolution is needed for this.  Yours probably is, but might still not work.
>
> If you have problems try installing a VESA BIOS driver (like the Scitech 
>
> Display Doctor), otherwise contact me and I see if I can help out.
>
> NB: The function to export the images to .bmp files creates 16-bit colour
>
>     bitmap files.  AFAIK the format it produces conforms to the standard,
>
>     and at the least mspaint will read them.  If you have trouble loading
>
>     them into your favourite image manipulation program, try loading them
>
>     in Paint and then saving them from there - better yet, try to fix the
>
>     bug in my .bmp code 
>
> 
>
> 
>
> Use the following keys to browse the images:
>
> 
>
> 'v' - foward 1       'f' - back 1
>
> 'c' - foward 10      'd' - back 10
>
> 'x' - foward 100     's' - back 100
>
> 'z' - foward 1000    'a' - back 1000
>
> 
>
> <cr> - dump current image(s) to .bmp files (see note above).
>
> 
>
> ' ' (space) - toggle mask (removes transparency info, try this if an image looks
>
>               whacked).
>
> esc - exit

i try [https://web.archive.org/web/*/http://www.bursik.de/](https://web.archive.org/web/*/http://www.bursik.de/)*
but no success maybe somebody have?

## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-12-28T08:01:58+00:00
- Post Title: Noesis RPG model template

Here's a template that I use when writing python plugins using the rich procedural geometry interface.

[http://xtsukihime.webs.com/Noesis%20Plu ... emplate.py](http://xtsukihime.webs.com/Noesis%20Plugins/Template/rapi_model_template.py)

All I have to do is fill in the name of the game/program, the extension, and then fill out the parse_file method.
I use a rather lengthy variable name like "self.inFile" for the bitstream so you might change that to something else if it is too tedious.

The one I use is this one:

[http://xtsukihime.webs.com/Noesis%20Plu ... e_sanae.py](http://xtsukihime.webs.com/Noesis%20Plugins/Template/rapi_model_template_sanae.py)

It inherits from an object defined in [Sanae.py](http://xtsukihime.webs.com/Noesis%20Plugins/Template/Sanae.py) (I tossed it into a package available in signature for no particular reason), which is supposed to provide shortcuts for some common things that you might do that are also available in the rapi module, but might be too hard to remember. Like getting the directory path of the input file (self.dirpath). Or the input filename (self.basename).

All of the model loading and constructing is done separately, so I only have to worry about how to parse the file.

This assumes you are using the rapi module for building the module though, like binding all sorts of buffers.

Most of it is based on what I've seen in example scripts, and there isn't really anything about loading in bones/weights or animations.

Most of the lists are not important. You might use them for immediate mode rendering, or if you're directly creating noesis objects, but other than that, they won't be used.

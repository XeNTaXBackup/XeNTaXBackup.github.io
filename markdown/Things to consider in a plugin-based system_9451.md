## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2012-08-11T00:02:38+00:00
- Post Title: Things to consider in a plugin-based system

I'm writing an image viewer with a plugin system (so I can figure out how to parse images and also figure out how to build a decent plugin system at the same time).

For example, each plugin will somehow take input, and then return an image.

Since it's an image viewer, all I really need is an image object that I can display on the screen, so at this point it looks like as long as every plugin implements a function that will return an image, I should be fine.

It sounds pretty simple to build a plugin system (because the program itself is simple in concept), but what are some things that I should think about while designing the program?
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-08-12T04:21:29+00:00
- Post Title: Things to consider in a plugin-based system

few that roll out my head:
design your plugin communication to be scalable
helps with version control when you add more stuff

to plugin: are you a [image program] plugin? this is my version number
to program: register this extension please!
to plugin: user wants to view this image - here is the filename!
to program: here is the image in a format you can understand!

i'd do the initial handshake by sending a structure for the plugin to populate

struct HELLOPLUGIN
{
  int program_ver;
  char your_ext[10]; // to POPULATE    although it could be signature based - watto uses signatures to guess the type by scoring how the file matches with recognised types
  char plugin_name[32]; // to POPULATE
};
how you will keep track of supported extensions
> how do you handle duplicate formats?
handling error messages
## Post #3
- Username: WRS
- Rank: Site Admin
- Number of posts: 786
- Joined date: Mon Sep 13, 2004 8:55 am
- Post datetime: 2012-08-12T05:12:54+00:00
- Post Title: Things to consider in a plugin-based system

Consider if a plugin system is really the way you want to go. It may be more interesting implementing a scripting system, along the lines of MexScript or Noesis' scripting language, and this would also open the system to more people since it eliminates a certain amount of effort that goes into adding support for a new format (for instance, chances are that plugins would have to handle all the details of pixel formats themselves, which means that as more plugins are added for more formats, an ever-increasing amount of effort is expended on duplicate code; a script system, on the other hand, could provide reasonably high-level primitives for common pixel formats, and a lower-level interface for coding support for unusual pixel formats - and, in fact, adding higher-level support for ever more unusual formats wouldn't add terribly much overhead, so long as the system is designed right).

Of course, if you're really sold on getting a feel for how plugin systems work, you should ignore my suggestion.
## Post #4
- Username: Wobble
- Rank: ultra-veteran
- Number of posts: 584
- Joined date: Wed Jan 05, 2005 4:47 am
- Post datetime: 2012-10-08T02:46:08+00:00
- Post Title: Things to consider in a plugin-based system

[out]

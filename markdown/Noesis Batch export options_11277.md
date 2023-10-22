## Post #1
- Username: dainazinas
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Feb 01, 2012 3:32 am
- Post datetime: 2014-03-03T18:59:48+00:00
- Post Title: Noesis Batch export options

How do I modify noesis batch proccess options? Changing anything in "$inpath$\$inname$_files\$inname$out.$outext$" don`t seem to do anything. How do I force it to save files in the same folder as originals, and not into separate sub folders like it does by default?

Does anyone know where to find any documentation for Noesis?

Thanks
## Post #2
- Username: dainazinas
- Rank: Moderator
- Number of posts: 1007
- Joined date: Mon Mar 23, 2009 9:57 am
- Post datetime: 2014-03-04T01:31:57+00:00
- Post Title: Noesis Batch export options

Just remove the $inname$_files\ part if you don't want files in subdirectories. That behavior is default for modules that have common filenames that would overwrite each other in the same directory.

That is just the template export string. You have to do "folder batch", it will use that template string to generate export commands for all of the files under the directory your select, optionally recursively. Once it fills the edit box with commands, you hit "Export" to actually run those commands.

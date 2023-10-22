## Post #1
- Username: kaninchen
- Rank: n00b
- Number of posts: 12
- Joined date: Sun Jul 11, 2010 9:03 am
- Post datetime: 2010-08-19T23:57:45+00:00
- Post Title: Samantha Swift and the Fountains of Fate *.dat can't be extr

I've tried some extractors but the files they extract are not complete.
And this is the code in contents.dat

This is a HotSource assets attributes file. Place attributes here using following syntax:
#   "FileName|*" AttributeName "AttributeValue"
#   * - means any file in current directory or any subdirectory.
#
# Available attributes are:
#   MipMaps (true, false) - whether create mip-levels for texture.
#   Compressed (true, false) - whether use DXT compression for texture.
#   PixelAccess (true, false) - whether texture supports read/write operations. This flag is required for alpha-based hit test.
#
# Example:
#   "*" MipMaps "true"
#   "Background.png" Compressed "false"

"*" MipMaps "false"
"*" PixelAccess "true"
"*" Compressed "true"

--------------------------------
Thanks for helping me.
## Post #2
- Username: bacter
- Rank: veteran
- Number of posts: 142
- Joined date: Tue Feb 23, 2010 3:42 am
- Post datetime: 2010-08-20T08:15:01+00:00
- Post Title: Samantha Swift and the Fountains of Fate *.dat can't be extr

Here's a simple unpacker for the game. It's a commandline util. Usage:
Swift_extr.exe <DAT_File> <TargetDir>
[Swift_extr.rar](https://xentaxbackup.github.io/file/3356_Swift_extr.rar)

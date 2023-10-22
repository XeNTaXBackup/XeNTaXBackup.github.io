## Post #1
- Username: vier86
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 07, 2011 8:42 am
- Post datetime: 2011-01-07T17:55:03+00:00
- Post Title: Xsyon - Extract for wiki

Looking for help extracting Xsyons .xsip game archives for the purpose of creating a game Wiki
Example .xsip archive in .rar .

Thank you for any help.
[Script.rar](https://xentaxbackup.github.io/file/3779_Script.rar)
## Post #2
- Username: vier86
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Fri Jan 07, 2011 8:42 am
- Post datetime: 2011-01-08T15:32:45+00:00
- Post Title: Xsyon - Extract for wiki

Bumping for a little help?
Really want to some content on the wiki
## Post #3
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2011-01-09T17:53:08+00:00
- Post Title: Xsyon - Extract for wiki

straightforward format - no compression or anything of importance unknown

remember that XeNTaX also has a wiki, so please update that when you write this up

```
# XSIP DUMPER (QuickBMS script)

get UN6 byte        # 6
get UN2 byte        # 2
get PAK string      # ASCII "PAK\x0"
get FILECOUNT long  # VAR
get PDATASIZE long  # (packed data size)
get HEADSIZE long   # 22
get DATASTART long  # (end of headers pointer)

for i = 0 < FILECOUNT

  get SIZE long
  get POINTER long
  get HASH long
  get UN0 long      # (always 0 in sample Script.xsip)
  get FILENSIZE long
  getdstring FILEN FILENSIZE
  log FILEN POINTER SIZE

next i

```

## Post #1
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-14T03:11:56+00:00
- Post Title: Re: Stacking - How to open ~p, ~h?

not sure if this tool can help - [viewtopic.php?p=72975#p72975](http://forum.xentax.com/viewtopic.php?p=72975#p72975)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2012-10-14T19:14:25+00:00
- Post Title: Re: Stacking - How to open ~p, ~h?

file data (*.~p) is either zlib or raw (with size flag)

rough structure for anyone who can understand how to unscramble the file data entries

```
endian big
get table1 longlong # type table pointer
get table2 longlong # fn table pointer
get cntTypes long # number of types
get fntablesize long # size of fn table
get cntFiles long # file count
get MARKER long # 23A1CEABh

getdstring unknown 16
get pntr1 longlong # .~p table
get pntr2 longlong
get pntr2 longlong
get unknown long
get MARKER long # 23A1CEABh again

# goto table1
## ## structure (cntTypes items)
# get len long, getdstring name len
# get unknown long, get unknown long, get unknown long

goto pntr1
for f = 0 < cntFiles
 ## NOTE: values are scrambled
  get unknown_1 long
  get unknown_2 long
  get unknown_3 long
  get unknown_4 long
next f

# goto table2
## ## structure (size of fntablesize)
# get fname string

```

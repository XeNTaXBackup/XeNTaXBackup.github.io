## Post #1
- Username: HenryEx
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Feb 07, 2013 8:30 am
- Post datetime: 2013-05-17T15:10:09+00:00
- Post Title: Creating a CSV table with QuickBMS

... Yeah, i think QBMS wasn't really designed for outputting a text log.

Well, i've got a lot of parameter files containing basically binary tables of various values, and for each of these files another file that defines each parameter in the first file (name, size, type, value ranges etc.).
Now, i could get me a hex editor and map out a parameter file via structures with the info from the parameter definition files, but i'd have to do this for every single one by hand. I want QuickBMS to read the X definitions, then read the X parameters for Y entries, and put them all together in a nice table. Makes it a lot easier to compare values between entries than via hex editor, too.

This is only the third script i ever wrote and i'm facing some difficulties, especially "printing" the number values to the file. There's also the issue that boolean flags are still typed as "u8" and i can only discern them by their name being followed by :1 or the like. I have to manually count where the byte is full and where the net byte starts. Haven't really got an elegant solution for that, and i don't really get how the ReadBytes function works. 

There was also an issue with a C string. I wanted to assign a linebreak with:
  set LINEBREAK string "\"\n\""
The result was that the quotes were outputted correctly, but instead of a linebreak it printed \n as text. I got around it with binary type, but i'm not sure why it doesn't work.

This is what the output would ideally look like:


The first four (heading) lines are read from the parameter definitions, everything below are the actual parameters.

This is what i got so far:

[Script linked because it's loooong](http://pastebin.com/ZuyVFYvc)

So, i need a little help. First off, the script doesn't run because apparently the variable type "signed_short" and similar don't work. They were in the help file, so i thought they would work, and i kind of need them because i have to differentiate between f32, s32, u32, s16, u16, s8 and u8 data types. 

Then there's the issue of reading the parameter and then converting that value into a string somehow. 
"set PARAM string PARAM" kind of works, but there's still the sign issue. A s16 parameter of -1 would output 65535 instead.

Then i have no idea how to read a boolean, output it to text, then try to find out whether or not to increase the read offset if i don't know how long the bit array is. They are only designated by their name being something like "canBeDeposited:1" or "displayChange:6".
The code i currently have for this...

```
      string CUR_NAME | ":"   # cut string to value behind colon
      set BLENGTH byte CUR_NAME
      math BOOLS += BLENGTH
      get BFLAG byte 0
      string FIELD0 b BFLAG   # change to hex display (i hope)
    endif

    if BOOLS > 8   # we shouldn't go over one byte in bits
      print "Bitflag array error! Name of current bitflag array at offset %PDOFFSET0%. \nExiting..."
      CleanExit
    elif BOOLS == 8   # if one byte is full, reset counter and inc. offset
      set BOOLS byte 0
      math CUR_PARAM += 1
    elif BOOLS != 0   # if we just processed at least one bit, we started a bit array
      set CUR_LEN byte 0   # do nothing, basically
    else   # in all other cases (not a bit array)
      math CUR_PARAM += CUR_LEN   # adjust offset by length of this parameter
    endif

```

... is almost certainly completely wrong and sure to result in complete nonsense.

Anyone got some ideas for me? Or maybe i overlooked a simple way to do this and am overcomplicating this terribly.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2013-05-22T06:02:54+00:00
- Post Title: Creating a CSV table with QuickBMS

parsing strings with quickbms is a pain just because the language wasn't intended for it.
for LINEBREAK you need to use the binary type because \n is a C escape char handled only by the bynary type.
signed_short is handled in read mode like get VAR signed_int, and yes it's my fault to forget "signed_short" and leaving only "signed_int"... will fix it next week.

for the rest I have not understood if you need to create the csv file (easy job) or you must read it (not easy).

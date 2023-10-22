## Post #1
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-21T21:50:16+00:00
- Post Title: SF4 Model Enable State Tool (SF4 MEST)

Tool for modifying model/object States from Stage or Character files for Street Fighter 4 PC

(Remove body parts or anything from a stage)

July 21st, 2009 (CET)
Initial release v0.9.0.0



NOTE: BE VERY CAREFUL WITH THE "SAVE" OPTION FOR NOW, THERE ARE ALMOST NO CHECKS ON WHETHER WRITING THE FILE WAS SUCCESSFUL OR NOT, IT JUST WRITES AND CLOSES.

Things to know
For now, only use it if you know what you are doing, or be very careful.
There are many checks when opening a file, reading a file and when entering new values. I'm pretty certain that you cannot destroy your EMB with this tool
It does NOT unpack EMZ files YET, use OffZip or QuickBMS first
This tool was created using AutoIt (latest version)
It uses PHP for file reading/writing, this is MUCH faster than using AutoIt on it's own.
Because it uses PHP, I had to make the program extract files on runtime, thus some files will be copied to your Temp folder and removed when the program shuts down.
The 64 bit version also uses an 64 bit PHP (v5.2.6 unofficial);  The 32 bit version uses the official PHP v5.3.0
To Do
A "Save As" option
Recognizing and unpacking EMZ archives to EMB
Quick-edit 1 selected item
A "Reload file" option
Searching/Selecting with multiple terms
Possibility to Copy/Paste a list
Undo possibilities
Drag&Drop files
Command-line version and/or possibility to drop a file on this tool's EXE
More, more, more.......
Hint: Use the program on COS files from Characters, like "CNL_01.cos.emz", and on main Stage files, like "STG_RVR.emz".

Download
32 bit
64 bit

Please report ANY problems/feedback/questions, Thanks 
Enjoy.
## Post #2
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2009-07-22T02:46:18+00:00
- Post Title: SF4 Model Enable State Tool (SF4 MEST)

1st!    

awesome man, will this allow for model import?

*mario runs off to test new app* woho! ^_^

thanks man

edit
oh.. no model export/injection yet
## Post #3
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2009-07-22T02:59:55+00:00
- Post Title: SF4 Model Enable State Tool (SF4 MEST)

Can you release the source code i would be interested in seeing the programing that went into this tool.
Thanks in advance
## Post #4
- Username: LouNGeR
- Rank: beginner
- Number of posts: 31
- Joined date: Mon Jul 06, 2009 6:58 am
- Post datetime: 2009-07-22T03:46:14+00:00
- Post Title: SF4 Model Enable State Tool (SF4 MEST)

Sorry, source isn't ready for release.
It WILL be released though, don't worry.
BTW, it's actually A LOT of code for doing something very small to a file.  

So what part are you interested in? The part on how to disable models?

My initial PHP code was easy, the only 'special' thing it needed was a "strpos_all" function that could rly rly fast give me all offsets of #EMG tags in a file.
The code below will set ALL objects to 00.

```
$file = "some_file.emb.emz.emg.dat";
$new_val = "00";

// HEX -> BIN
function h2b($h) {
    return pack("H*", $h);
}

$emg = file_get_contents($file);                // There's probably a better way, because stage files can be up to ~30MB
$emg_positions = strposall($emg, "#EMG");       // Get all offsets of "#EMG" tags

$fp = fopen($file, "r+b");                      // Read/Write, Binary

foreach($emg_positions as $pos)
{
    fseek($fp, $pos + 6);                       // Seek to sweet spot (2 bytes after #EMG tag)

    print "Offset:" . $pos . " - Old value: "
        . bin2hex( fread($fp, 1) ) . "\n"       // Read old value

    fseek($fp, $pos + 6);                       // Seek to sweet spot again
    fwrite($fp, h2b($new_val));                 // Write new value
}

fclose($fp);
?>
```


Or, was there something else you were interested in?

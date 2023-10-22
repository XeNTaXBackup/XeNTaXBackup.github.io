## Post #1
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-10T05:31:42+00:00
- Post Title: God of War 1, save checksum help?

Does anybody have any familiarity with checksums on save files?

Below is a decrypted copy of my save file.  The checksum at the end is "B2 47 58 2F".  Tracing the GoW ELF through a debugger as it saves, that checksum appears to originally be "01 6E B2 47 58 2F" and then gets truncated before it is written to the end of the file.

[https://www.dropbox.com/sh/e0q3guu1c76d ... DATA00.BIN](https://www.dropbox.com/sh/e0q3guu1c76dwk3/kVYCwRVjRR/DATA00.BIN)

I'm still stabbing blindly in the dark when it comes to figuring out the important bits through a debugger, but does anybody have any thoughts on how that checksum is calculated?  I'd like to write my own GoW save editor and this checksum is obviously rather important.
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-10T06:50:23+00:00
- Post Title: God of War 1, save checksum help?

> Reply from Wulf
>
> I'm still stabbing blindly in the dark when it comes to figuring out the important bits through a debugger,So we are...
If you are just using a debugger why not getting the crc routine start where you would find at least the startaddress of the buffer/buffersize being used.

> but does anybody have any thoughts on how that checksum is calculated?Might be CRC32. Find bufferstart/size (see above), save it as a file and for a quick test use [http://www.checksumcalculator.com/](http://www.checksumcalculator.com/) for example.

As a rule savegames are compressed so "decrypted" means uncompressed? 
Anyway - I'm not sure when crc is calculated - before or after compression/encryption?

Seems crc is calculated 'before'?
## Post #3
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-10T14:43:46+00:00
- Post Title: God of War 1, save checksum help?

> Reply from shakotay2
>
> If you are just using a debugger why not getting the crc routine start where you would find at least the startaddress of the buffer/buffersize being used.
I'm not quite sure how to do that.  My main method for finding things involves searching for known values in memory and then setting a hardware breakpoint when that location is written to, or just watching it and its surrounding memory change live as I play.  I can follow the result back a short way, but I'm not sure how to follow it from the beginning of the calculation.

It should be easy to test which portions of the save are checksummed by making changes and seeing if it still loads.  

I am able to see what it thinks the checksum should be if I attempt to load a save that doesn't match it.  Are you familiar with any methods that could narrow down the checksum by changing values in the file and seeing the new result?  The reverse can also be done, modifying the save in memory before the checksum is written and the checksum is created based on the modified data.

> Might be CRC32. Find bufferstart/size (see above), save it as a file and for a quick test use...
HxD is a hex editor.  I'm able to open the save file with it, select various parts of the file, and calculate checksums on it.  I'm not able to get anything resembling that checksum from it no matter what I select.

> As a rule savegames are compressed so "decrypted" means uncompressed? 
>
> Anyway - I'm not sure when crc is calculated - before or after compression/encryption?
These save games are not compressed.  They are basically small memory dumps of the game's checkpoint data.

The encryption comes from the PS3 user-signing, locking it to your account.  That has been removed.  The checksum is calculated before encryption, written to the file, and then the whole file including the checksum is encrypted.  For my purposes, we can assume the encryption is not a factor.

CAFEBAD100000000 seems to be some sort of comparison value.  It is present at the start of every save game, unchanged.  I'm at work for the day, but the last thing I was trying to figure out last night was why the instruction "clrldi (checksum register), (CAFEBAD100000000), 32)" was being run.  Thought I'd throw that out there in case it means anything to you.
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-10T21:14:53+00:00
- Post Title: God of War 1, save checksum help?

> Reply from Wulf
>
> My main method for finding things involves searching for known values in memory and then setting a hardware breakpoint when that location is written toYes, that would it be for windows OS, too.
There you would find something like
; /pOverlapped = NULL
; |pBytesRead => ARG.EAX+10
; |Size => [ARG.EAX+8]
; |Buffer => [ARG.EAX+14]
; |hFile => [ARG.EAX]
; \KERNEL32.ReadFile
(Don't know what this would be for PS3 OS.)

> It should be easy to test which portions of the save are checksummed by making changes and seeing if it still loads.Good idea.

> Are you familiar with any methods that could narrow down the checksum by changing values in the file and seeing the new result?I'm not sure what methods that should be.
Did you read this?
[http://www.nextgenupdate.com/forums/cal ... c32-6.html](http://www.nextgenupdate.com/forums/call-duty-modern-warfare-2/76112-ps3-x360-how-update-checksum-gamesave-file-crc32-6.html)

> The reverse can also be done, modifying the save in memory before the checksum is written and the checksum is created based on the modified data.Why not set all the bytes to zero except one set to 0x01 ?

> [...]the last thing I was trying to figure out last night was why the instruction "clrldi (checksum register), (CAFEBAD100000000), 32)" was being run.  Thought I'd throw that out there in case it means anything to you.Nope - as I said I'm not familiar with PS OS.
## Post #5
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-10T22:52:38+00:00
- Post Title: God of War 1, save checksum help?

I think I see the checksum method and should be able to confirm it all later tonight.  Is this method common enough to have a name?

The 'starting' checksum is CA FE BA D1.  The file contents are broken up into 4byte chunks and then added to the starting checksum, rollover numbers are discarded.

```
00 00 00 00 = CA FE BA D1
01 00 00 00 = CB FE BA D1
11 00 00 00 = DB FE BA D1

88 88 88 88 88 88 88 88 = 01 DC 0F CB E1
11 11 11 11             =    DC 0F CB E2
11 11 11 11 10          =    EC 0F CB E2
00 00 00 1F             =    CA FE BA F0
00 00 00 0F 10          =    DA FE BA E0
```


Edit:  I wrote a tool to calculate the checksum.  It's accurate if I zero out the second half of the save file, but doesn't match on the whole thing.  I guess that leaves me an evening of cutting saves in half until I find the discrepancy.
## Post #6
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-11T05:46:55+00:00
- Post Title: God of War 1, save checksum help?

Checksum issue resolved.  VB2010 code below to handle the checksum, for anybody interested.

The code isn't pretty but it gets the job done.  I make it way more complex than it should be with the hex conversions, but I was focusing more on the checksum than figuring out efficient VB usage.

```
        Dim bytes = My.Computer.FileSystem.ReadAllBytes(txtFile.Text)
        Dim checksum As ULong
        Dim power As ULong
        Dim csum As String



        For i = 0 To 81915
            power = 16 ^ (2 * (3 - (i Mod 4)))
            checksum = checksum + bytes(i) * power
        Next

        csum = Microsoft.VisualBasic.Right(Hex(checksum).ToString, 8)
        MsgBox(csum)

        For i = 1 To 7 Step 2
            bytes(81915 + (i + 1) / 2) = Integer.Parse(Mid(csum, i, 2), System.Globalization.NumberStyles.HexNumber)
        Next

        Dim oFileStream As System.IO.FileStream
        oFileStream = New System.IO.FileStream(txtFile.Text, System.IO.FileMode.Create)
        oFileStream.Write(bytes, 0, bytes.Length)
        oFileStream.Close()
    End Sub
```


Thanks for the help with it.
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2013-09-11T08:10:04+00:00
- Post Title: God of War 1, save checksum help?

Well done!  
Projects like these encourage me looking for a PS3 on next jumble sale (in german it's called 'Flohmarkt' what describes it better but there's no suitable translation to english I guess).

Just out of curiosity: how did you get this formula?
power = 16 ^ (2 * (3 - (i Mod 4)))

Is it a "common form" for CRC32?

"81915" is a constant or should it be replaced by "buffersize"?
## Post #8
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-11T13:50:20+00:00
- Post Title: God of War 1, save checksum help?

> encourage me looking for a PS3
I'd recommend it if you find one cheap.  Just make sure that you get a model capable of being downgraded/flashed.  The new ones are theoretically possible to do, but last I heard the methods weren't ready for the masses.

> in German it's called 'Flohmarkt'
I only dabble at being a cunning linguist, but I believe that would be a "flea market" in English.

> Just out of curiosity: how did you get this formula?
>
> power = 16 ^ (2 * (3 - (i Mod 4)))
>
> 
>
> Is it a "common form" for CRC32?
That...  is an ugly hack to avoid dealing with 4 bytes at a time.  I read one byte out of the byte array, then multiply it by 16 for every digit past the 'ones' column it is.

eg.
4A 00 hex  = 18944 decimal
4A hex = 74 * 16 * 16 = 18944 decimal

> "81915" is a constant or should it be replaced by "buffersize"?
For this game it's a constant.  The files are zero-filled up to that point.

I suppose better programming practice would be to leave 4 characters before End of File.
## Post #9
- Username: Wulf
- Rank: beginner
- Number of posts: 32
- Joined date: Sat Feb 11, 2012 2:46 am
- Post datetime: 2013-09-13T18:14:02+00:00
- Post Title: God of War 1, save checksum help?

Made a video of my savegame editor (with download links) here:
[http://youtu.be/J_U4Gt7GrF4](http://youtu.be/J_U4Gt7GrF4)

If anybody's ever looking for specifics on the save game stuff they can ask me here, or at my YT account there.

Once I've finalized everything and moved on from the project I'll try to come back to this topic and post all my data for posterity.

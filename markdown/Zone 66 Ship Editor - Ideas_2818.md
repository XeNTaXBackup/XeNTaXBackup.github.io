## Post #1
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-14T19:48:13+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

To start off, I'll explain what I'm trying to accomplish. I'm wanting to take what is accomplished by the old Zone 66 Cheat Patch given to me by Ardent. Even better it came with a source code. What I'm trying to do is take what it does but instead of having a program that automatically sets things within the Z66 ship archive it instead allows one to manually modify the fields along with the fields we've found.

The source here:

```
#include <stdio.h>
#include <fcntl.h>
#include <dos.h>

#define uchar unsigned char

typedef struct
{
    char    padding[36];
    uchar   payload;
    uchar   fuel;
    uchar   armor;
    uchar   topspeed;
    uchar   accel;
    uchar   turning;

} SHIPDAT0;

void main( void )
{
    int handle;
    SHIPDAT0 sdat;

    /* This is a fake file to screw us over. */
    remove( "SHIPDAT0.Z66" );

    /* Real stats are stored here. */
    handle = open( "MAPADAT3.Z66", O_BINARY | O_RDWR );
    lseek( handle, 1423L, SEEK_SET );
    _read( handle, &sdat, sizeof sdat );
    lseek( handle, 1423L, SEEK_SET );

    sdat.payload = 255;         /* Max, because uchars are used. */
    sdat.fuel = 120;            /* Bleah.  You guess. */
    sdat.accel = 1;             /* 0 = EXCELLENT, 4 = POOR */
    sdat.turning = 1;           /* Ditto */
    sdat.topspeed = 7;          /* DON'T GO OVER 7! */
    sdat.armor = 120;           /* Doesn't really work */

    _write( handle, &sdat, sizeof sdat );
    close( handle );

    puts( "Patch done!" );
}
```


What I'm trying to accomplish is making a rather simple VB windows tool that allows easy editing of the ship fields. Additionally next and back buttons that will show the next ship down in the list, or up in the list.
[ShipEditorBetaGUI.PNG](https://xentaxbackup.github.io/file/1368_ShipEditorBetaGUI.PNG)
## Post #2
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-15T19:36:00+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

What I mean is, what would I have to establish to get it to do the thing I wish it to do? I've already got the load part set up to look for only Z66 files. The next is reading the bytes, outputting the information into the fields, then after that being able to "browse" the ships with the back and next buttons.

Then after that is accomplished it's a matter of writing back those values into the file. I'll make sure it's pretty much foolproof by adding checks for if the fields are given numeric values and do not exceed a limit.

I know SOME VB2005 command equals of these commands but things like "sdat" and such throw me off. And of course it's code is automatically running through a singly file and maxing out the fields as a cheat. Mine instead will be used for modifying ship stats for applying to custom ship packs possibly.

Edit: [Ship Disection](http://www.geocities.com/shindarkfox/ZONE66SHIPDAT0.PNG)

Eventually I plan to include all available fields as seen here. And possibly some discovered by Ardent when I get the full specs. Also I'll try to find a way to handle ship images because I'm clueless how that is worked out.

Edit 2 (little note): If you look at my observation compared to me that the guy says the maximum safe speed is 7, I say it is 8. I'm uncertain how to handle the guns as I do not know how to increase weapon hold or what those bytes accomplish.
## Post #3
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-15T22:36:47+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

Tomorrow after work I'll write you an example routine in VS.NET 2005 for you (it's a bit to late now (0:36 AM)).


Cheers,


Nick Kusters.
## Post #4
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-15T22:47:04+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

```
{ 
    char    padding[36]; 
    uchar   payload; 
    uchar   fuel; 
    uchar   armor; 
    uchar   topspeed; 
    uchar   accel; 
    uchar   turning; 

} SHIPDAT0; 

```


UCHAR according to [http://msdn2.microsoft.com/en-us/library/aa505945.aspx](http://msdn2.microsoft.com/en-us/library/aa505945.aspx): 

> An 8-bit integer block of data with the range: 0 through 255 decimal. Because a UCHAR is unsigned, its first bit (Most Significant Bit (MSB)) is not reserved for signing.

So this is a normal Byte (BinaryReader.ReadByte for example)

So, you can read the data using:

Dim Padding() as byte = BR.ReadBytes(36)
Dim PayLoad as byte = BR.ReadByte()
... you get the idea

```
{ 
    int handle; 
    SHIPDAT0 sdat; 

    /* This is a fake file to screw us over. */ 
    remove( "SHIPDAT0.Z66" ); 

    /* Real stats are stored here. */ 
    handle = open( "MAPADAT3.Z66", O_BINARY | O_RDWR ); 
    lseek( handle, 1423L, SEEK_SET ); 
    _read( handle, &sdat, sizeof sdat ); 
    lseek( handle, 1423L, SEEK_SET ); 

    sdat.payload = 255;         /* Max, because uchars are used. */ 
    sdat.fuel = 120;            /* Bleah.  You guess. */ 
    sdat.accel = 1;             /* 0 = EXCELLENT, 4 = POOR */ 
    sdat.turning = 1;           /* Ditto */ 
    sdat.topspeed = 7;          /* DON'T GO OVER 7! */ 
    sdat.armor = 120;           /* Doesn't really work */ 

    _write( handle, &sdat, sizeof sdat ); 
    close( handle ); 

    puts( "Patch done!" ); 
}

```


What this does, is read binary data from a stream into the sdat structure (just an object holding the data).

After it has bean read, he overwrites values (you'll add your own here), and write it back.


So, all there is left to do is to figure out at what position you have to start reading, and the rest is a piece of cake 


Sincerely,


Nick Kusters.
## Post #5
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-16T01:14:48+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

Hmmm... is BR.ReadBytes a function in VB2005 .NET because it's not present here. I'm not new to programming but I'm not out of the beginning yet. Closest I've made was a frontend program to run a console image conversion program.

BR is not in VB 2005, probably only the .NET one which stinks. Means now it'll be harder than ever.

Edit: This much I have established

```
    Dim fileopen
    Dim br As New IO.BinaryReader(fileopen)
    Dim PayLoad As Byte = br.ReadByte()
    Dim Fuel As Byte = br.ReadByte()
    Dim Acc As Byte = br.ReadByte()
    Dim Turning As Byte = br.ReadByte()
    Dim TopSpeed As Byte = br.ReadByte()
    Dim Armor As Byte = br.ReadByte()
    Dim Gun1 As Byte = br.ReadByte()


    Private Sub btnLoad_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnLoad.Click
        Dim openFileDialog1 As New OpenFileDialog()
        Dim Padding() As Byte = br.ReadBytes(36)

        openFileDialog1.InitialDirectory = "c:\"
        openFileDialog1.Filter = "zone66 files (*.z66)|*.z66"
        openFileDialog1.FilterIndex = 2
        openFileDialog1.RestoreDirectory = True
        openFileDialog1.ShowDialog()

        fileopen = openFileDialog1.FileName


    End Sub

End Class
```


I had to DIM BR for it to work. This is all pretty early still I know but it's my first go at something like this.
## Post #6
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T05:49:54+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

> Reply from Darkfox
>
> Hmmm... is BR.ReadBytes a function in VB2005 .NET because it's not present here. I'm not new to programming but I'm not out of the beginning yet. Closest I've made was a frontend program to run a console image conversion program.

Check out the BinaryReader class ([http://msdn2.microsoft.com/en-us/librar ... eader.aspx](http://msdn2.microsoft.com/en-us/library/system.io.binaryreader.aspx)), i used BR as an abbreviation, sorry.

BR is not in VB 2005, probably only the .NET one which stinks. Means now it'll be harder than ever.

Edit: This much I have established

```
    Dim fileopen
    Dim br As New IO.BinaryReader(fileopen)
    Dim PayLoad As Byte = br.ReadByte()
    Dim Fuel As Byte = br.ReadByte()
    Dim Acc As Byte = br.ReadByte()
    Dim Turning As Byte = br.ReadByte()
    Dim TopSpeed As Byte = br.ReadByte()
    Dim Armor As Byte = br.ReadByte()
    Dim Gun1 As Byte = br.ReadByte()


    Private Sub btnLoad_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnLoad.Click
        Dim openFileDialog1 As New OpenFileDialog()
        Dim Padding() As Byte = br.ReadBytes(36)

        openFileDialog1.InitialDirectory = "c:"
        openFileDialog1.Filter = "zone66 files (*.z66)|*.z66"
        openFileDialog1.FilterIndex = 2
        openFileDialog1.RestoreDirectory = True
        openFileDialog1.ShowDialog()

        fileopen = openFileDialog1.FileName


    End Sub

End Class
```


I get back from work in about 9-10 hours, when I come back I'll make the example for you, as promissed, explaining it step by step.
## Post #7
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T16:40:40+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

```
Public Structure Zone66Ship
    Dim Padding() As Byte ' 36 bytes
    Dim PayLoad As Byte
    Dim Fuel As Byte
    Dim Acc As Byte
    Dim Turning As Byte
    Dim TopSpeed As Byte
    Dim Armor As Byte
    Dim Gun1 As Byte ' Total should be 43 bytes.
End Structure

```


```

    Private Const StructSize As Integer = 43

    Private Function Example() As Zone66Ship
        Dim Result As New Zone66Ship
        Dim SourceFile As String = BrowseForFile("C:\", "zone66 files (*.z66)|*.z66")
        If Not String.IsNullOrEmpty(SourceFile) Then
            ' The "Using" constructor ensures us that
            ' if something goes wrong, everything will be handled as it should
            ' (Handles get closed, memory is released, this is because of the IDisposable interface).
            Using BR As New IO.BinaryReader(New IO.FileStream(SourceFile, IO.FileMode.Open))
                If BR.BaseStream.Length >= StructSize + BR.BaseStream.Position Then
                    Result.Padding = BR.ReadBytes(36)
                    Result.PayLoad = BR.ReadByte
                    Result.Fuel = BR.ReadByte
                    Result.Acc = BR.ReadByte
                    Result.Turning = BR.ReadByte
                    Result.TopSpeed = BR.ReadByte
                    Result.Armor = BR.ReadByte
                    Result.Gun1 = BR.ReadByte
                Else
                    MsgBox("Not enough bytes left to read")
                End If
            End Using
        Else
            MsgBox("No source file was selected")
        End If
        Return Result
    End Function

    Private Function BrowseForFile(ByVal InitialDir As String, ByVal Filter As String) As String
        ' Initialize Result to avoid warnings since we will return
        ' this variable, even if a user doesn't select a file
        Dim Result As String = String.Empty
        ' Create a new OpenFileDialog
        Dim ofd As New OpenFileDialog()
        ' Set the specified Start directory
        ofd.InitialDirectory = InitialDir
        ' Set the file filter
        ofd.Filter = Filter
        ' Make sure that if this function get's called again,
        ' the previous selected folder will be the next base dir
        ofd.RestoreDirectory = True
        ' Calling ShowDialog() returns a Dialog result.
        ' We should only take action if the user pressed OK to select
        ' the file. There is no need to do a check afterwards if 
        ' the file exists (as you would do when normaly accepting
        ' file input, since this OFD does these checks for us).
        If ofd.ShowDialog = Windows.Forms.DialogResult.OK Then
            Result = ofd.FileName
        End If
        ' Return the result variable, which could be empty, or hold the filename
        Return Result
    End Function

    Private Function BrowseForFileSteam(ByVal InitialDir As String, ByVal Filter As String) As System.IO.Stream
        ' Initialize Result to avoid warnings since we will return
        ' this variable, even if a user doesn't select a file
        Dim Result As System.IO.Stream = Nothing
        ' Create a new OpenFileDialog
        Dim ofd As New OpenFileDialog()
        ' Set the specified Start directory
        ofd.InitialDirectory = InitialDir
        ' Set the file filter
        ofd.Filter = Filter
        ' Make sure that if this function get's called again,
        ' the previous selected folder will be the next base dir
        ofd.RestoreDirectory = True
        ' Calling ShowDialog() returns a Dialog result.
        ' We should only take action if the user pressed OK to select
        ' the file. There is no need to do a check afterwards if 
        ' the file exists (as you would do when normaly accepting
        ' file input, since this OFD does these checks for us).
        If ofd.ShowDialog = Windows.Forms.DialogResult.OK Then
            Result = ofd.OpenFile
        End If
        ' Return the result variable, which could be empty, or hold the filename
        Return Result
    End Function

End Class

```
## Post #8
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T17:04:12+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

```
    ' this is just a simple example, you'd want
    ' to validate input better, but that takes
    ' to much time for this simple example
#Region " Public Properties "
    Public Property PayLoad() As Byte
        Get
            Return GetByteFromString(txtPayLoad.Text)
        End Get
        Set(ByVal value As Byte)
            txtPayLoad.Text = value.ToString
        End Set
    End Property
    Public Property Fuel() As Byte
        Get
            Return GetByteFromString(txtFuel.Text)
        End Get
        Set(ByVal value As Byte)
            txtFuel.Text = value.ToString
        End Set
    End Property
    Public Property Acc() As Byte
        Get
            Return GetByteFromString(txtAcc.Text)
        End Get
        Set(ByVal value As Byte)
            txtAcc.Text = value.ToString
        End Set
    End Property
    Public Property Turning() As Byte
        Get
            Return GetByteFromString(txtTurning.Text)
        End Get
        Set(ByVal value As Byte)
            txtTurning.Text = value.ToString
        End Set
    End Property
    Public Property TopSpeed() As Byte
        Get
            Return GetByteFromString(txtTopSpeed.Text)
        End Get
        Set(ByVal value As Byte)
            txtTopSpeed.Text = value.ToString
        End Set
    End Property
    Public Property Armor() As Byte
        Get
            Return GetByteFromString(txtArmor.Text)
        End Get
        Set(ByVal value As Byte)
            txtArmor.Text = value.ToString
        End Set
    End Property
    Public Property Gun1() As Byte
        Get
            Return GetByteFromString(txtGun1.Text)
        End Get
        Set(ByVal value As Byte)
            txtGun1.Text = value.ToString
        End Set
    End Property
    ' This smart property ensures you maximum flexibility
    ' with geting and setting the values various ways
    Public Property Zone66Ship() As Zone66Ship
        Get
            Dim Result As New Zone66Ship
            Result.PayLoad = PayLoad
            Result.Fuel = Fuel
            Result.Acc = Acc
            Result.Turning = Turning
            Result.Armor = Armor
            Result.Gun1 = Gun1
            Return Result
        End Get
        Set(ByVal value As Zone66Ship)
            PayLoad = value.PayLoad
            Fuel = value.Fuel
            Acc = value.Acc
            Turning = value.Turning
            Armor = value.Armor
            Gun1 = value.Gun1
        End Set
    End Property
#End Region
#Region " Help Functions "
    Private Function GetByteFromString(ByVal Value As String) As Byte
        Dim Result As Byte
        ' If TryParse fails, Result becomes 0
        If Not Byte.TryParse(txtPayLoad.Text, Result) Then
            Debug.WriteLine(String.Format("'{0}' is not a valid byte", txtPayLoad))
        End If
        Return Result
    End Function
#End Region
#Region " Event Handlers "
    Private Sub btnCancel_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnCancel.Click
        ' Setting the DialogResult property automaticly closes the form
        Me.DialogResult = Windows.Forms.DialogResult.Cancel
    End Sub
    Private Sub btnSave_Click(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles btnSave.Click
        ' Setting the DialogResult property automaticly closes the form
        Me.DialogResult = Windows.Forms.DialogResult.OK
    End Sub
#End Region
End Class

```
## Post #9
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T17:11:19+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

```
        Dim Result As New Zone66Ship
        Dim SourceFile As String = BrowseForFile("C:\", "zone66 files (*.z66)|*.z66")
        If Not String.IsNullOrEmpty(SourceFile) Then
            Dim MyShip As Zone66Ship = GetZone66Ship(SourceFile, 0)
        Else
            MsgBox("No source file was selected")
        End If
        Return Result
    End Function
    Private Function GetZone66Ship(ByVal FileName As String, ByVal StartPosition As Int64) As Zone66Ship
        Dim Result As New Zone66Ship
        If System.IO.File.Exists(FileName) Then
            ' The "Using" constructor ensures us that
            ' if something goes wrong, everything will be handled as it should
            ' (Handles get closed, memory is released, this is because of the IDisposable interface).
            Using BR As New IO.BinaryReader(New IO.FileStream(FileName, IO.FileMode.Open))
                If StartPosition < BR.BaseStream.Length Then
                    If BR.BaseStream.Length >= StructSize + BR.BaseStream.Position Then
                        ' Jump to the position in memory
                        BR.BaseStream.Seek(StartPosition, IO.SeekOrigin.Begin)
                        Result.Padding = BR.ReadBytes(36)
                        Result.PayLoad = BR.ReadByte
                        Result.Fuel = BR.ReadByte
                        Result.Acc = BR.ReadByte
                        Result.Turning = BR.ReadByte
                        Result.TopSpeed = BR.ReadByte
                        Result.Armor = BR.ReadByte
                        Result.Gun1 = BR.ReadByte
                    Else
                        MsgBox("Not enough bytes left to read")
                    End If
                Else
                    MsgBox(String.Format("The position {0} lies beyond the length of file File '{1}' (MAX = {2})!", StartPosition, FileName, BR.BaseStream.Length))
                End If
            End Using
        Else
            MsgBox(String.Format("File '{0}' does not exist!", FileName))
        End If
        Return Result
    End Function

```
## Post #10
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T17:13:29+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

Here are the files, I was posting as I write, to give you something to read while waiting, but now your ready to get bussy 

Hope you like it, feedback is always welcome.

Sincerely,


Nick Kusters.
[Zone66.zip](https://xentaxbackup.github.io/file/1372_Zone66.zip)
## Post #11
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T17:56:56+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

Before I forget, I havn't added writing back values yet, but it shouldn't be a problem for you, just make sure you seek back with the BinaryWriter.basestream back to the starting point of the info, and write the values in the correct order.
## Post #12
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-16T21:26:45+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

I do like what I see and it will help out alot. Though I wonder, does the main form act as a place where things can be loaded from then it can open the edit form? I've never worked with more than a single form (YET, still a student but I've become so addicted)

It's different from my idea but it seems a smarter approach. That is the intention of it correct?
## Post #13
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T21:28:57+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

> Reply from Darkfox
>
> I do like what I see and it will help out alot. Though I wonder, does the main form act as a place where things can be loaded from then it can open the edit form? I've never worked with more than a single form (YET, still a student but I've become so addicted)

It's different from my idea but it seems a smarter approach. That is the intention of it correct?

Yup, but it doesn't have to be, you can create it into a single form application with ease. Let me show you, I'll post an example in a few
## Post #14
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T21:42:59+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

Here's a rework of the project (made a few quick hacks, won't win the beauty award )


In Short:

* Remember last stream position
* Pick source file on start
* Remember sourcefile
* Reset source file if end of stream is reached
* Auto pick new file after source file is reset (have to click next again)
* added option to move on to the next ship and not save changes, or save and continue

Think that's about it.
[Zone66v2.zip](https://xentaxbackup.github.io/file/1373_Zone66v2.zip)
## Post #15
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-16T21:45:41+00:00
- Post Title: Zone 66 Ship Editor - Ideas?

Well it does work on regular VB2005 and I do see what is going on in the code. I can see the public structure is established like it is in the one guy's code with the addition of Gun1 (a bit iffy since guns are handled in a different way but all have at least 1 gun so it's alright I would believe)

The problem though becomes that a Zone 66 *mapdata3.z66 contains... I'm not sure the exact count but around 4-6 ships. I'd have to look at the files when I get home to get that information. Thats why I was adding a "next" and "back" button.

Edit: Nevermind. LOL Your post addressed that. Thanks. This'll really help with that. I'm at college right now so I'll have to do testing and work on it at home. Later I'll try throwing in some of the additional stuff like modifying the name and "ship graphic used" editing.
## Post #16
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T21:46:40+00:00
- Post Title: 

If this is all you want to do, it's good enough, if not, you want to go back to the multi form one (display more info, select a specific entry, etc). There are loads of things you can add that would benefit the program. I don't have to game so I have no idea or real insentive to create something, but if I would, I'm sure i can think of over 10 things to put in there.

I'll let you get to it now, and please post what you made out of it, I'm curious and will give you some pointers if you like.
## Post #17
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T21:49:49+00:00
- Post Title: 

> Reply from Darkfox
>
> Well it does work on regular VB2005 and I do see what is going on in the code. I can see the public structure is established like it is in the one guy's code with the addition of Gun1 (a bit iffy since guns are handled in a different way but all have at least 1 gun so it's alright I would believe)

The problem though becomes that a Zone 66 *mapdata3.z66 contains... I'm not sure the exact count but around 4-6 ships. I'd have to look at the files when I get home to get that information. Thats why I was adding a "next" and "back" button.

Edit: Nevermind. LOL

Well, if every ship is padded with 36 0's, you'd have a signature to look for, and you'd be able to find them in the file.

An idea: try to find out how to detect a ship, write a routine that reads thrue the stream, finding starting positions of the ship data, and using those positions. Once you have that, you could use a listview or dropdownlist that allows a user to pick a ship and edit it.
## Post #18
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-16T22:04:26+00:00
- Post Title: 

> An idea: try to find out how to detect a ship, write a routine that reads thrue the stream, finding starting positions of the ship data, and using those positions. Once you have that, you could use a listview or dropdownlist that allows a user to pick a ship and edit it.

A great idea and I see where you are coming from. Instead of seeking the next ship in the file or going back it would just list them all based on name and you'de select from a list? I'd have to see if current knowhow and what I can assimilate (lol Borg) from what you've written will give me the idea. But as far as that goes I'm more intent on establishing something that works first THEN pretty it up.

  Establishing a working foundation is my first concern almost always. Then I can have fun with it. 

Thanks a whole lot and I'll check it once I get home which shouldn't be long from now.

> Well, if every ship is padded with 36 0's, you'd have a signature to look for, and you'd be able to find them in the file.

There tends to be around that number of 0s after a name if you saw the ship disection image I put together. I think the program seeks the meat of the ship data. Later I'd have to find a way to not use these 0s perhaps and instead a pattern within the z66 format structure that tells it instead. Just some thoughts.
## Post #19
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-16T22:07:10+00:00
- Post Title: 

Okies  It's past midnight here now, so I'll be off to bed. I'll be sure to check back tomorrow to see if there are any questions.


Good Luck,


Nick Kusters.
## Post #20
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-17T21:03:43+00:00
- Post Title: 

It is displaying values within the files but they aren't the correct values. I'll just tweak some things until it displays correctly or if I get something more solid on the ship packs. It's good to see it's gotten this far at least.

Edit: Alright, some things to tweak and add is all for right now. I'll attach it when I'm done. 

Edit2: Got every value displaying on the form, still not the right values but still it is displaying everything (minus Gun1, which for now is disabled bringing byte total to 42). More tweaking. I can't help but think something the one program the guy made compared to this one has something else. What were those other numbers?

```
    handle = open( "MAPADAT3.Z66", O_BINARY | O_RDWR );
    lseek( handle, 1423L, SEEK_SET );
    _read( handle, &sdat, sizeof sdat );
    lseek( handle, 1423L, SEEK_SET ); 
```


1423L? "lseek" seems that it seeks each instance of a set of these values. 1423L I'm not certain of.

Edit3: Leaves me wondering. Guess it's best to test the cheat program then compare the results.

Edit 4: Now this is what happened, the cheat program only changes one ship. The "dfa bomber" which means I'll have to figure out something more solid about the structure. :\

Edit 5: Yep, it's been confirmed to be the case. The cheat program was designed SPECIFICALLY to edit the data of "dfa bomber" only. Well at least now something is started. Thanks. I guess I'll just ask somebody if they can figure out the way it stores this information.
## Post #21
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-19T15:02:45+00:00
- Post Title: 

lseek definition: [http://www.opengroup.org/onlinepubs/007 ... lseek.html](http://www.opengroup.org/onlinepubs/007908799/xsh/lseek.html)

I am not sure if the 'L' in the value stands for 'Long' (64 bits), but it could be that it seeks to 1423 bytes into the file. How big is the file you are editing? Also, if you position the binarywriter.basestream with seek (1423 bytes from beginning), do you get the correct data?
## Post #22
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-19T15:05:17+00:00
- Post Title: 

hmm, just looked at the image with the file dissection, could you upload the entire file? I'd might be able to help a bit if I find some time...
## Post #23
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-19T15:11:04+00:00
- Post Title: 

I was still a bit curious about that 'L' in lseek, it turns out my suspicions were right (according to [http://msdn2.microsoft.com/en-us/librar ... S.80).aspx](http://msdn2.microsoft.com/en-us/library/1yee101t%28VS.80%29.aspx) ). Even though he doesn't use the _lseek but a older lseek, it seems to be the MS C++ flavour that adds the L (just speculating here, C++ is not a language I program in, but I get the general concept and can read it to a certain extent).
## Post #24
- Username: Darkfox
- Rank: VVIP member
- Number of posts: 688
- Joined date: Sat Jul 05, 2003 1:11 am
- Post datetime: 2007-10-20T03:23:19+00:00
- Post Title: 

Here is the file I'm trying to edit. I included two ship packs to help see a pattern. The bytes should look about the same as identified in the image. That was an old thing I did with the SHIPDAT0.Z66 file which is actually where it stores ship data as like a cache from all MAP(letter)DAT3.Z66 files.
[MAPADAT3.zip](https://xentaxbackup.github.io/file/1380_MAPADAT3.zip)

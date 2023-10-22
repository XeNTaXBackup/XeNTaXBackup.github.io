## Post #1
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-09-30T08:38:27+00:00
- Post Title: Settlers VI bba archives

Documentation on the bba format used in Settlers V can be found in the xentax wiki:
[http://wiki.xentax.com/index.php/Settle ... e_Of_Kings](http://wiki.xentax.com/index.php/Settlers_-_Heritage_Of_Kings)

Here are some example files from the new tilte:
[http://uploaded.to/?id=kzeb9s](http://uploaded.to/?id=kzeb9s)

Any help appreciated 

EDIT: atm I can't figure out the encryption algorithm cause I don't have a No-CD, thus the copy protection is preventing me from disassembling the exe.
## Post #2
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-08T22:44:38+00:00
- Post Title: Settlers VI bba archives

Dear Rheini,


First of all, thanks for the format you posted on the WiKi  I would love to be able to extract the audio from the songs the viking character sings 

I've went ahead and started on a vb.net program to read the initial headers, any extra info is appreciated a lot (i have my own CRC32 routine, that isn't the problem, just new to the decryption).

I am already running into problems on the Header (Directory*) data, since i am reading the encrypted data. Any pointers would be appreciated 

Don't know if it's usefull, but here's what i've done so far (not much:))

Updated to show new built output

```

    Private Sub Form1_Load(ByVal sender As System.Object, ByVal e As System.EventArgs) Handles MyBase.Load

        Dim DirectoryEncryptionIdentifiers As New Dictionary(Of UInt32, List(Of String))

        For Each FI As IO.FileInfo In New IO.DirectoryInfo("F:\THE SETTLERS - Rise of an Empire Install\base\bba\").GetFiles("*.bba")
            Dim B As BAF = ReadBAF(FI.FullName)
            If DirectoryEncryptionIdentifiers.ContainsKey(B.Header.DirectoryEncryptionIdentifier) Then
                DirectoryEncryptionIdentifiers(B.Header.DirectoryEncryptionIdentifier).Add(B.FileName)
            Else
                Dim Files As New List(Of String)
                Files.Add(B.FileName)
                DirectoryEncryptionIdentifiers.Add(B.Header.DirectoryEncryptionIdentifier, Files)
            End If
        Next
        For Each Key As UInt32 In DirectoryEncryptionIdentifiers.Keys
            Debug.WriteLine(String.Format("{1}Key: 0x{0} is used By:", Key.ToString("X"), vbCrLf))
            For Each File As String In DirectoryEncryptionIdentifiers(Key)
                Debug.Write(String.Format("{0}{1}{2}", vbTab, File, vbCrLf))
            Next
        Next
        '        ReadBAF("F:\THE SETTLERS - Rise of an Empire Install\base\bba\shrgcfg0.bba")
    End Sub

    Private Function ReadBAF(ByVal FileName As String) As BAF
        Dim Result As New BAF
        Result.FileName = IO.Path.GetFileName(FileName)
        If IO.File.Exists(FileName) Then
            Using BR As New IO.BinaryReader(New IO.FileStream(FileName, IO.FileMode.Open, IO.FileAccess.Read))
                Result.ArchiveHeader = BR.ReadChars(3)
                Result.Version = BR.ReadByte
                Result.Unknown = BR.ReadUInt32
                Result.HeaderSize = BR.ReadUInt32
                Result.HeaderEncryptionIdentifier = BR.ReadUInt32
                If Result.HeaderEncryptionIdentifier = &H29D58DC5 Then
                    '  Debug.WriteLine("Known Encryption Header :)")
                Else
                    Debug.WriteLine("UnKnown Encryption Header :( => " & Result.HeaderEncryptionIdentifier.ToString("X"))
                End If
                Result.Header = New BAFHeader
                Result.Header.DirectoryOffsetLow = BR.ReadUInt32
                Result.Header.DirectoryOffsetHigh = BR.ReadUInt32
                Result.Header.DirectoryLength = BR.ReadUInt32
                Result.Header.DirectoryCRC32CheckSum = BR.ReadUInt32
                Result.Header.DirectoryEncryptionIdentifier = BR.ReadUInt32
                Dim Padding As Integer = Result.HeaderSize - 20
                If Padding > 0 Then Result.Header.Padding = BR.ReadBytes(Padding)
            End Using
            Debug.WriteLine(BAF2String(Result))
        Else
            Debug.WriteLine(String.Format("'{0}' does not exist...", FileName))
        End If
        Return Result
    End Function
    Private Function BAF2String(ByVal B As BAF) As String
        Dim Result As String = String.Empty
        Result &= "File                           : " & B.FileName & vbCrLf
        Result &= "Archive Header                 : " & B.ArchiveHeader & vbCrLf
        Result &= "Version                        : " & B.Version & vbCrLf
        Result &= "Unknown                        : " & B.Unknown & vbCrLf
        Result &= "Header Size                    : " & B.HeaderSize & vbCrLf
        Result &= "Header Encryption Identifier   : " & "0x" & B.HeaderEncryptionIdentifier.ToString("X") & vbCrLf
        Result &= "Directory Offset Low           : " & B.Header.DirectoryOffsetLow & vbCrLf
        Result &= "Directory Offset High          : " & B.Header.DirectoryOffsetHigh & vbCrLf
        Result &= "Directory Length               : " & B.Header.DirectoryLength & vbCrLf
        Result &= "Directory CRC32 CheckSum       : " & "0x" & B.Header.DirectoryCRC32CheckSum.ToString("X") & vbCrLf
        Result &= "Directory Encryption Identifier: " & "0x" & B.Header.DirectoryEncryptionIdentifier.ToString("X") & vbCrLf
        Return Result
    End Function
End Class
Public Structure BAF
    Dim FileName As String
    Dim ArchiveHeader As String ' BAF
    Dim Version As Byte ' 4
    Dim Unknown As UInt32 ' 5
    Dim HeaderSize As UInt32  ' 64
    Dim HeaderEncryptionIdentifier As UInt32 ' 0x29D58DC5
    Dim Header As BAFHeader
End Structure
Public Structure BAFHeader ' Encrypted!
    Dim DirectoryOffsetLow As UInt32
    Dim DirectoryOffsetHigh As UInt32 ' null
    Dim DirectoryLength As UInt32
    Dim DirectoryCRC32CheckSum As UInt32
    Dim DirectoryEncryptionIdentifier As UInt32
    Dim Padding() As Byte
End Structure

```


Sincerely,


Nick Kusters.
## Post #3
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-08T22:54:26+00:00
- Post Title: Settlers VI bba archives

Well, I think they changed some parts of the file format (had a look at the memory dump)
Reading the encrypted values doesn't get you further. As already said I can't crack the encryption cause of the copy protection. I'd need a nocd.
## Post #4
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-08T23:02:16+00:00
- Post Title: Settlers VI bba archives

Maybe it's a coincidence, but take a look at the following (list in the end in particular):


```
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 1196988368
Directory Offset High          : 3871155334
Directory Length               : 2058234415
Directory CRC32 CheckSum       : 0xDD03B3C5
Directory Encryption Identifier: 0x45C0E120

File                           : lngencfg1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngengfx0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 3606262391
Directory Offset High          : 879410701
Directory Length               : 1065294082
Directory CRC32 CheckSum       : 0xA8C04462
Directory Encryption Identifier: 0xAB9B9126

File                           : lngengfx1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngensnd0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 2959249868
Directory Offset High          : 3740051079
Directory Length               : 1520614706
Directory CRC32 CheckSum       : 0xE0AC2FC3
Directory Encryption Identifier: 0x260937EA

File                           : lngensnd1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngenvid0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 4192530955
Directory Offset High          : 3751230659
Directory Length               : 4002790725
Directory CRC32 CheckSum       : 0x8EF74859
Directory Encryption Identifier: 0x53727CFB

File                           : lngenvid1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngnlcfg0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 3570510255
Directory Offset High          : 3965622274
Directory Length               : 2881330263
Directory CRC32 CheckSum       : 0xDC3923E9
Directory Encryption Identifier: 0xF514FFBC

File                           : lngnlcfg1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngnlgfx0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 1376497629
Directory Offset High          : 1317855434
Directory Length               : 1009338530
Directory CRC32 CheckSum       : 0xDB298A73
Directory Encryption Identifier: 0x411B5FF8

File                           : lngnlgfx1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngnlsnd0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngnlsnd1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngnlvid0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : lngnlvid1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : shrgcfg0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 2975153854
Directory Offset High          : 3553821097
Directory Length               : 1591050018
Directory CRC32 CheckSum       : 0x5568F363
Directory Encryption Identifier: 0x4D38FD74

File                           : shrgcfg1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 1960815207
Directory Offset High          : 3462568127
Directory Length               : 1108658202
Directory CRC32 CheckSum       : 0xC3FAE21E
Directory Encryption Identifier: 0x3D580DEE

File                           : shrgmap0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 2647765936
Directory Offset High          : 1909630748
Directory Length               : 2636763174
Directory CRC32 CheckSum       : 0xCBBD6527
Directory Encryption Identifier: 0x236D5A34

File                           : shrgmap1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 800859420
Directory Offset High          : 1607494606
Directory Length               : 828932505
Directory CRC32 CheckSum       : 0xC0DBC58E
Directory Encryption Identifier: 0x991B2868

File                           : shrlgfx0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 3546334276
Directory Offset High          : 2611121269
Directory Length               : 534973197
Directory CRC32 CheckSum       : 0xC597E6F5
Directory Encryption Identifier: 0x3AA333D2

File                           : shrlgfx1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : shrlmnu0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 1040582878
Directory Offset High          : 2454405875
Directory Length               : 2821459722
Directory CRC32 CheckSum       : 0x82B83BB5
Directory Encryption Identifier: 0x5BA1F7F2

File                           : shrlmnu1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : shrlsnd0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 3131505170
Directory Offset High          : 2427431120
Directory Length               : 2667128408
Directory CRC32 CheckSum       : 0xFBAFA158
Directory Encryption Identifier: 0xCB280D2F

File                           : shrlsnd1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : shrlvid0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 4278376358
Directory Offset High          : 3711618061
Directory Length               : 2464262524
Directory CRC32 CheckSum       : 0x8AEB58C8
Directory Encryption Identifier: 0x6B481406

File                           : shrlvid1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F

File                           : shrtmed0.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 1036181376
Directory Offset High          : 3818352367
Directory Length               : 3866723845
Directory CRC32 CheckSum       : 0xC90CB949
Directory Encryption Identifier: 0x761DBC8C

File                           : shrtmed1.bba
Archive Header                 : BAF
Version                        : 4
Unknown                        : 5
Header Size                    : 64
Header Encryption Identifier   : 0x29D58DC5
Directory Offset Low           : 39847937
Directory Offset High          : 931131212
Directory Length               : 1924721570
Directory CRC32 CheckSum       : 0xC5D84FDF
Directory Encryption Identifier: 0x7CDBA52F


Key: 0x45C0E120 is used By:
	lngencfg0.bba

Key: 0x7CDBA52F is used By:
	lngencfg1.bba
	lngengfx1.bba
	lngensnd1.bba
	lngenvid1.bba
	lngnlcfg1.bba
	lngnlgfx1.bba
	lngnlsnd0.bba
	lngnlsnd1.bba
	lngnlvid0.bba
	lngnlvid1.bba
	shrlgfx1.bba
	shrlmnu1.bba
	shrlsnd1.bba
	shrlvid1.bba
	shrtmed1.bba

Key: 0xAB9B9126 is used By:
	lngengfx0.bba

Key: 0x260937EA is used By:
	lngensnd0.bba

Key: 0x53727CFB is used By:
	lngenvid0.bba

Key: 0xF514FFBC is used By:
	lngnlcfg0.bba

Key: 0x411B5FF8 is used By:
	lngnlgfx0.bba

Key: 0x4D38FD74 is used By:
	shrgcfg0.bba

Key: 0x3D580DEE is used By:
	shrgcfg1.bba

Key: 0x236D5A34 is used By:
	shrgmap0.bba

Key: 0x991B2868 is used By:
	shrgmap1.bba

Key: 0x3AA333D2 is used By:
	shrlgfx0.bba

Key: 0x5BA1F7F2 is used By:
	shrlmnu0.bba

Key: 0xCB280D2F is used By:
	shrlsnd0.bba

Key: 0x6B481406 is used By:
	shrlvid0.bba

Key: 0x761DBC8C is used By:
	shrtmed0.bba

```


Are you sure this header is encrypted? Seems odd that so many files would have the same EncryptionKey (after encryption).
## Post #5
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-08T23:05:55+00:00
- Post Title: Settlers VI bba archives

Well it's just a guess that the files are encrypted, at least the directory.
But where do you know that this the encryption key?
## Post #6
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-08T23:09:44+00:00
- Post Title: Settlers VI bba archives

Oh, sorry, i just now see that your are talking about settlers 5, not 6, sorry 

I built it from spec at [http://wiki.xentax.com/index.php/Settle ... _An_Empire](http://wiki.xentax.com/index.php/Settlers_-_Rise_Of_An_Empire)
## Post #7
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-08T23:29:43+00:00
- Post Title: Settlers VI bba archives

I see. Thanks for the info, I didn't know nevermind already found something out.
## Post #8
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-09T13:46:06+00:00
- Post Title: Settlers VI bba archives

But I doubt he will give us the algorithm.
## Post #9
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-09T17:22:13+00:00
- Post Title: Settlers VI bba archives

To bad  Without the bold parts, we'll be lost  

> The encryption algorithm is a modified TEA version (it has the same characteristic bitshifts) 
>
> 	There exists multiple versions of the same algorithm but with different 128-bit keys and different deltas 
>
> 	The Encryption Identifier will tell you which algorithm to use
>
> 
>
> ...
>
> 
>
> Example: We have a file with File Type Identifier 1. We look at slot 1 of the encryption table and will find the value: 0x9BB3F065. This tells us that we have a file that is compressed and that the first 16 Bytes of the filedata are encrypted with a simple XOR-algorithm.
## Post #10
- Username: nevermind
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Oct 09, 2007 10:38 pm
- Post datetime: 2007-10-09T18:43:20+00:00
- Post Title: Settlers VI bba archives

You can find out the decryption algorithm by disassembling the exe of Settlers 5 - it's the same, just look for the constant 0x9E3779B9. But without the right keys it's useless. Don't ask for them - I don't know 

PS: PNG or MP3 files are not compressed or encrypted. Maybe you can extract the music without the knowledge of the algorithms
## Post #11
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-09T18:59:48+00:00
- Post Title: Settlers VI bba archives

> Reply from nevermind
>
> You can find out the decryption algorithm by disassembling the exe of Settlers 5 - it's the same, just look for the constant 0x9E3779B9. But without the right keys it's useless. Don't ask for them - I don't know 

PS: PNG or MP3 files are not compressed or encrypted. Maybe you can extract the music without the knowledge of the algorithms

Wouldn't I need to know how to decrypt the data in the header to find the position of the directory structure, which in turn is required to find the data files? The offsets don't make sense at this time (thanks for the info tho).

I probably won't get any further on my own, I have no experience with dissasembling exe's (as a .NET developer, I only deal with managed languages. This also means I havn't had the need for a debugger other then the one MS ships with Visual Studio...). 

In short: I need help
## Post #12
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-09T19:13:03+00:00
- Post Title: Settlers VI bba archives

At the moment we can't do anything unless we get an exe with removed copy protection (e.g. most No-CDs)
We need the right keys to decrypt the directory.
## Post #13
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-09T19:36:07+00:00
- Post Title: Settlers VI bba archives

Well, I started to look at files with a HEX editor, most of the small files are 100% alike, but other then that, I didn't notice much.

All *1.bba files are 1kb, with only two exceptions:

shrgcfg1.bba (7KB)
shrgmap1.bba (well over 5 MB)

I did find something interesting when viewing the files with a hex editor.

The file lngnlgfx0.bba has a unencrypted PNG file header (89  50  4e  47  0d  0a  1a  0a), starting at address 0x50, 0x3E4C0 and 0x5F308.
This means the first 80 bytes must be the header, according to the specs, this adds up, so far, so good.

Update
Decided to check all files, another unencrypted png header was found:
shrgmap1.bba Found PNG header (89 50 4E 47 0D 0A 1A 0A) @ 0x551868
/Update

The fact that in the specs it says 

> byte {44}     - null
is wrong, there is data there.

Something else i tried to check was find multiple instances of 0x29D58DC5 to hopefully locate the directory entry. No such luck, so that entry must eather be encrypted or just not present. Without that info, we don't know how big the files are, etc :-/ 

So far, it's all confusing, but I am glad i at least could find out some more bits and pieces
## Post #14
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-11T01:32:12+00:00
- Post Title: Settlers VI bba archives

Well, at least there is some good news 

I have managed to write a small tool that is able to extract mp3's from the archives.

In short: I've implemented the MP3 format, created a file scanner to look for the format and use the MP3 headers to calculate the required positions.

There are still a lot of bugs, etc, and I edit code on the fly at the moment, so nothing worthy of releasing yet, but as soon as I have put something togeather that is usable by other people, I'll make sure to post it here.

So far I was able to extract about 80-90% of all mp3's inside, so I am quite happy  I was also able to find the songs I was looking for.

To make sure other people won't miss out on these great songs, I'll work on a stand alone tool that extracts the three songs I have found only (I can do that safely).

Cheers,


Nick Kusters.
## Post #15
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-11T09:14:50+00:00
- Post Title: Settlers VI bba archives

Good Work!

> Reply from NKCSS
>
> To make sure other people won't miss out on these great songs, I'll work on a stand alone tool that extracts the three songs I have found only (I can do that safely).
Why create a tool for 3 songs  Why don't you just release those 3 songs in an archive, isn't that easier?
## Post #16
- Username: john_doe
- Rank: VIP member
- Number of posts: 80
- Joined date: Sat Oct 21, 2006 9:25 pm
- Post datetime: 2007-10-11T10:38:20+00:00
- Post Title: 

> Reply from Rheini
>
> isn't that easier?

That wouldn't be quite legal.
## Post #17
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-11T11:29:38+00:00
- Post Title: 

Yup, this way, people who have bought the game can extract it, it is still copywrighted material.
## Post #18
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-11T13:29:02+00:00
- Post Title: 

good ol' copyright
## Post #19
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-11T23:30:52+00:00
- Post Title: 

Here's the tool I promissed 

Let me know what you think 


Sincerely,


Nick Kusters


N.B.


I invested quite some time to create this tool. Future tools might just create scripts to work with this one since it offers a large part to what is needed to get the data we want 
[NDE.zip](https://xentaxbackup.github.io/file/1352_NDE.zip)
## Post #20
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-12T05:06:51+00:00
- Post Title: 

Good work man 
But I personally really hate setups for such small apps, so I won't test it
## Post #21
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-12T05:17:22+00:00
- Post Title: 

> Reply from Rheini
>
> Good work man 
But I personally really hate setups for such small apps, so I won't test it

It's to handle File extention Registration, better then including .reg files, don't you think??
## Post #22
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-12T05:20:30+00:00
- Post Title: 

> Reply from Rheini
>
> Good work man 
But I personally really hate setups for such small apps, so I won't test it

Since there is no setup, there is also no dependancy requirement now, so:

You need to have the .NET Framework 2.0 installed to run this application. You can get it here: [http://www.microsoft.com/downloads/deta ... laylang=nl](http://www.microsoft.com/downloads/details.aspx?FamilyID=0856EACB-4362-4B0D-8EDD-AAB15C5E04F5&displaylang=nl)

Update:

Removed attatchment, get newer version!
## Post #23
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2007-10-12T06:05:22+00:00
- Post Title: 

> Reply from NKCSS
>
> Rheini wrote:Good work man 
But I personally really hate setups for such small apps, so I won't test it 

It's to handle File extention Registration, better then including .reg files, don't you think??
I don't say it's bad to have a setup!  Most users prefer it cause it's easier, but I personally don't like it.
## Post #24
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T10:54:23+00:00
- Post Title: 

I have good news and bad news 

The good news is:

I've managed to write an algo that is able to extract all mp3 files within the roughly 400MB lngensnd0.bba file (6401 mp3s).

I have randomly tested a bunch of them, and they all worked great!

The bad news is the other big sound archive (shrlsnd0.bba) is a lot different then the archive I've just cracked 

With the lngensnd0.bba archive, i had to use my MP3 Frame calculations and substract 1 byte from it to end up at the correct address (this has nothing to do with the padded bit, they just seemed to have clipped 1 byte from each mp3 frame in that file).

In the other archive, I don't have to remove that byte to end up at the correct address.

So far so good, but after 64 mp3's in the shrlsnd0.bba, things go wrong.

I am able to get 1 mp3 frame, then end up lost. This continues over and over (might be and ID3v2.* thing, will have to look into that). The other thing is, that uncompressed PCM Wave files also reside within the archive (have a list of addressed within the archive so that i can take a look at them).

So, the next step will be for me to pull out my old WAVE code I have written ages ago, and read in the headers to extract those aswell and find a way to skip those parts when I am looking for more mp3s.

Hope this all makes sence,


Nick Kusters.
## Post #25
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T10:56:47+00:00
- Post Title: 

Almost forgot, I have been working on the NKCSS Data Extractor a bit aswell. An updated version will be posted shortly (needed to add relative path support and some other minor fixes). 

This version will be able to handle the new script I have created to dump the lngensnd0.bba file
## Post #26
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T11:40:31+00:00
- Post Title: 

Here's an updated version of the NKCSS Data Extractor tool (v1.0.1).

I have added relative path support for .nde scripts to facilitate large amounts of files to be put in subfolders relative to the script file to make sure your Windows Explorer doesn't go mad 


Update:
Removed download due to new version, see v1.0.2 on page 3
## Post #27
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T11:45:16+00:00
- Post Title: 

Here's the new script I promissed.

This extracts all 6461 mp3's from the lngensnd0.bba archive.

You need the NKCSS Data Extractor v1.0.1 (which I posted before this file) to make sure this script works (if you use it with the older version, it will create a mess  ).

Let me know what you think!


Sincerely,


Nick Kusters
[lngensnd0.bba.nde.zip](https://xentaxbackup.github.io/file/1356_lngensnd0.bba.nde.zip)
## Post #28
- Username: Savage
- Rank: VIP member
- Number of posts: 559
- Joined date: Sun Apr 17, 2005 6:00 pm
- Post datetime: 2007-10-13T14:32:37+00:00
- Post Title: 

mmm.maybe im' so silly, but i can extract generic data with this program?
In minds, works like dragonunpacker or jaedernaub?
Any example? Any tutorial?
Thanks
## Post #29
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T14:45:56+00:00
- Post Title: 

> Reply from Savage
>
> mmm.maybe im' so silly, but i can extract generic data with this program?
In minds, works like dragonunpacker or jaedernaub?
Any example? Any tutorial?
Thanks

Hehe, sorry if it was a bit unclear as to what this program actualy does.

It's quite simple realy....

* Select a source file (a game archive for example)
* Add what data you would want

* Start offset (decimal system, uint64)
* End offset (decimal system, uint64)
* Filename for the region of data you want to export



This tool then just rips the sections of data from the file and saves it to the specified file.

Easy does it 

I am currently working on a generic tool that is able to generate scripts that work with this tool that is able to detect unencrypted/uncompressed files within larger files.

Sincerely,


Nick Kusters.
## Post #30
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T15:40:42+00:00
- Post Title: 

Havn't posted this one seperately yet, so here's the nde script for the 3 mp3's that caused me to wind up here in the first place 

File: NDE script for the Songs by the Viking character in the Settlers VI game (3 mp3's) (from the lngensnd0.bba archive, which is different from the other script).

Update:

Uploaded new version of the script, the old version contained a wrong sourcefile name, sorry!
[Fixed Settlers Character Songs.zip](https://xentaxbackup.github.io/file/1363_Fixed Settlers Character Songs.zip)
## Post #31
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T15:57:49+00:00
- Post Title: NDE Screenshots

Starting the application by running a script


Selecting the directory where your .bba archives are located


File type filter and file name are pre-filled, you only have to press ok 


Loading DataPart entries


Finished loading, reporting number of entries imported


Selecting wanted files for extraction & pressing Extract Selected files (note the (1) part in the name extention, I have created it so that it will always look for a unique name if the filename specified already exists).


Selecting a full extract, reporting extracted items & total size


Demonstrating the relative filenames


Nother extract


Editing existing entries


Updated entry


Showing updated entry


Showing Created folders relative to the script file


Showing Created folders content.

Hope this gives you a better idea of the application.


Sincerely,


Nick Kusters
## Post #32
- Username: Shockwave
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 13, 2007 10:59 pm
- Post datetime: 2007-10-13T17:38:32+00:00
- Post Title: NDE Screenshots

NKCSS, I've downloaded you program and script. When I try to launch
NKCSS Data Extractor with script you've provided one post before after choosing file to extract I get an exception:
[](http://img220.imageshack.us/my.php?image=errorlq3.jpg)
Something is wrong with path to file. If I click continue I get this:
[](http://img218.imageshack.us/my.php?image=error2pl0.jpg)
And of course after trying to extract files I get another exception: Object reference not set to an instance of an object.

What can be wrong in your program or am I doing smth wrong way?
## Post #33
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T18:21:43+00:00
- Post Title: NDE Screenshots

> Reply from Shockwave
>
> NKCSS, I've downloaded you program and script. When I try to launch
NKCSS Data Extractor with script you've provided one post before after choosing file to extract I get an exception:

Something is wrong with path to file. If I click continue I get this:

And of course after trying to extract files I get another exception: Object reference not set to an instance of an object.

What can be wrong in your program or am I doing smth wrong way?

Did you make sure you have version 1.0.1? It can be downloaded here: [download.php?id=1355](http://forum.xentax.com/download.php?id=1355)


I also created a v1.0.0.0 compattible version of the script if you don't want to download a new version.
[lngensnd0.bba_v1.0.0.0_compatible.nde.zip](https://xentaxbackup.github.io/file/1358_lngensnd0.bba_v1.0.0.0_compatible.nde.zip)
## Post #34
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T18:27:40+00:00
- Post Title: NDE Screenshots

I am very sorry, I just noticed that it's because of the file type registration that it crashes  it sends along padded "" with the path, causing the crash.

You can fix it by going to: Start -> Run -> "C:\Program Files\Nick Kusters Custom Software Solutions\NKCSS Data Extractor\NKCSS Data Extractor.exe" C:\lngensnd0.bba.nde

Then press of (verifying the .nde file path is ok and the install directory).

If you can wait a bit, I could release a new version where this is fixed, but it isn't fully tested yet (implemented threading).

Sorry once again for the bad version, i'll make sure the next one works 


Sincerely,


Nick Kusters
## Post #35
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T18:39:10+00:00
- Post Title: NDE Screenshots

Fixed bug with script paths containing surrounding ""

Made everything threaded (now all processing occurs on it's own thread, not realy multi-threading tasks yet).

Sorry for the bug in the last version  
[NKCSS Data Extractor v1.0.2 Setup.zip](https://xentaxbackup.github.io/file/1359_NKCSS Data Extractor v1.0.2 Setup.zip)
## Post #36
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T23:04:43+00:00
- Post Title: NDE Screenshots

After talking to Peter on MSN, he asked if I was able to get the video files from the game, so I went in and took a peek. It wasn't to hard, so here is the script.

I have added comments and descriptions in the filenames, if you know the character names (couldn't remember and ubisoft page didn't help), it would be nice to give them better names.

I also have a few issues, 1 track seems corrupt, and there is a black video track with leading auto track that crackles a bit, not sure what to think of it.

Besides the BlueByte intro, the UbiSoft intro and the Game opening video, there are no sound files in the archive.

Does anyone know what type of file is used to mix in with .bik files if the audio isn't in a seperate .bik file at that time?


Enjoy,


Nick Kusters.
[shrlvid0.bba.nde.zip](https://xentaxbackup.github.io/file/1361_shrlvid0.bba.nde.zip)
## Post #37
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-13T23:29:55+00:00
- Post Title: NDE Screenshots

Updated version of the script (names) thanks to Shockwave!
[shrlvid0.bba.nde.zip](https://xentaxbackup.github.io/file/1364_shrlvid0.bba.nde.zip)
## Post #38
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-14T01:28:16+00:00
- Post Title: NDE Screenshots

Vids now completely unpacked, here are the missing audio files with the latest NDE script  I am really beginning to love this stuff 

Enjoy!

Sincerely,


Nick Kusters.


N.B.


I have added information to the WiKi with status table for all archives and links to the scripts.
[lngenvid0.bba.nde.zip](https://xentaxbackup.github.io/file/1365_lngenvid0.bba.nde.zip)
## Post #39
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-10-14T02:04:03+00:00
- Post Title: NDE Screenshots

I have been working on some scripts to mux the video's for you, but I am having a problem with combining .bik video files. Sent a mail to their support department, so hope to have something more for you soon 

For most of the files, this isn't a problem tho.

Just download the RAD bink tools from [http://www.radgametools.com/bnkdown.htm](http://www.radgametools.com/bnkdown.htm) and use these commandlines:

Example:

C:\Program Files\RADVideo>binkmix "C:\Settlers VI Video\Settlers VI Video 014 (Picknick ppl at night with Fireworks over Castle).bik" "C:\Settlers VI Audio\Settlers VI Audio 020 (Red Prince and Crimson Sabatt in chains, Perfect Castle, Fireworks, Full History, King).bik" "C:\fireworks.bik"


Ok, i know this is a bad example since you'd need to mux the Red Prince in chains in front of it, but you get the idea 

Sincerely,


Nick Kusters.
## Post #40
- Username: OlaHaldor
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 04, 2007 11:17 pm
- Post datetime: 2007-11-04T22:42:27+00:00
- Post Title: NDE Screenshots

What about the music? I didn't know there was an exclusive version with the soundtrack as a CD before someone mentioned it at the Ubi-forums. Is there any chance there will be tools available to extract the superb music?
## Post #41
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-11-04T22:54:04+00:00
- Post Title: NDE Screenshots

> Reply from OlaHaldor
>
> What about the music? I didn't know there was an exclusive version with the soundtrack as a CD before someone mentioned it at the Ubi-forums. Is there any chance there will be tools available to extract the superb music?

The NDE tool + scripts extracts over 6000 mp3s from the game archives, the music might be in there somewhere (might take some digging thru files).

I have been working on my new website, once that settles down a bit, I'll spend some time in extracting the rest of the archives. As soon as i get some time, I'll create a site for the NDE + scripts (url will be [http://nde.nickkusters.com/](http://nde.nickkusters.com/), but not created yet).
## Post #42
- Username: OlaHaldor
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 04, 2007 11:17 pm
- Post datetime: 2007-11-05T01:45:48+00:00
- Post Title: NDE Screenshots

I sorted all the MP3s by size - and the largest files were about 400 and something kilobytes.. I can't see how those great soundtracks would fit in one of those. I listened to a few of them - it's just several versions of alerts during gameplay in a certain mission from each knight.

I'd suggest you take a look at the vshrlsnd0.bba  Have no idea what it is, though.. 


Edit

OK!! I tried.. Used NKCSS Data Extractor, and opened this file - added from 80 bytes to the full value - and WOHOO! I've got an MP3 containing over 6 hours of material.. Though, when I try to scrub through the MP3, Windows Media Player freeze up. But it's certainly the correct file. 

Edit 2
I opened the MP3 in Nero WaveEditor - the entire soundtrack, including Thordals three songs, are about about 2h 7m  GREAT! All I need to do now really, is cut it up in pieces.. I really appreciate your time in finding a way to revert the bba-files!
## Post #43
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-11-05T16:42:28+00:00
- Post Title: NDE Screenshots

> Reply from OlaHaldor
>
> 
Edit

OK!! I tried.. Used NKCSS Data Extractor, and opened this file - added from 80 bytes to the full value - and WOHOO! I've got an MP3 containing over 6 hours of material.. Though, when I try to scrub through the MP3, Windows Media Player freeze up. But it's certainly the correct file. 

Edit 2
I opened the MP3 in Nero WaveEditor - the entire soundtrack, including Thordals three songs, are about about 2h 7m  GREAT! All I need to do now really, is cut it up in pieces.. I really appreciate your time in finding a way to revert the bba-files!

Good to know  The part where I left of were 68 MP3's into the file, where things got a bit messy. I also noticed that there are WAVE files in the archive. I started to also implement reading WAVE files to parse more of the archive, but it's cool to know that Nero can detect it all.
As soon as I finish some of my current projects, I'll try to finish this one
## Post #44
- Username: OlaHaldor
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Sun Nov 04, 2007 11:17 pm
- Post datetime: 2007-11-06T17:54:44+00:00
- Post Title: NDE Screenshots

I took the MP3-file over to my Mac Pro, and opened it in Soundtrack.

Soundtrack reads the MP3 perfectly, and I can now start exporting each track as its own file. I haven't counted the number of tracks, but there's sure a lot of them.

What are these WAVs you're talking about? The music in better quality?
## Post #45
- Username: NKCSS
- Rank: advanced
- Number of posts: 76
- Joined date: Tue Oct 09, 2007 5:19 am
- Post datetime: 2007-11-06T19:09:21+00:00
- Post Title: NDE Screenshots

> Reply from OlaHaldor
>
> I took the MP3-file over to my Mac Pro, and opened it in Soundtrack.

Soundtrack reads the MP3 perfectly, and I can now start exporting each track as its own file. I haven't counted the number of tracks, but there's sure a lot of them.

What are these WAVs you're talking about? The music in better quality?

I just found WAVE headers inside the archive, didn't have time yet to further explore.
## Post #46
- Username: Rafulpower
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Thu Nov 15, 2007 1:15 am
- Post datetime: 2010-02-25T15:55:50+00:00
- Post Title: Re: Settlers VI bba archives

Hi, people!
I want to translate the dialogs for Portuguese.
How to extract lngencfg0.bba and lngescfg0.bba files?

Thanks.
## Post #47
- Username: Rheini
- Rank: Moderator
- Number of posts: 652
- Joined date: Thu Oct 19, 2006 4:48 am
- Post datetime: 2010-02-25T16:00:44+00:00
- Post Title: Re: Settlers VI bba archives

not possible.
nevermind, who obviously had some extraction code, refused to release it.
## Post #48
- Username: Csimbi
- Rank: veteran
- Number of posts: 108
- Joined date: Fri Nov 07, 2008 4:29 am
- Post datetime: 2010-08-21T21:14:51+00:00
- Post Title: Re: Settlers VI bba archives

Is anyone looking into this?
I would like to extract the LUA files.

I found the appropriate video names:

```
videos\bluebyte_vid.bik
videos\c00_endofact1_vid.bik
videos\c00_endofact2_vid.bik
videos\c00_endofact3_alandra_vid.bik
videos\c00_endofact3_elias_vid.bik
videos\c00_endofact3_hakim_vid.bik
videos\c00_endofact3_kestral_vid.bik
videos\c00_endofact3_marcus_vid.bik
videos\c00_endofact3_thordal_vid.bik
videos\c00_endofact3_vid.bik
videos\c00_endofact4_final1_vid.bik
videos\c00_endofact4_final2_vid.bik
videos\c00_endofact4_final3_vid.bik
videos\c00_endofact4_vid.bik
videos\c00_intro_snd.bik
videos\c00_intro_vid.bik
videos\ubipresents_snd.bik
videos\ubipresents_vid.bik
videos\ubisoft_snd.bik
videos\ubisoft_vid.bik
```

At another location I found the audios (probably separate due to localization issues):

```
videos\c00_endofact1_male_snd.bik
videos\c00_endofact2_female_snd.bik
videos\c00_endofact2_male_snd.bik
videos\c00_endofact3_alandra_full_female_snd.bik
videos\c00_endofact3_alandra_full_male_snd.bik
videos\c00_endofact3_elias_full_female_snd.bik
videos\c00_endofact3_elias_full_male_snd.bik
videos\c00_endofact3_hakim_full_female_snd.bik
videos\c00_endofact3_hakim_full_male_snd.bik
videos\c00_endofact3_kestral_full_female_snd.bik
videos\c00_endofact3_kestral_full_male_snd.bik
videos\c00_endofact3_marcus_full_female_snd.bik
videos\c00_endofact3_marcus_full_male_snd.bik
videos\c00_endofact3_thordal_full_female_snd.bik
videos\c00_endofact3_thordal_full_male_snd.bik
videos\c00_endofact4_final1_full_male_snd.bik
videos\c00_endofact4_final2_full_female_snd.bik
videos\c00_endofact4_final2_full_male_snd.bik
videos\c00_endofact4_final3_full_female_snd.bik
videos\c00_endofact4_final3_full_male_snd.bik
```

And finally, the XML files (that supposedly link video, audio and subtitles together):

```
config\videos\bluebyte.xml
config\videos\c00_endofact1.xml
config\videos\c00_endofact2.xml
config\videos\c00_endofact3.xml
config\videos\c00_endofact3_alandra.xml
config\videos\c00_endofact3_elias.xml
config\videos\c00_endofact3_hakim.xml
config\videos\c00_endofact3_kestral.xml
config\videos\c00_endofact3_marcus.xml
config\videos\c00_endofact3_thordal.xml
config\videos\c00_endofact4.xml
config\videos\c00_endofact4_final1.xml
config\videos\c00_endofact4_final2.xml
config\videos\c00_endofact4_final3.xml
config\videos\c00_intro.xml
config\videos\ubipresents.xml
config\videos\ubisoft.xml
```


I might have missed a few since it's a manual copy-paste.
It should help you in finding out how the strings are stored/encrypted.
## Post #49
- Username: Rockerduck
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Mar 22, 2010 1:52 am
- Post datetime: 2010-12-27T06:23:56+00:00
- Post Title: Re: Settlers VI bba archives

Hiya y'all!

Good to see there are still people working on the game! I am very interested in extracting meshes / textures from the game but I take it this is still very much impossible? I wonder if there's a way to utilize the SEED Map Maker tool to export whatever models you can load into the tool. Probably not. *sigh*

This must be the only game on the planet which isn't moddable. Impressive.
## Post #50
- Username: magnapeccatrix
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Fri Feb 04, 2011 6:15 am
- Post datetime: 2011-02-03T22:35:04+00:00
- Post Title: Re: Settlers VI bba archives

Hello guys;

Is that extractor working? I want to extract mission soundtracks and listen them without playing the game. They are just lovely! I have downloaded the extractor and here is text message:

```
Extracted byte 0 till 416805060 to asd
Extracted 1 files totalling 397MB!
```


Created file has unknown file type. What shall I do with it?

Please help me out extracting mission soundtracks!


Edit: I got it working but extracted .mp3 wont play at all. Any help is welcome.

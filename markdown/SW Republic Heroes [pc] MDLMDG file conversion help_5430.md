## Post #1
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-11-21T23:26:51+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

I managed to unpack the RKV files in Republic Heroes but have had no success in
converting the MDL/MDG files to usable mesh files.    

Has anyone had success with these file types?

Any help with these file types would be GREATLY appreciated!!

- Marc
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2010-11-22T00:10:41+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

no one can help without samples
## Post #3
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-11-22T00:55:48+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

> Reply from chrrox
>
> no one can help without samples

That would be helpful wouldn't it??

Here ya go!



Thanks!!
## Post #4
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-11-23T23:19:08+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

I thought of a couple more things that might help.

The game developer is "Krome Studios".

The file structure seems to be very similar to those found in SW Knights of the Old Republic I & II,
which are MDL and MDX files.
## Post #5
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-11-27T19:05:21+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

Chrrox,

I tried to use the 3DS script you made for the import of Blade Kitten models in this tread:
[viewtopic.php?f=16&t=5098](http://forum.xentax.com/viewtopic.php?f=16&t=5098)

You mentioned the compatibility for Republic Heroes in the BMS script file for QuickBMS. 
So I was hoping that the 3DS script would be compatible also.

However it is returning a "--Unable to convert: undefined to type: Integer" error.

Any ideas on what might be causing this error?


Thanks for your help!
## Post #6
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-12-01T22:34:57+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

If someone could help, that would be great!
If not, please let me know and I stop checking this thread.
## Post #7
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-12-04T05:11:34+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

WOW, YOU GUYS SURE ARE HELPFUL HERE!!
## Post #8
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-12-05T01:42:06+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

Wow, That sure is the way to get people that have no vested interest in helping you to rip a model so you can make a helmet out of paper and show all your friends how talented you are  to help you

Maybe next time you could do a little research yourself, instead of acting like corporate America and barking orders
## Post #9
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-12-05T06:52:09+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

Sadly there seems to be little interest in this game and it looks like the author of this thread became impatient and removed his link to the mdg samples too so i uploaded more HERE (samples provided upon request) if anyone wants to pick them apart.  

@Zerovisibilite
You mentioned [here](http://forum.xentax.com/viewtopic.php?p=44598#p44598) that the tex files are just dds textures without the header, so how would you go about making these readable by Photoshop to be viewed properly? I tried to insert headers from working dds textures into the beginning of the tex file but when i open it in PS it is just pixelated colors.
## Post #10
- Username: Zerovisibilite
- Rank: n00b
- Number of posts: 19
- Joined date: Sun Jun 13, 2010 9:41 am
- Post datetime: 2010-12-05T13:40:29+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

Basiclly if you look at the last couple bytes of the tex file , it will tell you the length and width. then i just took a raw dds file and copied the header from that to the top of the text file. You can leave all the info in the tex file as most if not all will look at the header to decide how long the file is and not the file itself. Then change the Length and width values in the new header to the values that were stored in the bottem.

here is the actual code for the vb stuff i was doing
This is in a seperate module but i am including it so yoiu can see the data structures

Type Texture_MK_HeaderInfo
    MK_Header As String * 4
    MK_Width As Integer
    MK_Height As Integer
    MK_Unknown1 As Integer
    MK_Mips As Byte
    'Start Pixel Info at 54
End Type

Type DDS_DXT1_HeaderInfo
    ddsMiscHeader(1 To 12) As Byte
    ddsWidth As Long
    ddsHeight As Long
    ddsHolder1 As Byte
    ddsHolder2 As Long
    ddsHolder3 As Byte
    ddsHolder4 As Integer
    ddsMipMap  As Integer
    ddsHolder6 As Byte
    ddsFin(96) As Byte
End Type


This is the begining of the meat and potato code that does the copy and paste

Dim DDS_Info As DDS_DXT1_HeaderInfo
Dim MK_info As Texture_MK_HeaderInfo
Dim MKPixels() As Byte
    ddsFilename = App.Path & "\DXT1Header.hex"
    Open ddsFilename For Binary As #1
        Get #1, 1, DDS_Info
    Close #1

    file_length = FileLen(TextureFilename)
    ReDim MKPixels(1 To file_length)
    Open TextureFilename For Binary As #1
        Get #1, file_length - 47, MK_info '1     33960'2    '287959
        'Get #1, 220885, PSKFAce '1     33960'2    '287959
        Get #1, 1, MKPixels
    Close #1
    test0 = UBound(MKPixels)
    Test1 = MK_info.MK_Header
    Test2 = MK_info.MK_Width
    Test3 = MK_info.MK_Height
    Test4 = MK_info.MK_Unknown1
    Test5 = MK_info.MK_Mips

    Test8 = DDS_Info.ddsHeight
    Test9 = DDS_Info.ddsWidth
    Test10 = DDS_Info.ddsMipMap

    DDS_Info.ddsHeight = MK_info.MK_Height
    DDS_Info.ddsWidth = MK_info.MK_Width
    DDS_Info.ddsMipMap = MK_info.MK_Mips

    Open OutputDDSFilename For Binary As #1
        Put #1, 1, DDS_Info '1     33960'2    '287959
        Put #1, , MKPixels
    Close #1
Based on the code i used it looks like the information in the tex file is 48 bytes before the end of the file

I can take a look at revamping is project a little but I wouldn't hold your breath on how long it will be. I am really swamped at work
## Post #11
- Username: Acewell
- Rank: VIP member
- Number of posts: 1330
- Joined date: Wed Nov 05, 2008 7:16 pm
- Post datetime: 2010-12-05T22:13:26+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

Thank you for this information it works great!   



Edit: Fixed image
## Post #12
- Username: NullARC
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Sun Nov 21, 2010 10:34 pm
- Post datetime: 2010-12-10T23:23:28+00:00
- Post Title: SW Republic Heroes [pc] MDL/MDG file conversion help

> Reply from Zerovisibilite
>
> Wow, That sure is the way to get people that have no vested interest in helping you to rip a model so you can make a helmet out of paper and show all your friends how talented you are  to help you

Maybe next time you could do a little research yourself, instead of acting like corporate America and barking orders

If you would look at the posts I did do my research and I never made a single "order". Every time I posted, I asked kindly and with respect. So you can get off your high horse Zero. And who said anything about paper helmets??

Sorry that I got frustrated.
I posted multiple times with additional information and waited WEEKS without another single comment.


Thank you Acewell and Zero for your help, I truly appreciate it.

- Marc

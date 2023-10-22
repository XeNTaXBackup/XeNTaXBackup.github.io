## Post #1
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2010-03-02T20:17:46+00:00
- Post Title: Heroes of Might and Magic 1

Hey all you genius's   

Heroes 1 contains a single file "heroes.agg" that i have managed to extract.
However, there are a lot of different files there that have a old strange format.

EG: The BMP files are not the standard windows bitmap, instead a word header, width, height and then uncompressed data.  Simple enough.

However, there are other files there.
ICN - Is an archive of sprites with a difficult header - I know the first 2 bytes are a word for the number of files, but how do I get a list of images and get those images.
There are also ATK / STD / WIP / FNT and WLK files that I have no idea how to access.

This is obviously from the old, heydays of PC gaming, so I was wondering if anyone had a  format or some code in delphi / pascal (      ) for me to look through to get access to this data.

PS: If you need some example files, I can upload, they about 200K unzipped, just not sure where to upload to tho
## Post #2
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-02T22:23:59+00:00
- Post Title: Heroes of Might and Magic 1

Upload them here. You should be fine.
## Post #3
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2010-03-03T02:37:03+00:00
- Post Title: Heroes of Might and Magic 1

Hi.

Thanks a lot.

Here's some examples, I can always up more if needed

Regards
[Heroes1Files.zip](https://xentaxbackup.github.io/file/2833_Heroes1Files.zip)
## Post #4
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-07T22:56:31+00:00
- Post Title: Heroes of Might and Magic 1

Ok, I had to have some time to take a look at it. It is beginning to make sense now. I will move this to the Graphics Format forum, where it belongs. 

Anyway, the files of the sprites contain frames for standing (std), walking (wlk) and attacking (atk), right? Right. 

it starts off with a table that tells of how many frames, where they start and such. Let's figure that in detail out later. 

The image format is what is higher on the priority list. After the table come all the images. The images have 127 colours. Not 128, and not 256. Why? Because they needed the extra bits to tell the image creator additional info. In this respect, an 0x80 (128 in decimal numbers) means 'image end', so the reader knows that the image has ended. Start off an image with that and you'll see no picture is displayed. 
a byte value of 128 means bit 7 (as in 0 - 7) is set. Not a colour value, but a message to the reader. If a section starts off with a 0x81 (129) or higher, then a horizontal line starts. Actually, that is an X-offset of the line start. You see, each image is drawn relative to the x position on screen, right? Well, if 0x80 means END OF IMAGE, then 0x81 mean relative X coordinate 0 (as in Xonscreen + Xrelative = Xonscreen for drawing). Standard sprites (as in computer slang) have a range of 70 pixels wide, so 0xc9 (199) is about max, but the maximum relative x offset limit is 0xff-0x81 (126) to start the sprite image horizontal line. The next byte is the number of pixels that follow. So theoretically, the maximum width of a horizontal line in pixels is 255, starting at relative offset 0-126. Lastly, the colour-bytes of each pixel follow. 

So the image data is build up like: 

```

// Horizontal line 

[1] Relative X-offset (0x80 - END OF IMAGE, 0x81 - FF - offset)
[1] Number of pixels (n)
[n] pixel colour (1-127)
[1] Termination (0) byte. If there is not termination, then there is a new relative offset byte, indicating to continue the line relative from the current position on screen

```


EDIT : Here's a partial reconstruct to prove the theory. I used the Elf.std file I extracted from the heroes.agg file with MultiEx Commander.



image2_elfstd.raw.bmp.jpg (14.41 KiB) Viewed 426 times
## Post #5
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-08T23:03:47+00:00
- Post Title: Heroes of Might and Magic 1

Okay, so the palettes are standard rgb (768 bytes) of 256 in total. However, there are for each sprite model only 127 colours to use. The palette files (.pal) have something like a right shifted RGB values. Left shifting them again gives a 97% accurate palette.



image2_elfstd.raw.bmp.png (3.13 KiB) Viewed 392 times





gargoyle.std_2.png (4.54 KiB) Viewed 393 times





gargoyle.std_3.png (4.58 KiB) Viewed 393 times





gargoyle.std_4.png (4.32 KiB) Viewed 393 times





gargoyle.std_6.png (4.83 KiB) Viewed 393 times
## Post #6
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2010-03-10T10:35:04+00:00
- Post Title: Heroes of Might and Magic 1

Damn - thats amazing - don't know how you got there so fast.

I played around for a week or 2 and only got the big files format.

Thanks for all the effort so far
## Post #7
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-10T10:52:47+00:00
- Post Title: Heroes of Might and Magic 1

Well, the format still has some more tricks that my converter does not tackle yet, I will have to do some more thinking about the properties of some images that don't come out right. The method is a nice way of compressing bitmaps obsiously, as a 4K compressed image is about 12K decompressed.
## Post #8
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-12T06:39:28+00:00
- Post Title: Heroes of Might and Magic 1

Right, so I've got a small converter working that will convert to BMP, but I notice some can still not be shown. So more research to be done.
## Post #9
- Username: MasterRipper
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Wed May 27, 2009 8:33 pm
- Post datetime: 2010-03-12T07:59:32+00:00
- Post Title: Heroes of Might and Magic 1

Thanks Mr. Mouse for all the hard work. 

It is really appreciated.
## Post #10
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-13T10:55:31+00:00
- Post Title: Heroes of Might and Magic 1

Allrightey, here's a crude viewer. Select HOMM1 Image in the first drop down box and click Convert. 

You can open: .std, .wip, .atk and .wlk files.



homm1c.png (30.22 KiB) Viewed 297 times
## Post #11
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-03-14T23:27:48+00:00
- Post Title: Heroes of Might and Magic 1

Ok, here is the tool that will let you view and convert to a folder of your choice.


 HOMM1C_1_3.zip
(27.88 KiB) Downloaded 59 times



It will open ATK, WLK, ICN, BMP, STD and WIP files at the moment. 

A few extracts:



heroes.PNG (127.31 KiB) Viewed 263 times





newgame.PNG (49.11 KiB) Viewed 262 times
## Post #12
- Username: xman2000
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-07-04T21:11:53+00:00
- Post Title: Heroes of Might and Magic 1

Here's the latest version of HOMM1C:

Not idiot proof. And probably buggy. 

Opens .std, .atk, .wlk, .wip, .icn, .bmp, .xtl, .til and what not. 


 HOMM1C_1_4.zip
Added more functionality (151.86 KiB) Downloaded 63 times





homm1c_1_4.JPG (158.93 KiB) Viewed 203 times
## Post #13
- Username: Mr.Mouse
- Rank: Site Admin
- Number of posts: 4073
- Joined date: Thu Jan 16, 2003 1:45 am
- Post datetime: 2010-07-05T20:01:46+00:00
- Post Title: Heroes of Might and Magic 1

I wrote the program in lousy VB6, but here's the source for decompressing and compressing the sprite data:

```

Dim b As Byte
Dim c As Byte
Dim xit As Boolean
Dim sil As Boolean
Dim cc As Long
Dim ch As Long
Dim ci As Long
'Dim datat() As Byte
Dim rl() As Byte
On Error GoTo hell
xit = False
sil = (typ = 2)
ReDim datat(h * w - 1)
cc = 0: ch = 0: ci = 0
While Not xit
b = data(cc)
Select Case b
Case 0: DoEvents
        If w > li Then
        ch = ch + (w - li)
        ReDim Preserve datat(ch - 1)
        For T = 0 To (w - li) - 1
        datat(ci + T) = 0
        Next T
        ci = ci + (w - li)
        End If
        li = 0:
        cc = cc + 1
        l = l + 1
Case 128: xit = True
Case 129 To 255:    b = b - 128
                    ch = ch + b
                    ReDim Preserve datat(ch - 1)
                    For T = 0 To b - 1
                    datat(ci + T) = 0
                    Next T
                    ci = ci + b
                    li = li + b
                    cc = cc + 1
Case 1 To 127:      c = data(cc + 1)
                    If sil = True Then
                     ch = ch + b
                     ReDim Preserve datat(ch - 1)
                     For T = 0 To b - 1
                     datat(ci + T) = 1
                     Next T
                     li = li + b
                     ci = ci + b
                     cc = cc + 1
                     If c = 0 Then
                        If w > li Then
                             ch = ch + (w - li)
                             ReDim Preserve datat(ch - 1)
                             For T = 0 To (w - li) - 1
                             datat(ci + T) = 0
                             Next T
                             ci = ci + (w - li)
                         End If
                     li = 0: l = l + 1: cc = cc + 1
                     End If
                    
                    Else 'sil not true
                    ch = ch + b
                    cc = cc + 1
                    ReDim Preserve datat(ch - 1)
                    
                    For T = 0 To b - 1
                    datat(ci + T) = data(cc + T)
                    Next T
                    li = li + b
                    cc = cc + b
                    ci = ci + b
                    
                    End If
                   
End Select
Wend
DecompressHOMM1Bitmap = True
Exit Function
hell:
DecompressHOMM1Bitmap = False
End Function
```


```
Dim nulc As Byte
Dim col() As Byte
Dim con As Long
Dim con2 As Long
Dim colc As Byte
Dim xcon As Integer
Dim osize As Long
Dim wn As Integer
On Error GoTo hell

wn = w
con = 0: con2 = 0: xcon = 0: nulc = 0

osize = Abs(w) * Abs(h)

ReDim datat(osize * 2) 'just to be sure , will reduce later
While con < osize
If nulc > 100 Then
DoEvents
End If
  Select Case data(con)
  Case 0:    DoEvents
             If colc > 0 Then
             datat(con2) = colc
             con2 = con2 + 1
             If typ = 1 Then
             CopyMemory datat(con2), col(0), colc
             con2 = con2 + colc
             End If
             xcon = xcon + 1
             nulc = nulc + 1
             colc = 0
             Else
             xcon = xcon + 1
               nulc = nulc + 1
             End If
             If nulc = 127 Then
             datat(con2) = 255
             con2 = con2 + 1
             nulc = 0
             End If
  Case Else: DoEvents
             If nulc > 0 Then
             nulc = nulc + 128
             datat(con2) = nulc
             con2 = con2 + 1
             nulc = 0
             End If
             ReDim Preserve col(colc)
             col(colc) = data(con)
             colc = colc + 1
             xcon = xcon + 1
             If colc = 127 Then
               datat(con2) = colc
               con2 = con2 + 1
               If typ = 1 Then
                 CopyMemory datat(con2), col(0), colc
                 con2 = con2 + colc
               End If
               If colc = w Then
                datat(con2) = 0
               con2 = con2 + 1
               End If
             colc = 0
             End If
  End Select
    con = con + 1
If xcon = w Then
    If nulc > 0 Then
    datat(con2) = 0
    con2 = con2 + 1
    End If
    If colc > 0 Then
            datat(con2) = colc
             con2 = con2 + 1
             CopyMemory datat(con2), col(0), colc
             con2 = con2 + colc
   datat(con2) = 0
    con2 = con2 + 1
             colc = 0
    End If
    xcon = 0
    nulc = 0
    con = con + (wn - w)
  End If
Wend
ReDim Preserve datat(con2)
datat(con2) = 128
CompressHOMM1Bitmap = True

Exit Function
hell:
Debug.Print Err.Description; CompressHOMM1Bitmap = False
End Function
```
## Post #14
- Username: Cyrus Annihilator
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 10, 2011 2:46 am
- Post datetime: 2011-08-16T13:30:01+00:00
- Post Title: Heroes of Might and Magic 1

Hi there, I'm a fan of Heroes of Might and Magic series and want to extract to sprites of this game.
I'm having problems with the program, the files that I extracted from "heroes.agg" are openned with wrong colors:


What I should do?
## Post #15
- Username: Nazaroff
- Rank: advanced
- Number of posts: 40
- Joined date: Mon Oct 11, 2010 7:30 pm
- Post datetime: 2011-08-18T17:46:17+00:00
- Post Title: Heroes of Might and Magic 1

[HERE](http://sites.google.com/site/sergroj/heroes) you can find good tools for unpacking and graphic converting from heroes 1and heroes 2. With sources!
## Post #16
- Username: Cyrus Annihilator
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Wed Aug 10, 2011 2:46 am
- Post datetime: 2011-08-19T20:40:54+00:00
- Post Title: Re: Heroes of Might and Magic 1

This is all that I need!
Thank you very much Nazaroff!!!

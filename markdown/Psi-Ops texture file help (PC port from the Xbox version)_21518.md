## Post #1
- Username: Kainalo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 21, 2019 2:51 am
- Post datetime: 2019-12-20T21:11:14+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

Hey! I've been trying to look into Psi-Ops: The Mindgate Conspiracy PC version textures to hopefully modify the hud elements a bit. The game archive has multiple .tex files which are all 44bytes and a XBOX_global_texture_buffer.tbx file(Linked below). I've been able to make the tbx file a bit more clearer with TextureFinder and Raw Texture Cooker (DXT5), but it looks like I can never get the full image to be clear, only sections. So I assume it's somehow compressed from multiple parts but I have no idea how. I'd appreciate any help on how to modify the file in a proper way and then save it in the proper format.

[https://drive.google.com/file/d/1FF1OK- ... sp=sharing](https://drive.google.com/file/d/1FF1OK-3sX-8paBGPsl6LvKo01RpfeRV3/view?usp=sharing)

Here's the archive that includes the UI files (I think) 
[https://drive.google.com/file/d/19Jqlng ... sp=sharing](https://drive.google.com/file/d/19JqlngoElWuVNtZiz_x7GsTZ54UYkPZ2/view?usp=sharing)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-23T16:27:23+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

Wrapped raw data with PVRTexTool on LEVEL00U.w32:



icon.jpg (82.68 KiB) Viewed 143 times



The XBOX_global_texture_buffer.tbx has a copy in LEVEL00U.w32, did you get it by unpacking the .w32 file?
## Post #3
- Username: Kainalo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 21, 2019 2:51 am
- Post datetime: 2019-12-23T17:44:29+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

Yes I got that from unpacking the .w32 file.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-24T01:46:31+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

> Reply from Kainalo ↑Tue Dec 24, 2019 1:44 am at Tue Dec 24, 2019 1:44 am
>
> 
Yes I got that from unpacking the .w32 file.
With what?
## Post #5
- Username: Kainalo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 21, 2019 2:51 am
- Post datetime: 2019-12-24T09:23:31+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

> Reply from Bigchillghost ↑Tue Dec 24, 2019 9:46 am at Tue Dec 24, 2019 9:46 am
>
> 
Kainalo wrote: ↑Tue Dec 24, 2019 1:44 am
Yes I got that from unpacking the .w32 file.

With what?

Watto Game Extractor. The archive looks like this unpacked
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-24T12:34:05+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

Here's a BMS script that'll convert all tex files in the w32 archive to dds dxt5 format, and extract all the contents like the tool you used.
[w32TexConv.zip](https://xentaxbackup.github.io/file/17228_w32TexConv.zip)
## Post #7
- Username: Kainalo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 21, 2019 2:51 am
- Post datetime: 2019-12-26T10:28:54+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

> Reply from Bigchillghost ↑Tue Dec 24, 2019 8:34 pm at Tue Dec 24, 2019 8:34 pm
>
> 
Here's a BMS script that'll convert all tex files in the w32 archive to dds dxt5 format, and extract all the contents like the tool you used.

Oh thanks so much! Any chance of packing the files up after editing some of them? Also happy holidays!
## Post #8
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2019-12-26T15:36:06+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

> Reply from Kainalo ↑Thu Dec 26, 2019 6:28 pm at Thu Dec 26, 2019 6:28 pm
>
> Any chance of packing the files up after editing some of them?
You might use the following scripts for reimport:


 Repacking.zip
(903 Bytes) Downloaded 27 times



Usage:
1. Unpack and convert the textures to DDS with previous script(w32TexConv.bms).
2. Edit the textures as you pleased, but be aware that you must NOT change the pixel format, and its size, that is, no MIPs are allowed.
3. Create a folder along the w32 file that's to be repacked, named as in the following format: "<filename>_repack". 
For instance, "LEVEL00U_repack" for the file "LEVEL00U.w32". Copy or move your edited dds textures into this folder.
4. Run the script "DDS2PXL.bms" on all the dds textures (using wildcard "*.dds") in the folder. This should convert all your edited textures to raw pixel data files.
5. Backup your w32 file before repacking. Run "reimport2.bat" from the QuickBMS folder, select the script "w32Repacking.bms" from this attachment, then the exact w32 file that you unpacked your files from, in this case, "LEVEL00U.w32". That should reimport the pixel data back to the archive.

Theoretically it'll work for all unpacked files, but it's your job to make sure you know what you're doing.

Have fun!
## Post #9
- Username: Kainalo
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Sat Dec 21, 2019 2:51 am
- Post datetime: 2019-12-26T19:16:09+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

> Reply from Bigchillghost ↑Thu Dec 26, 2019 11:36 pm at Thu Dec 26, 2019 11:36 pm
>
> 
Kainalo wrote: ↑Thu Dec 26, 2019 6:28 pmAny chance of packing the files up after editing some of them?

You might use the following scripts for reimport:
Repacking.zip


Usage:
1. Unpack and convert the textures to DDS with previous script(w32TexConv.bms).
2. Edit the textures as you pleased, but be aware that you must NOT change the pixel format, and its size, that is, no MIPs are allowed.
3. Create a folder along the w32 file that's to be repacked, named as in the following format: "<filename>_repack". 
For instance, "LEVEL00U_repack" for the file "LEVEL00U.w32". Copy or move your edited dds textures into this folder.
4. Run the script "DDS2PXL.bms" on all the dds textures (using wildcard "*.dds") in the folder. This should convert all your edited textures to raw pixel data files.
5. Backup your w32 file before repacking. Run "reimport2.bat" from the QuickBMS folder, select the script "w32Repacking.bms" from this attachment, then the exact w32 file that you unpacked your files from, in this case, "LEVEL00U.w32". That should reimport the pixel data back to the archive.

Theoretically it'll work for all unpacked files, but it's your job to make sure you know what you're doing.

Have fun!

Thank you so much!! Time to fix up the UI textures
## Post #10
- Username: Cofeefe
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Jan 23, 2023 9:24 pm
- Post datetime: 2023-01-23T13:36:41+00:00
- Post Title: Psi-Ops texture file help (PC port from the Xbox version)

> Reply from Bigchillghost ↑Tue Dec 24, 2019 8:34 pm at Tue Dec 24, 2019 8:34 pm
>
> 
Here's a BMS script that'll convert all tex files in the w32 archive to dds dxt5 format, and extract all the contents like the tool you used.
I can't open these .dds files. I have tried with Gimp and paint.net.
Any idea as to what am doing wrong?

## Post #1
- Username: mehrdad995gta
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 19, 2016 10:13 pm
- Post datetime: 2020-05-24T14:13:38+00:00
- Post Title: RevHeadz .obb extraction

Greetings,
I'm willing to extract the fev and fsb data from [this app](https://play.google.com/store/apps/details?id=au.com.revheadz.revheadz).
it's an app that simulates car engine sounds and uses FMOD which supports the fev and fsb format.
The obb doesn't have any meaningful header, it's header is the following binary (0100 0000 2101 0000 0B00 0000).
My assumption is that the obb archive doesn't have any encryption and compression at all as I can read all addresses and directories as plain text however I can't open the file using 7zip or WinRAR.

The structure of the file as far as I could understand is like this:

an unknown header
all directories and addresses
---
properties of each sound like rpm, gear counts, etc...
3 chunks of data (these should be the fmod bank files as they start with RIFF keyword, the files-bank, strings-bank, and master-bank)
*these datas get repeated 63 times representing the 63 engine sounds of the app.

regarding the chunk size my assumption is the first one is the one containing all events and sound assets for the first engine sound so I tried to copy the first bank data into a new file with .bank extension to extract it by the "Fmod Bank Tools" but this throwes me errors as the file doesnt seem correct.

can someone please guide me through?
thanks a lot.

[main.37.au.com.revheadz.revheadz.obb](https://mega.nz/file/w14zXZbB#W8fL1ApPpfzYJVm91lVe0ndOLbxxKKQGhxgESO9thBE)
obb file for reference but I only kept up to the first 3 engine sounds and removed the rest to lower the size.
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-05-25T02:22:07+00:00
- Post Title: RevHeadz .obb extraction

Use this BMS script to unpack it.
[RevHeadzObbUnpack.zip](https://xentaxbackup.github.io/file/18206_RevHeadzObbUnpack.zip)
## Post #3
- Username: mehrdad995gta
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 19, 2016 10:13 pm
- Post datetime: 2020-05-25T17:43:16+00:00
- Post Title: RevHeadz .obb extraction

Thanks a lot @Bigchillighost
I noticed that the error I got previously was due to the fsb file encryption itself as I still get it when I extract them using the script you provided,
so I searched a bit and found decfsb.exe and the password to be (1^7%82#&5$~/8sz), however when I decrypted the fsb file, the outputed .wav files seem curropted.
they open but the sound itsef is so noisy.

I would appriciate any help  .

[encrypted .fsb sample](https://mega.nz/file/B0gATAZY#Km15gcrrMcPlXc4HkaBceEwDb7-PBSb8aVzT5ChK3P8)
[decrypted .wav files](https://mega.nz/file/IhwW1KIZ#EZiPSJue5cBRuCXbE8G-d7F-g_cA5E-88I2M4oZLCnQ)
## Post #4
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-05-25T18:58:35+00:00
- Post Title: RevHeadz .obb extraction

Instead of using decfsb, just drop the encrypted fsb file into Foobar with Vgmstream installed.  It plays the files perfectly.
## Post #5
- Username: mehrdad995gta
- Rank: ultra-n00b
- Number of posts: 7
- Joined date: Fri Aug 19, 2016 10:13 pm
- Post datetime: 2020-05-26T06:38:20+00:00
- Post Title: RevHeadz .obb extraction

Fantastic, have never heard of this software.
You guys are a life saver, Thanks A Lot
## Post #6
- Username: Lolkid654
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Mon Aug 23, 2021 3:03 pm
- Post datetime: 2021-08-23T07:11:36+00:00
- Post Title: RevHeadz .obb extraction

I have no idea how to extract these files. i Managed to open the OBB with 7zip and extract all the bank files but i cant open the bank files.

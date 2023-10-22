## Post #1
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2022-05-22T05:49:38+00:00
- Post Title: AKB1/149: Love Election (PSP) alld1.apk

i triying to extract alld1.apk with QuickBMS with dragon_ball_z_boz.bms and i get this error , its possible to extract alld1.apk? file from AKB1/149: Love Election with other bms from QuickBMS??

link: <link deleted by moderator, sharing full games is forbidden here>
## Post #2
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-05-22T23:08:30+00:00
- Post Title: AKB1/149: Love Election (PSP) alld1.apk

Do not post entire game here, is forbidden.

try this script to unpack the file.

i Remember that i helped someone in xentax channel.

```

goto 0x07c8

for
get offset long
get zeros long
get unknown long
get zeros long
get size long
get zeros long
getdstring idontknow 0x10
 if OFFSET == 0x0000000 # "ONDINHA PROMOSSAUM PSN" 
    break
     endif

 string NAME p "%08x.7z" offset

log name offset size
next
```
## Post #3
- Username: Wrland
- Rank: advanced
- Number of posts: 49
- Joined date: Sun Nov 22, 2020 10:46 pm
- Post datetime: 2022-05-23T03:47:44+00:00
- Post Title: AKB1/149: Love Election (PSP) alld1.apk

thanks!, but its only 7z, i trying to extract ALLD2.APK in the same bms and get this error , its possible to extract ALLD2.APK with other bms script on QuickBMS??
## Post #4
- Username: Rabatini
- Rank: veteran
- Number of posts: 97
- Joined date: Tue Nov 22, 2016 8:13 pm
- Post datetime: 2022-05-23T12:47:40+00:00
- Post Title: AKB1/149: Love Election (PSP) alld1.apk

upload.
allpak1 and allpak2
its lz, because the files are compressed.

## Post #1
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-06-14T17:55:23+00:00
- Post Title: [PC] Halo Wars Definitive Edition - Sound Extraction with full name strings

Hello, people of Xentax! I've been researching Halo Wars for quite some time now and wondered if sound extraction was possible. 

The simple answer? Yes. However, the main issue is that due to the WWISE codec used, I tried unpacking them with "Wwise-Unpacker-master"  and messing around with Ravioli Game Tools, however everytime I export, the sound despite being playable is a random assortment of numbers, for example: "Sounds_3254". It's almost impossible to sort through these considering that not only are all the sound effects mixed together with the voices, but also that there is no separation for localization, so languages from English to German are present throughout all  voice lines.


If there is anyone who happens to know a tool or script that is able to extract the files and preserving their original sound names that would be wonderful.    All the best and thank you for your time!

Here is a sample uploaded: [https://drive.google.com/file/d/1StfoxX ... E7q9I/view](https://drive.google.com/file/d/1StfoxXx7Wdr0NeId6q4Ak-zhgTNE7q9I/view)
## Post #2
- Username: DKDave
- Rank: ultra-veteran
- Number of posts: 357
- Joined date: Tue May 07, 2019 1:07 am
- Post datetime: 2020-06-15T16:30:12+00:00
- Post Title: [PC] Halo Wars Definitive Edition - Sound Extraction with full name strings

There aren't any filenames stored in that archive, so that's why the unpacker can't create them.  Unless the filenames are stored elsewhere then there's no way to get them.
## Post #3
- Username: Pepsee
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Mar 05, 2016 4:26 am
- Post datetime: 2020-06-15T17:15:12+00:00
- Post Title: [PC] Halo Wars Definitive Edition - Sound Extraction with full name strings

> Reply from DKDave ↑Tue Jun 16, 2020 12:30 am at Tue Jun 16, 2020 12:30 am
>
> 
There aren't any filenames stored in that archive, so that's why the unpacker can't create them.  Unless the filenames are stored elsewhere then there's no way to get them.

Thanks for the reply, Dave! I did some more digging and managed to find some .XML files that might be responsible for that. Check the files I attached.
[Sound XML.7z](https://xentaxbackup.github.io/file/18329_Sound XML.7z)

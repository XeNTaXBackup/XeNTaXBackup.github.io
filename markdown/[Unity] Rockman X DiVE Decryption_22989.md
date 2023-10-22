## Post #1
- Username: AtlasF
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 11, 2020 3:12 pm
- Post datetime: 2020-11-11T07:32:49+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

/
## Post #2
- Username: einherjar007
- Rank: mega-veteran
- Number of posts: 188
- Joined date: Sat Dec 23, 2017 2:56 pm
- Post datetime: 2020-11-11T07:35:45+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

Can't you wait for a while? As I suggested in vg-resource, XDive is very promising content in the future.
When cryptography no longer makes sense as cryptography, they should change its method.
Now I use the XOR method which is easy to get, but it is difficult to decrypt if it is changed to AES or bit shift is used.
## Post #3
- Username: AtlasF
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Nov 11, 2020 3:12 pm
- Post datetime: 2020-11-11T07:48:50+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

/
## Post #4
- Username: dOrOganWilson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 15, 2020 7:06 pm
- Post datetime: 2020-11-26T12:27:13+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

what tool do you use to view the data? i have found the list of files but i can't view it by UnityEX
## Post #5
- Username: dOrOganWilson
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Wed Apr 15, 2020 7:06 pm
- Post datetime: 2020-12-05T08:39:10+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

please help me read those .file from Rockman X Dive. i have used many program such as UABE, AssetStudio,etc but i can't read those files 
It comes with a bunch of files with no extension. it seems to be encrypted into another type. please help
[Untitled.png](https://xentaxbackup.github.io/file/19139_Untitled.png)
## Post #6
- Username: TheButterDawg
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Mon Feb 08, 2021 8:20 pm
- Post datetime: 2021-02-11T12:56:20+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

I think i figured out it's source of encryption, there's some scripts in this game that do that action of locking them up but i can't seem to tell if it's either AesCrypto.cs of LZ4Codec.cs.They somehow tell the difference of streaming the assets from encrypted header.

The dumped scripts are in my google folder: {[https://drive.google.com/file/d/1QwJsqY ... sp=sharing](https://drive.google.com/file/d/1QwJsqYsXkBiEilipw3yNLn39skUNZST8/view?usp=sharing)}

Search for either AesCrypto, LZ4Codec of AssetBundle scripts in my zip file.
## Post #7
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2022-08-22T07:41:15+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

pardon me, but the file is not found when i clicked the link
## Post #8
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-01-16T18:41:25+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

Apparently after two years they're using around the same encryption for assets. Scripts for decrypting them are available in [this topic](https://forum.xentax.com/viewtopic.php?t=26884).

Update: Separate script for offline version is added to the same place. Both online and offline scripts are reworked, and now they're also sorting output files properly with unknown files being put in "other" subfolder. Among those unknown files there are some base64 encoded files with unknown contents in offline version, and unknown files with "73 42 13 00" header in online version.
## Post #9
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2023-06-08T07:33:28+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

again its gone... btw the game is about to shutdown on september 27th, so this might be the last chance to be able to find a solution for decryption
## Post #10
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2023-06-09T04:34:23+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

Already have all the decrypted files (both PC and Android) + the decryption script for the "OrangeData and OrangeTextData" binary files and also the sound files from the game, but i still have to wait till the game goes EOS on it's final version 15.23.0000, then i can dump all the gacha images from the game.
## Post #11
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-06-20T16:40:12+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

I've fixed link in my previous post, scripts are now available here at xentax.
## Post #12
- Username: nuocda
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Fri Oct 02, 2015 11:01 am
- Post datetime: 2023-09-06T03:00:41+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

need help xor "5b6078a6159fcc95bfb21214f91e48c2" in offline files , follow some guide xor 556E6974794653000000 can't make it readable with uabae

[https://drive.google.com/file/d/1wjw5tr ... sp=sharing](https://drive.google.com/file/d/1wjw5tr0fE7iRqZZ_WpCh_A9mgmrZBRlF/view?usp=sharing)
## Post #13
- Username: MrYouKnowItAll
- Rank: n00b
- Number of posts: 14
- Joined date: Sat Aug 27, 2022 12:35 pm
- Post datetime: 2023-09-06T04:31:48+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

Already did everything in offline.
## Post #14
- Username: Spiritovod
- Rank: mega-veteran
- Number of posts: 187
- Joined date: Mon Oct 11, 2010 4:44 am
- Post datetime: 2023-09-06T12:59:26+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

Script for offline version is added to the same topic mentioned above. For more info read update notes. Though some unknown files are not handled - but all bundles and audio should be processed properly, at least for offline version.
## Post #15
- Username: void133
- Rank: beginner
- Number of posts: 26
- Joined date: Sat Jul 10, 2021 2:51 pm
- Post datetime: 2023-09-25T07:17:43+00:00
- Post Title: [Unity] Rockman X DiVE Decryption

hmmm... i gave the script for rockman x dive a try on the files i got, but it didnt get any files... i wonder if i did anything wrong...

## Post #1
- Username: Rinaldi104
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 02, 2019 5:11 pm
- Post datetime: 2021-02-14T07:50:55+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

Happy Valentine Days to all of you
I hope everyone here get a chocolates

Recently i've been working to look any toaru index imaginary fest files with my phone unfortunately i've got a solution with using Bluestacks and rooted with bluestack tweakers. 
Based the other post i've got game files inside data/data/com.square_enix.android_googleplay.index_if
I manage to get those files and try to opened with Asset Studio but it failed
Someone said that it is encrypted with simple 1-byte xor key
So the question is
Is there anyone know how to solve this encryption and also get a texture files from this games
[https://drive.google.com/file/d/1-0oYZw ... p=drivesdk](https://drive.google.com/file/d/1-0oYZwDHiS9ceRbekyeIMQSXj6YFuMh-/view?usp=drivesdk)
## Post #2
- Username: andree
- Rank: veteran
- Number of posts: 149
- Joined date: Sun Jul 09, 2017 8:36 pm
- Post datetime: 2021-02-14T14:49:13+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from Rinaldi104 ↑Sun Feb 14, 2021 3:50 pm at Sun Feb 14, 2021 3:50 pm
>
> 
Happy Valentine Days to all of you
I hope everyone here get a chocolates

Recently i've been working to look any toaru index imaginary fest files with my phone unfortunately i've got a solution with using Bluestacks and rooted with bluestack tweakers. 
Based the other post i've got game files inside data/data/com.square_enix.android_googleplay.index_if
I manage to get those files and try to opened with Asset Studio but it failed
Someone said that it is encrypted with simple 1-byte xor key
So the question is
Is there anyone know how to solve this encryption and also get a texture files from this games
https://drive.google.com/file/d/1-0oYZw ... p=drivesdk
[viewtopic.php?f=16&t=21917&p=171399#p171411](https://forum.xentax.com/viewtopic.php?f=16&t=21917&p=171399#p171411)

There is a script made for this.
## Post #3
- Username: Rinaldi104
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 02, 2019 5:11 pm
- Post datetime: 2021-02-15T11:35:20+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

Thank you andree 
You're life saver
## Post #4
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2021-02-19T07:11:25+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from Rinaldi104 ↑Mon Feb 15, 2021 7:35 pm at Mon Feb 15, 2021 7:35 pm
>
> 
Thank you andree 
You're life saver

did you manage to encrypt them?
## Post #5
- Username: Rinaldi104
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 02, 2019 5:11 pm
- Post datetime: 2021-02-21T18:35:23+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

Actually i got them already
## Post #6
- Username: DarkSonic1
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Tue Jun 19, 2018 6:20 am
- Post datetime: 2021-02-27T19:24:44+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from Rinaldi104 ↑Mon Feb 22, 2021 2:35 am at Mon Feb 22, 2021 2:35 am
>
> 
Actually i got them already

all files? Most of my files have not been decrypted
## Post #7
- Username: libaibaba
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 26, 2018 3:33 pm
- Post datetime: 2021-03-05T05:13:46+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

After a night of brain burning, I found that most of the files XOR to 0x100, and then loop. After further analysis, I guess that there are 1024 decryption schemes for the files, two of which are not encrypted or spam themselves (but you can delete them manually). They all have plaintext: unityfs, and one of the remaining 1022 is [viewtopic.php?f=16&t=21917&p=171560&hil ... st#p171560](https://forum.xentax.com/viewtopic.php?f=16&t=21917&p=171560&hilit=Imaginary+Fest#p171560) Use only one byte encryption，I only manually decrypted a few keys, which are only useful for a few files. I also decrypted the "b20e38b5" in the root directory, and found the details that seem to be the decryption scheme? I don't know the code. So I'm not sure.Looking at the installation package, I found that the company has another game I am playing:Nier Re[in]carnation，I have reason to believe that Nier uses the same encryption method。（Please forgive my grammar, it comes from the translation engine）
[1.png](https://xentaxbackup.github.io/file/19643_1.png)
## Post #8
- Username: libaibaba
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 26, 2018 3:33 pm
- Post datetime: 2021-03-05T05:14:53+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

And this
[2.png](https://xentaxbackup.github.io/file/19645_2.png)
## Post #9
- Username: libaibaba
- Rank: n00b
- Number of posts: 12
- Joined date: Thu Jul 26, 2018 3:33 pm
- Post datetime: 2021-03-05T10:42:09+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

Hello, it's me. Again, I think I've found a certain rule. Look at this:


无标题.png (101.53 KiB) Viewed 598 times

 I listed the bytes of some files from 0x7 to 0xa. Guess what? xor.key Changed with it! And it's cyclical! Sorry about my explanatory power.. For example: file a, byte 0x7-0xa is 00537b43, its first XOR key is 47, and file B, byte 0x7-0xa is 537b4385 (do you see it? The XOR key 47 is the last! File C, byte of 0x7-0xa is 7b43859a > >....... Cycle!
## Post #10
- Username: Rinaldi104
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 02, 2019 5:11 pm
- Post datetime: 2021-03-07T05:47:41+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

Actually not all the files that i've got there
It seems Decrypted somehow
Can't figure it out actually
My mind is blowing
## Post #11
- Username: Rinaldi104
- Rank: n00b
- Number of posts: 13
- Joined date: Sat Feb 02, 2019 5:11 pm
- Post datetime: 2021-03-07T06:12:46+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from libaibaba ↑Fri Mar 05, 2021 6:42 pm at Fri Mar 05, 2021 6:42 pm
>
> 
Hello, it's me. Again, I think I've found a certain rule. Look at this:无标题.png I listed the bytes of some files from 0x7 to 0xa. Guess what? xor.key Changed with it! And it's cyclical! Sorry about my explanatory power.. For example: file a, byte 0x7-0xa is 00537b43, its first XOR key is 47, and file B, byte 0x7-0xa is 537b4385 (do you see it? The XOR key 47 is the last! File C, byte of 0x7-0xa is 7b43859a > >....... Cycle!
Hello libaibaba thank you for your hard work
It seems i can't understand about your explanation
What i can get is the xor key might be 47
I don't know it work as well to another files
But if your theory was right
We might be able to makes a script for those files
## Post #12
- Username: tachiban
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 18, 2021 2:09 pm
- Post datetime: 2022-03-31T01:18:09+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from libaibaba ↑Fri Mar 05, 2021 1:13 pm at Fri Mar 05, 2021 1:13 pm
>
> 
After a night of brain burning, I found that most of the files XOR to 0x100, and then loop. After further analysis, I guess that there are 1024 decryption schemes for the files, two of which are not encrypted or spam themselves (but you can delete them manually). They all have plaintext: unityfs, and one of the remaining 1022 is viewtopic.php?f=16&t=21917&p=171560&hil ... st#p171560 Use only one byte encryption，I only manually decrypted a few keys, which are only useful for a few files. I also decrypted the "b20e38b5" in the root directory, and found the details that seem to be the decryption scheme? I don't know the code. So I'm not sure.Looking at the installation package, I found that the company has another game I am playing:Nier Re[in]carnation，I have reason to believe that Nier uses the same encryption method。（Please forgive my grammar, it comes from the translation engine）
Can Nier re [in] carnation be unpacked?
## Post #13
- Username: zerotaku5123
- Rank: beginner
- Number of posts: 31
- Joined date: Tue Aug 06, 2019 8:17 am
- Post datetime: 2022-05-10T05:56:36+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from libaibaba ↑Fri Mar 05, 2021 1:13 pm at Fri Mar 05, 2021 1:13 pm
>
> 
After a night of brain burning, I found that most of the files XOR to 0x100, and then loop. After further analysis, I guess that there are 1024 decryption schemes for the files, two of which are not encrypted or spam themselves (but you can delete them manually). They all have plaintext: unityfs, and one of the remaining 1022 is viewtopic.php?f=16&t=21917&p=171560&hil ... st#p171560 Use only one byte encryption，I only manually decrypted a few keys, which are only useful for a few files. I also decrypted the "b20e38b5" in the root directory, and found the details that seem to be the decryption scheme? I don't know the code. So I'm not sure.Looking at the installation package, I found that the company has another game I am playing:Nier Re[in]carnation，I have reason to believe that Nier uses the same encryption method。（Please forgive my grammar, it comes from the translation engine）

I really didn't understand anything I read, it burned my brain   , and I hope someday they will share the updated scrip for this game.
## Post #14
- Username: GDL
- Rank: veteran
- Number of posts: 150
- Joined date: Fri Jul 09, 2010 11:54 pm
- Post datetime: 2022-05-27T20:52:31+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from tachiban ↑Thu Mar 31, 2022 9:18 am at Thu Mar 31, 2022 9:18 am
>
> 
libaibaba wrote: ↑Fri Mar 05, 2021 1:13 pm
After a night of brain burning, I found that most of the files XOR to 0x100, and then loop. After further analysis, I guess that there are 1024 decryption schemes for the files, two of which are not encrypted or spam themselves (but you can delete them manually). They all have plaintext: unityfs, and one of the remaining 1022 is viewtopic.php?f=16&t=21917&p=171560&hil ... st#p171560 Use only one byte encryption，I only manually decrypted a few keys, which are only useful for a few files. I also decrypted the "b20e38b5" in the root directory, and found the details that seem to be the decryption scheme? I don't know the code. So I'm not sure.Looking at the installation package, I found that the company has another game I am playing:Nier Re[in]carnation，I have reason to believe that Nier uses the same encryption method。（Please forgive my grammar, it comes from the translation engine）

Can Nier re [in] carnation be unpacked?

Looks like it can be with this tool:

[https://github.com/190nm/rein-kuro](https://github.com/190nm/rein-kuro)
## Post #15
- Username: tachiban
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Wed Aug 18, 2021 2:09 pm
- Post datetime: 2022-06-05T13:07:57+00:00
- Post Title: Toaru Majutsu no Index: Imaginary Fest mesh files and Textures

> Reply from GDL ↑Sat May 28, 2022 4:52 am at Sat May 28, 2022 4:52 am
>
> 
tachiban wrote: ↑Thu Mar 31, 2022 9:18 am
libaibaba wrote: ↑Fri Mar 05, 2021 1:13 pm
After a night of brain burning, I found that most of the files XOR to 0x100, and then loop. After further analysis, I guess that there are 1024 decryption schemes for the files, two of which are not encrypted or spam themselves (but you can delete them manually). They all have plaintext: unityfs, and one of the remaining 1022 is viewtopic.php?f=16&t=21917&p=171560&hil ... st#p171560 Use only one byte encryption，I only manually decrypted a few keys, which are only useful for a few files. I also decrypted the "b20e38b5" in the root directory, and found the details that seem to be the decryption scheme? I don't know the code. So I'm not sure.Looking at the installation package, I found that the company has another game I am playing:Nier Re[in]carnation，I have reason to believe that Nier uses the same encryption method。（Please forgive my grammar, it comes from the translation engine）

Can Nier re [in] carnation be unpacked?


Looks like it can be with this tool:

https://github.com/190nm/rein-kuro
What should I do? I have extracted the game files from my mobile phone. But I don't know how to use this tool.

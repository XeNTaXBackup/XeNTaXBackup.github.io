## Post #1
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-07T23:04:13+00:00
- Post Title: Encrypted MQO (MME)

The contents of this post was deleted because of possible forum rules violation.
## Post #2
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-09T18:01:40+00:00
- Post Title: Encrypted MQO (MME)

I have downloaded the latest version (V110103) of mmViewer from the website of his author:
[http://hheaven.net/mmViewer/](http://hheaven.net/mmViewer/)

and I have modified it a bit for automatically dumping the decrypted file from the memory to the file with name "x.z".

so:
- launch mmdump.exe
- select the file you want to decrypt
- the program will dump it and exit
- rename the file x.z as you wish and open it normally

for the list of bytes I modifed do a binary comparison with the original executable
[mmdump.7z](https://xentaxbackup.github.io/file/4027_mmdump.7z)
## Post #3
- Username: mariokart64n
- Rank: ultra-veteran
- Number of posts: 586
- Joined date: Sun Jun 05, 2005 7:00 pm
- Post datetime: 2011-03-09T21:17:58+00:00
- Post Title: Encrypted MQO (MME)

awesome! I tried disassembling the mmEncrypt.exe tool >_< lol but guess I should have been looking at the other program. thanks for the dumper.
## Post #4
- Username: aluigi
- Rank: VVIP member
- Number of posts: 1916
- Joined date: Thu Dec 08, 2005 7:26 pm
- Post datetime: 2011-03-09T21:39:26+00:00
- Post Title: Encrypted MQO (MME)

eh eh eh :)
this time I preferred this unusual solution because I noticed that the algorithm was enough long and I was annoyed.

in reality I guess that probably I will think to a wider project for doing this type of stuff: converting any normal program in a dumper without much effort

it would save time in various cases of programs that make use of compressions and encryptions and seems also interesting

for who is interested in the technical details, I simply created a dumping function (CreateFile+WriteFile(data,len)+CloseHandle) and placed it immediately after the calling of the decrypting function
## Post #5
- Username: Ninja
- Rank: veteran
- Number of posts: 84
- Joined date: Sat Feb 26, 2011 10:44 am
- Post datetime: 2011-03-10T16:04:09+00:00
- Post Title: Encrypted MQO (MME)

Thanks for this, much appreciated, been bugging the hell out of me as well this one.
Like your solution, much quicker than trying to fumble through the hex dumps.

Japanese do have a decrypter for this,  [http://witchcraft-jp.sakura.ne.jp/](http://witchcraft-jp.sakura.ne.jp/)  stopped publishing his/her work because of it. 
Another encrypted/compressed mqo viewer is :- [http://sio29.sakura.ne.jp/celsview/celsview.html](http://sio29.sakura.ne.jp/celsview/celsview.html)

## Post #1
- Username: Lotus06
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Tue Sep 20, 2022 4:12 pm
- Post datetime: 2022-10-02T18:40:26+00:00
- Post Title: [Help] Need Help editing eboot.bin File [Files provided]

I need someone to help me modify a decrypted eboot. PB eboot.bin has no restriction but EV eboot.bin has been configured to only read compressed files where PB eboot does not. The eboots are very similar! Both games have identical file structures after decompression.but mods aren't applying because of EV eboot has set the default to read compressed files only, not decompressed files like PB eboot.bin. So somewhere there may be instructions that make EV eboot.bin ignore uncompressed files which causes modded decompressed files not to have any effect in-game. Would appreciate some help, please!

Compressed game folder image(tons of folder packed into large .tpk files):
[https://gyazo.com/fdeb33115bb1bc995a3062c9c977132c](https://gyazo.com/fdeb33115bb1bc995a3062c9c977132c)

Decompressed game folder image:
[https://gyazo.com/7258b396537632f6616fcc6fad2af322](https://gyazo.com/7258b396537632f6616fcc6fad2af322)

Synchronize scrolling with 010 editor file compare  to line up both eboots. at address 
```
591DC0
```
 for PB 
```
5F7830
```
 for EV

PB eboot:
https://drive.google.com/file/d/1nPAZeR ... sp=sharing

EV eboot:
https://drive.google.com/file/d/1D4Kh_M ... p=drivesdk

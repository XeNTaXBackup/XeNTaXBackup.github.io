## Post #1
- Username: ChadTheRad
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Aug 12, 2018 2:20 am
- Post datetime: 2018-08-11T18:25:42+00:00
- Post Title: Mirai Nikki RE: WRITE's res.ptd archive file

The PSP visual novel 'Mirai Nikki RE: WRITE - 13 Ninme No Nikki Shoyuusha' has its game contents held in an archive file called res.ptd; I have been attempting to extract this archive however I have been unable to properly work out how. By looking at an extracted BOOT.ELF file of the game I was able to work out the the file functions as an archive with subdirectories that assets are called from (e.g res/bgm/bgPark.at3). From this decoded BOOT.ELF file I learnt that music is stored in the format at3 (which is atrac3) and sound effects as fsb (fmod sound bank). There are multiple 'MIG' files which I believe are actually GIM files which is a format used by the PSP for images (these are likely the character portraits, backgrounds and ui). The string YKLZ is also repeated throughout the file and seems to act as a sort of file or directory end. The header T2FP also occurs and the hex code 87 4C 74 68.

After learning this I have hit a wall as I am unsure of how to progress in getting the files as I do not know how it is encrypted or where the files start and end. If anyone can tell me how I could go about reversing the decryption function in an emulator or can provide any help about the file it would be greatly appreciated.

Extracted BOOT.ELF: [https://www.dropbox.com/s/sa38i7asc699g ... 5.BIN?dl=0](https://www.dropbox.com/s/sa38i7asc699glv/ULJM05565.BIN?dl=0)
res.ptd archive file: [https://www.dropbox.com/s/i2dxvjfo45dalfx/res.ptd?dl=0](https://www.dropbox.com/s/i2dxvjfo45dalfx/res.ptd?dl=0)

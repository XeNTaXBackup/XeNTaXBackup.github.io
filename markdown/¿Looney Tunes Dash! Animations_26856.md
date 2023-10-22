## Post #1
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-14T16:09:15+00:00
- Post Title: ¿Looney Tunes Dash! Animations?

Hello i am Dani and thanks to shakotoday and Durik256 i learned how to extract by my self meshes and uvs from fmlb files of looney tunes dash but i have a question is possible to extract animations? if is posible can anyone show me an example of extrtacted animation of fmlb file to learn by my self?

[https://www.mediafire.com/file/ehxgzpa9 ... .fmlb/file](https://www.mediafire.com/file/ehxgzpa9elymkvb/TasmanianDevilMaster!.fmlb/file)
[Captura.PNG](https://xentaxbackup.github.io/file/23923_Captura.PNG)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-15T22:58:01+00:00
- Post Title: ¿Looney Tunes Dash! Animations?

> Reply from Dani ↑Thu Jun 15, 2023 12:09 am at Thu Jun 15, 2023 12:09 am
>
> if is posible can anyone show me an example of extrtacted animation of fmlb file to learn by my self?Hello. So far I didn't see any exported anims from fmlb. The sample you've uploaded seems to contain about 20 anims with 20 bones each.

I'd suggest to start with the skeleton, i.e. its bones. Search for ROOT or joint_TD_...
Once you got the skeleton we could look for more.

Meanwhile I'm little motivated only. Here's some keyframes, maybe for translation (DWORD number and 3 floats). The rotation matrices to follow (wild guess).
.



fmlb-keyframes.png (46.85 KiB) Viewed 96 times
## Post #3
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-16T06:45:15+00:00
- Post Title: ¿Looney Tunes Dash! Animations?

Ooooooooooooo interestly mmm ¿how can extract or convert these data?
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2023-06-16T08:19:38+00:00
- Post Title: ¿Looney Tunes Dash! Animations?

"These data" shows some keyframes. As I wrote you'll need to start with the skeleton.
Read and learn, here for example:

> Reply from Bigchillghost ↑Fri Feb 01, 2019 2:42 pm at Fri Feb 01, 2019 2:42 pm
>
> 

> Reply from Bigchillghost ↑Fri Feb 01, 2019 2:46 pm at Fri Feb 01, 2019 2:46 pm
>
>
## Post #5
- Username: Dani
- Rank: beginner
- Number of posts: 31
- Joined date: Sat Feb 27, 2021 10:17 pm
- Post datetime: 2023-06-16T16:08:48+00:00
- Post Title: ¿Looney Tunes Dash! Animations?

I have a idea i need a small script that convert only faces vértices uvs and animation data to hex similar to hex2obj but in this case obj to hex

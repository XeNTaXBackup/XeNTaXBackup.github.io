## Post #1
- Username: AnonBaiter
- Rank: veteran
- Number of posts: 82
- Joined date: Fri Oct 16, 2015 3:15 am
- Post datetime: 2016-02-05T15:44:59+00:00
- Post Title: Katamari Damacy (PS2) .BIN

So I came across a PS2 game that uses BIN files as game archives. Here are the files(split through the filecutter.bms script) ...and another two files for something else.

[https://mega.nz/#!xAtQACQJ!ZoEDOgs4RDx7 ... RFkFYuzLBc](https://mega.nz/#!xAtQACQJ!ZoEDOgs4RDx7dVbkfrrNP2z1O1V5Z9XWjRFkFYuzLBc)
[https://mega.nz/#!JB9m3AII!S-JwMMOIG49K ... aF5AcZWixc](https://mega.nz/#!JB9m3AII!S-JwMMOIG49KibGpJc9JhO6afDJBYr314aF5AcZWixc)

Thanks.

EDIT: I think I know where the files from FILE_00.BIN are from the offsets. Here they are:

```
000000(000007 - TMPGEnc header)
273080(273087 - TMPGEnc header)
3BF500(3BF507 - TMPGEnc header)
4BAD80(4BAD87 - TMPGEnc header)
5B6600(5B6607 - TMPGEnc header)
6F0680(6F0687 - TMPGEnc header)
7EBF00(7EBF07 - TMPGEnc header)
901380(901387 - TMPGEnc header)
A11C00(A11C07 - TMPGEnc header)
B27080(B27087 - TMPGEnc header)
C37900(C37907 - TMPGEnc header)
CF5180(CF5187 - TMPGEnc header)
DB2A00(DB2A07 - TMPGEnc header)
E70280(E70287 - TMPGEnc header)
F2DB00(F2DB07 - TMPGEnc header)
FEB380(FEB387 - TMPGEnc header)
10A8C00(10A8C07 - TMPGEnc header)
1166480(1166487 - TMPGEnc header)
1223D00(1223D07 - TMPGEnc header)
12E1580(12E1587 - TMPGEnc header)
1410200(1410207 - TMPGEnc header)
1687E80(1687E8B - TMPGEnc header)
170A700(170A707 - TMPGEnc header)
1753B80(1753B87 - TMPGEnc header)
17C6C00(17C6C0B - TMPGEnc header)
1839C80(1839C8B - TMPGEnc header)
18ACD00(18ACD0B - TMPGEnc header)
18F0D80(18F0D87 - TMPGEnc header)
193F600(193F60B - TMPGEnc header)
198DE80(198DE8B - TMPGEnc header)
19DC700(19DC707 - TMPGEnc header)
1B7EF80(1B7EF87 - TMPGEnc header)
1BC3000(1BC3007 - TMPGEnc header)
1C07080(1C07087 - TMPGEnc header)
1C4B100(1C4B107 - TMPGEnc header)
1C8F180(1C8F187 - TMPGEnc header)
1CD3200(1CD3207 - TMPGEnc header)
1D17280(1D1728B - TMPGEnc header)
1D5B300(1D5B307 - TMPGEnc header)
1D9F380(1D9F38B - TMPGEnc header)
1DE3400(1DE3407 - TMPGEnc header)
1E27480(1E27487 - TMPGEnc header)
1E6B500(1E6B507 - TMPGEnc header)
1EAF580(1EAF587 - TMPGEnc header)
1EF3600(1EF3607 - TMPGEnc header)
1F37680(1F37687 - TMPGEnc header)
1F7B700(1F7B70B - TMPGEnc header)
1FF3B80(1FF3B87 - TMPGEnc header)
1FF8780(no header, ends with the 1FF8B22 offset)
1FF8B80(no header - ends with the 1FF8C82 offset)
```

If I'm not mistaken, the .PSS files end with the 1FF850D offset. The rest of the FILE_00.BIN files are there starting with the 2043981 offset and end with the 253FFFF offset.

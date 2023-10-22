## Post #1
- Username: rballad
- Rank: n00b
- Number of posts: 12
- Joined date: Mon Aug 11, 2014 9:40 am
- Post datetime: 2017-03-03T11:31:47+00:00
- Post Title: fatal frame 5 maiden of black water

the  problem is that when  the gtx  is converted, the resulting dds is scrambled just like this
[https://i.imgur.com/d4Fyds0.jpg](https://i.imgur.com/d4Fyds0.jpg)

i uploaded a file so that you guys can  take a look
[http://www.mediafire.com/file/ypkard4a9 ... H_YRI_B.7z](http://www.mediafire.com/file/ypkard4a994blkp/H_YRI_B.7z)
here is a  a quickbms  from chrrox to extract .g1t  from the .gmpk 


```
for i
findloc start string "G1TG0060"
goto start
print "%start%"
savepos offset
getdstring null 0x8
get size long
get NAME filename
string name + ".g1t"
log name offset size

next i
```


next you run this g1t to to gtx script from random talking bush 
[https://mega.nz/#!q5gi1AKD!v4dHgB1F84_B ... 9SZk7l-ofk](https://mega.nz/#!q5gi1AKD!v4dHgB1F84_BnT6owg-t-wybGauwwFXA59SZk7l-ofk)

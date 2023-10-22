## Post #1
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-07-11T02:09:54+00:00
- Post Title: [Request] Simple BMS script .bin -> json (have .bt)

Can anyone help me with making a simple BMS script that that converts this file into json? I have a .bt templete for it.

I would like it to look like this 

```
    {
     "Unknown0": 100,
     "Unknown2": 1,
     "Unknown3": 1,
     "Unknown4": 0,
     "Unknown5": 0,
     "Unknown6": 600,
     "Unknown7": 0,
     "Unknown8": 200,
     "Unknown9": 0,
     "UnknownA": 0,
     "UnknownB": 2,
     "UnknownC": 100,
     "UnknownD": -1,
     }
     
```

[mst_equipment_growth_param.zip](https://xentaxbackup.github.io/file/18434_mst_equipment_growth_param.zip)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2020-07-13T10:12:49+00:00
- Post Title: [Request] Simple BMS script .bin -> json (have .bt)

> Reply from hellacopters ↑Sat Jul 11, 2020 10:09 am at Sat Jul 11, 2020 10:09 am
>
> 
Can anyone help me with making a simple BMS script that that converts this file into json?
BMS is a bad choice for text format convertion. And honestly what's the point of this request given that all these fields are "Unknown"?

Anyway here's the bms script that meets with your need. 
[bin2json.zip](https://xentaxbackup.github.io/file/18458_bin2json.zip)
## Post #3
- Username: hellacopters
- Rank: n00b
- Number of posts: 13
- Joined date: Fri Apr 19, 2019 5:23 am
- Post datetime: 2020-07-15T04:01:34+00:00
- Post Title: [Request] Simple BMS script .bin -> json (have .bt)

Thank you sir!

The reason for conversion is to find out what value means. Then I can name each one  These bin don't have an entry index, just an entry count (as you can tell)

## Post #1
- Username: retroartebox
- Rank: ultra-n00b
- Number of posts: 4
- Joined date: Fri Aug 12, 2022 4:45 pm
- Post datetime: 2023-01-03T00:01:16+00:00
- Post Title: how to decrypt .xml using powershell

I need help from masters in powershell and binary files. I'm trying to decode .xml files using powershell and this is the code I'm using:

```
$content = $_ | Get-Content
Set-Content -PassThru $_.Fullname $content -Encoding UTF8 -Force} | out-file D:\converted1.txt
```


It works fine for the yatomanne.xml but not for the coldring2link.xml, and it's strange because both files have the same header, they are game files, can someone help me understand why coldring2link.xml doesn't convert?

Here is an attachment of the files: 
[https://drive.google.com/file/d/1Mj0CId ... sp=sharing](https://drive.google.com/file/d/1Mj0CIds7o3gWVtG-rjeuiTA87D2MqYGu/view?usp=sharing)

[https://drive.google.com/file/d/1uXtnri ... sp=sharing](https://drive.google.com/file/d/1uXtnria4Zt78L2d2fOYIfKLKOIAnXiUc/view?usp=sharing)

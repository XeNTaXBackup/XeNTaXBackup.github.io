## Post #1
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-05-01T20:32:53+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

Hello , i tried to extract with fsb extractor and some programs but it doesn't work

here is the file im trying to extract

[http://www8.zippyshare.com/v/vAuMA3zT/file.html](http://www8.zippyshare.com/v/vAuMA3zT/file.html)
## Post #2
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-05-05T21:09:34+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

Try this 

> Reply from aluigi
>
> The easiest solution is dumping the FSB5 archive from it or using directly fsbext -o -1 with the BANK archive (it's the option that forces fsbext to scan the file for FSB archives).
## Post #3
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-05-06T14:12:37+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

> Reply from brendan19
>
> Try this 
aluigi wrote:The easiest solution is dumping the FSB5 archive from it or using directly fsbext -o -1 with the BANK archive (it's the option that forces fsbext to scan the file for FSB archives).
thanks for the reply. i did as you said and it extracted files but i can't play any of them, it says "Cannot render the file". they are all headerless ogg files.
## Post #4
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-05-06T14:15:34+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

You'll have to either rebuild them as PCM in FMOD Designer or use MusicPlayerEX to convert them.
## Post #5
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-05-06T21:13:44+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

> Reply from brendan19
>
> You'll have to either rebuild them as PCM in FMOD Designer or use MusicPlayerEX to convert them.
i guess i'll have to rebuild them since converting them to mp3 or wav doesn't seem to work or i'm doing something wrong
## Post #6
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-05-07T00:56:05+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

You probably need to update the FMOD DLLs

[http://www19.zippyshare.com/v/vk2Btc8Q/file.html](http://www19.zippyshare.com/v/vk2Btc8Q/file.html)

Put these in the lib folder of MusicPlayerEX
## Post #7
- Username: ricky12
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Fri Oct 24, 2014 6:47 pm
- Post datetime: 2015-05-07T10:07:12+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

it's still not working   

It gives me an empty file when i tried to convert it to mp3/wav

[http://www48.zippyshare.com/v/vG0cUfln/file.html](http://www48.zippyshare.com/v/vG0cUfln/file.html)

this is the file i was trying to convert
## Post #8
- Username: brendan19
- Rank: ultra-veteran
- Number of posts: 389
- Joined date: Thu Aug 12, 2010 3:15 pm
- Post datetime: 2015-05-08T16:25:07+00:00
- Post Title: Telltale Games Game Of Thrones - How do i extract .bank file

I checked the file, there's no FSB header :/

The file might be compressed/encrypted.

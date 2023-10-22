## Post #1
- Username: glacier
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sun Jan 24, 2021 4:03 am
- Post datetime: 2021-01-23T20:12:28+00:00
- Post Title: Only able to extract text from some scripts- Oregairu 2 VN

Hello, so I have been translating the Oregairu 2 Visual Novel for the PS Vita, and I have managed to translate the prologue. I'm unable to translate a lot of the other scripts because the tool I'm using ([https://github.com/CommitteeOfZero/SciA ... s/SC3Tools](https://github.com/CommitteeOfZero/SciAdv.Net/tree/transition/src/Tools/SC3Tools)) always gives me an error when I try to extract text from the other script files. I asked MrComputerRevo about it, and heres what he said, "if you’re familiar with programming a bit you can try adding the missing command yourself
What you’d have to do is essentially create another present command here
[https://github.com/CommitteeOfZero/SciA ... ndCodes.cs](https://github.com/CommitteeOfZero/SciAdv.Net/blob/transition/src/SciAdvNet.SC3Script/Text/EmbeddedCommandCodes.cs)
Like the Present_0x18 one, except yours will need to be Present_0x05 and equal to 0x05
Then in these files you’ll have to pretty much copy the stuff that is for Present_0x18 but with 0x05 instead, like, add it here
[https://github.com/CommitteeOfZero/SciA ... ng.cs#L297](https://github.com/CommitteeOfZero/SciAdv.Net/blob/158e197af18569b08b9afe24d869896899c22700/src/SciAdvNet.SC3Script/Text/SC3String.cs#L297)
Here
[https://github.com/CommitteeOfZero/SciA ... zer.cs#L86](https://github.com/CommitteeOfZero/SciAdv.Net/blob/158e197af18569b08b9afe24d869896899c22700/src/SciAdvNet.SC3Script/Text/DefaultSC3StringSerializer.cs#L86)
Here
[https://github.com/CommitteeOfZero/SciA ... er.cs#L158](https://github.com/CommitteeOfZero/SciAdv.Net/blob/158e197af18569b08b9afe24d869896899c22700/src/SciAdvNet.SC3Script/Text/SC3StringDecoder.cs#L158)
And here
[https://github.com/CommitteeOfZero/SciA ... er.cs#L108](https://github.com/CommitteeOfZero/SciAdv.Net/blob/158e197af18569b08b9afe24d869896899c22700/src/SciAdvNet.SC3Script/Text/SC3StringEncoder.cs#L108) "

Since I'm not a programmer, I don't know how to do this, so if someone that does know how to program could help me do this, that would be really helpful. Thanks!

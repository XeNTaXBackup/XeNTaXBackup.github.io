## Post #1
- Username: tkreyche
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 17, 2013 3:02 am
- Post datetime: 2013-01-16T19:40:43+00:00
- Post Title: Offer of legit job for file decryption/modification

My client’s windows PC-based mapping and charting program uses a 3rd party DLL to calculate ocean currents and tides. The DLL works by reading harmonic coefficients (floating point values) for various tide station locations from files off the disk. It then generates the tide predictions via an algorithm, and returns tide height values to the calling program. 

As of 1/1/2013 attempts to use the DLL fail with an invalid date error and customers are unhappy. The files are mixed ASCII and binary. There is a date in the file header that indicates the file is usable from 2003-2012, although the actual tide coefficients should be ok for years. Changing the date in the header to various values doesn’t fix the problem. No it is not going to be fast or easy to plug in a different DLL.

My client paid the 3rd party company to develop the DLL as a custom solution from a standard product, but the DLL source code is long gone. The company that wrote the DLL is out of business and nobody associated with the company can be found by mail, email or phone. Their place of business was sold, website is dead and there is no forwarding address.

So I need to find someone good with figuring out file formats to see if there is a date field or something else that I’m missing. Ideally it would be possible to modify the coefficient files to give them another 6 months or year until there’s time to produce a better solution. The coefficient files are in a proprietary format (there are standard formats for coefficient files, such as those for a program called XTide). Beyond Compare does a pretty good job showing repetitive fields in the coefficient files. I have a simple windows console test program that allows a person to see if the file reads are throwing a date error, so modifications to the files can easily be tested, file i/o off the disk could be captured etc.

I can’t pay unless the work is successful and it’s not a big money opportunity. If this interests you please respond to [seakrejci@gmail.com](mailto:seakrejci@gmail.com)
## Post #2
- Username: WRS
- Rank: ultra-veteran
- Number of posts: 603
- Joined date: Fri Nov 06, 2009 7:13 am
- Post datetime: 2013-01-17T00:32:58+00:00
- Post Title: Offer of legit job for file decryption/modification

does the algorithm rely on the date at all? 

if you could pm links to the files (dll/console test app/coefficient files) i'd like to give this a try
## Post #3
- Username: tkreyche
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Jan 17, 2013 3:02 am
- Post datetime: 2013-01-18T14:13:38+00:00
- Post Title: Offer of legit job for file decryption/modification

Thanks for your interest - contact me at [tkreyche@gmail.com](mailto:tkreyche@gmail.com) and I'll send you the details.

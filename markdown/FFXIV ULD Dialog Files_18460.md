## Post #1
- Username: ShadowRoze
- Rank: ultra-n00b
- Number of posts: 9
- Joined date: Tue Jun 24, 2008 1:50 am
- Post datetime: 2018-07-18T06:49:37+00:00
- Post Title: FFXIV ULD Dialog Files

Hi,
I've been working on decoding the form/window/gui descriptors in FFXVI. However, there is a couple of settings I cant seem to figure out what they govern.
The bytes in question is a triplet of shorts. Most commonly found as 0x64 0x64 0x64  (100/100/100), also, they Always seem to have the same value across all three. This property is involved in animations somehow too.
It is not scale, cause scale is defined elsewhere. Rotation is also defined in its own property. The values found this far is 100/100/100, 50/50/50 and 20/20/20. Can it be some kind of blending property?

As part of a standard graphics node. Think of it as a HTML div, rotaion and scaling handled by transform filters


Following is a part of an animation descriptor.


PS. I did not achieve any particular result by changing the values for a standard node....

Secondly, there is one byte which seemingly govern how elements are "spaced/layouted", and I cant for the life of me figure out the order.
I have a bunch of observations regarding this. 
I has almost entirely discarded the suggested structure included in the picture. 
I'm now more into the possiblility of a YYYYXXXX style. 
Standard value is 0x53 (0b01010011) for nodes, 0x5B (0b01011011) for containers.



The following is what happens when I swap the up and down button Y values for a scrollbar. Oddly, there seems to be an offset appearing that is not defined anywhere. The controls have no field for padding.


(I do hope that using discord as file host works  )

//Kind regards, any suggestions is most welcomed.

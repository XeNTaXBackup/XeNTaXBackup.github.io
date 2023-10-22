## Post #1
- Username: finale00
- Rank: M-M-M-Monster veteran
- Number of posts: 2382
- Joined date: Sat Apr 09, 2011 8:22 am
- Post datetime: 2011-08-10T20:15:16+00:00
- Post Title: Connecting bones together

I'm looking for a quick summary of how to connect bones together. I've read a little about skeleton and IK and stuff but figured it's not details I really need to know ATM.

I just need to take a set of bones and connect child/parent together (or whatever the technical terms are) so it's not just "a pile of bones".

I've been looking at different max and blender scripts, in particular the bone section, and notice that they commonly store index to the parent bone.

Now if I have a set of bones, their indices, and their parent indices, how should I go about constructing the skeleton?

Presumably I would start from the top-most parent and then do a search for any other bones that refer to this bone and then say it's the child, then repeat the process until I have connected everything, but that is pretty slow cause if I have n bones, I have to search n - 1 times for each bone. That's pretty bad no matter how I look at it.

Is there a more efficient way of doing things?
## Post #2
- Username: chrrox
- Rank: Moderator
- Number of posts: 2602
- Joined date: Sun May 18, 2008 10:01 pm
- Post datetime: 2011-08-10T21:56:26+00:00
- Post Title: Connecting bones together

most formats export the bones in order
so you just convert the bones as you go and store those bones in an array then when you read a bone you just get its parent id and point it to that index in the array.
its a lot easier to know with what file your looking at.

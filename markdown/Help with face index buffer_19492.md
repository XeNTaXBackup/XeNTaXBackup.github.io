## Post #1
- Username: Vuze
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Sat Aug 11, 2018 4:33 am
- Post datetime: 2019-02-14T09:27:49+00:00
- Post Title: Help with face index buffer

Hi,

I'm currently working with 3D model data for the first time and have read a fair bit about the basics. I've managed to find the vertex buffer (which outputs fine using the 3D Model Researcher tool) and face index buffer. The latter seems to use Tristrip format. However, as seen below, it doesn't build 100% correct. I'm not exactly sure what to look out for here.



I have uploaded the model here: [https://www73.zippyshare.com/v/7ckhkTDg/file.html](https://www73.zippyshare.com/v/7ckhkTDg/file.html)
Face dump: [https://pastebin.com/hriLYdx3](https://pastebin.com/hriLYdx3)

As seen in the image:
Vertex buffer @ 0x142C, Count 604, Float
Face index buffer @ 0x50, Count 1104, Integer, Tristrip

Thank you for any help!

E: The solution was that the face index buffer was further separated into arrays. facecount followed by facecount * 4 in actual indices

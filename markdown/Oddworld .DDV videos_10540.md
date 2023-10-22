## Post #1
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2013-06-24T18:28:31+00:00
- Post Title: Oddworld *.DDV videos

Hey guys ^^

I really want to create a full polish localisation to Oddworld: Abe's Oddysee and i have for now translated all texts and textures, but there is some trubles with movies. They are in DDV format and i don't know any way to convert them to avi or some other format and then convert back to DDV. I just want to add subtitles to these movies (or maybe create a dubbing in the future). Can i count on you? It is very important for me and other people from Oddworld community. Please help 

I saw that a tool "Masher" can play videos in this format from Oddworld: Abe's Exoddus but not from Oddworld: Abe's Oddysee. You can download it here [viewtopic.php?f=33&t=10524](http://forum.xentax.com/viewtopic.php?f=33&t=10524)

Here are a few samples: < link expired >

I found a bit of documentation about this format. Maybe it helps:

[http://hg.sitedethib.com/oddworld-forma ... mats/ddv.h](http://hg.sitedethib.com/oddworld-formats/file/ff949d856c60/doc/formats/ddv.h)

```
// DDV video format
// Abe's Odyssey seems to have another version of it, referred to as MOIR AKIK
// Abe's Exoddus version

struct DDVVideoHeader {
uint32_t unknown1;
uint32_t video_width;
uint32_t video_height;
uint32_t unknown2;
uint32_t unknown3;
uint32_t keyframe_spacing; // Number of frames between keyframes
};
struct DDVAudioHeader {
uint32_t audio_freq;
uint32_t unknown1;
//...
};
struct DDVHeader {
char header[4]; // == "DDV\0"
uint32_t ddv_version;
#define DDV_CONTAIN_VIDEO 1
#define DDV_CONTAIN_AUDIO 2
uint32_t ddv_contains;
uint32_t ddv_fps;
uint32_t ddv_nb_frames;
};

```

## Post #1
- Username: FifaYoun
- Rank: ultra-n00b
- Number of posts: 1
- Joined date: Sat Apr 25, 2020 11:42 pm
- Post datetime: 2020-04-25T17:07:25+00:00
- Post Title: FIFA Street (4/2012) MPF/MUS EA Sound Editing

Hi there, I've been looking in this forum for a long time to understand EA's .mus/.mpf sound files and I can play the music inside this file using VGMstream. However, I want to understand how the files are structured to know where and when I can edit the music (or even add). Since VGMstream is able to play the music and cut them into multiple pieces (as they should be as that is how EA made the "interactive" music in FIFA Street), it means that it knows what the .mpf file refers to in the .mus and where it can find it. But I am no expert in this area, so I would hope if someone will be able to tell me where the parts are that can be edited (replace with another song) or whether it is possible to even add songs.

I've looked into the audio files for a bit to try understand what the files refer to. I will tell my findings here.

First, let's look at what's known about FIFA Street. FIFA Street was released in 2012 and shares a lot of similarities in file structures to FIFA 12, but also a lot of similar structures to FIFA 10 (which was different to FIFA 12), most probably because the game was already in development at that time.

In FIFA 12 the songs (EATrax) and almost all audio are in a .sbr/.sbs audiobank, in FIFA Street many files are in those banks aswell, but it also uses EA's .abk and the music is in EA's .mus/.mpf format. Knowing the history about this format is that it is mostly used for "interactive" music. The audio inside the .mus is in ealayer3 format.

This is why in FIFA Street there is no usual "EA Trax" section in the menus where you can turn on/off music or there is no way to skip a song, unlike the other FIFA games. 

Now, how does the music work in FIFA Street? Inside the menus you have the full song, for example Unorthodox by Wretch 32 ft. Example. So as long as you are browsing the menus, the songs are being played. However, once you go into a match, the songs are now in "instrumental" version. During the intro cinematics of a match, you'll hear the beginning of the instrumental of the song (about 10 seconds of it) and it keeps being looped until the intro ends and the gameplay starts. From the moment the gameplay starts, the whole instrumental is being played for the duration of the half of the match (so in the 2nd half of the game you'll hear the instrumental of another song). However, once you score a goal, the instrumental transitions into the full song with vocals until the gameplay starts again, in which case it transitions into the instrumental again. Once the half ends, you again have a cinematic in which the players walk off the pitch. During this cinematic and the half time screen, you'll hear the instrumentals of the ending of the song (let's say last 10 seconds) and this keeps being looped until the 2nd half starts (in which case the instrumental of another song starts) or until returning to the main menus (in which case another full version of a song starts).

Using VGMstream we can see how this works. The 1st audio file is the complete song (3 minutes long). The following audio files afterwards are cut into small parts (3/4/5/6 seconds) and these all form the complete instrumental of the song. The first few parts are the ones used like described above in the "intro" of the match, the majority of the parts are the "gameplay" instrumental and the final few parts are the "end cinematic" instrumental. Following the complete instrumental, you find another few small parts which are used as the "goalsong" in which the vocals are added.  After this, the process above is repeated for other songs in the game, leading to a total of 1000 parts being played in VGMstream.

Now, the .mpf and .mus file were found in audiodata/pathfinder folder. Inside this folder there are other files, which probably help the game identify the songs and what they are used for. These are the files:

-loadfile.xml
-path_adapter.csi
-pathcontext_events.csi
-csis_path_adapter.xml
-pathcontext_eventsystem.bin
-path_adapter_events.bin
-path_contextdata.bin
-textscripts.dat

I decided to look into the csis_path_adapter.xml and found this:

<AudioFramework>
  <Module type="PathModule" name="FS4PathModule">
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_01" eventType="event" eventValue="0x19AD43A" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_02" eventType="event" eventValue="0x1938227" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_03" eventType="event" eventValue="0x194B268" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_04" eventType="event" eventValue="0x1F0279B" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_05" eventType="event" eventValue="0x1F71842" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_06" eventType="event" eventValue="0x1FE4621" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_07" eventType="event" eventValue="0x1F9767C" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_08" eventType="event" eventValue="0x1466B7D" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_09" eventType="event" eventValue="0x1415C22" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_10" eventType="event" eventValue="0x186D25D" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_11" eventType="event" eventValue="0x181E300" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_12" eventType="event" eventValue="0x188B2DF" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_13" eventType="event" eventValue="0x18F833E" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_14" eventType="event" eventValue="0x1EB1643" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_15" eventType="event" eventValue="0x1EC270C" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_16" eventType="event" eventValue="0x1E576D9" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_17" eventType="event" eventValue="0x1E24756" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_18" eventType="event" eventValue="0x15D5A35" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_19" eventType="event" eventValue="0x15A6AF8" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_20" eventType="event" eventValue="0x1AB8209" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_21" eventType="event" eventValue="0x1ACB1E6" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_22" eventType="event" eventValue="0x1A5E0B7" />
    <EventMapping eventName="PATH_EVENT_Global_Song_ID_23" eventType="event" eventValue="0x1A2CFD8" />
    <EventMapping eventName="PATH_EVENT_Global_Song_FE_Playback" eventType="event" eventValue="0x1849965" />
    <EventMapping eventName="PATH_EVENT_Global_Pause_On" eventType="event" eventValue="0x108741B" />
    <EventMapping eventName="PATH_EVENT_Global_Pause_Off" eventType="event" eventValue="0x1CE40E0" />
    <EventMapping eventName="PATH_EVENT_Global_Intro" eventType="event" eventValue="0x1F04B26" />
    <EventMapping eventName="PATH_EVENT_Global_Start" eventType="event" eventValue="0x18CDB32" />
    <EventMapping eventName="PATH_EVENT_Global_End" eventType="event" eventValue="0x1AD1CBB" />
    <EventMapping eventName="PATH_EVENT_Global_Fade_Out" eventType="event" eventValue="0x18D62E3" />
    <EventMapping eventName="PATH_EVENT_Global_Fade_In" eventType="event" eventValue="0x1E4FD2C" />
    <EventMapping eventName="PATH_EVENT_Global_Goal1_Home" eventType="event" eventValue="0x108556D" />
    <EventMapping eventName="PATH_EVENT_Global_Goal1_Away" eventType="event" eventValue="0x181FAB7" />
    <EventMapping eventName="PATH_EVENT_Global_Goal_Finished" eventType="event" eventValue="0x1756340" />
    <EventMapping eventName="PATH_EVENT_Global_Song_Stop" eventType="event" eventValue="0x138FD5D" />
    <EventMapping eventName="PATH_StopAll" eventType="stop" />
    <EventMapping eventName="PATH_ClearAllEvents" eventType="clear" />
    <EventMapping eventName="PATH_Control" eventType="control" />
  </Module>
</AudioFramework>

After finding this I looked into the .csi and .bin files using a hex-editor and I found the same "eventnames" included in most of them, but I don't know what the values mean. I understood some things, but again, I am not and expert in this stuff, so I hope someone who might understand more can find out what these files do together.

I have included all the necessary files and hope someone can find out what the files mean and how they are linked and hopefully find a way to replace or add files.

[https://www.mediafire.com/file/17cg4eq8 ... ta.7z/file](https://www.mediafire.com/file/17cg4eq81pqzdcw/audiodata.7z/file)

Thank you,
FifaYoun

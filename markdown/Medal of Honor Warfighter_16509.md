## Post #1
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-07T17:20:07+00:00
- Post Title: Medal of Honor Warfighter

Hello. Can you tell me what can be and how to fix it, or what other scripts should I use?
To extract game archives used scripts from here -- [http://www.bfeditor.org/forums/index.ph ... -archives/](http://www.bfeditor.org/forums/index.php?/topic/15731-file-dumper-for-sbtoc-archives/)
To get audio used this script - [viewtopic.php?p=85375#p85375](http://forum.xentax.com/viewtopic.php?p=85375#p85375)

The problem is that many audio in the WAV format (3072 kbps. PCM (floating-point)) do not have a sound. These are tracks from music that without sound and all the SFX also have no sound.

```
020_Bas1_Music_DoorBreach1_Commit_RAM 0 0 0
020_Bas1_Music_DoorBreach2_Commit_RAM 0 0 0
020_Bas1_Music_DoorBreach3_Commit_RAM 0 0 0
049_Bainbridge_Music_SniperTensionOverlayRAM 0 0 0
100_Bosnia_Music_OutroGag 0 0 0
120_Ship_FerryTakeShip_FMX_94BPM_Transition 0 0 0
160_Chitral_Music_DoorBreach1_Entry_RAM 0 0 0
160_Chitral_Music_DoorBreach2_Commit_RAM 0 0 0
MUS_MP_SectorControl_EndOfRound_LP 0 0 0
MUS_MP_SectorControl_FlagLose 0 0 0
Music_MenuScreen 0 0 0
Music_MP_AfghanPop_01 0 0 0
Music_MP_CM_BombArmed_45sec 0 0 0
Music_MP_CM_BombArmed_A 0 0 0
Music_MP_CM_BombArmed_B 0 0 0
Music_MP_CM_BombArmed_C 0 0 0
Music_MP_CM_MatchWin 0 0 0
Music_MP_HS_TargetIdentified 0 0 0
Music_MP_HS_TargetIdentified 0 1 0
Music_MP_HS_TargetIdentified 0 2 0
Music_MP_SportsMode_30SecondsLeft 0 0 0
Music_MP_SportsMode_FlagCapture 0 0 0
Music_MP_SportsMode_Haltime 0 0 0
Music_MP_SportsMode_Haltime 0 1 0
Music_MP_SportsMode_Haltime 0 2 0
Music_MP_SportsMode_Haltime 0 3 0
Music_MP_SportsMode_Haltime 0 4 0
Music_MP_SportsMode_Haltime 0 5 0
Music_MP_SportsMode_Haltime 0 6 0
Music_MP_SportsMode_Intro_LP 0 0 0
Music_MP_SportsMode_LastManAlive 0 0 0
Music_MP_SportsMode_MatchStart 0 0 0
Music_MP_SportsMode_RoundLost 0 0 0
Music_MP_SportsMode_RoundLost 0 1 0
Music_MP_SportsMode_RoundLost 0 2 0
Music_MP_SportsMode_RoundWon 0 0 0
Music_MP_SportsMode_RoundWon 0 1 0
Music_MP_SportsMode_RoundWon 0 2 0
Music_MP_SportsMode_RoundWon 0 3 0
Music_SP_BA_XSliceStackUp 0 0 0
Music_SP_BA_XSliceUpperFloorFullLooping 0 0 0
Music_SP_BA_XSliceUpperFloorFullLooping 0 0 1
Music_SP_Som1_DoorBreachCommit_v1 0 0 0
Music_SP_Som1_HandsOnPressDemo_TowerBreachOutroCard 0 0 0
Music_SP_Som1_LTLMPaintRAM_v1 0 0 0
Music_SP_Som1_SniperEnd_v2 0 0 0
Music_SP_Yemen_ClassroomGagToDoorBreachStackup 0 0 0
Music_SP_Yemen_DoorBreach1Commit_RAM_v1 0 0 0
```
## Post #2
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-12T12:18:09+00:00
- Post Title: Medal of Honor Warfighter

Hi,

Very weird 'cause I just checked my files and I've got these musics and sounds fully playable. 

Are you sure you used the latest version of ealayer3? Plus, if you got any errors during the audio conversion in Python, post it on this thread.
## Post #3
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-13T11:10:34+00:00
- Post Title: Medal of Honor Warfighter

> Reply from Vosvoy
>
> Hi,
Very weird 'cause I just checked my files and I've got these musics and sounds fully playable. 
Are you sure you used the latest version of ealayer3? Plus, if you got any errors during the audio conversion in Python, post it on this thread.
Extracted game files... no errors.
ealayer3-0.7.0
Decode audo errors:

```
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 603, in <module>
    decodeAudio()
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 68, in decodeAudio
    dbx.decode()
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 519, in decode
    blocks[i]=decode(f.read(76))
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 574, in decode
    xaslib.decode(charbufpointer, floatbufpointer)
WindowsError: [Error -529697949] Windows Error 0xE06D7363
```
## Post #4
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-13T16:23:54+00:00
- Post Title: Medal of Honor Warfighter

> Reply from VladlenCry
>
> Vosvoy wrote:Hi,
Very weird 'cause I just checked my files and I've got these musics and sounds fully playable. 
Are you sure you used the latest version of ealayer3? Plus, if you got any errors during the audio conversion in Python, post it on this thread.
Extracted game files... no errors.
ealayer3-0.7.0
Decode audo errors:
Code: Select allTraceback (most recent call last):
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 603, in <module>
    decodeAudio()
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 68, in decodeAudio
    dbx.decode()
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 519, in decode
    blocks[i]=decode(f.read(76))
  File "E:\Games\Medal of Honor Warfighter\audiodeoder.py", line 574, in decode
    xaslib.decode(charbufpointer, floatbufpointer)
WindowsError: [Error -529697949] Windows Error 0xE06D7363

Ok, got few questions:

- At which point the script crashed/stopped (name of the file)? You should be able to answer by looking at the Python process window.
- Are you sure the libmpg123.dll is in the same folder as ealayer3.exe?

I remember that I got some troubles with this game in terms of audio decoding. VO sounds couldn't be decoded (for my part).
## Post #5
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-13T17:26:50+00:00
- Post Title: Medal of Honor Warfighter

> Reply from Vosvoy
>
> 
- At which point the script crashed/stopped (name of the file)? You should be able to answer by looking at the Python process window.
- Are you sure the libmpg123.dll is in the same folder as ealayer3.exe?
- Unfortunately I can not tell on which file. Because I do not see the decoding process. There is only a message that elayer3 is detected. 
Although the process is not visible, decoding occurs.
- Yes
## Post #6
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-13T17:52:21+00:00
- Post Title: Medal of Honor Warfighter

> - Unfortunately I can not tell on which file. Because I do not see the decoding process. There is only a message that elayer3 is detected. 
>
> Although the process is not visible, decoding occurs.

Strange, because you should be able to see the process in the "Python 2.7.6 Shell window" via IDLE.

Well, I suggest to you using the script I've attached, instead of the old one you've got, and we'll see what happen (don't forget to change the directories!).

Put all the files in the same folder and launch the decoding.

This is almost the last test because if it doesn't work after the final solution, it will be beyond my knowledge. Plus, I don't have this game anymore so I can't try by myself and, honestly, I don't even remember which script I used. If you still have some troubles, take the time to convert .ebx files to .txt and I'll see what I can do for you.
[scrip-xas-easpeex.zip](https://xentaxbackup.github.io/file/13103_scrip-xas-easpeex.zip)
## Post #7
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-14T01:41:40+00:00
- Post Title: Medal of Honor Warfighter

> Reply from Vosvoy
>
> Well, I suggest to you using the script I've attached, instead of the old one you've got, and we'll see what happen (don't forget to change the directories!).
[/i]

```
  File "E:\Games\Medal of Honor Warfighter\decode\fb3decoder.py", line 561, in <module>
    main()
  File "E:\Games\Medal of Honor Warfighter\decode\fb3decoder.py", line 551, in main
    dbx=Dbx(f,relPath)
  File "E:\Games\Medal of Honor Warfighter\decode\fb3decoder.py", line 301, in __init__
    self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHii",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
  File "E:\Games\Medal of Honor Warfighter\decode\fb3decoder.py", line 154, in __init__
    self.name            = keywordDict[varList[0]]
KeyError: 3741007056L
```

EBX to TXT

```
  File "E:\Games\Medal of Honor Warfighter\EBXtoTEXT.py", line 416, in <module>
    main()
  File "E:\Games\Medal of Honor Warfighter\EBXtoTEXT.py", line 48, in main
    createGuidTable()
  File "E:\Games\Medal of Honor Warfighter\EBXtoTEXT.py", line 65, in createGuidTable
    dbx=Dbx(f,relPath)
  File "E:\Games\Medal of Honor Warfighter\EBXtoTEXT.py", line 203, in __init__
    self.fieldDescriptors=[FieldDescriptor(self.unpack("IHHii",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
  File "E:\Games\Medal of Honor Warfighter\EBXtoTEXT.py", line 152, in __init__
    self.name            = keywordDict[varList[0]]
KeyError: 3741007056L
```

Maybe you can understand I send you EBX files - [https://mega.nz/#!rVoAhZxa!JcoEAHdqryT4 ... yvjb0wVzlE](https://mega.nz/#!rVoAhZxa!JcoEAHdqryT4pDP_Kzfhlt5BKQa7MzIgayvjb0wVzlE)
## Post #8
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-15T12:03:53+00:00
- Post Title: Medal of Honor Warfighter

> Maybe you can understand I send you EBX files - https://mega.nz/#!rVoAhZxa!JcoEAHdqryT4 ... yvjb0wVzlE

I'll see if I can know what the problem is with that soon, don't have a lot of time right now.

EDIT: You gave me .ebx files whereas I already got those files converted to .txt.

Could you share some .chunks files? For instance, Audio\Music\Shell\Music_Shell -> 9b33f95e65a329813520297d215f70bb (This is the chunk's name. I know that thanks to my .ebx file). 

Do a quick search in the Windows Search Bar in the dumped chunks folder. I'll keep your .ebx files, just in case.

Cordialy.
## Post #9
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-15T13:14:31+00:00
- Post Title: Medal of Honor Warfighter

> Reply from Vosvoy
>
> Could you share some .chunks files? For instance, Audio\Music\Shell\Music_Shell -> 9b33f95e65a329813520297d215f70bb (This is the chunk's name. I know that from my .ebx file).
Hmm... I do not have such a chunk in the files.
While there were no errors when extracting files.
Edit: You extracted files from the PC exactly, maybe you are from XBOX?
## Post #10
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-15T13:52:31+00:00
- Post Title: Medal of Honor Warfighter

> Reply from VladlenCry
>
> maybe you are from XBOX?

Absolutely not. One thing I'm sure is that I used a PC version of this game (100% sure, because .XMAs are a pain in the ass to convert manually). But, I can't remember which script I used and if the game was in Beta or what. I'm just hoping you're not using a Xbox version because all of that would be a big misunderstanding and I've no solution for you in this case.

Listen, when I open my .txt file, I can see that:

```
    $::AudioGraphNodeData
        $::DataContainer
    Trigger::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 3
        IsConnected True
    Release::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 6
        IsConnected True
    A::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    D::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    S::AudioGraphNodePort
        UnconnectedValue 1.0
        ValueIndex 0
        IsConnected False
    R::AudioGraphNodePort
        UnconnectedValue 3.0
        ValueIndex 0
        IsConnected False
    Value::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 4
        IsConnected True
    Finished::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 5
        IsConnected True
AudioGraphEvent 34a77ea08272294e9e87b8f93d076dd0
    $::AudioGraphParameter
        $::DataContainer
        DefaultValue 0.0
        NameHash 230748069
        ValueIndex 1
AudioGraphEvent 9a1bf0d8703d2f4abdc3aa2d59e066c5
    $::AudioGraphParameter
        $::DataContainer
        DefaultValue 0.0
        NameHash 2089401213
        ValueIndex 2
FlatOutputNodeData 2d3df0c54c429a4abd99f99182ed80d2
    $::OutputNodeData
        $::AudioGraphNodeData
            $::DataContainer
        In::AudioGraphNodePort
            UnconnectedValue 0.0
            ValueIndex 0
            IsConnected True
        AmplitudeScale::AudioGraphNodePort
            UnconnectedValue 1.0
            ValueIndex 0
            IsConnected False
        BypassHeadroom::AudioGraphNodePort
            UnconnectedValue 0.0
            ValueIndex 0
            IsConnected False
        LowPassFreq::AudioGraphNodePort
            UnconnectedValue 24000.0
            ValueIndex 0
            IsConnected False
        MinDistance 1000.0
        AttenuationCurve::AudioCurve
            Points *nullArray*
            CurveType AudioCurveType_Spline
        FalloffInner 0.0
        FalloffOuter 100.0
        FalloffClamp 0.0
        FalloffCurve DCGF_None
        Solo False
        HFDampingDistance 0.0
        HFDampingObstruction 0.0
        HFDampingOcclusion 0.0
        Gain 10.0
        MainSend settings/master/1185ef5fb8682945959a3ed31e93e6c4
        EnableHdr False
        TransformSource OutputTransformSource_Sound
        OutputName Flat
        OutputNameHash 2088683098
        LowPassPlugin::SoundGraphPluginRef
            IsValid True
            VoiceIndex 0
            PluginIndex 4
        VuPlugin::SoundGraphPluginRef
            IsValid True
            VoiceIndex 0
            PluginIndex 5
        MainSendPlugin::SoundGraphPluginRef
            IsValid True
            VoiceIndex 0
            PluginIndex 7
    Angle 80.0
    ReverbGain -12.0
    ReverbSend *nullGuid*
    CenterLevel::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    LfeLevel::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    ReverbLevel::AudioGraphNodePort
        UnconnectedValue 1.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_1::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_2::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_3::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_4::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_5::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_6::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_7::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSendLevel_8::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    AUXSends *nullGuid*
    PanPlugin::SoundGraphPluginRef
        IsValid True
        VoiceIndex 0
        PluginIndex 6
    ReverbSendPlugin::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_1::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_2::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_3::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_4::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_5::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_6::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_7::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
    AUXSendPlugin_8::SoundGraphPluginRef
        IsValid False
        VoiceIndex 0
        PluginIndex 0
ReceiveEntry b7d0dc5638d7ae419785900298280589
    $::AudioGraphNodePortGroup
        $::DataContainer
    Out::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 3
        IsConnected True
    Source 34a77ea08272294e9e87b8f93d076dd0
    Parameter 0.0
    SavedValue 0.0
ReceiveEntry b88819fc01536a4e9af54d90ffc1b70e
    $::AudioGraphNodePortGroup
        $::DataContainer
    Out::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 6
        IsConnected True
    Source 9a1bf0d8703d2f4abdc3aa2d59e066c5
    Parameter 0.0
    SavedValue 0.0
ReceiveNodeData eabe5abee8cf3f42859d5a0b6ed56548
    $::AudioGraphNodeData
        $::DataContainer
    Entries::array
        member b7d0dc5638d7ae419785900298280589
        member b88819fc01536a4e9af54d90ffc1b70e
SamplerNodeData 880890b8322b084287b7f6ca333e0ded
    $::AudioGraphNodeData
        $::DataContainer
    ExternalWave::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Variation::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Offset::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Delay::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Pitch::AudioGraphNodePort
        UnconnectedValue 1.0
        ValueIndex 0
        IsConnected False
    Amplitude::AudioGraphNodePort
        UnconnectedValue 1.0
        ValueIndex 4
        IsConnected True
    EnableStep::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Buffer::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Trigger::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 3
        IsConnected True
    Release::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 5
        IsConnected True
    Step::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Output::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected True
    Finished::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Buffered::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Position::AudioGraphNodePort
        UnconnectedValue 0.0
        ValueIndex 0
        IsConnected False
    Wave music/shell/assets/mohw_music_menuscreen/9b33f95e65a329813520297d215f70bb
    BasePitch 1.0
    Loop LtForward
    ShuffleSegments False
    Timeout -1.0
    Plugins::array
        member::SamplerPlugins
            SndPlayer::SoundGraphPluginRef
                IsValid True
                VoiceIndex 0
                PluginIndex 0
            Resample::SoundGraphPluginRef
                IsValid True
                VoiceIndex 0
                PluginIndex 1
            Pause::SoundGraphPluginRef
                IsValid True
                VoiceIndex 0
                PluginIndex 2
            Gain::SoundGraphPluginRef
                IsValid True
                VoiceIndex 0
                PluginIndex 3
SoundGraphData 7981c89ef1327c4787167aa24694896c
    $::AudioGraphData
        $::DataContainer
        Nodes::array
            member eabe5abee8cf3f42859d5a0b6ed56548
            member 9d7dacba5746284281ed81e7bf730218
            member 880890b8322b084287b7f6ca333e0ded
            member 2d3df0c54c429a4abd99f99182ed80d2
        PublicParameters *nullArray*
        PublicEvents::array
            member 34a77ea08272294e9e87b8f93d076dd0
            member 9a1bf0d8703d2f4abdc3aa2d59e066c5
            member *nullGuid*
        PublicAssetParameters *nullArray*
        PublicValueCount 3
        ValueCount 7
    Info::SoundGraphInfo
        Voices::array
            member::SoundGraphVoiceInfo
                Plugins::array
                    member::SoundGraphPluginInfo
                        Id 1399738417
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 2
                        EnableAttributeReadMask 7
                    member::SoundGraphPluginInfo
                        Id 1383297072
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 2
                        EnableAttributeReadMask 0
                    member::SoundGraphPluginInfo
                        Id 1348564272
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 2
                        EnableAttributeReadMask 0
                    member::SoundGraphPluginInfo
                        Id 1197566256
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 2
                        EnableAttributeReadMask 0
                    member::SoundGraphPluginInfo
                        Id 1279865392
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 2
                        EnableAttributeReadMask 0
                    member::SoundGraphPluginInfo
                        Id 1450528048
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 2
                        EnableAttributeReadMask 320
                    member::SoundGraphPluginInfo
                        Id 1349399089
                        ConstructParams::array
                            member::SoundGraphPluginConstructParam
                                Index 0
                                Value 45.0
                            member::SoundGraphPluginConstructParam
                                Index 1
                                Value 135.0
                            member::SoundGraphPluginConstructParam
                                Index 2
                                Value 2.0
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Unconnected
                            VoiceIndex 0
                            Bus *nullGuid*
                            Parameters *nullArray*
                        OutputChannelCount 4
                        EnableAttributeReadMask 0
                    member::SoundGraphPluginInfo
                        Id 1399156272
                        ConstructParams *nullArray*
                        Connection::SoundGraphPluginConnection
                            ConnectionType SoundGraphPluginConnectionType_Bus
                            VoiceIndex 0
                            Bus settings/master/1185ef5fb8682945959a3ed31e93e6c4
                            Parameters *nullArray*
                        OutputChannelCount 4
                        EnableAttributeReadMask 0
                ProcessingStage 0
        LinkedPluginAttributes *nullArray*
        PluginsParamCount 50
        PluginCount 8
    InputParameters *nullArray*
    OutputParameters *nullArray*
    InputEvents::array
        member 34a77ea08272294e9e87b8f93d076dd0
        member 9a1bf0d8703d2f4abdc3aa2d59e066c5
    OutputEvents *nullArray*
SoundPatchAsset 862e41079cb3484eb9ba9913082b9c9a #primary instance
    $::SoundGraphAsset
        $::SoundAsset
            $::Asset
                $::DataContainer
                Name MOHW/Audio/Music/Shell/Music_Shell
            Scope *nullGuid*
        Graph 7981c89ef1327c4787167aa24694896c
        Mixer *nullGuid*
    OutputNodes::array
        member 2d3df0c54c429a4abd99f99182ed80d2
    Loudness 75.0
    UIAttenuationControl UI_Attenuation_None
    Radius 0.5
    DopplerFactor 0.0
    MasterPitch 1.0
    IsLooping True
    IsPersistent False
    DefaultStartEvent 34a77ea08272294e9e87b8f93d076dd0
    DefaultStopEvent 9a1bf0d8703d2f4abdc3aa2d59e066c5
    DefaultEnterScopeEvent 34a77ea08272294e9e87b8f93d076dd0
    DefaultForceInitEvent *nullGuid*
    MixGroup mixers/mohw_mixersystem/d03cfbde62d3bc439cbc4c86edce7e4c
    RoloffStart 0.0
    RoloffStop 100.0
    RoloffClamp 0.0
    RoloffCurve DCGF_None
    EnableSoundAreaCheck False
    SoundAreaCheckMinDistanceDelta 1.0
```

 >>   Wave music/shell/assets/mohw_music_menuscreen/9b33f95e65a329813520297d215f70bb is the line where you can, by default, find the chunk name (but maybe I'm wrong). If you don't find any of those chunk names, well, something is weird. Before anything, try to search all those chunk names (we'll see if you've got an other version of the game).
## Post #11
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-15T14:05:01+00:00
- Post Title: Medal of Honor Warfighter

> Reply from Vosvoy
>
> VladlenCry wrote:I'm just hoping you're not using a Xbox version because all that would be a big misunderstanding and I've no solution for you in this case.
I'm from the PC, licensed game.
I tried to search for chunks of members, the results were zero. In some games, members are versions of the sound of the main file.
You can share the script for converting ebx to txt? Maybe I do not have that version of the script, so I can not convert them to text files.
## Post #12
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-15T14:26:58+00:00
- Post Title: Medal of Honor Warfighter

> Reply from VladlenCry
>
> I'm from the PC, licensed game.

Yeah, I definitely didn't have this version, maybe an early access one.

> Reply from VladlenCry
>
> You can share the script for converting ebs to txt?

The last EBXtoTXT script I used was for BF1. You'll probably have some trouble with it. Anyway, I attached it.

I really don't understand why it's not working for you. Maybe some updates screwed up the chunks order and you don't have the same chunk names as me. It happened with BF3, as the creator of the original script had to update it after BF3 updates. But, so many versions of this freaking script are available on the web and, again, I can't tell which one I used (I deleted it after process).
[EBXtoTEXT.zip](https://xentaxbackup.github.io/file/13108_EBXtoTEXT.zip)
## Post #13
- Username: VladlenCry
- Rank: advanced
- Number of posts: 48
- Joined date: Wed Sep 10, 2014 7:40 am
- Post datetime: 2017-07-15T14:35:07+00:00
- Post Title: Medal of Honor Warfighter

> Reply from Vosvoy
>
> The last EBXtoTXT script I used was for BF1. You'll probably have some trouble with it. Anyway, I attached it.
Apparently I have it, because The same error produces. Does not convert.
## Post #14
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-07-15T14:45:21+00:00
- Post Title: Medal of Honor Warfighter

> Reply from VladlenCry
>
> Vosvoy wrote:The last EBXtoTXT script I used was for BF1. You'll probably have some trouble with it. Anyway, I attached it.
Apparently I have it, because The same error produces. Does not convert.

Alright, sent you a PM. We'll see one thing together. The result will be post here.
## Post #15
- Username: Vosvoy
- Rank: veteran
- Number of posts: 127
- Joined date: Fri Feb 18, 2011 11:58 pm
- Post datetime: 2017-08-23T18:18:25+00:00
- Post Title: Medal of Honor Warfighter

Alright,

If you want to extract MOHW sounds and musics, use this script with ealayer3.exe Zench's tool (don't forget to edit dir paths):

```
import string
import sys
from binascii import hexlify
from struct import unpack
import os
from cStringIO import StringIO
import cProfile
import cPickle
import subprocess
from ctypes import *

#adjust input and output folders here
inputFolder=r"D:\MOHWResearches\Dump0"
outputFolder=r"D:\MOHWResearches\Out0\Audio"

#Download Zench's tool so the script can handle EALayer3.
ealayer3Path=r"D:\MOHWResearches\Script\ealayer3.exe" 

#These paths are relative to the dumpDirectory. They don't need to be changed.
ebxFolder    = r"bundles\ebx" 
chunkFolder  = r"chunks"
chunkFolder2 = r"bundles\chunks" #if the chunk is not found in the first folder, use this one

#make the paths absolute and normalize the slashes
ebxFolder,chunkFolder,chunkFolder2 = [os.path.normpath(inputFolder+"\\"+path)+"\\" for path in (ebxFolder, chunkFolder, chunkFolder2)]
targetDirectory=os.path.normpath(outputFolder) #it's an absolute path already

EXTENSION=".txt"
SEP="    "

#let's see if XAS and Speex exist
try:
    xas = cdll.LoadLibrary("xas")
    def decodeXas(chunkPath, target, samplesOffset):
        makeLongDirs(target)
        try:
            xas.decode(chunkPath, target, samplesOffset)
        except:
            print "Error executing XAS dll."
    def decodePcm(chunkPath, target, samplesOffset):
        makeLongDirs(target)
        xas.swapEndianPcm(chunkPath, target, samplesOffset)
    print "XAS1 dll detected."
except:
    def decodeXas(chunkPath, target, samplesOffset):
        print "Skipping XAS1 due to missing dll."
    def decodePcm(chunkPath, target, samplesOffset):
        print "Skipping PCM due to missing dll."
    print "XAS1 dll not detected."

try:
    speex = cdll.LoadLibrary("easpeex")
    def decodeSpeex(chunkPath, target, samplesOffset):
        makeLongDirs(target)
        speex.decode(chunkPath, target, samplesOffset)
    print "EASpeex dll detected."
except:
    def decodeSpeex(chunkPath, target, samplesOffset):
        print "Skipping Speex due to missing dll."
    print "EASpeex dll not detected."

#By default Python opens a new EALayer3 window for a split second and puts focus on it. This info makes no window show up at all.
startupinfo = subprocess.STARTUPINFO()
startupinfo.dwFlags |= subprocess.STARTF_USESHOWWINDOW
startupinfo.wShowWindow = subprocess.SW_HIDE

try:
    #make sure EALayer3 exists by calling it once without arguments 
    #subprocess.Popen([ealayer3Path],startupinfo=startupinfo)
    def decodeEaLayer(chunkPath, target, samplesOffset):
        makeLongDirs(target)
        try:
            process = subprocess.Popen([ealayer3Path,chunkPath,"-i",str(samplesOffset),"-o",target,"-s","all"], stderr=subprocess.PIPE,startupinfo=startupinfo)
            process.communicate() #this should set the returncode
            if process.returncode:
                print process.stderr.readlines()
        except:
            print "Error executing EALayer3."
    print "EALayer3 tool detected."
except:
    def decodeEaLayer(chunkPath, target, samplesOffset):
        print "Skipping EALayer3 due to missing tool."
    print "EALayer3 tool not detected."

def makeLongDirs(path):
    #create folders if necessary and return the file handle
    #first of all, create one folder level manully because makedirs might fail
    path=os.path.normpath(path)
    pathParts=path.split("\\")
    manualPart="\\".join(pathParts[:2])
    if not os.path.isdir(manualPart): os.makedirs(manualPart)
    
    #now handle the rest, including extra long path names
    folderPath=lp(os.path.dirname(path))
    if not os.path.isdir(folderPath): os.makedirs(folderPath)

def open2(path,mode="rb"):
    if mode=="wb": makeLongDirs(path)
    return open(lp(path),mode)


def main():
    for dir0, dirs, ff in os.walk(ebxFolder):
        for fname in ff:
            if fname[-4:]!=".ebx": continue
            absPath=os.path.join(dir0,fname)
            relPath=absPath[len(ebxFolder):-4]
            
            f=open(lp(absPath),"rb")
            try:
                dbx=Dbx(f,relPath)
                print fname    
                f.close()
            except ValueError as msg:
                f.close()
                if str(msg).startswith("The file is not ebx: "):
                    continue
                else: asdf
            dbx.decode()

def lp(path): #long pathnames
    if len(path)<=247 or path=="" or path[:4]=='\\\\?\\': return path
    return unicode('\\\\?\\' + os.path.normpath(path))

class Stub:
    pass
          
def hasher(keyword): #32bit FNV-1 hash with FNV_offset_basis = 5381 and FNV_prime = 33
    hash = 5381
    for byte in keyword:
        hash = (hash*33) ^ ord(byte)
    return hash & 0xffffffff # use & because Python promotes the num instead of intended overflow
class Header:
    def __init__(self,varList): ##all 4byte unsigned integers
        self.absStringOffset     = varList[0]  ## absolute offset for string section start
        self.lenStringToEOF      = varList[1]  ## length from string section start to EOF
        self.numGUID             = varList[2]  ## number of external GUIDs
        self.null                = varList[3]  ## 00000000
        self.numInstanceRepeater = varList[4]
        self.numComplex          = varList[5]  ## number of complex entries
        self.numField            = varList[6]  ## number of field entries
        self.lenName             = varList[7]  ## length of name section including padding
        self.lenString           = varList[8]  ## length of string section including padding
        self.numArrayRepeater    = varList[9]
        self.lenPayload          = varList[10] ## length of normal payload section; the start of the array payload section is absStringOffset+lenString+lenPayload
class FieldDescriptor:
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
class ComplexDescriptor:
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.fieldStartIndex = varList[1] #the index of the first field belonging to the complex
        self.numField        = varList[2] #the total number of fields belonging to the complex
        self.alignment       = varList[3]
        self.type            = varList[4]
        self.size            = varList[5] #total length of the complex in the payload section
        self.secondarySize   = varList[6] #seems deprecated
class InstanceRepeater:
    def __init__(self,varList):
        self.null            = varList[0] #called "internalCount", seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc,dbxhandle):
        self.desc=desc
        self.dbx=dbxhandle #lazy
    def get(self,name):
        pathElems=name.split("/")
        curPos=self
        if pathElems[-1].find("::")!=-1: #grab a complex
            for elem in pathElems:
                try:
                    curPos=curPos.go1(elem)
                except Exception,e:
                    raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
            return curPos
        #grab a field instead
        for elem in pathElems[:-1]:
            try:
                curPos=curPos.go1(elem)
            except Exception,e:
                raise Exception("Could not find complex with name: "+str(e)+"\nFull path: "+name+"\nFilename: "+self.dbx.trueFilename)
        for field in curPos.fields:
            if field.desc.name==pathElems[-1]:
                return field
            
        raise Exception("Could not find field with name: "+name+"\nFilename: "+self.dbx.trueFilename)

    def go1(self,name): #go once
        for field in self.fields:
            if field.desc.type in (0x0029, 0xd029,0x0000,0x0041):
                if field.desc.name+"::"+field.value.desc.name == name:
                    return field.value
        raise Exception(name)
class Field:
    def __init__(self,desc):
        self.desc=desc

numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}

class Dbx:
    def __init__(self, f, relPath):
        #metadata
        magic=f.read(4)
        if not magic=="\xCE\xD1\xB2\x0F":
            raise ValueError("The file is not ebx: "+relPath)
        self.trueFilename=""
        self.header=Header(unpack("11I",f.read(44)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)   
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)]
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        for instanceRepeater in self.instanceRepeaters:
            for repetition in xrange(instanceRepeater.repetitions):
                instanceGUID=f.read(16)
                self.internalGUIDs.append(instanceGUID)
                if instanceGUID==self.primaryInstanceGUID: self.isPrimaryInstance=True
                else: self.isPrimaryInstance=False

                inst = self.readComplex(instanceRepeater.complexIndex,f)
                if self.isPrimaryInstance: self.prim=inst
                self.instances.append( (instanceGUID,inst) )
        f.close()
       
        #if no filename found, use the relative input path instead
        #it's just as good though without capitalization
        if self.trueFilename=="":
            self.trueFilename=relPath
       

    def readComplex(self, complexIndex,f):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc,self)
       
        startPos=f.tell()                 
        cmplx.fields=[]
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
            cmplx.fields.append(self.readField(fieldIndex,f))
       
        f.seek(startPos+complexDesc.size)
        return cmplx


    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc)
       
        if fieldDesc.type in (0x0029, 0xd029,0x0000):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc,self)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
           
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            f.seek(self.header.absStringOffset+unpack("I",f.read(4))[0])
            string=""
            while 1:
                a=f.read(1)
                if a=="\x00": break
                else: string+=a
            f.seek(startPos+4)
           
            if len(string)==0: field.value="*nullString*" #actually the string is ""
            else: field.value=string
           
            if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
           
                   
        elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
            compareValue=unpack("I",f.read(4))[0]
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break
        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        else:
            (typ,length)=numDict[fieldDesc.type]
            num=unpack(typ,f.read(length))[0]
            field.value=num
       
        return field

    def decode(self):
        if not self.prim.desc.name=="SoundWaveAsset": return

        histogram=dict() #count the number of times each chunk is used by a variation to obtain the right index

        Chunks=[]
        for i in self.prim.get("$::SoundDataAsset/Chunks::array").fields:
            chnk=Stub()
            Chunks.append(chnk)
            chnk.ChunkId=i.value.get("ChunkId").value
            
            chnk.ChunkSize=i.value.get("ChunkSize").value

        Variations=[]
        Segments=[]

        SegmentCount=0
        for var in self.instances:
            if not var[1].desc.name=="SoundWaveVariation": continue
            Variation=Stub()
            Variations.append(Variation)
            Variation.ChunkIndex=var[1].get("ChunkIndex").value
            Variation.ChunkId=hexlify(Chunks[Variation.ChunkIndex].ChunkId)
            Variation.ChunkSize=Chunks[Variation.ChunkIndex].ChunkSize

            FirstSegmentIndex=len(Segments);
            for seg in var[1].get("Segments::array").fields:
                Segment=Stub()
                Segments.append(Segment)
                Segment.SamplesOffset = seg.value.get("SamplesOffset").value
                Segment.SeekTableOffset = seg.value.get("SeekTableOffset").value
                Segment.SegmentLength = seg.value.get("SegmentLength").value
                SegmentCount+=1

            Variation.Segments=Segments[FirstSegmentIndex:SegmentCount]
        
            #find the appropriate index
            #the index from the Variations array can get large very fast
            #instead, make my own index starting from 0 for every chunkIndex
            if Variation.ChunkIndex in histogram: #has been used previously already
                Variation.Index=histogram[Variation.ChunkIndex]
                histogram[Variation.ChunkIndex]+=1
            else:
                Variation.Index=0
                histogram[Variation.ChunkIndex]=1


        
        #for var in self.prim.get("RuntimeVariations::array").fields:
        
        #everything is laid out neatly now
        #Variation fields: ChunkId, ChunkSize, Index, ChunkIndex, SeekTablesSize, FirstLoopSegmentIndex, LastLoopSegmentIndex, Segments
        #Variation.Segments fields: SamplesOffset, SeekTableOffset, SegmentLength

        ChunkHandles=dict() #for each ebx, keep track of all file handles

##        chunkErrors=set() #
        for Variation in Variations:
            try:
                f=ChunkHandles[Variation.ChunkId]
            except:
                try:
                    f=open2(chunkFolder+Variation.ChunkId+".chunk")
                    currentChunkName=chunkFolder+Variation.ChunkId+".chunk"
                except IOError:
                    try:
                        f=open2(chunkFolder2+Variation.ChunkId+".chunk")
                        currentChunkName=chunkFolder2+Variation.ChunkId+".chunk"
                    except:
                        #print "Chunk does not exist: "+Variation.ChunkId+" "+self.trueFilename
                        #chunkErrors.add("Chunk does not exist: "+Variation.ChunkId+" "+self.trueFilename)
                        continue #do NOT return, instead print the messages at the very end
                ChunkHandles[Variation.ChunkId]=f


            for ijk in xrange(len(Variation.Segments)):
                Segment=Variation.Segments[ijk]
                f.seek(Segment.SamplesOffset)
                magic=f.read(4)
                
                if magic!="\x48\x00\x00\x0c":
                    continue
                    raise Exception("Wrong XAS magic.")

                audioType=ord(f.read(1)) #0x14 is XAS, 0x16 is EALayer3, 0x13 is XMA, 0x12 is PCM
                target=os.path.join(targetDirectory,self.trueFilename)+" "+str(Variation.ChunkIndex)+" "+str(Variation.Index)+" "+str(ijk)
                
                if audioType==0x16: #EALayer3
                    target+=".mp3"
                    decodeEaLayer(currentChunkName, target, Segment.SamplesOffset)  
                elif audioType==0x19: #Speex
                    target+=".wav"
                    decodeSpeex(currentChunkName, target, Segment.SamplesOffset)
                elif audioType==0x14: #XAS1
                    target+=".wav"
                    decodeXas(currentChunkName, target, Segment.SamplesOffset)
                elif audioType==0x12: #16bit big endian PCM
                    target+=".wav"
                    decodePcm(currentChunkName, target, Segment.SamplesOffset)
                else:
                    print "Unknown type "+hex(audioType)+": "+Variation.ChunkId+" "+self.trueFilename

        for key in ChunkHandles:
            ChunkHandles[key].close()
        print self.trueFilename
        #print Variation.ChunkId+" "+self.trueFilename

main()
```


Then, you can use the following script to convert .ebx files to .txt files to be able to read them (again, don't forget to change dir paths):

```
import string
import sys
from binascii import hexlify
from struct import unpack
import os
from cStringIO import StringIO
import cProfile
import cPickle

#adjust input and output folders here
inputFolder=r"D:\MOHWResearches\Dump\ebx"
outputFolder=r"D:\MOHWResearches\Out\TxtEbx"
guidTableName="guidTable mohw" #name of the guid table file

EXTENSION=".txt"
SEP="    "

#the script can use the actual filenames in the explorer for the guid table (fast)
#or it can parse almost the entire file to retrieve the filename (slow, but necessary when the explorer names are just hashes)
#in case #2, create a separate guidTable file, in case#1 do not create that file.
#True/False
useExplorerNames=True


#ignore all instances and fields with these names when converting to text:
IGNOREINSTANCES=[]
IGNOREFIELDS=[]
##IGNOREINSTANCES=["ShaderAdjustmentData","SocketData","WeaponSkinnedSocketObjectData","WeaponRegularSocketObjectData"]
##IGNOREFIELDS=["Mesh3pTransforms","Mesh3pRigidMeshSocketObjectTransforms"]


#run createGuidTable or dumpText, or both (preferably in the right order)
#When using explorer names, do not change anything below.
#When not using explorer names you might want to make the guid table first, then restart the script to dump text only,
#though it should work fine without change too.
def main():
    createGuidTable()
    dumpText()




##############################################################
##############################################################
if useExplorerNames:
    def createGuidTable(): #guid vs filename
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                path=os.path.join(dir0,fname)
                f=open(path,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                #grab the file guid directly, absolute offset 48 bytes
                f.seek(48)
                fileguid=f.read(16)
                f.close()
                filename=path[len(inputFolder):-4].replace("\\","/")
                guidTable[fileguid]=filename
else:
    def createGuidTable():
        for dir0, dirs, ff in os.walk(inputFolder):
            for fname in ff:
                f=open(dir0+"\\"+fname,"rb")
                if f.read(4)!="\xCE\xD1\xB2\x0F":
                    f.close()
                    continue
                dbx=Dbx(f)
                guidTable[dbx.fileGUID]=dbx.trueFilename
        f5=open(guidTableName,"wb") #write the table
        cPickle.dump(guidTable,f5)
        f5.close()

def dumpText():
    for dir0, dirs, ff in os.walk(inputFolder):
        for fname in ff:
            f=open(dir0+"\\"+fname,"rb")
            if f.read(4)!="\xCE\xD1\xB2\x0F":
                f.close()
                continue
            dbx=Dbx(f)
            dbx.dump(outputFolder)
           
try:
    from ctypes import *
    floatlib = cdll.LoadLibrary("floattostring")
    def formatfloat(num):
        bufType = c_char * 100
        buf = bufType()
        bufpointer = pointer(buf)
        floatlib.convertNum(c_double(num), bufpointer, 100)
        rawstring=(buf.raw)[:buf.raw.find("\x00")]
        if rawstring[:2]=="-.": return "-0."+rawstring[2:]
        elif rawstring[0]==".": return "0."+rawstring[1:]
        elif "e" not in rawstring and "." not in rawstring: return rawstring+".0"
        return rawstring
except:
    def formatfloat(num):
        return str(num)
def hasher(keyword): #32bit FNV-1 hash with FNV_offset_basis = 5381 and FNV_prime = 33
    hash = 5381
    for byte in keyword:
        hash = (hash*33) ^ ord(byte)
    return hash & 0xffffffff # use & because Python promotes the num instead of intended overflow
class Header:
    def __init__(self,varList): ##all 4byte unsigned integers
        self.absStringOffset     = varList[0]  ## absolute offset for string section start
        self.lenStringToEOF      = varList[1]  ## length from string section start to EOF
        self.numGUID             = varList[2]  ## number of external GUIDs
        self.null                = varList[3]  ## 00000000
        self.numInstanceRepeater = varList[4]
        self.numComplex          = varList[5]  ## number of complex entries
        self.numField            = varList[6]  ## number of field entries
        self.lenName             = varList[7]  ## length of name section including padding
        self.lenString           = varList[8]  ## length of string section including padding
        self.numArrayRepeater    = varList[9]
        self.lenPayload          = varList[10] ## length of normal payload section; the start of the array payload section is absStringOffset+lenString+lenPayload
class FieldDescriptor:
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.type            = varList[1]
        self.ref             = varList[2] #the field may contain another complex
        self.offset          = varList[3] #offset in payload section; relative to the complex containing it
        self.secondaryOffset = varList[4]
class ComplexDescriptor:
    def __init__(self,varList,keywordDict):
        self.name            = keywordDict[varList[0]]
        self.fieldStartIndex = varList[1] #the index of the first field belonging to the complex
        self.numField        = varList[2] #the total number of fields belonging to the complex
        self.alignment       = varList[3]
        self.type            = varList[4]
        self.size            = varList[5] #total length of the complex in the payload section
        self.secondarySize   = varList[6] #seems deprecated
class InstanceRepeater:
    def __init__(self,varList):
        self.null            = varList[0] #called "internalCount", seems to be always null
        self.repetitions     = varList[1] #number of instance repetitions
        self.complexIndex    = varList[2] #index of complex used as the instance
class arrayRepeater:
    def __init__(self,varList):
        self.offset          = varList[0] #offset in array payload section
        self.repetitions     = varList[1] #number of array repetitions
        self.complexIndex    = varList[2] #not necessary for extraction
class Complex:
    def __init__(self,desc):
        self.desc=desc
class Field:
    def __init__(self,desc):
        self.desc=desc

numDict={0x0035:("I",4),0xc10d:("I",4),0xc14d:("d",8),0xc0ad:("?",1),0xc0fd:("i",4),0xc0bd:("B",1),0xc0ed:("h",2), 0xc0dd:("H",2), 0xc13d:("f",4)}

class Dbx:
    def __init__(self, f):
        #metadata
        self.trueFilename=""
        self.header=Header(unpack("11I",f.read(44)))
        self.arraySectionstart=self.header.absStringOffset+self.header.lenString+self.header.lenPayload
        self.fileGUID, self.primaryInstanceGUID = f.read(16), f.read(16)   
        self.externalGUIDs=[(f.read(16),f.read(16)) for i in xrange(self.header.numGUID)]
        self.keywords=str.split(f.read(self.header.lenName),"\x00")
        self.keywordDict=dict((hasher(keyword),keyword) for keyword in self.keywords)
        self.fieldDescriptors=[FieldDescriptor(unpack("IHHII",f.read(16)), self.keywordDict) for i in xrange(self.header.numField)]
        self.complexDescriptors=[ComplexDescriptor(unpack("IIBBHHH",f.read(16)), self.keywordDict) for i in xrange(self.header.numComplex)]
        self.instanceRepeaters=[InstanceRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numInstanceRepeater)]
        while f.tell()%16!=0: f.seek(1,1) #padding
        self.arrayRepeaters=[arrayRepeater(unpack("3I",f.read(12))) for i in xrange(self.header.numArrayRepeater)]

        #payload
        f.seek(self.header.absStringOffset+self.header.lenString)
        self.internalGUIDs=[]
        self.instances=[] # (guid, complex)
        for instanceRepeater in self.instanceRepeaters:
            for repetition in xrange(instanceRepeater.repetitions):
                instanceGUID=f.read(16)
                self.internalGUIDs.append(instanceGUID)
                if instanceGUID==self.primaryInstanceGUID: self.isPrimaryInstance=True
                else: self.isPrimaryInstance=False
               
                self.instances.append( (instanceGUID,self.readComplex(instanceRepeater.complexIndex,f)) )
        f.close()
       
       

    def readComplex(self, complexIndex,f):
        complexDesc=self.complexDescriptors[complexIndex]
        cmplx=Complex(complexDesc)
       
        startPos=f.tell()                 
        cmplx.fields=[]
        for fieldIndex in xrange(complexDesc.fieldStartIndex,complexDesc.fieldStartIndex+complexDesc.numField):
            f.seek(startPos+self.fieldDescriptors[fieldIndex].offset)
            cmplx.fields.append(self.readField(fieldIndex,f))
       
        f.seek(startPos+complexDesc.size)
        return cmplx


    def readField(self,fieldIndex,f):
        fieldDesc = self.fieldDescriptors[fieldIndex]
        field=Field(fieldDesc)
       
        if fieldDesc.type in (0x0029, 0xd029,0x0000):
            field.value=self.readComplex(fieldDesc.ref,f)
        elif fieldDesc.type==0x0041:
            arrayRepeater=self.arrayRepeaters[unpack("I",f.read(4))[0]]
            arrayComplexDesc=self.complexDescriptors[fieldDesc.ref]

##            if arrayRepeater.repetitions==0: field.value = "*nullArray*"
            f.seek(self.arraySectionstart+arrayRepeater.offset)
            arrayComplex=Complex(arrayComplexDesc)
            arrayComplex.fields=[self.readField(arrayComplexDesc.fieldStartIndex,f) for repetition in xrange(arrayRepeater.repetitions)]
            field.value=arrayComplex
           
        elif fieldDesc.type in (0x407d, 0x409d):
            startPos=f.tell()
            f.seek(self.header.absStringOffset+unpack("I",f.read(4))[0])
            string=""
            while 1:
                a=f.read(1)
                if a=="\x00": break
                else: string+=a
            f.seek(startPos+4)
           
            if len(string)==0: field.value="*nullString*" #actually the string is ""
            else: field.value=string
           
            if self.isPrimaryInstance and self.trueFilename=="" and fieldDesc.name=="Name": self.trueFilename=string
           
                   
        elif fieldDesc.type==0x0089: #incomplete implementation, only gives back the selected string
            compareValue=unpack("I",f.read(4))[0]
            enumComplex=self.complexDescriptors[fieldDesc.ref]

            if enumComplex.numField==0:
                field.value="*nullEnum*"
            for fieldIndex in xrange(enumComplex.fieldStartIndex,enumComplex.fieldStartIndex+enumComplex.numField):
                if self.fieldDescriptors[fieldIndex].offset==compareValue:
                    field.value=self.fieldDescriptors[fieldIndex].name
                    break
        elif fieldDesc.type==0xc15d:
            field.value=f.read(16)
        else:
            (typ,length)=numDict[fieldDesc.type]
            num=unpack(typ,f.read(length))[0]
            field.value=num
       
        return field
       

    def dump(self,outputFolder):
        dirName=os.path.dirname(outputFolder+self.trueFilename)
        if not os.path.isdir(dirName): os.makedirs(dirName)
        if not self.trueFilename: self.trueFilename=hexlify(self.fileGUID)
        f2=open(outputFolder+self.trueFilename+EXTENSION,"wb")
        print self.trueFilename
       
        for (guid,instance) in self.instances:
            if instance.desc.name not in IGNOREINSTANCES: #############
                if guid==self.primaryInstanceGUID: f2.write(instance.desc.name+" "+hexlify(guid)+ " #primary instance\r\n")
                else: f2.write(instance.desc.name+" "+hexlify(guid)+ "\r\n")
                self.recurse(instance.fields,f2,0)
        f2.close()

    def recurse(self, fields, f2, lvl): #over fields
        lvl+=1
        for field in fields:
            if field.desc.type in (0xc14d, 0xc0fd, 0xc10d, 0xc0ed, 0xc0dd, 0xc0bd, 0xc0ad, 0x407d, 0x409d, 0x0089):
                f2.write(lvl*SEP+field.desc.name+" "+str(field.value)+"\r\n")
            elif field.desc.type == 0xc13d:
                f2.write(lvl*SEP+field.desc.name+" "+formatfloat(field.value)+"\r\n")
            elif field.desc.type == 0xc15d:
                f2.write(lvl*SEP+field.desc.name+" "+hexlify(field.value).upper()+"\r\n") #upper case=> chunk guid
            elif field.desc.type == 0x0035:
                towrite=""
                if field.value>>31:
                    extguid=self.externalGUIDs[field.value&0x7fffffff]
                    try: towrite=guidTable[extguid[0]]+"/"+hexlify(extguid[1])
                    except: towrite=hexlify(extguid[0])+"/"+hexlify(extguid[1])
                elif field.value==0: towrite="*nullGuid*"
                else: towrite=hexlify(self.internalGUIDs[field.value-1])
                f2.write(lvl*SEP+field.desc.name+" "+towrite+"\r\n")
            elif field.desc.type==0x0041 and len(field.value.fields)==0:
                f2.write(lvl*SEP+field.desc.name+" "+"*nullArray*"+"\r\n")
            else:
                if field.desc.name not in IGNOREFIELDS: #############
                    f2.write(lvl*SEP+field.desc.name+"::"+field.value.desc.name+"\r\n")
                    self.recurse(field.value.fields,f2,lvl)


if outputFolder[-1] not in ("/","\\"): outputFolder+="/"
if inputFolder[-1] not in ("/","\\"): inputFolder+="/"


#if there's a guid table already, use it
try:
    f5=open(guidTableName,"rb")
    guidTable=cPickle.load(f5)
    f5.close()
except:
    guidTable=dict()


main()
```


That's all for me. I'm not the owner/creator of those scripts but I'm glad I kept them 'cause they're pretty old.

Cordialy

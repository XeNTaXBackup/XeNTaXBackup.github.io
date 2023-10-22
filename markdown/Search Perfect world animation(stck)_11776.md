## Post #1
- Username: FearGod
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 10, 2014 3:39 am
- Post datetime: 2014-08-12T05:40:26+00:00
- Post Title: Search Perfect world animation(stck)

Hi

I am looking for a script to 3ds max to import animations (.stck) of Perfect World


stck.h

```

using namespace System::IO;
using namespace System::Text;

public ref struct Point3f
{
        float X;
        float Y;
        float Z;
};

public ref struct Point4f
{
        float X;
        float Y;
        float Z;
        float W;
};

public ref struct KeyPointController
{
        int StartTime;
        int EndTime;
        int StartKeyPointIndex;
        int EndKeyPointIndex;
};

public ref struct AnimatedJointKeyFrames
{
        public: int JointID;
        public: int unknown1;
        public: array<Point3f^>^ PositionKeyPoints; // vectors
        public: array<KeyPointController^>^ PositionKeyPointControllers;
        public: int unknown2;
        public: array<Point4f^>^ OrientationKeyPoints; // quaternions
        public: array<KeyPointController^>^ OrientationKeyPointControllers;
};

public ref class STCK
{
        public: STCK()
        {
        }

        protected: ~STCK()
        {
        }

        public: array<unsigned char>^ Signature; // 8 byte GBK
        public: int Version;
        public: int unknown1;
        public: int unknown2;
        public: int unknown3;
        public: array<AnimatedJointKeyFrames^>^ JointKeyFrames;

        // only for loading v1
        public: void Load(String^ File)
        {
                FileStream^ fs = File::OpenRead(File);
                BinaryReader^ br = gcnew BinaryReader(fs);

                Signature = br->ReadBytes(8);
                Version = br->ReadInt32();
                int AnimatedJointCount = br->ReadInt32();
                unknown1 = br->ReadInt32();
                unknown2 = br->ReadInt32();
                unknown3 = br->ReadInt32();

                JointKeyFrames = gcnew array<AnimatedJointKeyFrames^>(AnimatedJointCount);
                for(int b=0; b<JointKeyFrames->Length; b++)
                {
                        JointKeyFrames[b] = gcnew AnimatedJointKeyFrames();
                        JointKeyFrames[b]->JointID = br->ReadInt32();
                        int PositionKeyPointCount = br->ReadInt32();
                        int Properties1KeyPointCount = br->ReadInt32();
                        JointKeyFrames[b]->unknown1 = br->ReadInt32();
                        JointKeyFrames[b]->PositionKeyPoints = gcnew array<Point3f^>(PositionKeyPointCount);
                        for(int i=0; i<JointKeyFrames[b]->PositionKeyPoints->Length; i++)
                        {
                                JointKeyFrames[b]->PositionKeyPoints[i] = gcnew Point3f();
                                JointKeyFrames[b]->PositionKeyPoints[i]->X = br->ReadSingle();
                                JointKeyFrames[b]->PositionKeyPoints[i]->Y = br->ReadSingle();
                                JointKeyFrames[b]->PositionKeyPoints[i]->Z = br->ReadSingle();
                        }
                        JointKeyFrames[b]->PositionKeyPointControllers = gcnew array<KeyPointController^>(Properties1KeyPointCount);
                        for(int i=0; i<JointKeyFrames[b]->PositionKeyPointControllers->Length; i++)
                        {
                                JointKeyFrames[b]->PositionKeyPointControllers[i] = gcnew KeyPointController();
                                JointKeyFrames[b]->PositionKeyPointControllers[i]->StartTime = br->ReadInt32();
                                JointKeyFrames[b]->PositionKeyPointControllers[i]->EndTime = br->ReadInt32();
                                JointKeyFrames[b]->PositionKeyPointControllers[i]->StartKeyPointIndex = br->ReadInt32();
                                JointKeyFrames[b]->PositionKeyPointControllers[i]->EndKeyPointIndex = br->ReadInt32();
                        }
                        int OrientationKeyPointCount = br->ReadInt32();
                        int Properties2KeyPointCount = br->ReadInt32();
                        JointKeyFrames[b]->unknown2 = br->ReadInt32();
                        JointKeyFrames[b]->OrientationKeyPoints = gcnew array<Point4f^>(OrientationKeyPointCount);
                        for(int i=0; i<JointKeyFrames[b]->OrientationKeyPoints->Length; i++)
                        {
                                JointKeyFrames[b]->OrientationKeyPoints[i] = gcnew Point4f();
                                JointKeyFrames[b]->OrientationKeyPoints[i]->X = br->ReadSingle();
                                JointKeyFrames[b]->OrientationKeyPoints[i]->Y = br->ReadSingle();
                                JointKeyFrames[b]->OrientationKeyPoints[i]->Z = br->ReadSingle();
                                JointKeyFrames[b]->OrientationKeyPoints[i]->W = br->ReadSingle();
                        }
                        JointKeyFrames[b]->OrientationKeyPointControllers = gcnew array<KeyPointController^>(Properties2KeyPointCount);
                        for(int i=0; i<JointKeyFrames[b]->OrientationKeyPointControllers->Length; i++)
                        {
                                JointKeyFrames[b]->OrientationKeyPointControllers[i] = gcnew KeyPointController();
                                JointKeyFrames[b]->OrientationKeyPointControllers[i]->StartTime = br->ReadInt32();
                                JointKeyFrames[b]->OrientationKeyPointControllers[i]->EndTime = br->ReadInt32();
                                JointKeyFrames[b]->OrientationKeyPointControllers[i]->StartKeyPointIndex = br->ReadInt32();
                                JointKeyFrames[b]->OrientationKeyPointControllers[i]->EndKeyPointIndex = br->ReadInt32();
                        }
                }

                br->Close();
                fs->Close();
        }

        // only for saving v1
        public: void Save(String^ File)
        {
                FileStream^ fs = gcnew FileStream(File, FileMode::Create, FileAccess::Write);
                BinaryWriter^ bw = gcnew BinaryWriter(fs);

                bw->Write(Signature);
                bw->Write(Version);
                bw->Write(JointKeyFrames->Length);
                bw->Write(unknown1);
                bw->Write(unknown2);
                bw->Write(unknown3);

                for(int b=0; b<JointKeyFrames->Length; b++)
                {
                        bw->Write(JointKeyFrames[b]->JointID);
                        bw->Write(JointKeyFrames[b]->PositionKeyPoints->Length);
                        bw->Write(JointKeyFrames[b]->PositionKeyPointControllers->Length);
                        bw->Write(JointKeyFrames[b]->unknown1);
                        for(int i=0; i<JointKeyFrames[b]->PositionKeyPoints->Length; i++)
                        {
                                bw->Write(JointKeyFrames[b]->PositionKeyPoints[i]->X);
                                bw->Write(JointKeyFrames[b]->PositionKeyPoints[i]->Y);
                                bw->Write(JointKeyFrames[b]->PositionKeyPoints[i]->Z);
                        }
                        for(int i=0; i<JointKeyFrames[b]->PositionKeyPointControllers->Length; i++)
                        {
                                bw->Write(JointKeyFrames[b]->PositionKeyPointControllers[i]->StartTime);
                                bw->Write(JointKeyFrames[b]->PositionKeyPointControllers[i]->EndTime);
                                bw->Write(JointKeyFrames[b]->PositionKeyPointControllers[i]->StartKeyPointIndex);
                                bw->Write(JointKeyFrames[b]->PositionKeyPointControllers[i]->EndKeyPointIndex);
                        }
                        bw->Write(JointKeyFrames[b]->OrientationKeyPoints->Length);
                        bw->Write(JointKeyFrames[b]->OrientationKeyPointControllers->Length);
                        bw->Write(JointKeyFrames[b]->unknown2);
                        for(int i=0; i<JointKeyFrames[b]->OrientationKeyPoints->Length; i++)
                        {
                                bw->Write(JointKeyFrames[b]->OrientationKeyPoints[i]->X);
                                bw->Write(JointKeyFrames[b]->OrientationKeyPoints[i]->Y);
                                bw->Write(JointKeyFrames[b]->OrientationKeyPoints[i]->Z);
                                bw->Write(JointKeyFrames[b]->OrientationKeyPoints[i]->W);
                        }
                        for(int i=0; i<JointKeyFrames[b]->OrientationKeyPointControllers->Length; i++)
                        {
                                bw->Write(JointKeyFrames[b]->OrientationKeyPointControllers[i]->StartTime);
                                bw->Write(JointKeyFrames[b]->OrientationKeyPointControllers[i]->EndTime);
                                bw->Write(JointKeyFrames[b]->OrientationKeyPointControllers[i]->StartKeyPointIndex);
                                bw->Write(JointKeyFrames[b]->OrientationKeyPointControllers[i]->EndKeyPointIndex);
                        }
                }

                bw->Close();
                fs->Close();
        }
};

```


sample monster:
[https://mega.co.nz/#!bAhxkLCQ!Op3VxnMyP ... 5CBH-3xjeQ](https://mega.co.nz/#!bAhxkLCQ!Op3VxnMyP8dmsmZloS5VCuxlAsiaKQsCD5CBH-3xjeQ)
## Post #2
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-16T01:15:15+00:00
- Post Title: Search Perfect world animation(stck)

this is the boss clenching his left fist but the last frames are looking a little bit weird.
Also I've to get rid of the hardcoded offsets I used.



boss_leftFist.JPG (56.62 KiB) Viewed 807 times
## Post #3
- Username: FearGod
- Rank: ultra-n00b
- Number of posts: 5
- Joined date: Thu Jul 10, 2014 3:39 am
- Post datetime: 2014-08-16T07:32:35+00:00
- Post Title: Search Perfect world animation(stck)

can help you with this program converts stck to txt

[https://mega.co.nz/#!3E4SnQRJ!YlP13rkoI ... KiZX0GZNJM](https://mega.co.nz/#!3E4SnQRJ!YlP13rkoI3jjY-p0914bnGWfSMgAiHm6oKiZX0GZNJM)

Here is a easy model

[https://mega.co.nz/#!CVIhnAaK!6zMi0arlJ ... jVSj_EgyKw](https://mega.co.nz/#!CVIhnAaK!6zMi0arlJJ5ZVWUMknqiGv3enNUPR7cVyjVSj_EgyKw)
## Post #4
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-08-16T08:46:52+00:00
- Post Title: Search Perfect world animation(stck)

thx, but that's too late.   As you can imagine I wrote a program on my own to analyse the .stck files.
The output is nearly the same:

  1. c: 3 / 3 = 1
 0.000000 0.000000 -0.000000 
  2. 38: 4 / 4 = 1
 0.500000 0.500000 0.500000 0.500000 
  3. 64: 18 /3 = 6
 0.181932 -0.317132 0.125416 
 0.182031 -0.317132 0.125416 
 0.182088 -0.317132 0.125416 
 0.182080 -0.317132 0.125416 
 0.182070 -0.317132 0.125416 
 0.182057 -0.317132 0.125416 
  4. cc: 176 / 4 = 44
 0.690028 0.721725 0.038112 -0.039013 
 0.690290 0.721993 0.033025 -0.033692 
 0.690543 0.722250 0.027236 -0.027637 
...

But you might translate some text for me? (used the stck with a file size of 40336 bytes from your previous sample)
(Guess ¹Ø¼üÖ¡Êý: 1 means frame count: 1 for example.)

ÎÄ¼þÍ·:MOXBKCTS
°æ±¾:1
¹Ç÷ÀÊý66
Î´Öª£º¡¾0¡¿¡¾43¡¿¡¾15¡¿
===========<1oh,c>=============
¹Ç÷ÀË÷Òý: 0
¹Ø¼üÖ¡Êý: 1
Î´Öª:	1 15
A-0  <0.000000 0.000000 -0.000000>
Î´Öª:0 2866 0
-------<4oh,4>-------
Î´ÖªË÷Òý: 0
Î´ÖªË÷ÒýÊý: 1
Î´Öª:	1 15
U-0: <0.500000 0.500000 0.500000 0.500000>
Î´Öª:0 2866 0
Áã:0
===========<7oh,4>=============
¹Ç÷ÀË÷Òý: 1
¹Ø¼üÖ¡Êý: 6
Î´Öª:	1 15
A-0  <0.181932 -0.317132 0.125416>
A-1  <0.182031 -0.317132 0.125416>
A-2  <0.182088 -0.317132 0.125416>
A-3  <0.182080 -0.317132 0.125416>
A-4  <0.182070 -0.317132 0.125416>
A-5  <0.182057 -0.317132 0.125416>
Î´Öª:333 666 0
-------<doh,8>-------
Î´ÖªË÷Òý: 5
Î´ÖªË÷ÒýÊý: 44
Î´Öª:	1 15
U-0: <0.690028 0.721725 0.038112 -0.039013>
U-1: <0.690290 0.721993 0.033025 -0.033692>
U-2: <0.690543 0.722250 0.027236 -0.027637>
...
## Post #5
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-09T18:04:08+00:00
- Post Title: Search Perfect world animation(stck)

well this topic is interesting, here I checking some stcks and well, after see that, here we are, here translated file.

> Header: MOXBKCTS 
>
> Version: 1 
>
> Number of bones 86 
>
> Unknown: [0] [52] [15] 
>
> =========== <1oh, c> ============= 
>
> Bones Index: 0 
>
> Key Frames: 1 
>
> Unknown: 115 
>
> A-0 <0.000014 -0.000099 0.000000> 
>
> Unknown: 034,660 
>
> ------- <4oh, 4> ------- 
>
> Unknown index: 0 
>
> Unknown index: 1 
>
> Unknown: 115 
>
> U-0: <0.497884 0.502109 0.502107 0.497882> 
>
> Unknown: 034,660 
>
> Zero: 0 
>
> =========== <7oh, 4> ============= 
>
> Bones index: 1 
>
> Key Frames: 53 
>
> Unknown: 115 
>
> A-0 <2.497315 0.194873 0.013372> 
>
> A-1 <2.505276 0.194873 0.013516> 
>
> A-2 <2.512207 0.194873 0.013791> 
>
> A-3 <2.517823 0.194873 0.014172> 
>
> A-4 <2.522053 0.194873 0.014636> 
>
> A-5 <2.525032 0.194873 0.015163> 
>
> A-6 <2.527008 0.194873 0.015733> 
>
> A-7 <2.528081 0.194873 0.016324> 
>
> A-8 <2.528323 0.194873 0.016916> 
>
> A-9 <2.527961 0.194873 0.017488> 
>
> A-10 <2.527685 0.194874 0.018025> 
>
> A-11 <2.528600 0.194874 0.018512> 
>
> A-12 <2.530873 0.194874 0.018931> 
>
> A-13 <2.534093 0.194874 0.019255> 
>
> A-14 <2.538535 0.194874 0.019464> 
>
> A-15 <2.544399 0.194874 0.019540> 
>
> A-16 <2.551817 0.194874 0.019459> 
>
> A-17 <2.560909 0.194874 0.019204> 
>
> A-18 <2.572472 0.194874 0.018755> 
>
> A-19 <2.586883 0.194874 0.018099> 
>
> A-20 <2.604227 0.194874 0.017206> 
>
> A-21 <2.623814 0.194874 0.016061> 
>
> A-22 <2.649481 0.194874 0.014658> 
>
> A-23 <2.682458 0.194873 -0.011544> 
>
> A-24 <2.720797 0.194873 -0.027295> 
>
> A-25 <2.764810 0.194874 0.019332> 
>
> A-26 <2.814255 0.194874 0.083223> 
>
> A-27 <2.865808 0.194874 0.114512> 
>
> A-28 <2.919127 0.194874 0.119755> 
>
> A-29 <2.970982 0.194874 0.108651> 
>
> A-30 .018724 0.194874 0.084958> 
>
> A-31 .060284 0.194874 0.053031> 
>
> A-32 .094174 0.194874 0.018685> 
>
> A-33 .118690 0.194873 -0.011566> 
>
> A-34 .132865 0.194873 -0.031591> 
>
> A-35 .134097 0.194873 -0.037696> 
>
> A-36 .114017 0.194873 -0.040297> 
>
> A-37 .075623 0.194873 -0.041629> 
>
> A-38 .023687 0.194873 -0.041806> 
>
> A-39 <2.962497 0.194873 -0.040927> 
>
> A-40 <2.896643 0.194873 -0.039082> 
>
> A-41 <2.831235 0.194873 -0.036383> 
>
> A-42 <2.770960 0.194873 -0.032937> 
>
> A-43 <2.720150 0.194873 -0.028820> 
>
> A-44 <2.682165 0.194873 -0.024137> 
>
> A-45 <2.650961 0.194873 -0.019112> 
>
> A-46 <2.624242 0.194873 -0.013904> 
>
> A-47 <2.600760 0.194873 -0.008611> 
>
> A-48 <2.579709 0.194873 -0.003430> 
>
> A-49 <2.560000 0.194873 0.001492> 
>
> A-50 <2.540416 0.194873 0.006038> 
>
> A-51 <2.519846 0.194873 0.010056> 
>
> A-52 <2.497315 0.194873 0.013372> 
>
> Unknown: 034,660 
>
> ------- <30oh, c> ------- 
>
> Unknown Index: 52 
>
> Unknown Index: 53 
>
> Unknown: 115 
>
> U-0: <0.656047 0.748033 0.024996 0.097083> 
>
> U-1: <0.667582 0.738193 -0.021063 0.094667> 
>
> U-2: <0.679411 0.724590 -0.073075 0.089612> 
>
> U-3: <0.689160 0.708774 -0.124867 0.084292> 
>
> U-4: <0.695452 0.693345 -0.170370 0.081198> 
>
> U-5: <0.697760 0.681727 -0.203743 0.082881> 
>
> U-6: <0.695913 0.677620 -0.219312 0.091862> 
>
> U-7: <0.687626 0.687401 -0.202439 0.116913> 
>
> U-8: <0.671177 0.707830 -0.154792 0.156644> 
>
> U-9: <0.648191 0.728911 -0.095771 0.198407> 
>
> U-10: <0.624455 0.744851 -0.045944 0.230528> 
>
> U-11: <0.609585 0.754186 -0.026289 0.242731> 
>
> U-12: <0.606760 0.759817 -0.039819 0.230075> 
>
> U-13: <0.609775 0.763640 -0.071330 0.199850> 
>
> U-14: <0.614843 0.763616 -0.114191 0.160682> 
>
> U-15: <0.619013 0.758880 -0.161709 0.121549> 
>
> U-16: <0.620792 0.750462 -0.207360 0.091791> 
>
> U-17: <0.619978 0.741047 -0.244832 0.080835> 
>
> U-18: <0.618317 0.731438 -0.270067 0.098721> 
>
> U-19: <0.615945 0.719220 -0.288474 0.141833> 
>
> U-20: <0.610052 0.701686 -0.309266 0.199569> 
>
> U-21: <0.598232 0.676856 -0.341169 0.259977> 
>
> U-22: <0.546728 0.600511 -0.449412 0.372162> 
>
> U-23: <-0.443953 -0.450371 0.599508 -0.490572> 
>
> U-24: <0.292692 0.253815 -0.715348 0.581538> 
>
> U-25: <0.099440 0.032918 -0.764452 0.636114> 
>
> U-26: <-0.110365 -0.190887 -0.741146 0.634101> 
>
> U-27: <-0.295222 -0.375874 -0.665635 0.573143> 
>
> U-28: <0.453012 0.517124 0.555258 -0.468030> 
>
> U-29: <0.558810 0.617899 0.427564 -0.350886> 
>
> U-30: <0.623000 0.694262 0.280482 -0.226279> 
>
> U-31: <0.655981 0.741108 0.113263 -0.087289> 
>
> U-32: <0.653522 0.753399 -0.053203 0.049689> 
>
> U-33: <0.623977 0.738590 -0.194299 0.165488> 
>
> U-34: <0.585526 0.714308 -0.292904 0.247246> 
>
> U-35: <0.556144 0.698687 -0.343277 0.291034> 
>
> U-36: <0.531749 0.693178 -0.370147 0.315814> 
>
> U-37: <0.511858 0.696469 -0.381391 0.327831> 
>
> U-38: <0.496868 0.706937 -0.380226 0.329834> 
>
> U-39: <0.486458 0.722398 -0.369344 0.324169> 
>
> U-40: <0.480180 0.740342 -0.351226 0.312988> 
>
> U-41: <0.477577 0.758138 -0.328594 0.298618> 
>
> U-42: <0.478271 0.773535 -0.304228 0.283455> 
>
> U-43: <0.482117 0.784732 -0.280889 0.269925> 
>
> U-44: <0.489730 0.790718 -0.260051 0.259427> 
>
> U-45: <0.503846 0.794040 -0.234537 0.246235> 
>
> U-46: <0.523228 0.794912 -0.203898 0.229723> 
>
> U-47: <0.546220 0.793027 -0.168899 0.210298> 
>
> U-48: <0.570826 0.788263 -0.130999 0.188778> 
>
> U-49: <0.595378 0.780790 -0.091459 0.165914> 
>
> U-50: <0.618569 0.771015 -0.051338 0.142383> 
>
> U-51: <0.639157 0.759707 -0.011987 0.119078> 
>
> U-52: <0.656047 0.748033 0.024996 0.097083> 
>
> Unknown: 034,660 
>
> Zero: 52
## Post #6
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-10T01:05:44+00:00
- Post Title: Search Perfect world animation(stck)

thx for translating!
Meanwhile I made some progress, here's frames 0, 3, 5 and 12 of the boss.
At frame 12 he's crossing his arms like a snakeman and I'm not sure whether that's the way he's behaving ingame
or it's just a fault in the script.

Will have to check it with the bloatfly sample.



boss_frame_1_to_12.JPG (72.65 KiB) Viewed 752 times
## Post #7
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-10T22:54:35+00:00
- Post Title: Search Perfect world animation(stck)

script seems to work for simple animations now:



Boss_moving_right_arm.JPG (66.04 KiB) Viewed 738 times


Before you can view the animation you'll have to load a model (mesh, skeleton).
There's a script from zaramot here for ski and bon files:
[viewtopic.php?f=16&p=94870#p94870](http://forum.xentax.com/viewtopic.php?f=16&p=94870#p94870)

Then you can load the animation file (.stck)
```
	Import PerfectWorld .stck Animation
	basic structure borrowed from Taylor Mouse
	8-16-2014
*/

/************************************************************************************************
 STRUCTS 
************************************************************************************************/
struct D3Bone ( ID, Name, TheBone )
struct TranslationAnimation ( BoneId, KeyFrame, Position )
struct RotationAnimation (BoneId, KeyFrame, Quaternion  )
struct ScaleAnimation (BoneId, KeyFrame, Scaling )

allBones = #()
bone_names = #()

fn GetBoneNames = (	-- from steev, 10-28-2008
    max modify mode --important! the below won't work unless you're in the modify tab
	--print geometry
    for n in geometry do
    (
        select n -- this selects the current object in the array
        if n.modifiers != undefined do
        (
            if n.modifiers[#Skin] != undefined do
            (
                sk = n.modifiers[#Skin]
                modPanel.setCurrentObject sk -- this selects the skin modifier
                numBones = skinops.getnumberbones sk
                if (numBones>0) then print ("bones found:")
                for i = 1 to numBones do
                (
                    bnName = skinops.getbonename sk i 1
					append bone_names bnName
                    format "% %'\n" i bnName					
                )
                for i = 1 to numBones do
                (
			b = D3Bone()
			b.ID = i				--> for reference only
			b.Name = bone_names[i]			-- name of the bone
			--format "%: %\n" i b.Name
			b.TheBone = GetNodeByName b.Name	-- find the bone in the scene
			append allBones b					
		)
		-- print allBones
            )
        )
    )
	return numBones  -- returns 'undefined' if no skeleton loaded!
)


/************************************************************************************************
	MAIN function
************************************************************************************************/
function ReadAniFile fName startFrame =
(
    startingFrame = 0
    startingFrame = startFrame 
		
    format "-- Start reading PerfectWorld ANIMATION file --"

    stream = fOpen fname "rb"	-- Open the file for reading

    MOXB = readlong stream
    if (MOXB != 0x42584F4D) then
	    throw "This doesn't seem to be a PerfectWorld file!"
    KCTS = readlong stream
    if (KCTS != 0x5354434B) then
	    throw "This doesn't seem to be a PerfectWorld anim file!"
    tmp =  readlong stream
    nAllBones =  readlong stream		-- notinuse: number of all bones, 66 for Boss, but only 53 are used for his upper body
	--nBones = 53	-- Boss
	--nBones = 31	-- BloatFly
    
    /* Frame data*/
    Frame_cnt = #()
    Frame_offs = #()
    allTranslations = #()
    allRotations = #()

    for i=1 to nBones do	/* handle BONES */
    (
	    tmp =  readlong stream
	    unk =  readlong stream ; print unk
	    tmp =  readlong stream ; tmp =  readlong stream
	    if (i != 1) then (
		    ID =  readlong stream ; -- format "ID %\n" ID
	    )		
	    Frame_cnt = readlong stream
	    tmp =  readlong stream ; unk =  readlong stream ; format "% %\n" tmp unk  -- 01 000000 0F 000000

 	    -- Read the translation data structure
        --print ("@ trans: 0x"+ bit.intAsHex(ftell stream) as string)		
	    for fd=1 to Frame_cnt do
	    (
		    tran = TranslationAnimation()
		    tran.BoneId = i
		    tran.KeyFrame = i*200-10		-- 200 seems to work good for the boss
		    tran.Position = [ReadFloat stream, ReadFloat stream, ReadFloat stream]

		    append allTranslations tran
	    )

	    tmp =  readlong stream
	    unk =  readlong stream ; print unk
	    tmp =  readlong stream ; tmp =  readlong stream
	    Frame_cnt = readlong stream
	    tmp =  readlong stream ; unk =  readlong stream ; format "% %\n" tmp unk  -- 01 000000 0F 000000
    
	    /* ROTATION */
	    -- Read the rotation data structure
        --print ("@ rot: 0x"+ bit.intAsHex(ftell stream) as string)		
	    for fd=1 to Frame_cnt do
	    (
		    rot = RotationAnimation()
		    rot.BoneId = i
		    rot.KeyFrame = i*200-10
		    x = ReadFloat stream
		    y = ReadFloat stream
		    z = ReadFloat stream
		    w = ReadFloat stream
			
		    rot.Quaternion = quat x y z w
	
		    append allRotations rot
	    )

    )
    --print allTranslations
    --print allRotations

	--echo "-- DONE READING ANI FILE --\n"
	--echo "-- APPLYING ANIMATION TO THE BONES --\n"
	
	--Apply the Rotation
	prevQ = quat 1 -- set a starting rotation
	prevB = 1
	for i=1 to allRotations.count do
	(
		b = allBones[allRotations[i].BoneId].TheBone
		if(b == undefined) then continue
		
		t = allRotations[i].KeyFrame + startingFrame 
		q = allRotations[i].Quaternion

		with animate on
		(
			at time t (
				b.assumeskinpose()
				local mtrx = matrix3 1
				rotate mtrx (inverse q)
				mtrx.row4 = b.pos
				if b.parent != undefined then(
					mtrx = mtrx * b.parent.transform 
				)
				b.transform = mtrx
				deleteKey b.position.controller (numKeys b.position.controller)
				deleteKey b.scale.controller (numKeys b.scale.controller)
			)
		)
		
	)

	-- Apply the Translation
	for i=1 to allTranslations.count do
	(
		b = allBones[allTranslations[i].BoneId].TheBone
		t = allTranslations[i].KeyFrame + startingFrame
		pos = allTranslations[i].Position

		with animate on
			at time t 
				in coordsys parent b.position = pos
	)
	
	fClose stream
)

-- entry point --

ClearListener()
nBones = GetBoneNames()
if (nBones == undefined) then (
	messagebox "load ski and bon file before! (mesh and skeleton)"
	throw "load ski and bon file before! (mesh and skeleton)"
)
else format "nBones: %\n" nBones

fname = getOpenFileName \
caption:"3D Model" \
types:"3D Model (*.*)|*.stck" \
historyCategory:"3D Model"

ReadAniFile fName 10
max create mode

```
 Didn't have a walking anim sample - so this has to be tested.
Don't blame me, it's my first animation max script. I took the basic structure from one of Taylormouse's scripts.

You'll also notify that I used fn GetBoneNames (from steev which I modified).
Would have made more sense to get the bone's names directly from the bon file but that file is used
by zaramot's script, too. So I got the names from the scene.
## Post #8
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-11T01:12:45+00:00
- Post Title: Search Perfect world animation(stck)

well many thanks for support it, thats wonderful, after download I go to test it and no work, the animation loaded but anyway it show like skin fucked or something like that, here I upload a video showing it, if you can take a look, grateful.

[http://www.youtube.com/watch?v=V5HYOLzfsyE](http://www.youtube.com/watch?v=V5HYOLzfsyE)
## Post #9
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-11T05:54:10+00:00
- Post Title: Search Perfect world animation(stck)

Is that 3dsmax 2013? They changed the sorting of the bone names for example. Thus many scripts for max 2009 don't work correctly.
Otherwise I would need the ski, bon and the stck file (3 or 4 other stcks would be nice).
## Post #10
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-09-12T01:32:55+00:00
- Post Title: Search Perfect world animation(stck)

> Reply from shakotay2
>
> Is that 3dsmax 2013? They changed the sorting of the bone names for example. Thus many scripts for max 2009 don't work correctly.
Otherwise I would need the ski, bon and the stck file (3 or 4 other stcks would be nice).yeah you right is max2013, I have 9 and 2013, but well in 2 max got same error, so well here samples mate, many thanks for all.

[http://puu.sh/bvntf/5bd5a15464.7z](http://puu.sh/bvntf/5bd5a15464.7z)
## Post #11
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-09-12T10:34:11+00:00
- Post Title: Search Perfect world animation(stck)

I got an ogre whose right shoulder plate is rotating. That's not the way it's meant to be, I'm pretty sure.  

Sadly I don't have any idea about the cause atm.

Interestingly nothing changes when
 for i=1 to allRotations.count do

is replaced by
 for i=1 to 1 do

edit: upps, seems the animation buffer from previous run wasn't cleared
## Post #12
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-02T21:40:53+00:00
- Post Title: Search Perfect world animation(stck)

hello and sorry for become again, today I install perfecto world and don't have chance to got it working? don't know why? I try all methods and no work, I load model + bones and when press in script it try load animation for default but won't open a pop up to search for wich animation we can open and I got erro.

-- Error occurred in anonymous codeblock; filename: C:\Users\GAMEMASTER\AppData\Local\Autodesk\3dsMax\2013 - 64bit\ENU\usermacros\DragAndDrop-Macro2.mcr; position: 6428; line: 192
--  Frame:
--   fname: undefined
>> MAXScript MacroScript Error Exception:
-- Runtime error: load ski and bon file before! (mesh and skeleton) <<

it say load first ski and bon but I have loaded there, and anyway always give same error.
## Post #13
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-03T00:24:19+00:00
- Post Title: Search Perfect world animation(stck)

did you try using max2009?

(what's this DragAndDrop-Macro2.mcr script? It's not delivered with max2013, is it?)
## Post #14
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-03T21:40:17+00:00
- Post Title: Search Perfect world animation(stck)

> Reply from shakotay2
>
> did you try using max2009?

(what's this DragAndDrop-Macro2.mcr script? It's not delivered with max2013, is it?)no I don't try in max 2009 because I don't have, I try in Max9, 2010 and 2013, and this issue about dragn you mean is toolbar script, anyway I try using this shortcut in toolbar or too runing script but anyway same error, so no idea whats going on here, always give same error.
## Post #15
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T03:32:28+00:00
- Post Title: Search Perfect world animation(stck)

are you still able to load the ogre animation or does that fail, too?
## Post #16
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-04T07:09:14+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from shakotay2
>
> are you still able to load the ogre animation or does that fail, too?fail as always, no way to load it, so maybe you can try add your script of stck to zaramoth script? is possible made that? so you build all in one script? ski+bon+stck? this would be awesome and maybe this fix this issue.
## Post #17
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T10:21:26+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from CriticalError
>
> shakotay2 wrote:are you still able to load the ogre animation or does that fail, too?fail as always, no way to load it,In your post as of Thu Sep 11, 2014 2:12 am 
you wrote 

> Reply from CriticalError
>
> well many thanks for support it, thats wonderful, after download I go to test it and no work, the animation loaded but anyway it show like skin [...]
So "the animation loaded" now you write "fail as always".
You really should be more clear in your explanations.  

(We are talking about "loading". I know there are errors when the animation performs.)

> so you build all in one script? ski+bon+stck? this would be awesome and maybe this fix this issue.It's not a problem of separate scripts. In my experience separate scripts for mesh and animations are of advantage. (The problem might occur from the way you start the script. I'm starting from the MAXScript editor, Tools\Evaluate All.)

As a workaround you could copy the ogre ski+bon+stck into the same folder where you copied the scripts into and retry to load ski+bon+stck.
## Post #18
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-04T16:55:45+00:00
- Post Title: Re: Search Perfect world animation(stck)

ok so check now, this is tested in Max 2013, and check errors.

MAX 2009

When try load model I got this error? why? well simple, no unicode support in script of zaramoth, so Max2009 no support unicode, if you don't add this in script you can't use them.

> -- Error occurred in i loop; filename: E:\3ds max 2009\Scripts\ski + bon Importer (Zaramot).ms; position: 625
>
> --  Frame:
>
> --   i: 1
>
> --   called in readFixedString(); filename: E:\3ds max 2009\Scripts\ski + bon Importer (Zaramot).ms; position: 625
>
> --  Frame:
>
> --   str: ""
>
> --   fixedLen: 8
>
> --   bstream: undefined
>
> -- Error occurred during fileIn in <File:E:\3ds max 2009\Scripts\ski + bon Importer (Zaramot).ms>
>
> >> MAXScript FileIn Exception: -- Unable to convert: undefined to type: Integer <<


MAX 2013

SKI+BON Loaded



After execute stck script and begin reading it, some seconds ago I got this pop up?



so what is that? .3DModel? thats strange, anyway I cancel this pop up and got this error in MaxScript Listener.



> -- Start reading PerfectWorld ANIMATION file ---- Error occurred in ReadAniFile(); filename: E:\3ds max 2013\3ds Max 2013\scripts\stck Importer.ms; position: 2356; line: 65
>
> --  Frame:
>
> --   startingFrame: 10
>
> --   prevQ: undefined
>
> --   fname: undefined
>
> --   allRotations: undefined
>
> --   stream: undefined
>
> --   Frame_offs: undefined
>
> --   KCTS: undefined
>
> --   TMP: undefined
>
> --   allTranslations: undefined
>
> --   startframe: 10
>
> --   Frame_cnt: undefined
>
> --   nAllBones: undefined
>
> --   MOXB: undefined
>
> --   prevB: undefined
>
> -- Error occurred during fileIn in #E:\3ds max 2013\3ds Max 2013\scripts\stck Importer.ms; line number: 65
>
> >> MAXScript FileIn Exception:
>
> -- Unable to convert: undefined to type: FileName <<
## Post #19
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T17:40:15+00:00
- Post Title: Re: Search Perfect world animation(stck)

thank you for your explanations!  

1. well, my script wasn't designed to work with max2013 and I don't have the time to deal with it.

2. I remember renaming the unreadable stck filenames (not sure whether I mentioned it in one of my PMs),
so yep, no UNICODE support by my script, too, I guess (would have to change my code page and so on, so sry, can't test it).

> so what is that? .3DModel? thats strange,
the filter for file selection is types:"3D Model (*.*)|*.stck"
can't see a .3DModel there.

conclusions:

easiest workaround atm: rename the skl,bon,stck file names to ANSI like whatever_monster.skl (bon,stck) for example.
Then try to load them using a max version prior to 2013.

btw: I still don't know whether the ogre is/was loading or not for you
## Post #20
- Username: CriticalError
- Rank: double-veteran
- Number of posts: 678
- Joined date: Sun Jul 05, 2009 9:03 am
- Post datetime: 2014-10-04T18:49:06+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from shakotay2
>
> thank you for your explanations!  

1. well, my script wasn't designed to work with max2013 and I don't have the time to deal with it.

2. I remember renaming the unreadable stck filenames (not sure whether I mentioned it in one of my PMs),
so yep, no UNICODE support by my script, too, I guess (would have to change my code page and so on, so sry, can't test it).
so what is that? .3DModel? thats strange,
the filter for file selection is types:"3D Model (*.*)|*.stck"
can't see a .3DModel there.

conclusions:

easiest workaround atm: rename the skl,bon,stck file names to ANSI like whatever_monster.skl (bon,stck) for example.
Then try to load them using a max version prior to 2013.

btw: I still don't know whether the ogre is/was loading or not for you
well I try do this method and no work, I rename it to ANSI and anyway still getting same error, about Max 2009 I download them but the script of zaramoth won't load, give error with files, ok now about your stck importer no load animations, always stuck in same places like told you before and explain in past post.
## Post #21
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4300
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2014-10-04T20:35:08+00:00
- Post Title: Re: Search Perfect world animation(stck)

well, don't know where the problem might be.

Checked it with max2009, no error messages:



test_PerfWorld.JPG (70 KiB) Viewed 568 times



issue: the king's only rotating. (same with ogre's arm which had no translation)

That's the problem with my script but since I don't have the game (or english names of stck files) I don't know how the real movemment should look like.
When I set the rotation to zero a translational movement can be seen. But there's no relative movement of bones, the ogre's right arm moves as one object - that's strange. Some day I'll solve this...

But there's no issue loading files or the animation frames.
## Post #22
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-01T14:20:31+00:00
- Post Title: Re: Search Perfect world animation(stck)

Hi,
yes it works with 3ds max 2009 here - no errors, but its not the original animation - only one rotation what isnt really useable. The interesting thing is, that the original object have more .stck files / more animations like walking, running etc, but if i import a stck file - its always the same animation in 3ds max, thats strange.
The only way i can help with this, is to show you how it looks like the original animation.

Does anyone have another solution to import .stck animation for 3ds max 2009 or 2013 ?

Best regards
## Post #23
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-05-02T03:03:38+00:00
- Post Title: Re: Search Perfect world animation(stck)

Can you supply more model and animation samples?
## Post #24
- Username: TheAnkou
- Rank: ultra-n00b
- Number of posts: 3
- Joined date: Sat Oct 31, 2015 9:38 pm
- Post datetime: 2018-05-02T14:36:39+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from killercracker
>
> Can you supply more model and animation samples?

Here is some samples of npc and wings [https://mega.nz/#!oUYBlDpQ!a6ZPN4Jn8LcC ... Wxu3rxnp1Q](https://mega.nz/#!oUYBlDpQ!a6ZPN4Jn8LcC0IeODrc9C3-hUKtBQMAdAWxu3rxnp1Q)
## Post #25
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-02T15:45:23+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from killercracker
>
> Can you supply more model and animation samples? Here are some examples, too.
There are 4 Animation files (STCK). Also there is an .avi sample of each animation, too. I hope this help. If its possible to import .stck in max 2013 would be very nice, because the import of model, textures and bones was very good and without any problems.
I dont know, if its possible to import all in max 2009.

[https://www.dropbox.com/sh/oqom1g355wm5 ... F6jPa?dl=0](https://www.dropbox.com/sh/oqom1g355wm5n1n/AAB3ef0Al6Xd-F5QQ7CrF6jPa?dl=0)

I just only renamed the filenames, because there was asian characters, but i changed nothing in the files.
## Post #26
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-05T12:32:31+00:00
- Post Title: Re: Search Perfect world animation(stck)

No chance to make that possible?
## Post #27
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-05-06T03:16:49+00:00
- Post Title: Re: Search Perfect world animation(stck)

Thanks for the files. I wrote the script in 3ds max 2015 so I'm sure it'll work in 2013, but I'm not sure for 2009. I'm also working on an animation script for Saint Seiya because the formats are so similar. I'd have it finished now but the rotation data is kicking my ass.
[perfect world.rar](https://xentaxbackup.github.io/file/14324_perfect world.rar)
## Post #28
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-08T01:01:07+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from killercracker
>
> I wrote the script in 3ds max 2015 so I'm sure it'll work in 2013, but I'm not sure for 2009
Wow nice! Thank you so much. For me it works only in 2015, but only with .ski who have .stck animation files. There are many models, who dont have animation files (stck).
I was searching for the missing stck files, but nothing and I know why. There are different versions where the animations inside. For the newer version, the animations are in .stck files. For older versions the animations are in the .bon file self!

Here you can see, what i mean (version 6 .smd, then animations are in 1 bon file):


I uploaded a new sample for that. The animations must be in the .bon file inside:
[https://www.dropbox.com/sh/zstkr9so5f9v ... T4mna?dl=0](https://www.dropbox.com/sh/zstkr9so5f9vng8/AABtzM8k2Z0JakSdTW8gT4mna?dl=0)

Please help me
## Post #29
- Username: killercracker
- Rank: advanced
- Number of posts: 56
- Joined date: Mon Sep 26, 2011 6:31 am
- Post datetime: 2018-05-10T13:50:18+00:00
- Post Title: Re: Search Perfect world animation(stck)

I added support for the Saint Seiya models and animations. I'll add support for animation inside the .bon files when I get some more free time.
[ski & stck.rar](https://xentaxbackup.github.io/file/14344_ski & stck.rar)
## Post #30
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-12T21:53:28+00:00
- Post Title: Re: Search Perfect world animation(stck)

Many thanks killercracker! I cant wait for that   I hope its possible

Regards, olli
## Post #31
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-05-13T11:13:17+00:00
- Post Title: Re: Search Perfect world animation(stck)

How can I extract the .PCK files wich contain the models? I have a tool called "GsPck.exe" but this isn't working for me...

Kind regards,
## Post #32
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-05-14T18:34:57+00:00
- Post Title: Re: Search Perfect world animation(stck)

Could someone help me out? I've combined both models.pck & models.pkx, but when trying to extract I get an crash. Don't know what to do now...

Thanks,
## Post #33
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-15T13:06:34+00:00
- Post Title: Re: Search Perfect world animation(stck)

Hi,
please post more info about your system, os, wich spck version...? Normally it should work..

Regards, olli
## Post #34
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-05-15T18:38:41+00:00
- Post Title: Re: Search Perfect world animation(stck)

@olli9000 THanks for you reply.

My specifications: Processor - Intel(R) Core(TM) i7-7700HQ CPU 2.80 GHz
                                         RAM - 8 GB
                                         64-bit operating sytem

I've watched this video [https://www.youtube.com/watch?v=rdlH98kf1cY&t=59s](https://www.youtube.com/watch?v=rdlH98kf1cY&t=59s)
And I used this tool  - [https://epicpw.com/index.php?topic=43343.0](https://epicpw.com/index.php?topic=43343.0)   V1.0.0

But it always crashes.. Could you provide me another tool maybe? Or a little guide/video-guide on how to extract the models/animations.

Thankyou
## Post #35
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-05-17T17:17:48+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from WollieWoltaz
>
> 64-bit operating sytemWin7, win 8, win 10 ?? Wich 64bit system?

Iam using win 7 64bit and it works fine. I attached my GSpck tool, that i founded. 
Please start only GsPCK.exe for extracting this. For models u need to combine pck and pkx files ("Others" tab in this tool). I dont know if it works fine with win8 or 10. If it dont work, u can trying to start the tool as administrator (on right click).

I hope this helps,
Regards
[spck.rar](https://xentaxbackup.github.io/file/14368_spck.rar)
## Post #36
- Username: WollieWoltaz
- Rank: beginner
- Number of posts: 39
- Joined date: Thu Feb 09, 2017 3:44 am
- Post datetime: 2018-05-17T18:15:31+00:00
- Post Title: Re: Search Perfect world animation(stck)

Owh sorry i'm on win10 64-bit, but it doesn't work with the tool you provided neither with the tool i showed you in the video.
I also tried running in administrator mode but didn't work either.  And is also tried adding a "unpack.bat" file with this command "start spck.exe -u "MyPath"  but it still crashes.

Do you know anything else how to fix this? If not... could you provide the models/litmodels unpacked as of todays patch?

Would really appreciate it,

Regards,
## Post #37
- Username: Tosyk
- Rank: double-veteran
- Number of posts: 1027
- Joined date: Thu Oct 22, 2009 5:24 pm
- Post datetime: 2018-05-30T09:49:56+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from killercracker
>
> I added support for the Saint Seiya models and animations. I'll add support for animation inside the .bon files when I get some more free time.can you reupload your script? I can't unpack it - error. thanks
## Post #38
- Username: 123456789
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Sun Oct 05, 2014 12:48 am
- Post datetime: 2018-05-30T21:10:34+00:00
- Post Title: Re: Search Perfect world animation(stck)

Here is a data entry without animation, but there is a time after recording. I will store a sample. Thank you
[Sample appendage.zip](https://xentaxbackup.github.io/file/14414_Sample appendage.zip)
## Post #39
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-08-17T21:34:39+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from killercracker
>
> I'll add support for animation inside the .bon files when I get some more free time.

Any news about it? .stck files - no problem here, but there is only a .ski and .bon file, then its an older smd version and the animations must be in the .bon file itself. But i dont know about the bone structure. Someone can help me please?
## Post #40
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-08-20T17:26:51+00:00
- Post Title: Re: Search Perfect world animation(stck)

Hi guys, 
I keep my attention on this topic, but I didn't understand few thinks .
First of all does this script support model + every animation or just the first frame? ( I understood that it doesn't support animation in .bon) 
Second , which game does it support? There are different game made by perfect world.

THanks in advance for answering
## Post #41
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-08-20T19:39:48+00:00
- Post Title: Re: Search Perfect world animation(stck)

Hi,
first, perfect world is a game, made by arcgames. Arc makes some other games like forsaken world or jade dynasty.
Iam looking for an import script for pw (perfect world international) only, but the most models from jade dynasty have the same file structure.

Every model folder in pw have: 

- .smd (different versions, 5,6,8)
- .ski (mesh)
- .bon (skeleton infos)
- .ecm (other infos)
- texture folder with .dds textures

If the .smd file is a never version, then model animations are in files like .stck in the model folder. The import scripts from here worked with .ski, .bon, . stck (every stck is an animation).
But if there is an older model with animations (.smd version 5), then there are no .stck files and the skeleton animations are in the .bon file itself (or the instructions for the .bon file are in the .smd).
Here is what i mean: [viewtopic.php?p=140377#p140377](http://forum.xentax.com/viewtopic.php?p=140377#p140377)

So what iam looking for is an max 2013 import script for the model animations with .smd version 5. If i import those models, the .ski and .bon import fine, but only with the first frame, not all animations.
I really hope, someone can help me please   

Best regards,
olli
## Post #42
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2018-08-23T10:54:06+00:00
- Post Title: Re: Search Perfect world animation(stck)

Please anyone... or its not possible?
## Post #43
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-09-18T21:19:11+00:00
- Post Title: Re: Search Perfect world animation(stck)

> Reply from WollieWoltaz
>
> @olli9000 THanks for you reply.

My specifications: Processor - Intel(R) Core(TM) i7-7700HQ CPU 2.80 GHz
                                         RAM - 8 GB
                                         64-bit operating sytem

I've watched this video https://www.youtube.com/watch?v=rdlH98kf1cY&t=59s
And I used this tool  - https://epicpw.com/index.php?topic=43343.0   V1.0.0

But it always crashes.. Could you provide me another tool maybe? Or a little guide/video-guide on how to extract the models/animations.

Thankyou

Did you solve the problem? I have the same too with latest perfect world client.

Is there anyone with a working unpacker for the latest client 2018? I tried severals but doesn't work.

There are 3 models files : models.pck ,models.pkx , models2.pck 
How to merge them togheter?
## Post #44
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-09-19T15:17:21+00:00
- Post Title: Re: Search Perfect world animation(stck)

I tested the script for models and animation, tested with 3dsm 2012, everything works fine   
The unpacker working with the current client of PWI 2018 is this one made by beyastard [https://mega.nz/#!w2BjyCJC!uUrZm-SW_WyY ... QsceZhAp1I](https://mega.nz/#!w2BjyCJC!uUrZm-SW_WyY5M2C-JG3uYBH4-qeNY-gKQsceZhAp1I)
don't know if it extract every files but at least no crash   

Just one tip: before importing rename the .ski and .bon and .stck since they are in chinese 

Interested on seeing if it works with swordsman , we will see .

Thanks community
## Post #45
- Username: Drawing
- Rank: mega-veteran
- Number of posts: 283
- Joined date: Thu Jan 12, 2012 5:21 am
- Post datetime: 2018-12-13T13:21:31+00:00
- Post Title: Re: Search Perfect world animation(stck)

Hi man  I found some .ski models and .stck animation from a game made by perfect world. but I can't import them in 3dstudio max ( the structure is the one you worked on , a .ski model , a little .bon file , and stck animations)

Could you take a look please? 

Here is the link for sample files : [https://www.mediafire.com/file/mwmv69qi ... e.rar/file](https://www.mediafire.com/file/mwmv69qi570vhi3/sample.rar/file)
## Post #46
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2019-01-27T21:22:08+00:00
- Post Title: Re: Search Perfect world animation(stck)

Any news about old .bon files for animations? The stck files are newer animations, but i need the old animations from 1 .bon file to import this in max. I wait soo long time, can anyone help please?
## Post #47
- Username: olli9000
- Rank: advanced
- Number of posts: 40
- Joined date: Wed Dec 02, 2015 12:04 am
- Post datetime: 2019-03-08T12:22:18+00:00
- Post Title: Re: Search Perfect world animation(stck)

Anyone? Please help
## Post #48
- Username: darksimonus
- Rank: beginner
- Number of posts: 30
- Joined date: Sun May 02, 2010 3:57 am
- Post datetime: 2019-03-13T20:12:36+00:00
- Post Title: Re: Search Perfect world animation(stck)

Hello
is there a script for the animation of saint seiya online

Thx for help
## Post #49
- Username: KingJuls
- Rank: advanced
- Number of posts: 59
- Joined date: Wed Feb 28, 2018 3:29 pm
- Post datetime: 2019-08-22T13:57:48+00:00
- Post Title: Re: Search Perfect world animation(stck)

Have anyone Informationen about .bon support?

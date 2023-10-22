## Post #1
- Username: bachou123
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 12, 2018 6:24 pm
- Post datetime: 2022-02-22T03:06:55+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

this is an audio files from unity game however it has no extension, i tried to change it to wav and it crashed my windows explorer ! changing it to mp3 or ogg doesn't work either, can anyone take a look at this file ?

this file is from cache\sound folder so i'm not even sure if it's an audio file or not
[https://www30.zippyshare.com/v/4HuJL3Os/file.html](https://www30.zippyshare.com/v/4HuJL3Os/file.html)


and here's the files i got from assetstudio but they are labeled as textassets ?
[https://www29.zippyshare.com/v/xogDsjYe/file.html](https://www29.zippyshare.com/v/xogDsjYe/file.html)
the files are SB0004.acb.bytes and SB0004.awb.bytes. i tried to remove the .bytes extension leave them .acb and .awb then drag them on vgm tool, it created an 0 bytes folder so idk what's going on anymore
## Post #2
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-22T22:33:53+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

Files from "cache\sound" and from assets are AWB archives.
More info here [http://wiki.xentax.com/index.php/AWB_Archive](http://wiki.xentax.com/index.php/AWB_Archive)

You can change file extension to AWB and load it into foobar with vgmstream plugin,
but audio seems to be encrypted and you won't be able to play it without proper key.
## Post #3
- Username: bachou123
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 12, 2018 6:24 pm
- Post datetime: 2022-02-23T09:18:31+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

> Reply from ikskoks ↑Wed Feb 23, 2022 6:33 am at Wed Feb 23, 2022 6:33 am
>
> 
Files from "cache\sound" and from assets are AWB archives.
More info here http://wiki.xentax.com/index.php/AWB_Archive

You can change file extension to AWB and load it into foobar with vgmstream plugin,
but audio seems to be encrypted and you won't be able to play it without proper key.

is there a way to get the key ? this is what the .acb.bytes looks like in assetsutido, does this help ?

: 

```
[!Z)[7RIR^[s[{[�X�[�[�[�[�Z�P�[[[[1[LP^Rn[z[�[�[�[�[�[�[[)[H[W[b[s[�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�P�PPPP
P
PPPP[[([97 � P���h`�$��� M��d?�`�o��\�@L��P' `HeaderFileIdentifierSizeVersionTypeTargetAcfMd5HashCategoryExtensionCueTableCueNameTableWaveformTableAisacTableGraphTableGlobalAisacReferenceTableAisacNameTableSynthTableSeqCommandTableTrackTableSequenceTableAisacControlNameTableAutoModulationTableStreamAwbTocWorkOldAwbFileVersionStringCueLimitWorkTableNumCueLimitListWorksNumCueLimitNodeWorksAcbGuidStreamAwbHashStreamAwbTocWork_OldAcbVolumeStringValueTableOutsideLinkTableBlockSequenceTableBlockTableNameCharacterEncodingTypeEventTableActionTrackTableAcfReferenceTableWaveformExtensionDataTableBeatSyncInfoTableCuePriorityTypeNumCueLimitTrackCommandTableSynthCommandTableTrackEventTableSeqParameterPalletTableTrackParameterPalletTableSynthParameterPalletTableSoundGeneratorTableInstrumentPluginTrackTableInstrumentPluginParameterTableLipsMorphTableProjectKeySoundInstrumentsSoundProgramBankKeyMIDITrackTableR35R34R33R32R31R30R29R28R27R26R25R24R23R22R21R20R19R18R17R16R15R14R13R12R11R10R9R8R7R6R5R4R3R2R1R0PaddingAreaStreamAwbTocWorkStreamAwbAfs2Header
ACB Format/PC Ver.1.37.1 Build:
SB0004�f�P]��a�vsxz!|@UTF�Jg�
TP
RZ'R0[9TIPPPdRu�����CueCueIdReferenceTypeReferenceIndexUserDataWorksizeAisacControlMapLengthNumAisacControlMapsHeaderVisibilityNumRelatedWaveforms@UTFH"(HZRCueNameCueNameCueIndexSB0004@UTF�Oc�R	PP P*P6R?TLRWReRuR��DD����WaveformMemoryAwbIdEncodeTypeStreamingNumChannelsLoopFlagSamplingRateNumSamplesExtensionDataStreamAwbPortNoStreamAwbIdLipMorthIndex@UTF`Y�[
-PZR[,[;RGR]RpR�[�R�R�R����������SynthTypeVoiceLimitGroupNameCommandIndexReferenceItemsLocalAisacsGlobalAisacStartIndexGlobalAisacNumRefsControlWorkArea1ControlWorkArea2TrackValuesParameterPalletActionTrackStartIndexNumActionTracks@UTFX%=[SequenceCommandCommandAWZEA�o'@UTFTv"RR[R*R@RSPcZnTyZ�P�R���������������TrackEventIndexCommandIndexLocalAisacsGlobalAisacStartIndexGlobalAisacNumRefsParameterPalletTargetTypeTargetNameTargetIdTargetAcbNameScopeTargetTrackNo@UTF�h��1R	R[!R,[9RER[RnR~R�[�P�R�R�R�R�d��������SequencePlaybackRatioNumTracksTrackIndexCommandIndexLocalAisacsGlobalAisacStartIndexGlobalAisacNumRefsParameterPalletActionTrackStartIndexNumActionTracksTrackValuesTypeControlWorkArea1ControlWorkArea2InstPluginTrackStartIndexNumInstPluginTracksAFS2 �� �������DAg������@@�����?�����8���7K��h|Yc��>��$�3ɾ����i����/�d�
����tp�|̫� �c�D��x&u�� D���YH�<��5���O�v�?�d5�#�t��/�����A6IA6~�In�f�I�IAf���
P�
sӰ
}�����f��
AfP�PIss{A)t�
[
f���W���R����v�,v0���y�B�j��^�C�4�_��L뙦C��-���LG�d��sN�Йk��M�j��_��֠��m�NV�!�dS
�Dr����پx��ڇ	��e��"~�
�Ei����ְ�7��DQ�=�+7�"�T�x]���3v�,�6�U5��cL+��˝N�v��`��
R�2(��Y�����L6�m�w�L"a�g��?#댸͵M9��,���aW�qV��Ɓ�B�,����+KY{��	'}�x�o�!t�4�B����{��4U]����̀�[�i�<",�m,Nͭ77��k<�
|�́���v
`[&�~bl6:���b�2܎�EZB4,?�P�m��������#L�ȩ^�h�������&_�}�93q1��t�e�*=�ѧ���wM2������Y��\|7l3
�9�[َ�|~,&��}�k�lM��~�L�Aj���_s��v��h�������Bb@
s����F��|ך����4/��B��*�	���Iv��jCwپvT���� 
��d�;��Q��L���
�>e
L� U�\�X����/���!�� ������UE} �dv�$����Y�������me�9v�A���\�i�t�5�2�i��Q��iM9M�&ܑ�o���l�������S"A�h���;Fa�╤�س��&[ڿ�׊��3K)���pn=��Uʠ?=���
��/_,�k�U+�GMk�e�&�!��("^e������F5Uz�G+�%W�����I�o�a��5
q�%�8i�|~Ͱq_k�ͱ��k@��؅8�nc�6�f�6�z,�	c�-��QX��K��h�=�UM&B)���V�=Ybc?~��vvԫ���H��_r�&e�i�F#c�m:2�#��� a;�C�.��@�S#�{`A�1��K�)��˖��K�(��Z����̗�}�*,P~s?��˄�{���WIqO%�C*��f'�1�!�>�ϸe�p���x��
�j�j�j2v��j�����e�_���j�������c�j�-�?t�����_va��60�U�v鄛.�!y��;�$�H����O`��js���	�	匫�)6c'�i�.����W��:"~m����㬔U Xj#��%A�˥n����2K�'�/l�r.�����DK'E&��H�Q�Y���"�{-��>P��JfW,/�~� /�:�w2���h~Wlo���w�7A�X�%�}X	��\�vn�{o-P
�fT���kK�<�������=r�&3i�Iu��hw��9<u��S9cضt���o5�ǐ/�\�r��YV.�&�dM8���{jT�x�oT�u0��i�t'
�;\U%
�;w[�Z���5�t;��h�U����*�Qj��ztw�캋�P���]Y׉���^�8���2#���K37�kI�n=$�9�Ћ9nj�iGB�,�]�H� �H���R��jiTi��`d�����������V�1.��'ԈaGvʜˑ�3j�d�F����ddvyw�������������'���j��d���as�6�;l㇜
�
�j��,��^/�t+\,�k�~p!���%>��|��Π"��R����[��M$�Z�W��hLC��Z�W�IH�JV��-d��A�g�V��(�������c�e�����T�:H�Rvg�Hq�gZ#	xA�?��B�S5�h�kc�s��ǻR�r���jkX9��*E;��rg�#Zw޽�Pl��S��М~��/�TM/��Q���I'j�_��Y�p�D���4�?���}��2P�!P?�yY@"o�:��H�I�M�2�36��^�0���O�{�3���$�UyG����I�ea�M�.O���$�t���E��I\�.���tɌIP�B;������tp���"b�=����RӘ�2$:-(!�ۍ�,�~
��؂���g��4�ȳ�M��E7����~AZ����қ�e&ף?�w��d�N�7$Gly��G�Q�o�L��������T��0�i�و0!�|�5' k\�;e��'�`BtS��/X���-��#���Cq!����U,%�z_�Ӄ0F;�]z��D�X����'E�^胎k+�K��F��1��m����5���D"�x�(���~M�_�o�a{�����m*�I1cl��3��4�
�w������9�dE�v��(GHb��%S
x�A`�`�
�\枰��t�W^n�6H�i>��	X�[\7�&U$�&��#+\�%]�ȍ���.[8SV%�k�9����f��s���
XW�h	�t�Ւ�ф�!���O{E3xӟ��������g!�p��3,�\,�?����w--��[���23��m���н!
0����;�Mđ�� FƷ�	Tj[)$����aV��LC��/��EA�w?])�I��V���U� ����:��X�����<}�>�t�����Ė��қ�
�FMy0��H�]����r݊��e�6����#
�mـ#��ـ� �,�޷�3�J/��!j#�8oy��:]�wV�]�!��Kv�WI�L��dv�<��+�}�EH_v�x�/Qx��^O�u��u��ܯa;q7�ZP�ieX�;
k��s�B`���1_��}�O�Yl�ׇ����*��4	�y�	3�%F�n�g!�v	#���v��#U��́:��i㘑�,qT�$�����b/��
5ݖN�Ĝ����ʟ��C�F���ý�<a>�3�S���{8�m�ʊ��F��W<�eÕD�[�v�0���T����$v�c�w���k�wZ�:D]R��չd"4��V�>�8^�����0R�]�
�(y�������~8�G�ig޾�=�����������>=�}~�?��>[B��B6W�믕����:s�ގ�;�YH���I~�p7��䶚r�^=yM�X�\��l��h<�N��=*g��8|�rmO[
��؜�����v��`�����'�#�_>T!����F�N�;|߄���&3o��Nî������Mň�yҊ�z�3�3�Lʇ>Ӧ�����.<̠��P��t�O:���?��/�2|Bk%
ڏ�����%�����}��c[N�St�5��8
�p��Ja�8T����z�맴3ݵ���l�	ou��;�4$�3>��; C���ˑW^���n�+p�ݢ�
]bG���Jχ��%C�������
| g��N��a%�_p�D��?�I�l�k��}:�+-z��%��5֚e�㷢'�/W���=�A�6�2�E=�l#�Ώ����n�AQ�~���V�~i��`\a�!��TW��Kb��̑��*���V�-1i�}:Qu���#D	�YLOR�MJ�H�]hR����5���$�4��;�:Hs��٥'���Z�ϚB]�K���|�Ƭ��<��c�`��JQc����������<�0�G�-,¯���y�a)ׯJ�Q�������6Й��a�d�w��4���D>Ftm���Y��Z�d��y�#������)p\����Q'�h�� j����v� vC����b#MfH1��l%wh�:�+�M�����+��BbT���k��n�i�S���4I`W�yo�!�=�Ic'�U���3���㸶ObO<�����}������-5qj>z�+4��ܨ��t{��W���Kd�uMi܏�F�W�qKȪ5�BN�+d&q��˃}���,Z�)��g�f��ʊ�w!j&��r���Č��3D���xy�y����2�Q�������J,���f��q�S�<?�RFؖ%�Ԇ�T�v���\+J3��L#pEw��
s��}M�ԋ
^,u,����d�W�$C�<3����+j����bIە�]-�DD�tW�s�YI����ǧU���M��2���T_���f�����ޔ.g�ܰ�@1!�L��_��d���q�a6@)&���,��DLeh��Q"�-�Ҟx�j�K�����:4@UTF\".IZ
[StreamAwbNameHashSB0004]�|y�8�X�����@UTF�=~Z#(-27<StringsStringValueMasterOutBUS1BUS2BUS3BUS4BUS5BUS6BUS7@UTF�0��		P
Z:T!	%����	/����	4����	9����	>����	C����	H����	M����AcfReferenceTypeNameName2IdBGMMasterOutBUS1BUS2BUS3BUS4BUS5BUS6BUS7@UTFT"*RTT D��WaveformExtensionDataLoopStartLoopEnd@UTFD%8[
TrackEventCommand�ѐU�ِ)}��0|@UTFX%<[StreamAwbHeaderHeaderAFS2 �� �"
```
## Post #4
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-23T14:29:34+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

> is there a way to get the key ?

Yes, there is. But it requires some research and knowledge.
Here are the links where you can start looking:
[https://www.google.com/search?client=fi ... +hca+audio](https://www.google.com/search?client=firefox-b-d&q=decrypt+hca+audio)

[https://blog.mottomo.moe/categories/Tec ... ncryption/](https://blog.mottomo.moe/categories/Tech/RE/en/2018-10-12-New-HCA-Encryption/)

[http://wiki.xentax.com/index.php/HCA_Audio](http://wiki.xentax.com/index.php/HCA_Audio)

[https://github.com/vgmstream/vgmstream/ ... hca_keys.h](https://github.com/vgmstream/vgmstream/blob/master/src/meta/hca_keys.h)

Also, what is the name of this Unity game you need key for?
## Post #5
- Username: bachou123
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 12, 2018 6:24 pm
- Post datetime: 2022-02-27T08:23:20+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

it's a Japanese game called ヘブンバーンズレッド
don't know why the hell they put encryption into audio files...
## Post #6
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-27T11:33:43+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

> Reply from bachou123 ↑Sun Feb 27, 2022 4:23 pm at Sun Feb 27, 2022 4:23 pm
>
> 
it's a Japanese game called ヘブンバーンズレッド
don't know why the hell they put encryption into audio files...

Well, english name is "Heaven Burns Red" and the key is 6615518E8ECED447 in hex.
[https://github.com/vgmstream/vgmstream/ ... 0a01c85076](https://github.com/vgmstream/vgmstream/commit/64cbc9a99e08072d8989e4aa7ffb850a01c85076)


I have also added to the wiki a short tutorial how to apply this key and play the audio
[http://wiki.xentax.com/index.php/HCA_Au ... foobar2000](http://wiki.xentax.com/index.php/HCA_Audio#Applying_HCA_keys_with_foobar2000)
## Post #7
- Username: bachou123
- Rank: ultra-n00b
- Number of posts: 8
- Joined date: Thu Jul 12, 2018 6:24 pm
- Post datetime: 2022-02-28T10:10:33+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

what about the first file which is in cache\sound ? there's still some tracks are missing.
## Post #8
- Username: mono24
- Rank: Moderator
- Number of posts: 1671
- Joined date: Fri Jul 27, 2012 12:06 am
- Post datetime: 2022-02-28T16:36:21+00:00
- Post Title: Heaven Burns Red - unity audio file with no extension

This file from cache\sound uses the same key. 
So you just need to add ".awb" to the filename (rename the file), then apply key as described in tutorial
and then play it in foobar2000.

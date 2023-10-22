## Post #1
- Username: gimli
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 16, 2007 11:32 am
- Post datetime: 2007-09-04T10:06:59+00:00
- Post Title: shockwave flash scripting

Has anyone seen this kind of scripting language before, it seems to be a definition of a shockwave flash. Any ideas on how to execute it ?

-----

PngFileTable = {
	png => shinki_menu_0_?.png,
	png => shinki_menu_1_?.png,
)

Header:
SIGNATURE = CWS
VERSION = 7
File length = 1510
Rect size = (0, 0)-(20480, 15360)
Frame rate = 30
Frame count = 1

SWF::Element::Tag::DefineBitsLossless->new(
    CharacterID => 1,
    FileName => 0,
    BitmapFormat => 5,
    BitmapWidth => 256,
    BitmapHeight => 64,
)
SWF::Element::Tag::DefineShape->new(
    ShapeID => 2,
    ShapeBounds => SWF::Element::RECT->new(
        Xmin => 0,
        Ymin => 0,
        Xmax => 5120,
        Ymax => 1280,
    ),
    Shapes => SWF::Element::SHAPEWITHSTYLE1->new(
        FillStyles => SWF::Element::Array::FILLSTYLEARRAY1->new([
            SWF::Element::FILLSTYLE1->new(
                FillStyleType => 65,
                BitmapID => 1,
                BitmapMatrix => SWF::Element::MATRIX->new(
                    ScaleX => 20,
                    ScaleY => 20,
                    RotateSkew0 => 0,
                    RotateSkew1 => 0,
                    TranslateX => 0,
                    TranslateY => 0,
                ),
            ),			# 0
        ]),
        ShapeRecords => SWF::Element::Array::SHAPERECORDARRAY1->new([
            SWF::Element::SHAPERECORD1::STYLECHANGERECORD->new(
                MoveDeltaX => 5120,
                MoveDeltaY => 1280,
                FillStyle1 => 1,
            ),			# 0
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => -5120,
                DeltaY => 0,
            ),			# 1
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => 0,
                DeltaY => -1280,
            ),			# 2
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => 5120,
                DeltaY => 0,
            ),			# 3
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => 0,
                DeltaY => 1280,
            ),			# 4
        ]),
    ),
)
SWF::Element::Tag::DefineSprite->new(
    SpriteID => 3,
    FrameCount => 1,
    ControlTags => SWF::Element::Array::TAGARRAY->new([
        SWF::Element::Tag::PlaceObject2->new(
            Flags => 6,
            Depth => 1,
            CharacterID => 2,
            Matrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 0,
                TranslateY => 0,
            ),
        ),			# 0
        SWF::Element::Tag::ShowFrame->new(
        ),			# 1
        SWF::Element::Tag::End->new(
        ),			# 2
    ]),
)
SWF::Element::Tag::DefineButton2->new(
    ButtonID => 4,
    Flags => 0,
    Characters => SWF::Element::Array::BUTTONRECORDARRAY2->new([
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 1,
            CharacterID => 3,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 0,
                TranslateY => 0,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 2,
                RedMultTerm => 205,
                GreenMultTerm => 205,
                BlueMultTerm => 205,
                AlphaMultTerm => 205,
            ),
        ),			# 0
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 2,
            CharacterID => 3,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 0,
                TranslateY => 0,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 0,
            ),
        ),			# 1
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 4,
            CharacterID => 3,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 40,
                TranslateY => 40,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 0,
            ),
        ),			# 2
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 8,
            CharacterID => 2,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 40,
                TranslateY => 40,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 0,
            ),
        ),			# 3
    ]),
)
SWF::Element::Tag::PlaceObject2->new(
    Flags => 38,
    Depth => 1,
    CharacterID => 4,
    Matrix => SWF::Element::MATRIX->new(
        ScaleX => 1,
        ScaleY => 1,
        RotateSkew0 => 0,
        RotateSkew1 => 0,
        TranslateX => 7925,
        TranslateY => 7026,
    ),
    Name => "swf_test_btn",
)
SWF::Element::Tag::DefineBitsLossless->new(
    CharacterID => 5,
    FileName => 1,
    BitmapFormat => 5,
    BitmapWidth => 256,
    BitmapHeight => 64,
)
SWF::Element::Tag::DefineShape->new(
    ShapeID => 6,
    ShapeBounds => SWF::Element::RECT->new(
        Xmin => 0,
        Ymin => 0,
        Xmax => 5120,
        Ymax => 1280,
    ),
    Shapes => SWF::Element::SHAPEWITHSTYLE1->new(
        FillStyles => SWF::Element::Array::FILLSTYLEARRAY1->new([
            SWF::Element::FILLSTYLE1->new(
                FillStyleType => 65,
                BitmapID => 5,
                BitmapMatrix => SWF::Element::MATRIX->new(
                    ScaleX => 20,
                    ScaleY => 20,
                    RotateSkew0 => 0,
                    RotateSkew1 => 0,
                    TranslateX => 0,
                    TranslateY => 0,
                ),
            ),			# 0
        ]),
        ShapeRecords => SWF::Element::Array::SHAPERECORDARRAY1->new([
            SWF::Element::SHAPERECORD1::STYLECHANGERECORD->new(
                MoveDeltaX => 5120,
                MoveDeltaY => 1280,
                FillStyle1 => 1,
            ),			# 0
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => -5120,
                DeltaY => 0,
            ),			# 1
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => 0,
                DeltaY => -1280,
            ),			# 2
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => 5120,
                DeltaY => 0,
            ),			# 3
            SWF::Element::SHAPERECORDn::STRAIGHTEDGERECORD->new(
                DeltaX => 0,
                DeltaY => 1280,
            ),			# 4
        ]),
    ),
)
SWF::Element::Tag::DefineSprite->new(
    SpriteID => 7,
    FrameCount => 1,
    ControlTags => SWF::Element::Array::TAGARRAY->new([
        SWF::Element::Tag::PlaceObject2->new(
            Flags => 6,
            Depth => 1,
            CharacterID => 6,
            Matrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 0,
                TranslateY => 0,
            ),
        ),			# 0
        SWF::Element::Tag::ShowFrame->new(
        ),			# 1
        SWF::Element::Tag::End->new(
        ),			# 2
    ]),
)
SWF::Element::Tag::DefineButton2->new(
    ButtonID => 8,
    Flags => 0,
    Characters => SWF::Element::Array::BUTTONRECORDARRAY2->new([
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 1,
            CharacterID => 7,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 0,
                TranslateY => 0,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 2,
                RedMultTerm => 205,
                GreenMultTerm => 205,
                BlueMultTerm => 205,
                AlphaMultTerm => 205,
            ),
        ),			# 0
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 2,
            CharacterID => 7,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 0,
                TranslateY => 0,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 0,
            ),
        ),			# 1
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 4,
            CharacterID => 7,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 40,
                TranslateY => 40,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 0,
            ),
        ),			# 2
        SWF::Element::BUTTONRECORD2->new(
            ButtonStates => 8,
            CharacterID => 6,
            PlaceDepth => 1,
            PlaceMatrix => SWF::Element::MATRIX->new(
                ScaleX => 1,
                ScaleY => 1,
                RotateSkew0 => 0,
                RotateSkew1 => 0,
                TranslateX => 40,
                TranslateY => 40,
            ),
            ColorTransform => SWF::Element::CXFORMWITHALPHA->new(
                Flags => 0,
            ),
        ),			# 3
    ]),
)
SWF::Element::Tag::PlaceObject2->new(
    Flags => 38,
    Depth => 3,
    CharacterID => 8,
    Matrix => SWF::Element::MATRIX->new(
        ScaleX => 1,
        ScaleY => 1,
        RotateSkew0 => 0,
        RotateSkew1 => 0,
        TranslateX => 7925,
        TranslateY => 5586,
    ),
    Name => "task_test_btn",
)
SWF::Element::Tag::ShowFrame->new(
)
SWF::Element::Tag::End->new(
)
## Post #2
- Username: AngelSL
- Rank: beginner
- Number of posts: 29
- Joined date: Mon May 07, 2007 9:06 pm
- Post datetime: 2007-10-18T13:15:33+00:00
- Post Title: shockwave flash scripting

Thats DEFINITELY not actionscript.
## Post #3
- Username: gimli
- Rank: ultra-n00b
- Number of posts: 2
- Joined date: Thu Aug 16, 2007 11:32 am
- Post datetime: 2007-10-19T02:35:59+00:00
- Post Title: shockwave flash scripting

WOW, I got a reply !

Yes, its definately NOT actionscript Ive found

It appears to be some kind of perl script, the functions it is using are based on a modified version of this:
[http://search.cpan.org/~ysas/SWF-File-0.42/](http://search.cpan.org/~ysas/SWF-File-0.42/)

However, the 'PngFileTable' 'HEADER' things wont normally work

I can kind of make the language work with minimal modifications however the biggest failing is the 'filename =>' bit
It must be loading the zlibdata into the swf object.
However when I try to work around the lack of that function it messes up the png files - they wont retain see-through transperancy
e.g. if a png file is a diamond on top of a background, the diamond draws, but it becomes a diamond within a box covering the entire background !

Anyone understand how to get a swf graphic object built ?

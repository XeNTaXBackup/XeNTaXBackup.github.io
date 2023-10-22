## Post #1
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T13:49:19+00:00
- Post Title: Amateur Skeleton Hunter

1) Introduction
Amateur Skeleton Hunter, abbreviated ASH, is a helper tool designed for cosy examination on skeleton formats with as less coding work as possible. It provides a text-based C-like struct definition interface using only a handful of pre-defined variables, along with other GUI-based options for how to interpret the read data, allowing to describe different formats in a concise yet flexible way. 

2) Change Log

```
2023.09.14 - v1.3.1		Added support for nested layout;
				Added support for loop control;
				Added new Eval type "assert" for assertion;
				Added new variables "boneHash" and "parentHash" for hierarchy mapping;
				Added new types "Seek" and "Tell" for local address seeking/telling and alignment;
				Extended Eval operations to "boneIndex"/"parentIndex"/"boneNameIndex"/"boneNameAddress" for value adjustment;
				Allowed conditionally omitting T/R/S/M components;
				Allowed unified Scaling factor;
				Added support for custom variables;
				Added new type "Typedef" for defining dynamic type;
				Added support for multi sources (last source would be used by remaining layouts and the string buffer layout);
				Added key words highlighting and auto completions for layout editing.
2023.01.01 - v1.2.1		Fixed several bugs of semantics parsing;
				Fixed a constraint issue of the variable "boneNameIndex";
				Support for Axis Angle rotation encoding;
				Added "short" to the general data type "Real";
				Added independent normalization factors for transformation attributes using "short" as data type.
2022.02.05 - v1.1.0		Added a selector for exporting ASCII/binary FBX format.
2022.02.04 - v1.0.2		Auto handling of singularity situations when converting matrices to Euler angles;
				Rotation Order now applys only on Euler angles.
2021.12.23 - v1.0.1		Initial release.

```

3) User Interface

Refer to the [ASH Demos](viewtopic.php?f=29&t=24882) for a quick start.

4) Main Features
1. Support for parsing skeleton related data of all sorts of data types;
2. Ability to handle variant-length data structures via the "length" and the "skip" variables coulped with optional evaluation statements;
3. Support for common arithmetic, logical and bit operations on the "length" variable;
4. Support for serial evaluation statements under a specified condition via the "scope" variable;
5. Formatting operations for debugging raw/converted transformation info, name mapping and bone hierarchy;
6. Visualization of skeletons;
7. Export of the skeletons either as the FBX format, or as an exchange node dump that can be loaded by AXE.

5) Notes

There are some components used or required by ASH which are not likely to be changed frequently so they're detached from the release of the ASH executable.

The first component is an external mesh viewer called "ViewScene" which ASH uses to preview the skeleton.

The second component is required by ASH for its GUI is based on Qt technology thus it requires the Qt dependencies for execution.

These components can be downloaded through the links provided in the attachment.

You must place both the ViewScene folder and the Qt dependencies into the same path of the ASH executable.
The overall folder layout of ASH should be:

```
ASH/ViewScene/*
ASH/platforms/*
ASH/Qt5**.dll

```


Microsoft Visual C++ 2015 Redistributable (x86) or above is required for runtime.

6) Download
[ASH.7z](https://xentaxbackup.github.io/file/24373_ASH.7z)
## Post #2
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:02:40+00:00
- Post Title: Amateur Skeleton Hunter

- User Interface



- Terms and Definitions:

Bone Attributes: properties that owned by a bone node, including bone index, parent index, bone name, and transformation info such as translation, rotation and scaling (collectively referred to as the TRS components), or combined transformation matrix. The combined transformation matrix has a higher priority than individual transformation components. There're also a few accessary properties that serve as a means to determine certain properties if they don't exist in an explicit form, including bone name index and bone name address for determining the bone name, bone hash for determining the bone index, and parent hash or parent name for determining the parent index.

Bone Object Layout: layout definition of a struct holding the per-bone attributes. Each attribute can only be defined no more than once in the scope of each Branch. The mandatory attributes of a bone node, including bone index, parent index, bone name and transformation info, will be using the default values if they're not defined. The premise is that the struct is not empty.

String Pool Bone Name Object Layout: layout definition of a string element in the string pool. The only allowed variables in this layout are "skip", "length" and "boneName". This layout is only needed if the bone names are stored together into a buffer and referenced by an string index (or implicitly the bone index), or an address to the string. If it's referenced by index, a count of the string elements and a base address of the buffer is required. If it's referenced by address, a base address can also be specified for relative addressing.

Sibling Objects: a collection of bone object layouts which each holds exclusively parts of the required per-bone attributes. Each layout definition also comes with an optional address where the array of such defined elements begins. If the address is omitted, then it's assumed to be 0 for the first sibling object, or the address where the array defined by the previous object ends, for following objects.

Branch: a max collection of bone nodes describable by a set of Sibling Objects. A branch is defined by a set of Sibling Objects, the bone count, and optionally the String Pool Bone Name Object Layout (plus associated base address and/or string count).

Bone Tree: a set of Branches, where each node in the collection of all bones owns a unique bone index. For instance, a Branch of the character main skeleton contains 100 bones whose bone indices covered the entire closed interval from 0 to 99, and a second Branch contains 10 accessory bones (such as weapons, etc.) whose bone indices covered the entire closed interval from 100 to 109. The major obstacle to use only one Branch to complete the task could be that there's additional data inserted among the Branches, or that each Branch uses a different layout definition.

Bone Forest: a collection of Bone Trees. Useful only if there exist multiple independent skeletons in the scene.

- Global Properties:

Endianness: global endianness for how data are read. Default value is little.
String Encoding: character encoding of bone names. Default value is UTF8.
Rotation Encoding: representation form of rotation. Default value is Euler.
Scene Unit: FBX scene unit property for preview only. Default value is Centimeter, which is also what AXE uses.
Coordinate Space: reference frame of the transformation info. Default value is local space.
Rotation Order: order of the combining rotations along the X, Y and Z axes. Default value is XYZ. Applys to Euler angles only.
Quaternion Storage: storage order of the 4 Quaternion components. Default value is XYZW. Affects also on vec3 Quaternions omitting the 4th component. It's only served as a last resort if everything didn't work.
Original Axis System: axis system the format used. Target system follows the OpenGL standard, ie. Y up, Z front, and X right. So does the default value.
Major Order: storage order of rotation/transformation matrix. Default value is Row-major. Applies also to Quaternion/Axis Angle where it'll perform a transpose operation on the rotations, but no effects on Eluer rotations. This property is ignored if the matrices are in 3x4 form (i.e. TransformMatrix[12]) since row-major would then be the only option.
Transformation (Inverse Transformation): option for inverting the transformation info, regardless of the original form it used.

Note that the above properties take affect in a global level irrelevant to the Sibling Objects/Bone Tree/Bone Forest.

- Data Interpretation/Formatting

Hierarchy: print a hierarchy of the converted bone tree.
Bone Names: print a list of names of the converted bone tree.
Transformations: print the transformation info of each node of the converted bone tree.
Bone Index to Bone Name Mapping: print the mapping of the bone nodes and their names.
Raw Translations/Rotations/Scalings/Transformation Matrices: corresponding raw transformation info of a loaded Branch.

If there's no Branch/Tree in the list, it'll perform an automatic promotion from the layout definition, or failed if no layout has been defined.

- Syntax of the Layout Definition Interface:

Since it's a pretty common case to see variant-length or optional data elements in bone data structure it's not possible to design a pure graphical interface while keeping everything simple and flexible. Hence a more delightful solution will be using a text-based struct definition interface that shares a similar syntax to the C programming language, except that there's no semicolon at the end of each variable declaration statement. A variable declaration statement follows a simple syntax shown below:

```

```

Where "Type" stands for the allowed general data type for "Variable", and "Size" in the square brackets is an optional field that specifies the 1st and the 2nd dimension sizes if the variable is an array. Only certain variables support 2 dimensions to be defined, while the rest of them allow only 1 or 0 dimension. Single line comment is allowed using the "//" identifier.

There's no limit for the number of white spaces (space or tab) placed between "Type" and "Variable", and that after the last dimension size.

The pre-defined variables are listed below:

```
Eval		length[operator][num]
State		scope
State		loop[num|length]
Loop		loop[num|length]
Seek		address[num|length]
Tell		address[length]
Integer		skip[num|length]
Integer		skip[num|length][num]
Integer		skip[num][num|length]
Integer		boneIndex
Integer		boneNameIndex
Integer		boneNameAddress
Integer		boneHash
Integer		parentIndex
Integer		parentHash
Eval		boneIndex[operator][num|length]
Eval		parentIndex[operator][num|length]
Eval		boneNameIndex[operator][num|length]
Eval		boneNameAddress[operator][num|length]
TChar		boneName[num|?|length]
TChar		parentName[num|?|length]
Real		Translation[3|4]
Real		Rotation[3|4|9]
Real		Scaling[3|4]
Real		TransformMatrix[12|16]

```


The "operator" refers to one of the pre-defined operators (see below). The "num" refers to a literal value which can be either a decimal integer like 1234 or a hex value with the "0x" prefix like 0x789C (or 0x789c). The variable "length" can be used as a dimension size for variables including "skip", "boneName" and "parentName". The '?' mark is used as a notation for null-terminated string with unpredictable length. Various size candidates are separated by the '|' mark.

Custom variables can be defined as the following types:

```
Real		CustomVariable
Eval		CustomVariable[operator][num|var]
Typedef		CustomVariable[Integer|Real]

```

The "var" can be any defined custom variable except for an alias type. It can also be one of the pre-defined variables including length, boneIndex, parentIndex, boneNameIndex, and boneNameAddress. By default the custom variable mode is disabled and can be activated from the "Options" menu.

The instantiated data types of each general type are listed below:

```
Real:    half|short|float|double
TChar:   char|byte|word
Eval:    calc|test|assert
State:   begin|end
Loop:    break
Seek:    seek|align
Tell:    tell
Typedef: typedef

```


The variable "scope" can be used to achive serial evaluation statements when a given condition is met. In that case the serial statements body must be wrapped within the "begin scope" and the "end scope" statements. The variable "loop" can be used to perform loop operations.

The supported operators for each instantiation of the general type "Eval" are listed below:

```
test|assert: == != > < >= <=

```
## Post #3
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-23T14:04:14+00:00
- Post Title: Amateur Skeleton Hunter

- FAQ
This is a reserved section for future reference if we need a place for frequently asked questions.
## Post #4
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2021-12-24T11:41:57+00:00
- Post Title: Amateur Skeleton Hunter

Update:
Recompiled executable for WinXP.
## Post #5
- Username: dimis9138
- Rank: veteran
- Number of posts: 85
- Joined date: Tue Jul 28, 2020 1:37 am
- Post datetime: 2021-12-24T23:04:22+00:00
- Post Title: Amateur Skeleton Hunter

Sick release Ghost. Maybe now I'll get the courage to learn how to do skeletons.
## Post #6
- Username: Bigchillghost
- Rank: double-veteran
- Number of posts: 1031
- Joined date: Tue Jul 05, 2016 4:37 pm
- Post datetime: 2023-09-23T14:20:17+00:00
- Post Title: Amateur Skeleton Hunter

Updated v1.3.1:
- Added support for nested layout;
- Added support for loop control;
- Added new Eval type "assert" for assertion;
- Added new variables "boneHash" and "parentHash" for hierarchy mapping;
- Added new types "Seek" and "Tell" for local address seeking/telling and alignment;
- Extended Eval operations to "boneIndex"/"parentIndex"/"boneNameIndex"/"boneNameAddress" for value adjustment;
- Allowed conditionally omitting T/R/S/M components;
- Allowed unified Scaling factor;
- Added support for custom variables (see Options);
- Added new type "Typedef" for defining dynamic type;
- Added support for multi sources (last source would be used by remaining layouts and the string buffer layout);
- Added key words highlighting and auto completions for layout editing.

Updated v1.3.2:
- Added individual Radian switch checkbox for Euler and Axis Angle.

## Post #1
- Username: Durik256
- Rank: ultra-veteran
- Number of posts: 429
- Joined date: Thu Nov 22, 2018 2:26 am
- Post datetime: 2022-11-19T02:46:33+00:00
- Post Title: SkelFinder

SkelFinder
This little form is for finding the skeleton inside binary file.

ToolStripMenu[1]:
File:
--Open... - open any file for finding skel.
--Eport - export cur skel to [.SkelFinder], collada [.dae], valve [.smd].
--Exit - close Form.
-Tools:
--TextBox Mode - activate TextBox mode.(full template editing)
--ListBox Mode - activate ListBox mode.(adding and editing cmd using the UI)
--ist <-> text - copy all cmd from not active mode in active mode.(the inactive template will be cleared)
--open temp.txt - loads cmd(and params) from temp file.
--save temp.txt - save cmd(and params) in temp file from active mode.
--save BMP - save 3D preview to bmp picture.
CmdTabPages[2]:
--name - will read the string and assigned as the name of the bone.
>>>NumericUpDown - string length if fixed. (or '-1' to read all characters up to the first null byte)
>>>DropDown - to select the mode. (fixed or read the length value before the string)
>>>CheckBox[\x00] - indicate if there is a null byte at the end of the string.
--rotation - will read a rotation with the specified type and auto converted to a 4x4 matrix for the bone.
>>>DropDown - rotation type (Mat43, Mat44, Quat, Euler[rad,deg])
>>>DropDown - value type for cur rotation.
>>>if selected rotation UlerAngles: DropDown - transpose value (xyz, yxz, e.t.c)
>>>CheckBox[transpose] - Transposes the rows and columns of a matrix.(or quat)
>>>CheckBox[inverse/normalize] - Inverts the specified matrix. (or normalize for quat)
--position - will read a vector3 with the specified type, and set the position in the bone matrix.
>>>DropDown - value type.
--parent - will read parent, and set in the bone.
>>>DropDown - to select the mode. (string or integer)
>>>if a string, then the rest of the parameters are the same as for the command "name"
--seek - skip specified number of bytes.
>>>DropDown - to select the mode. (fixed or read the value from file)
>>>CheckBox[mul] - multiply the read value by the specified value.
>>>NumericUpDown - the value by which the read value will be multiplied.
--offset - the new position in the current stream(begin).divides the template into cycles.
FOR ALL CMD: 
>>Button[Add] - add current command to template.
>>Button[R] - overwrite the selected command in the template with the current command. (for editing, only for ListBox mode)
Template[3]:
>>>CheckBox[bigE] - whether to use big Endian when reading.
>>>CheckBox[mltply] - multiply child bones by parent. (from local to world space)
>>>NumericUpDown - specify how many bones to read from the file.
>>>Button[F] - open file. (red if no file is open, and green when open)
>>>ListBox/TextBox - template entry field.
>>>Button[↑] - move selected cmd up.(only for ListBox mode)
>>>Button[↓] - move selected cmd down.(only for ListBox mode)
>>>Button[clr] - clear all cmd from active(Template) mode.
>>>Button[del] - remove selected cmd.(only for ListBox mode)
>>>Button[run] - read bones from a file using the active template and the specified parameters.
Debug[4/5]:
>>>NumericUpDown - number of decimal places when printing.
>>>TextBox - bebug entry field.
>>>Button[clr]/[matrix]/[name]/[pos]/[prnt] - printing information.
3D View[6]:
>>>PictureBox - draw 3d skeleton.
>>>CheckBox[render name] - render name in 3d view.
>>>Button[color] - change cbackground color.
>>>Button[reset] - reset 3d view.(or click middle mouse button)
>>>Mouse - LKM DOWN AND MOVE for rotation. whell for zoom.
warning: "if the position goes beyond the boundaries of the file during reading, it will return those bones that were read before the error, also the multiplication will not be performed(if use), and the parent will not be converted to an integer from string(if use)
[github](https://github.com/Durik256/SkelFinder)
edit:
-bug fix
-Add export to [.dae/.smd]
[skelFinder.zip](https://xentaxbackup.github.io/file/23197_skelFinder.zip)
## Post #2
- Username: ptg1121
- Rank: advanced
- Number of posts: 40
- Joined date: Sun Nov 07, 2021 9:25 pm
- Post datetime: 2022-11-28T03:37:16+00:00
- Post Title: SkelFinder

> Reply from Durik256 ↑Sat Nov 19, 2022 10:46 am at Sat Nov 19, 2022 10:46 am
>
> 

HI Durik256:

That's great!

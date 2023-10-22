## Post #1
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-20T03:48:57+00:00
- Post Title: 3DRipperDX SqewFix Blender Plugin-3DS Max Conversion Request

As we all should know by now 3DripperDX (32bit) will often skew rips made
Dusan from the tombraiderforums created a Blender Plugin to realign and perfectly fix the model

Modern game ripping works very well with NinjaRipper(formally DxRipper) but for older games and my purposes I still need to use 3DripperDx in an 32bit XP environment.

The Blender Pugin works but personally I hate blender 'especially the older versions' and it would save me a lot of time to have this plugin converted for 3DS max (pref 2013,2015 or 2017)  
OR UPDATED TO WORK WITH THE NEWEST VERSION OF BLENDER

XYZ Plugin Fixer
Works with Blender & requires Python
[http://www.tombraiderforums.com/showpos ... ostcount=4](http://www.tombraiderforums.com/showpost.php?p=3874675&postcount=4)


For this plugin to work you need an ancient version of Blender the Script says Blender 2.48
[http://download.blender.org/release/Blender2.48/](http://download.blender.org/release/Blender2.48/)
And python 2.5.2
[https://www.python.org/downloads/windows/](https://www.python.org/downloads/windows/)

I contacted Dusan on TR forums but got no reply

```

"""
Name: 'Correct3DRipper'
Blender: 248
Group: 'Mesh'
"""

__author__ = "Dusan Pavlicek"
__email__ = "pavlicd@volny.cz"

import Blender
import math

from Blender import *
from Blender.Mathutils import *


BUTTON_ASSIGN_GROUND = 1
BUTTON_ASSIGN_FRONT = 2
BUTTON_ASSIGN_SIDE = 3
BUTTON_ADJUST_SCALES = 4
BUTTON_ALIGN_PLANES = 5

SELECTED_VERTS_GROUND = []
SELECTED_VERTS_FRONT = []
SELECTED_VERTS_SIDE = []

AXIS_X = 1
AXIS_Y = 2
AXIS_Z = 3

PLANE_XY = 1
PLANE_XZ = 2
PLANE_YZ = 3


def GetVisibleMeshObjects():
	editmode = Window.EditMode()
	Window.EditMode(0)
	meshObjects = []
	scene = Scene.GetCurrent()
	if scene != None:
		for object in scene.objects:
			if object.type != 'Mesh':
				continue
			visible = False
			for objectLayer in object.layers:
				if objectLayer in scene.layers:
					visible = True
					break
			if not visible:
				continue
			meshObjects.append(object)
	Window.EditMode(editmode)
	return meshObjects

	
def GetSelectedVisibleMeshObjects():
	editmode = Window.EditMode()
	Window.EditMode(0)
	meshObjects = []
	scene = Scene.GetCurrent()
	if scene != None:
		for object in scene.objects:
			if not object.sel:
				continue
			if object.type != 'Mesh':
				continue
			visible = False
			for objectLayer in object.layers:
				if objectLayer in scene.layers:
					visible = True
					break
			if not visible:
				continue
			meshObjects.append(object)
	Window.EditMode(editmode)
	return meshObjects


def GetMeshFromObject(object):
	if object.type != 'Mesh':
		return None
	return object.getData(mesh=True)


def GetSelectedVisibleVertices(onlySelectedMeshes):
	vertices = []
	if onlySelectedMeshes:
		objects = GetSelectedVisibleMeshObjects()
	else:
		objects = GetVisibleMeshObjects()
	for object in objects:
		objectMatrix = object.getMatrix()
		mesh = GetMeshFromObject(object)
		for vertex in mesh.verts:
			if not vertex.sel:
				continue
			if vertex.hide:
				continue
			vertices.append([object, vertex])
	return vertices


def CalcScaleTransform(axis, p1, p2, p3, q1, q2, q3):
	a = Vector(p2.x - p1.x, p2.y - p1.y, p2.z - p1.z)
	b = Vector(p3.x - p1.x, p3.y - p1.y, p3.z - p1.z)
	c = Vector(q2.x - q1.x, q2.y - q1.y, q2.z - q1.z)
	d = Vector(q3.x - q1.x, q3.y - q1.y, q3.z - q1.z)
	u = (a.y * b.z - a.z * b.y) * (c.y * d.z - c.z * d.y)
	v = (a.z * b.x - a.x * b.z) * (c.z * d.x - c.x * d.z)
	w = (a.x * b.y - a.y * b.x) * (c.x * d.y - c.y * d.x)
	sx = 1
	sy = 1
	sz = 1
	if axis == AXIS_X:
		if v + w != 0:
			t = -u / (v + w)
		else:
			t = -1
		if t > 0:
			s = math.sqrt(t)
			sx = s
	elif axis == AXIS_Y:
		if u + w != 0:
			t = -v / (u + w)
		else:
			t = -1
		if t > 0:
			s = math.sqrt(t)
			sy = s
	elif axis == AXIS_Z:
		if u + v != 0:
			t = -w / (u + v)
		else:
			t = -1
		if t > 0:
			s = math.sqrt(t)
			sz = s
	if t > 0:
		Draw.PupMenu('Axis scale multiplied by %f.' % s)
		if s == 1:
			return None
	else:
		if abs(u + v + w) < 1e-4:
			Draw.PupMenu('Planes are already perpendicular.')
		else:
			Draw.PupMenu('Sorry, I cannot make the two planes perpendicular.')
		return None
	return ScaleMatrix(sx, sy, sz)


def ScaleMatrix(sx, sy, sz):
	return Matrix(
		[sx, 0, 0, 0],
		[0, sy, 0, 0],
		[0, 0, sz, 0],
		[0, 0, 0, 1])


def CorrectAxisScale(axis, selectedVerts1, selectedVerts2):
	Window.WaitCursor(1)
	matrix = CalcScaleTransform(
			axis,
			selectedVerts1[0][1].co * selectedVerts1[0][0].getMatrix(),
			selectedVerts1[1][1].co * selectedVerts1[1][0].getMatrix(), 
			selectedVerts1[2][1].co * selectedVerts1[2][0].getMatrix(),
			selectedVerts2[0][1].co * selectedVerts2[0][0].getMatrix(), 
			selectedVerts2[1][1].co * selectedVerts2[1][0].getMatrix(), 
			selectedVerts2[2][1].co * selectedVerts2[2][0].getMatrix())
	if matrix != None:
		objects = GetVisibleMeshObjects()
		for object in objects:
			object.setMatrix(object.getMatrix() * matrix)
	Window.WaitCursor(0)
	Redraw()
	return


def CalcPlaneNormal(p1, p2, p3):
	u = Vector([p2.x - p1.x, p2.y - p1.y, p2.z - p1.z])
	v = Vector([p3.x - p1.x, p3.y - p1.y, p3.z - p1.z])
	return CrossVecs(u, v).normalize()


def CalcRotationTransform(p1, p2, p3, alignPlane):
	if alignPlane == PLANE_XY:
		i = Vector(0, 0, 1)
	elif alignPlane == PLANE_XZ:
		i = Vector(0, 1, 0)
	elif alignPlane == PLANE_YZ:
		i = Vector(1, 0, 0)

	normalPos = CalcPlaneNormal(p1, p2, p3)
	normalNeg = -normalPos
	anglePos = AngleBetweenVecs(normalPos, i)
	angleNeg = AngleBetweenVecs(normalNeg, i)
	if anglePos < angleNeg:
		angle = anglePos
		normal = normalPos
	else:
		angle = angleNeg
		normal = normalNeg

	if alignPlane == PLANE_XY:
		axis = Vector([-normal.y, normal.x, 0])
	elif alignPlane == PLANE_XZ:
		axis = Vector([-normal.z, 0, normal.x])
	elif alignPlane == PLANE_YZ:
		axis = Vector([0, -normal.z, normal.y])
	if axis.length < 1e-5:
		return Matrix().resize4x4().identity()

	matrixPos = RotationMatrix(+angle, 4, 'r', axis)
	matrixNeg = RotationMatrix(-angle, 4, 'r', axis)
	testPos = normal * matrixPos
	testNeg = normal * matrixNeg
	anglePos = AngleBetweenVecs(testPos, i)
	angleNeg = AngleBetweenVecs(testNeg, i)
	if anglePos < angleNeg:
		matrix = matrixPos
	else:
		matrix = matrixNeg
	return matrix


def CalcAlignTransform(p1, p2, p3, alignPlane):
	matrixRot = CalcRotationTransform(p1, p2, p3, alignPlane)
	test = p1 * matrixRot
	if alignPlane == PLANE_XY:
		matrixTrans = TranslationMatrix(Vector(0, 0, -test.z))
	elif alignPlane == PLANE_XZ:
		matrixTrans = TranslationMatrix(Vector(0, -test.y, 0))
	elif alignPlane == PLANE_YZ:
		matrixTrans = TranslationMatrix(Vector(-test.x, 0, 0))
	return matrixRot * matrixTrans


def AlignGeometry(p1, p2, p3, alignPlane):
	Window.WaitCursor(1)
	matrix = CalcAlignTransform(p1, p2, p3, alignPlane)
	objects = GetVisibleMeshObjects()
	for object in objects:
		object.setMatrix(object.getMatrix() * matrix)
	Window.WaitCursor(0)
	Redraw()
	return


def DrawGUI():
	YPOS = 360
	BGL.glClear(BGL.GL_COLOR_BUFFER_BIT)
	BGL.glColor3f(0, 0, 0)
	
	BGL.glRasterPos2d(10, YPOS)
	Draw.Text('This script adjusts scales of X, Y and Z axes so that')
	BGL.glRasterPos2d(10, YPOS - 15)
	Draw.Text('the specified ground, front and side planes become')
	BGL.glRasterPos2d(10, YPOS - 30)
	Draw.Text('perpendicular.')
	BGL.glRasterPos2d(10, YPOS - 45)
	Draw.Text('It also aligns the ground plane with the XY plane.')

	BGL.glRasterPos2d(10, YPOS - 80)
	Draw.Text('1) For each plane, select three vertices and click')
	BGL.glRasterPos2d(25, YPOS - 95)
	Draw.Text('a button to define the corresponding plane:')

	Draw.Button('Assign GROUND plane', BUTTON_ASSIGN_GROUND, 25, YPOS - 130, 150, 20)
	Draw.Button('Assign FRONT plane', BUTTON_ASSIGN_FRONT, 25, YPOS - 155, 150, 20)
	Draw.Button('Assign SIDE plane', BUTTON_ASSIGN_SIDE, 25, YPOS - 180, 150, 20)

	BGL.glRasterPos2d(10, YPOS - 205)
	Draw.Text('2) Then press the button to automatically')
	BGL.glRasterPos2d(25, YPOS - 220)
	Draw.Text('adjust all three axis scales.')

	Draw.Button('Adjust axes scales', BUTTON_ADJUST_SCALES, 25, YPOS - 255, 150, 20)

	BGL.glRasterPos2d(10, YPOS - 280)
	Draw.Text('3) Then press the button to automatically align')
	BGL.glRasterPos2d(25, YPOS - 295)
	Draw.Text('the three planes with the world coordinate system.')

	Draw.Button('Align planes', BUTTON_ALIGN_PLANES, 25, YPOS - 330, 150, 20)
	return


def HandleEvent(event, value):
	if event == Draw.ESCKEY:
		Draw.Exit()
	return


def HandleButton(button):
	global SELECTED_VERTS_GROUND
	global SELECTED_VERTS_FRONT
	global SELECTED_VERTS_SIDE

	if button == BUTTON_ASSIGN_GROUND:
		SELECTED_VERTS_GROUND = GetSelectedVisibleVertices(True)
		if len(SELECTED_VERTS_GROUND) != 3:
			Draw.PupMenu('Select exactly 3 vertices please.')
		return
	if button == BUTTON_ASSIGN_FRONT:
		SELECTED_VERTS_FRONT = GetSelectedVisibleVertices(True)
		if len(SELECTED_VERTS_FRONT) != 3:
			Draw.PupMenu('Select exactly 3 vertices please.')
		return
	if button == BUTTON_ASSIGN_SIDE:
		SELECTED_VERTS_SIDE = GetSelectedVisibleVertices(True)
		if len(SELECTED_VERTS_SIDE) != 3:
			Draw.PupMenu('Select exactly 3 vertices please.')
		return
	if button == BUTTON_ADJUST_SCALES:
		if len(SELECTED_VERTS_GROUND) == 0:
			Draw.PupMenu('Assign GROUND plane please.')
			return
		if len(SELECTED_VERTS_FRONT) == 0:
			Draw.PupMenu('Assign FRONT plane please.')
			return
		if len(SELECTED_VERTS_SIDE) == 0:
			Draw.PupMenu('Assign SIDE plane please.')
			return
		CorrectAxisScale(AXIS_Y, SELECTED_VERTS_GROUND, SELECTED_VERTS_FRONT)
		CorrectAxisScale(AXIS_X, SELECTED_VERTS_FRONT, SELECTED_VERTS_SIDE)
		CorrectAxisScale(AXIS_Z, SELECTED_VERTS_GROUND, SELECTED_VERTS_SIDE)
		return
	if button == BUTTON_ALIGN_PLANES:
		if len(SELECTED_VERTS_GROUND) == 0:
			Draw.PupMenu('Assign GROUND plane please.')
			return
		if len(SELECTED_VERTS_FRONT) == 0:
			Draw.PupMenu('Assign FRONT plane please.')
			return
		p1 = SELECTED_VERTS_GROUND[0][1].co * SELECTED_VERTS_GROUND[0][0].getMatrix()
		p2 = SELECTED_VERTS_GROUND[1][1].co * SELECTED_VERTS_GROUND[1][0].getMatrix()
		p3 = SELECTED_VERTS_GROUND[2][1].co * SELECTED_VERTS_GROUND[2][0].getMatrix()
		AlignGeometry(p1, p2, p3, PLANE_XY)
		p1 = SELECTED_VERTS_FRONT[0][1].co * SELECTED_VERTS_FRONT[0][0].getMatrix()
		p2 = SELECTED_VERTS_FRONT[1][1].co * SELECTED_VERTS_FRONT[1][0].getMatrix()
		p3 = SELECTED_VERTS_FRONT[2][1].co * SELECTED_VERTS_FRONT[2][0].getMatrix()
		AlignGeometry(p1, p2, p3, PLANE_XZ)
		return
	return


def Main():
	Draw.Register(DrawGUI, HandleEvent, HandleButton)
	return


Main()

```

Example of the Blender Script in action.
## Post #2
- Username: Andrakann
- Rank: ultra-veteran
- Number of posts: 392
- Joined date: Wed Jul 06, 2011 3:47 pm
- Post datetime: 2017-01-21T12:21:16+00:00
- Post Title: 3DRipperDX SqewFix Blender Plugin-3DS Max Conversion Request

> Reply from ReeceMix
>
> As we all should know by now 3DripperDX (32bit) will often skew rips made
Dusan from the tombraiderforums created a Blender Plugin to realign and perfectly fix the model
He's also made 3dsmax version of this script and another useful script for full scene rotation.
Attached.
[Max_Scripts_by_Dusan.zip](https://xentaxbackup.github.io/file/12258_Max_Scripts_by_Dusan.zip)
## Post #3
- Username: ReeceMix
- Rank: advanced
- Number of posts: 64
- Joined date: Sat Nov 10, 2007 10:01 pm
- Post datetime: 2017-01-21T13:43:21+00:00
- Post Title: 3DRipperDX SqewFix Blender Plugin-3DS Max Conversion Request

> Reply from Andrakann
>
> ReeceMix wrote:
He's also made 3dsmax version of this script and another useful script for full scene rotation.
Attached.

Ah thankyou, I was aware he made a 3DSmax version 1st and tried to contact him to get it but got no reply and the deepshadows links dont work.  I'm not sure if this 3ds max version works with newer versions of 3ds max but I will try it out. x

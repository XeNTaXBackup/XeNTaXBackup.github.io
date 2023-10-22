## Post #1
- Username: shakotay2
- Rank: MEGAVETERAN
- Number of posts: 4299
- Joined date: Fri Apr 20, 2012 4:24 pm
- Post datetime: 2016-03-19T15:30:59+00:00
- Post Title: [info] web based 3D model viewer

On my search for a web based 3D model viewer I found this stunning solution by Ivan Kuckir:
[http://blog.ivank.net/3d-tool-web-based ... iewer.html](http://blog.ivank.net/3d-tool-web-based-3d-model-viewer.html)

read here for more: [http://k3d.ivank.net](http://k3d.ivank.net)
"To use K3D, you should have a basic knowledge of 3D meshes, index / vertex coordinate arrays etc."

I've modified Ivan's example for loading the raptor.obj a little bit
so that it could load Agamemnon_90.obj from my harddisk.

(I used a fantasy texture because I don't have the original one.)
copy code into a html file of your choice
download the libraries ivank.js and K3D.js
copy them into the directory where your html file resides
put an obj file into the same directory
same with a suiting texture file (*.jpg)
change K3D.load("your.obj", loaded);
change s.graphics.beginBitmapFill(new BitmapData("your.jpg"));
drag html onto your browser (blank page)

```
<head>
     //<script type="text/javascript" src="http://lib.ivank.net/ivank.js"></script>
     //<script type="text/javascript" src="http://k3d.ivank.net/K3D.js"></script>
     <script type="text/javascript" src="ivank.js"></script>
     <script type="text/javascript" src="K3D.js"></script>
     <script type="text/javascript">
          
          function Start()
          {
               //K3D.load("raptor.obj", loaded);		// loading file ...
               K3D.load("AGAMEMNON_90.obj", loaded);
          }
          
          function loaded(data)
          {
               var m = K3D.parse.fromOBJ(data);	// done !
               console.log(m);
               
               var stage = new Stage("c");  
               var s = new Sprite(); 
               stage.addChild(s);
               
               s.x = stage.stageWidth/8;        // 2
               s.y = stage.stageHeight/4 + 280; // 200
               s.z = 300;			// 300
               s.scaleX = s.scaleY = s.scaleZ = 5;
               
               //	I need to index vertices and UVT with the same indices... 0, 1, 2, ...
               var vts = K3D.edit.unwrap(m.i_verts, m.c_verts, 3);
               
               //  In my engine, Y goes down, but in raptor model, Y goes up
               K3D.edit.transform(vts, K3D.mat.scale(1,-1,1));	
               //K3D.edit.transform(vts, K3D.mat.scale(1,1,-1));	

               var uvt = K3D.edit.unwrap(m.i_uvt  , m.c_uvt  , 2);
               var ind = [];
               for(var i=0; i<m.i_verts.length; i++) ind.push(i);
               
               //s.graphics.beginBitmapFill(new BitmapData("raptor.jpg"));
               s.graphics.beginBitmapFill(new BitmapData("mandelbrot.jpg"));
               s.graphics.drawTriangles3D(vts, ind, uvt);
               
               stage.addEventListener(Event.ENTER_FRAME, 
                    function(e) { s.rotationY += 0.01*(stage.mouseX - stage.stageWidth/2); } );
                    //function(e) { s.rotationZ += 0.01*(stage.mouseX - stage.stageWidth/2); } );
          }
     </script>
</head>
<body onload="Start();"><canvas id="c"></canvas></body>
</html>
```

In case you want to use the online libraries uncomment the two lines with src="http://...
and comment out the two lines behind them.

In case of problems with the texture I'd suggest to use a wavefront obj file
where the indices for vertices and uvs are identical, such like this:
f 1/1/1 2/2/2 3/3/3



Agamemnon_in_browser.jpg (22.78 KiB) Viewed 60 times


Successfully tested wiith QupZilla (should work with Mozilla, too).

Opera complained: XMLHttpRequest cannot load file:///X:/Web-3D/Agamemnon_90.obj. 
Cross origin requests are only supported for protocol schemes: 
http, data, chrome, chrome-extension, https, chrome-extension-resource.

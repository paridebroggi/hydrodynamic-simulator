#Hydrodynamic Simulator

![](screenshots/crater%20flood.png)

HDS is a hydrodynamic simulator that reproduces water behaviuor in different contests and landscape (parsed dynamically from a .hds file). At the moment rain, flood, drainage, waves and tsunami scenarios are implemented. It's built with C++ and OpenGL 4.0.

#Configuration

`OpenGL 3.3` or greater is required. It is currently set up to use `OpenGL 4.1`, but you can change it to match your hardware's specifics by editing the following lines:

*incs/Define.hpp*

```
# define GL_MAJOR					4
# define GL_MINOR					1
```

This programm was tested solely on `OSX` machines, but should be compatible with `UNIX` operating systems. You can always drop me a line for support, but keep in mind that it was not designed with cross-platform compatiblity as a requirement.

Depending on your graphical hardware, you might experience slowdowns when using the `rain` scenario. Decrease or increase the numbers of instances editing this line:

*incs/Define.hpp*

```
# define MAX_INSTANCES				17000
```

Recent graphical hardwares can handle up to millions of instances.

#Commands

During the simulation you can press the following keys:

`arrow keys`: change the angle of the camera

`+`: zoom in

`-` zoom out

`v`: start draining the water out of the scene

`f`: restart the simulation as a 'flood' scenario

`w`: trigger a wave

#Usage

**Run Hydrodynamic Simulator**

`./hds <scenario> <maps>`

Both parameters are required, otherwise an exception will be thrown.

**Available scenarios:**

`flood`: Water flood the scene from all four borders.

`waves`: Gentle waves come from one border of the scene and progressively covers the terrain.

`rain`: Strong precipitations.

`drain`: Drainage from all four borders.

`tsunami`: A giant wave crashes the scene.

**Maps**

Specify a path to a map file.

#Create map file

Map file should end with *.hds* extension and should have the following format:

*Resolution*

`width:<100:2560> height:<100:1440>`

*Grid*

`col:<20:3000> row:<20:3000>`

*Height Map*

`x:<0:col> y:<0:> z:<0:row>`

You can add as many height points as you like (y coordinate represent the height).
Feel free to create your own map and to share it on this github repository.

#Source tree

`incs/`
Contains header files related to libraries (GL, GLM, GLFW) and source files.

`lib/`
Contains GLEW and GLFW3 static libraries.

`srcs/`
Contains the C++ source code.

`maps/`
Contains a set of maps used by the programm.

#Licence:

<a href="http://opensource.org/licenses/MIT" target="_blank">The MIT License (MIT)</a>

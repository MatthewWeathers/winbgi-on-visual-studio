# winbgi-on-visual-studio
Some resources for using the WinBGI graphics library with Visual Studio 2022. Specifically, these are resources for teaching an Intro to Computer Science C++ course at the college level.

## About WinBGI / WinBGIm
Here's a description from the official website at the University of Colorado (https://home.cs.colorado.edu/~main/bgi/install.html)
>WinBGIm is a Windows C++ graphics library based on the classic Borland Graphics Interface (originally distributed with Borland’s Turbo Pascal and later with their Turbo C compilers). In addition to the original BGI interface, WinBGIm also provides programmer support for accessing the mouse and for using the graphics window as a C++ ostream.

This was originally developed around 2008, but it still works with a modern IDE like Visual Studio 2022.

Although this library is too outdated to use for a production environment, it provides an easy way for first-year students to use graphics in their C++ programs. These resources in this repository focus on the educational environment.

## Resources Included
A good place to start would be with this ZIP file: example-graphics-functions.zip (449k)

That file includes a complete Microsoft Visual Studio 2022 project folder with sample code and the necessary library files. The sample code shows examples of common graphics functions. This one ZIP file contains everything you need to make your own graphics programs.

## Rationale - Why use an old library?
In the context of education, we want students to be able to create C++ programs that have graphics with minimal effort, right from the beginning. The "empty" Windows Application template in Visual Studio has 170+ lines of complicated code with handlers and classes. So many Introduction to Computer Science classes avoid that altogether and teach students C++ using just command-line text-based program.

Using the WinBGI graphics library is a good middle ground between just teaching students only text-based program (which many see as boring), and trying to teach first-years students how to write full Windows applications. Using this WinBGI system, in order to draw a line on the screen, students just need to know these two lines:
```
#include "graphics.h"
line(20, 20, 100, 80);
```
This allows students to focus on learning coding, rather than having to figure out a whole modern GUI system. For example, here's a nested loop that draws boxes on the screen. It's easy to visualize how the nested loop works when it's graphically visible:
```
for (x = 300; x <= 500; x += 50) {
	for (y = 250; y <= 550; y += 50) {
		fillellipse(x, y, 15, 15);
		delay(100);
	}
}
```

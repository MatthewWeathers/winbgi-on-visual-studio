# winbgi-on-visual-studio
Some resources for using the WinBGI graphics library with Visual Studio 2022. Specifically, these are resources for teaching an Intro to Computer Science C++ course at the college level.

## About WinBGI / WinBGIm
Here's a description from the official website at the University of Colorado (https://home.cs.colorado.edu/~main/bgi/install.html)
>WinBGIm is a Windows C++ graphics library based on the classic Borland Graphics Interface (originally distributed with Borland’s Turbo Pascal and later with their Turbo C compilers). In addition to the original BGI interface, WinBGIm also provides programmer support for accessing the mouse and for using the graphics window as a C++ ostream.

This was originally developed around 2008, but it still works with a modern IDE like Visual Studio 2022.

Although this library is too outdated to use for a production environment, it provides an easy way for first-year students to use graphics in their C++ programs. These resources in this repository focus on the educational environment.

## Resources Included
A good place to start would be with this ZIP file: [ExampleGraphics.zip](https://github.com/MatthewWeathers/winbgi-on-visual-studio/ExampleGraphics.zip) (449 K). Or try this working program, which shows an animated circle bouncing around the screen: [BouncingCircle.zip](https://github.com/MatthewWeathers/winbgi-on-visual-studio/BouncingCircle.zip) (448 K)

That file includes a complete Microsoft Visual Studio 2022 project folder with sample code and the necessary library files. The sample code shows examples of common graphics functions. This one ZIP file contains everything you need to make your own graphics programs.

For teachers who use the Canvas LMS (Learning Management System): you can import this IMSCC file, which includes lots of example code for students, labs, and assignments which you could use to teach a semester-long Intro to C++ Programming class:

[template-intro-to-computer-science-csci105-tm-export.imscc](https://github.com/MatthewWeathers/winbgi-on-visual-studio/template-intro-to-computer-science-csci105-tm-export.imscc) (10.8 MB)

Note: if you don't use Canvas, you could still download this file, change the file extension from .imscc to .zip, unzip it, and find some of the code examples in the compressed folder.

Canvas

## Rationale - Why use an old library?
In the context of education, we want students to be able to create C++ programs that have graphics with minimal effort, right from the beginning. The "empty" Windows Application template in Visual Studio has 170+ lines of complicated code with handlers and classes. So many Introduction to Computer Science classes avoid that altogether and teach students C++ using just command-line text-based program.

Using the WinBGI graphics library is a good middle ground between just teaching students only text-based program (which many see as boring), and trying to teach first-years students how to write full Windows applications. Using this WinBGI system, in order to draw a line on the screen, students just need to use these three lines:
```
#include "graphics.h"

initwindow(800, 600);
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
This is in contrast to what code looks like for the template Winodws Application code. Here are the first few lines:
```
#include "framework.h"
#include "WindowsProject1.h"

#define MAX_LOADSTRING 100

// Global Variables:
HINSTANCE hInst;                                // current instance
WCHAR szTitle[MAX_LOADSTRING];                  // The title bar text
WCHAR szWindowClass[MAX_LOADSTRING];            // the main window class name

// Forward declarations of functions included in this code module:
ATOM                MyRegisterClass(HINSTANCE hInstance);
BOOL                InitInstance(HINSTANCE, int);
LRESULT CALLBACK    WndProc(HWND, UINT, WPARAM, LPARAM);
INT_PTR CALLBACK    About(HWND, UINT, WPARAM, LPARAM);

int APIENTRY wWinMain(_In_ HINSTANCE hInstance,
                     _In_opt_ HINSTANCE hPrevInstance,
                     _In_ LPWSTR    lpCmdLine,
                     _In_ int       nCmdShow)
```
I think that would intimidate any first-year student trying to learn to program!

Using this library allows teachers to focus on teaching the basics C++ at the beginning, in a way that is visually interesting without having to include complicated details about the user interface.


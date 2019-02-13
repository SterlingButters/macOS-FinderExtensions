# macOS-FinderExtensions

## About
The purpose of this project is to create a repository of resources for creating
Finder extensions for unexisting functionality. Common examples or integrations
of this include the invocation of a Terminal in the current directory, toggling
hidden files, connecting to remote servers, etc. The beauty of the implementation
discussed below is that there are actually very few limitations. The question you
might be currently asking is why not just get 3rd party application like Forklift
or Pathfinder? Well, I hope I speak for more than just myself when I say that not
everyone likes the introduction of a system redundancy i.e. why should I have two
applications that can do 90% of the same tasks. If you could remove the Finder
application and replace it with one of the 3rd party ones mentioned above then I
probably wouldn't have created this project. On another note, I like the idea of
"hackable" systems as the Atom text editor advertises itself. This introduces the
ability to customize your filesystem browser in a way you might not have thought
of before, you learn some cool stuff, AND... its free!

### Instructions:
1) As you may or may not know, Finder has the ability to insert applications
(even files!) into the toolbar menu by holding command (⌘) and dragging the file
into the toolbar (See figure). With this functionality, we can create .app(s)
using the native macOS Automator application to create workflows that we insert
directly into the tool menu. This repo will provide some sample `.app`(s) that
can be opened and edited with Automator to gain insight into a normal workflow
for an Application.

![alt text](https://github.com/SterlingButters/macOS-FinderExtensions/blob/master/Figures/View.png)
![alt text](https://github.com/SterlingButters/macOS-FinderExtensions/blob/master/Figures/CustomizeToolbar.png)

2) For some, styling may not matter, in fact, you may find that you like the
colorful look of the other icons such as those that normally represent everyday
applications. However, for others, it may be preferred to have a look and feel
that isn't so disruptive. This is where step 2 comes in. Once the .app is made
with Automator, we have an application that looks something like you see in the
next figure (notice the obnoxious Automator icon). What we can do now is create
a custom icon using several tools and some files stored in this repo. First, the
Pixelmator Pro Template file will provide a layer containing a menu button that
has almost the exact look of its counterparts. After that, you are free to add
as many extra layers as you'd like and export the image as a `.png`. Once, the
`.png` has been exported, I personally use Image2Icon to convert the `.png` to
a `.icns` file (macOS's default icon filetype). Once, that's done, you can simply
`Get Info` from the context menu by right-clicking the application and click and
drag the `.icns` file to the picture in the `Get Info` window as seen in the figure.
![alt text](https://github.com/SterlingButters/macOS-FinderExtensions/blob/master/Figures/GetInfo.png)

3) Finally, you can store all of your little workflows in a distant directory or
hide it with `chflags hidden <.app(s) directory>` and command+click-and-drag any
number of them to the the toolbar menu in Finder.

### Some ideas (some featured):
- chflags hidden
- hide files
- anything in /usr/local/bin or aliases
- MCNP, Serpent, OpenMC, Moose(make directory)
- Jupyter
- Open terminal here
- Get permissions (hmmm)
- start server
- compare diff
- git {push - pull}
- mounting drives

### Resources
- [Mac Scripting](https://developer.apple.com/library/archive/documentation/LanguagesUtilities/Conceptual/MacAutomationScriptingGuide/DisplayProgress.html#//apple_ref/doc/uid/TP40016239-CH37-SW1)

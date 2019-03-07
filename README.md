# Pi-Down2BareMetal

This is a simple place to put some code that I write for use on bare metal on BCM2835/2836/2837 based Single Board computers.

This will be focused on BCM2837 based devices with 1GB of RAM such as the RPi 3B+/3B

## Some History:

I had began writing an OS for the RPi BCM2835 based computers back in 2012, and got a lot of the basics completed, then I chose to let that code sit for a few years until 2018 when I began working on it again, and got near to a complete Operating System with a lot of the features I wanted it to have.  I even got it BCM2837 native with SMP.    Then comes the electric power issues of March-05-2018, the loss of my primary SD cards on 3 RPi systems as well as a Flash drive, I lost my work in progress not having a recent enough backup.

Thankfully I have made many notes on paper (though no source hard copy, my error), and can start over from scratch.  This time I will be doing single steps through and putting them here, for the world to potentially benifit from.   This time also I intend to use the GNU AS assembler for my code so those people that do not use RISC OS can still assemble and link the code (just need to be running on an ARM).

## Orginization of This Repository:
The projects will be in numbered and named subdirectories, in the order they are written.  To build the resulting OS up to the current state of play you will need all directories.   If you just want to use one feature there will be a build script in each to allow building a system that contains only the functionality of that section (relying only on what is absolutely needed from previous ones).

### The Future RoadMap (always subject to change), an SWI based API for many functions will be present from step 2 on:

NOTE:  The first 20 steps are just the getting the ground work built before it moves into a proper Operating System development project.  Hence why I call this project just some play RPi BareMetal Projects.  After step 20 there will be another Repo started for proper OS development, the OS that will be worked towards will likely be somewhat familiar to some people :) .

Step 21 is about getting enough of an environment to really develop the Operating system.

TODO: **01-FlashLED** : Flash an LED on the RPi 3B+, will be used to report errors until FrameBuffer is tested.

TODO: **02-FBGFX** : FrameBuffer Graphics Functions.

TODO: **03-MultiCoreInit** : Setup other cores, just putting them to sleep for now.  Include code to start threads on the other cores.

TODO: **04-MMUSetup** : Create a pagetable and setup the MMU with a single level pagetable.

TODO: **05-BitmapFont** : Add suport for Bitmap fonts to the FrameBuffer graphics.

TODO: **06-DMAGFX** : Add DMA support to the FrameBuffer Graphics, to increase speed.

TODO: **07-EMMC-FAT** : Add support for Reading files from the fat boot partition of the SD-Card.

TODO: **08-MiniUSB** : Implement a minimal USB stack, and use it to implement HID Class drivers for Mouse and Keyboard.

TODO: **09-AppLoad** : Bring the ability to load an application from the SD-Card and use the MMU to map it to 0x8000 then begin execution of the application.

TODO: **10-SplitKern** : Bringing support for loadable, protected, extensions, and pairing the kernel down to an almost MicroKernel.  This one also brings in support for Loadable Device Drivers and Loadable File Systems.

TODO: **11-VidoeCoreIV-Initial** : Put a few triangles on the screen using the VideoCoreIV graphics Processor.

TODO: **12-VideoCoreIV-Step2** : Add a good amount more to the VideoCoreIV accelerated graphics support.

TODO: **13-VideoCoreIV-Step3** : Round out the VideoCoreIV support to be fully usable, even if not complete.

TODO: **14-MTask** : Add a simple multitasking schedular and task switcher, that provides good seperation of priorities as well as somewhat balanced task alocation accross the 4 cores.

TODO: **15-MoreUSB** : Formalize the USB stack API, and add class drivers for Mass Storage devices and the on-board ethernet adaptor.

TODO: **16-TCP/IP** : Add a simple TCP/IP stack.

TODO: **17-Vector Fonts** : Implement a simple vector font engine, not based on anything before.

TODO: **18-WindowingSystem** : Implement a simple graphical Window Icon Menu Pointer system on top of the existing graphics and font engines.

TODO: **19-Desktop** : Implement a desktop environment and file manager ontop of the GUI/Windowing System.

TODO: **20-Command** : Implement a command interpreter, so we can run command line tools.

TODO: **21-Tools** : Implement and or port the tools needed for continued development on the new system.  This is kind of a big one.  This includes text editors, bitmapped graphics editors, assembler, linker, C Compiler, Debuging tools, misc command line tools, Resource Editor, and much more.

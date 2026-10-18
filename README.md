# GNU nano 9.2 (Windows MinGW-w64 Port)
Miracle of miracles, I actually built something from source that compiles, runs, and doesn't immediately crash or set the computer on fire. Grab the holy water and update your resumes, because history is being made right here.

# What is this?
This is a native, standalone Windows port of GNU nano 9.2, built using MSYS2 and MinGW-w64. That means you can run a proper terminal text editor directly in Windows without needing a full Linux subsystem running in the background. Type nano filename.txt, write code or edit configs, and save it like a normal human being.

# Why does it exist?
Because I stared at cross-compilation errors, missing dependencies (makeinfo, anyone?), broken pointer casts, and incompatible _stat64 structs until the code simply gave up and worked out of sheer exhaustion.

# How to Run It
Since this is a portable Windows build, nano.exe needs its bodyguards to function outside of MSYS2. To use it:

Drop nano.exe into a folder.

Toss the required DLLs right beside it:

libintl-8.dll

libncursesw6.dll

libiconv-2.dll

libwinpthread-1.dll

libcharset-1.dll

Add that folder to your Windows PATH environment variable so you can launch it from anywhere.

(Warning: You might still see a brief red startup error about a missing nanorc path because the binary was originally born in an MSYS2 ecosystem. Just ignore it, or pretend it's a feature letting you know nano is alive and judging your file paths.)

Wait... Might? Sorry, I meant it WILL show up. Soon I will try to fix it.

# Building from Source
If you want to try compiling it yourself and reliving Julian's descent into madness:

Fire up MSYS2 MinGW-w64.

Install your dependencies (pacman -S make gcc ncurses-devel gettext-devel texinfo).

Patch up browser.c and files.c when the compiler inevitably yells at you.

Run ./configure and make.

Enjoy the only known software artifact of its kind that actually functions.

# Just so you know
If you want it to work, you will need to put nano.exe in path, then you can use it normally by typing "nano filename.txt".

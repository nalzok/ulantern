.. _windows-msys2:

Installing MSYS2
================


.. note::

    This part is largely based on `Johannes Peter's tutorial for installing clang on Windows`_.

.. _Johannes Peter's tutorial for installing clang on Windows: http://blog.johannesmp.com/2015/09/01/installing-clang-on-windows-pt1/

The building of Lantern requires some tools which aren't shipped with Windows, such as a C compiler [#f1]_, Git, GNU Make, and Nodejs. Thus, equipping ourselves with these tools is the first thing to do.

Setting up a GNU toolchain on Windows is inherently unnatural and troublesome. Usually people use MinGW or Cygwin for this purpose, and I tried them, but failed. Finally, I found Mr. Johannes' great tutorial on Stack Overflow, and it smoothly solves this issue. As a bonus, his tutorial also prepares two fully working C++ compilers for you, which means you no longer need to take the pain of installing them in case you need them later.

Mr. Johannes provides two different approaches in his tutorial, one utilizes MinGW-w64 while the other relies on the less famous MSYS2. Since I personally prefer Linux's bash over Windows' cmd, I'll go with approach 2 in my tutorial.



Download and install MSYS2
--------------------------

#. Download and run the MSYS2 installer from the `offical website`_. Currently, the latest release is msys2-x86_64-20161025.exe_\ (warning: direct download).

   .. _offical website: http://www.msys2.org/
   .. _msys2-x86_64-20161025.exe: http://repo.msys2.org/distrib/x86_64/msys2-x86_64-20161025.exe

#. Launch the MSYS2 shell, either by using the "Run MSYS2 now" shortcut in the MSYS2 Setup Wizard, or by running ``C:\msys64\msys2_shell.cmd``.

   #. Update the core packages with::

          pacman --needed -Sy bash pacman pacman-mirrors msys2-runtime

      Type ``y`` when prompted to confirm.

   #. Re-launch the MSYS2 shell.

   #. Update all packages with::
         
          pacman -Su

   #. Install the 32 bit version of MinGW-w64 and Clang (currently gcc is version 7.1.0 and clang is version 4.0.0)::

          pacman -S mingw-w64-x86_64-clang mingw-w64-i686-clang

   #. Now you can close the MYYS2 shell.


Install Prerequisites
---------------------


#. Launch the MinGW64 shell, which you can find at ``C:\msys64\mingw64.exe``.
          
#. Install Git, GNU Make, Nodejs(which now includes NPM)::

       pacman -S git make mingw-w64-x86_64-nodejs

#. Install Gulp::

       npm i gulp-cli -g

#. Go to the next step, :ref:`windows-go`.


.. rubric:: Footnotes

.. [#f1] While the document says `a C compiler is optional`_, I just can't build Go without having one for some reason, even if ``CGO_ENABLED=0`` is set. Anyway, C/C++ compilers are useful, so I think it makes sense to install them now. At the very least, this is for future use.

.. _a C compiler is optional: https://golang.org/doc/install/source#ccompiler


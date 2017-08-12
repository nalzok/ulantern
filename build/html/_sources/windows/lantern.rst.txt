.. _windows-lantern:

Building Lantern
================

Now that all prerequisites have been met, we can start to build Lantern!


Fetch the Lantern repository
----------------------------

#. Launch a MinGW64 shell, which you can find at ``C:\msys64\mingw64.exe``, if you haven't yet.

   
#. Change directory to the ``Lantern`` directory::

       cd $HOME/Lantern


#. Download the Lantern repository from Github.com::

       git clone https://github.com/getlantern/lantern.git


Build Lantern
-------------

#. Change directory to ``lantern``::

       cd lantern


#. Build lantern::

       HEADLESS=true make clean-desktop lantern

   .. note::

      The standard way of building Lantern is ``make clean-desktop lantern`` without the preceding ``HEADLESS=true``. However, after doing this, I got a error::
      
          panic: Failed to load C:\Users\user0\AppData\Roaming\systray\systray.dll: %1 is not a valid Win32 application.
      
      I suspect this to be a Lantern's bug, which I cannot fix without modifying the source code, so I had to use this workaround. Lantern built with the ``HEADLESS`` flag won't be able to place its icon in the notification area, but would function normally except this.
      
   .. note::

      If you run ``make clean-desktop windows`` instead of ``HEADLESS=true make lantern``, the resulting executable file (it's named ``lantern_windows_386.exe`` instead of ``lantern``) would be presumably runable even on 32-bit Windws systems.


#. Copy the generated executable file to your desktop::
   
      cp lantern /c/User/user0/Desktop/lantern.exe

   .. note::

      If you did ``make clean-desktop windows``, run the following command instead::

          cp lantern_windows_386.exe /c/User/user0/Desktop/lantern.exe


#. Now you can find the ``lantern.exe`` on your desktop. Run it and profit!


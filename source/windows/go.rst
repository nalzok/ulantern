.. _windows-go:

Building a custom fork of Go
============================


.. note::

    For your reference, here is the relevant offical document: `Installing Go from source`_.

.. _Installing Go from source: https://golang.org/doc/install/source

Lantern requires a `custom fork of Go`, which doesn't provide pre-built binary files, so we'll have to compile it by ourselves.

.. _custom fork of Go: https://github.com/getlantern/go


Install Go compiler binaries
----------------------------

The Go tool chain is written in Go. To build it, you need a Go compiler installed.


#. Launch a MinGW64 shell, which you can find at ``C:\msys64\mingw64.exe``, if you haven't yet.

#. Change the current directory to your home directory::

       cd $HOME

#. According to the offical document, you can use a binary release as a bootstrap tool chain, see the `downloads page`_. However, the link seems to be blocked, so let's build the bootstrap tool chain from source instead.

   .. _downloads page: https://golang.org/dl/

   #. First, download the source by::

          wget https://storage.googleapis.com/golang/go1.4-bootstrap-20170531.tar.gz

      And a compressed file of 10.79 MB will be downloaded.

      .. note::

         If the download fails, try the following command::

             wget http://ulantern.readthedocs.io/en/latest/_downloads/go1.4-bootstrap-20170531.tar.gz
          

   #. Next, unpack it. This is going to take several seconds::

          mkdir Go1.4/ && tar -zxvf go1.4-bootstrap-20170531.tar.gz -C Go1.4/ --strip-components=1

   #. Finally, ``cd`` to the ``src`` subdirectory and run ``make.bat``. This would take a while::

          cd Go1.4/src/
          ./make.bat 


#. Now it's return to the home directory::

       cd $HOME

#. (Optional) Now you can delete the compressed file, if you want::

       rm go1.4-bootstrap-20170531.tar.gz 


Fetch the Go repository
-----------------------

#. Create a directory named ``Lantern``. It will be containing the repository (i.e. source code) of Go and Lantern::

       mkdir Lantern

#. Change directory to ``Lantern``::

       cd Lantern

#. Download the custom fork of Go from Github::

       git clone https://github.com/getlantern/go.git
       cd go
       git checkout lantern

   .. note::

      When you see a multi-line line code block, run the command on each line one aftr one.


Install Go
----------

#. Build the Go distribution::

       cd src
       ./all.bat

   ``all.bat`` would also run some tests after building Go. If you wish to skip the tests, run the following commands instead::

       cd src
       ./make.bat

#. Then, add the ``bin`` directory to ``$PATH``::

       echo "# getlantern/go" >> ~/.bashrc
       echo "export GOROOT=$HOME/Lantern/go" >> ~/.bashrc
       echo "export PATH=$PATH:$GOROOT/bin" >> ~/.bashrc
       source ~/.bashrc


#. Go to the final step, :ref:`windows-lantern`.


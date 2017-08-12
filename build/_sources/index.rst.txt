.. ulantern documentation master file, created by
   sphinx-quickstart on Fri Aug 11 08:40:35 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.

Welcome to Ulantern's documentation!
====================================


"Ulantern" stands for "Unlimited Lantern", referencing ``/dev/urandom`` for ``/dev/random`` on Unix-like operating systems. Lantern_ is a handy tool developed by Google, which gives people access to websites blocked in mainland China, such as Google, Youtube, Twitter and Facebook.

.. _Lantern: https://github.com/getlantern/lantern

However, Lantern has a drawback: there is a bandwidth limitation of 500MB per month, and the connection would be (greatly) slowed down once the limit is reached. If one require unlimited connection, they'll have to upgrade to Lantern Pro, which costs $32 (USD) for one year, or $48 (USD) for two years.

While it is always encouraged to buy lantern Pro in support of this awesome project, there exists another option: building it from source. Yes, for whatever reasons, they are charging for an open-source project! Anyway, the built-from-source version of Lantern doesn't have a data bandwidth limit, and that's all that matters. Unfortunately, building Lantern from scratch isn't trivial at all, especially on Windows. Ulantern to the rescue! Basically, Ulantern is a readme-only project which guides you to build Lantern from source in a step-by-step fashion.

Please note that this tutorial will be providing "workarounds" rather than "solutions". This is both due to my lack of expertise, and the fact that Lantern's repository is no longer actively maintained, which means its bugs will probably never be fixed.


.. attention::
  The tutorial is provided "as is", without warranty of any kind, express or implied, including but not limited to the warranties of merchantability, fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability, whether in an action of contract, tort or otherwise, arising from, out of or in connection with the tutorial or the use or other dealings in the tutorial. 


.. toctree::
   :maxdepth: 2
   :caption: Contents:

   windows
   macos
   linux


Indices and tables
==================

* :ref:`genindex`
* :ref:`search`

.. HoloViews documentation master file

.. raw:: html
  :file: latest_news.html

Introduction
____________

**Composable, declarative data structures for building even complex visualizations easily.**


..
   # Code used to generate mandelbrot.npy, for reference
   from numpy import *
   import pylab

   def mandelbrot( h,w, maxit=200 ):
           y,x = ogrid[ -1.4:1.4:h*1j, -2:0.8:w*1j ]
           c = x+y*1j
           z = c
           divtime = maxit + zeros(z.shape, dtype=int)
           for i in xrange(maxit):
                   z  = z**2 + c
                   diverge = z*conj(z) > 2**2
                   div_now = diverge & (divtime==maxit)
                   divtime[div_now] = i
                   z[diverge] = 2
           return divtime
   # Wait a long time..., then normalize
   arr = mandelbrot(4000,4000, maxit=2000)[400:800, 2500:2900]


..

.. notebook:: holoviews Homepage.ipynb

------------

Installation
____________

HoloViews is compatible with Python `2.7, 3.3, and 3.4 <https://travis-ci.org/ioam/holoviews>`_.

HoloViews requires `Param <http://ioam.github.com/param/>`_ and
`Numpy <http://numpy.org>`_, neither of which has any required dependencies,
and so it should be very easy to integrate HoloViews into your
workflow or as part of another project.

For plotting, HoloViews uses `Matplotlib <http://http://matplotlib.org/>`_,
which most scientists and engineers using Python will already have
installed.  HoloViews is pure Python, but it also provides optional
extensions enabled with ``%load_ext`` above that make it integrate
well with `IPython Notebook <http://ipython.org/notebook/>`_ 2 and 3.

Matplotlib and IPython Notebook can be installed using your operating
system's package manager, using a scientific Python distribution like
`Anaconda <http://continuum.io/downloads>`_ (particularly useful on
systems shipped without pip, such as Windows or Mac), or by using pip::

  pip install matplotlib 'ipython[notebook]'

You can then obtain the latest
public release of HoloViews using pip::

  pip install holoviews

Or you can get the latest development version by cloning our git
repository::

  git clone git://github.com/ioam/param.git
  git clone git://github.com/ioam/holoviews.git

Then launch IPython Notebook::

  ipython notebook

Now you can download the
`tutorial notebooks <Tutorials/notebook-1.0.0.zip>`_,
unzip them somewhere IPython Notebook can find them, and then open the
Homepage.ipynb tutorial or any of the others in the Notebook.  Enjoy
exploring your data!



|BuildStatus|_

------------

Contributors
____________

HoloViews was developed by `Jean-Luc R. Stevens <https://github.com/jlstevens>`_
and `Philipp Rudiger <https://github.com/philippjfr>`_,
in collaboration with `James A. Bednar <http://homepages.inf.ed.ac.uk/jbednar>`_.

HoloViews is completely `open source
<https://github.com/ioam/holoviews>`_, available under a BSD license
freely for both commercial and non-commercial use.  HoloViews is 
designed to be easily extensible, and contributions from
users are welcome and encouraged.  In particular, HoloViews components
can be combined in an infinite number of ways, and although the
tutorials are tested continuously, it is impossible
for us to test all other conceivable combinations.  Thus we welcome `bug
reports and feature requests <https://github.com/ioam/holoviews/issues>`_, 
particularly if they come with test cases showing how to reproduce the bugs and 
`pull requests <http://yangsu.github.io/pull-request-tutorial/>`_
showing how to fix the bug or implement the feature!

.. |BuildStatus| image:: https://travis-ci.org/ioam/holoviews.svg?branch=master
.. _BuildStatus: https://travis-ci.org/ioam/holoviews

.. toctree::
   :titlesonly:
   :hidden:
   :maxdepth: 2

   Home <self>
   Features <features>
   Tutorials <Tutorials/index>
   Reference Manual <Reference_Manual/index>
   FAQ
   Github source <http://github.com/ioam/holoviews>

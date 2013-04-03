Gaston: Julia plotting using gnuplot
==================================== 

Gaston provides an interface to plot using gnuplot.

Installation
------------

Gaston requires gnuplot to be installed in your system. It has been tested
with version 4.6

To install Gaston, run

    julia> Pkg.add("Gaston")

Then, load the module:

    julia> using Gaston

Documentation
-------------

To build the PDF documentation, cd into the doc/ subdirectory and type
'make help'. You can download the pre-build documentation from
https://bitbucket.org/mbaz/gaston/downloads

A note on OSX
-------------

Recent versions of OSX removed support for the aqua terminal from gnuplot.
Before attempting to use aqua in Gaston, open a terminal and run this
command:

    gnuplot -e "set term" | grep aqua

If nothing is printed, then you do not have support for the aqua terminal and
should not attempt to use it in Gaston. By default, Gaston uses the wxt
terminal. You can verify if your version of gnuplot supports it by issuing

    gnuplot -e "set term" | grep wxt

Again, if no output is printed, your gnuplot does not support wxt. In this
case, you need to run this command before any other Gaston command:

    set_terminal("x11")

x11 is a fallback terminal with less bells and whistles than wxt or aqua.

If you want to save your plots to a file, please see [this discussion first](https://github.com/mbaz/Gaston.jl/issues/4).

Demo
----

Gaston includes a demo that showcases its current capabilities:

    julia> gaston_demo()

This function is defined in Gaston/src/gaston\_demo.jl.

Tests
-----

Gaston includes many tests, wich you can run to make sure your installation is
working properly. To run the tests, do

    julia> gaston_tests()

All tests should pass.

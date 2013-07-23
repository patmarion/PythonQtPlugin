ParaView PythonQt Plugin
------------------------

The PythonQt plugin makes the Qt API available to users
from the ParaView Python console.  The plugin uses the PythonQt library.
The PythonQt homepage is pythonqt.sourceforge.net

Note, PythonQt is different from PyQt4, it is a separate project
and uses a different technique to generate Qt bindings.


Build Instructions
------------------

To satisfy the PythonQt dependency, first build and install the PythonQt
library and headers.  I recommend using the PythonQt fork maintained by
the commontk project.  Commits from the commontk fork are migrated upstream
to PythonQt on sourceforge.  To clone PythonQt using git:

    git clone https://github.com/commontk/PythonQt

Create a build directory and then configure with CMake:

    mkdir build
    cd build
    cmake ../PythonQt

When configuring PythonQt, my recommended settings are:

    BUILD_SHARED_LIBS=ON
    PythonQt_Wrap_Qtcore=ON
    PythonQt_Wrap_Qtgui=ON
    PythonQt_Wrap_Qtuitools=ON

When configuring this PythonQt plugin for ParaView, CMake will look for the
installed PythonQt library and headers.  Set PYTHONQT_LIBRARY to the installed
library, and set PYTHONQT_INCLUDE_DIR to the installed header directory that
contains PythonQt.h.


Testing the Plugin
------------------

After loading the PythonQt plugin in ParaView, you can try out the functions
defined by demo.py.

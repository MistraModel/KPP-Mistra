******************************************************************************

__KPP__ - The Kinetic PreProcessor

Builds simulation code for chemical kinetic systems (for version, see
`src/gdata.h`).

Copyright (C) 1995-1997 Valeriu Damian and Adrian Sandu, CGRER, Univ. Iowa (USA).

Copyright (C) 1997-2016 Adrian Sandu, Michigan Tech. & Virginia Tech. (USA), with contributions from Rolf Sander, Max-Planck Institute for
Chemistry, Mainz (Germany).

KPP is free software; you can redistribute it and/or modify it under the
terms of the GNU General Public License as published by the Free
Software Foundation (http://www.gnu.org/copyleft/gpl.html); either
version 2 of the License, or (at your option) any later version.

KPP is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or
FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License
for more details.

A copy of the GNU General Public License could be found below; you
could also consult http://www.gnu.org/copyleft/gpl.html or write to the
Free Software Foundation, Inc., 59 Temple Place - Suite 330, Boston, MA
02111-1307, USA.

Adrian Sandu
Computer Science Department
Virginia Polytechnic Institute and State University
Blacksburg, VA 24060
E-mail: sandu@cs.vt.edu

******************************************************************************

__KPP__ is a symbolic chemistry Kinetics PreProcessor, developed by
V. Damian and A. Sandu with contribution by R. Sander
(http://www.cs.vt.edu/~asandu/Software/Kpp).

__KPP-Mistra__ is a custom version of KPP for the Mistra model
(https://github.com/MistraModel/Mistra). It was developed starting
from KPP v2.2.3 and includes all the bugfixes and modifications by
R. Sander and J. Bock (https://bitbucket.org/gcst/kpp), plus some
additional modifications specific to Mistra by J. Bock. See
`CHANGELOG.md` for a summary of the changes.

The stable version of KPP-Mistra can be downloaded here:
https://github.com/MistraModel/KPP-Mistra/releases.

******************************************************************************

__To get started with KPP:__  Read user's manual (`doc/kpp_UserManual.pdf`)


__To install KPP:__

1. Make sure that FLEX (public domain lexical analizer) is installed on your machine.
   Type `flex --version` to test this.

2. Note down the exact path name where the FLEX library is installed.
   The library is called: `libfl.a` or `libfl.sh`

3. Make sure that BISON is installed on your machine. Type `bison --version` to test this.

4. Define the `KPP_HOME` environment variable to point to the complete
   path location of KPP. If, for example, KPP is installed in `$HOME/kpp`:

  - with C shell (or tcsh) edit the file .cshrc (or .tcshrc) in your home directory and add:

    ```shell
    setenv KPP_HOME $HOME/kpp
    set path=( $path $HOME/kpp/bin )
    ```

  - with bash shell edit the file .bashrc in your home directory and add:

    ```shell
    export KPP_HOME=$HOME/kpp
    export PATH=${PATH}:$HOME/kpp/bin
    ```

   - Execute `source ~/.cshrc` (or `.tcshrc`, or `.bashrc`) to make sure these
     changes are in effect.

5. In the `KPP_HOME` directory edit: `Makefile.defs` and follow the
   instructions included to specify the compiler, the location of the
   FLEX library, etc...

6. In the `KPP_HOME` directory build the sources using:
   `make`

******************************************************************************

__To clean the KPP installation:__

1. Delete the KPP object files with: `make clean`

2. Delete the whole distribution (including the KPP binaries) with: `make distclean`

******************************************************************************


If you have any problems please send the detailed error report and the machine
environment to:

sandu@cs.vt.edu

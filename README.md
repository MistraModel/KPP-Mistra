__KPP__ - The Kinetic PreProcessor

Builds simulation code for chemical kinetic systems (for version
number, see the `KPP_VERSION` variable in [src/gdata.h](./src/gdata.h)).

Copyright (C) 1995-1997 Valeriu Damian and Adrian Sandu, CGRER, Univ. Iowa (USA).

Copyright (C) 1997-2016 Adrian Sandu, Michigan Tech. & Virginia Tech. (USA),
with contributions from Rolf Sander, Max-Planck Institute for Chemistry, Mainz (Germany).

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
Blacksburg, VA 24060, USA  
E-mail: sandu@cs.vt.edu

******************************************************************************

__KPP__ is a symbolic chemistry Kinetics PreProcessor, developed by V. Damian and A. Sandu,
with the contribution of R. Sander. The KPP website is: https://people.cs.vt.edu/~asandu/Software/Kpp/.

__KPP-Mistra__ is a custom version of KPP for the [Mistra model](https://github.com/MistraModel/Mistra).
It was developed from KPP v2.2.3 and includes all the bugfixes and modifications made by
R. Sander and J. Bock (https://bitbucket.org/gcst/kpp), plus additional modifications
specific to Mistra made by J. Bock.

See the [changelog](./CHANGELOG.md) file for a summary of the changes.

The stable version of __KPP-Mistra__ to be used with the Mistra model
can be downloaded from the [releases page](https://github.com/MistraModel/KPP-Mistra/releases).

******************************************************************************

__To get started with KPP-Mistra:__  Read the [user's manual](./doc/kpp_UserManual.pdf).

__To install KPP-Mistra:__

1. Make sure that FLEX (open-source lexical analizer) is installed on your machine.
   Type `flex --version` to test this.

2. Note down the exact path name where the FLEX library is installed.
   The library is called: `libfl.a` or `libfl.sh`.

3. Make sure that BISON (open-source parser generator) is installed on your machine.
   Type `bison --version` to test this.

4. Define the `KPP_HOME` environment variable to point to the complete
   path location of KPP-Mistra. If, for example, KPP-Mistra is installed in `$HOME/KPP-Mistra`:

  - with __C shell__ (or __tcsh__) edit the file `.cshrc` (or `.tcshrc`) in your home directory and add:
    ```shell
    setenv KPP_HOME $HOME/KPP-Mistra
    set path=( $path $KPP_HOME/bin )
    ```

  - with __bash__ shell edit the file `.bashrc` in your home directory and add:
    ```shell
    export KPP_HOME=$HOME/KPP-Mistra
    export PATH=${PATH}:$KPP_HOME/bin
    ```

   - Execute `source ~/.cshrc` (or `.tcshrc`, or `.bashrc`) to make sure these
     changes are in effect.

5. In the `KPP_HOME` directory edit: `Makefile.defs` and follow the
   instructions included to specify the compiler, the location of the
   FLEX library, etc...

6. In the `KPP_HOME` directory build the source files using:  
   `make`

******************************************************************************

__To clean the KPP installation:__

1. Delete the KPP object files with:  
   `make clean`

2. Delete the whole distribution (including the KPP binaries) with:  
   `make distclean`

******************************************************************************

To acknowledge and cite KPP, please see instructions and references on the
[KPP website](https://people.cs.vt.edu/~asandu/Software/Kpp/).

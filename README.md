# KPP-Mistra

******************************************************************************

## KPP

__KPP__ is a symbolic chemistry Kinetics PreProcessor, developed by
V. Damian and A. Sandu, with the contribution of R. Sander. KPP builds
simulation code for chemical kinetic systems. For more information, go
to the [KPP website](https://people.cs.vt.edu/~asandu/Software/Kpp/).

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

### Reference

V. Damian, A. Sandu, M. Damian, F. Potra, G.R. Carmichael: "The
Kinetic PreProcessor KPP -- A Software Environment for Solving
Chemical Kinetics", Computers and Chemical Engineering, 26, 11,
1567-1579, 2002 [[link](https://doi.org/10.1016/S0098-1354(02)00128-X)].

******************************************************************************

## KPP-Mistra

__KPP-Mistra__ is a custom version of KPP for the
[Mistra model](https://github.com/MistraModel/Mistra).

KPP-Mistra was developed from KPP v2.2.3 and includes all the
bugfixes and modifications made by R. Sander and J. Bock (see the
`f77` and `mistra` branches at: https://bitbucket.org/gcst/kpp),
plus additional modifications specific to Mistra made by
J. Bock. A summary of the changes can be found in the
[changelog](./CHANGELOG.md) file.

The stable version of __KPP-Mistra__, to be used with the Mistra model, can be
downloaded from the [releases page](https://github.com/MistraModel/KPP-Mistra/releases).

### Instructions

__To install KPP-Mistra:__

1. Make sure that FLEX (open-source lexical analizer) is installed using the command:  
   `flex --version`

2. Note down the exact path name where the FLEX library is installed.
   The library is called `libfl.a` or `libfl.so`.

3. Make sure that BISON (open-source parser generator) is installed using the command:  
   `bison --version`

4. Define the `$KPP_HOME` environment variable to point to the path location of KPP-Mistra.
   If, for example, KPP-Mistra is installed in `$HOME/KPP-Mistra`:

  - with __C shell__ (or __tcsh shell__), edit the file `.cshrc` (or `.tcshrc`) in your home
    directory and add:
    ```shell
    setenv KPP_HOME $HOME/KPP-Mistra
    set path=( $path $KPP_HOME/bin )
    ```

  - with __bash__ shell, edit the file `.bashrc` in your home directory and add:
    ```shell
    export KPP_HOME=$HOME/KPP-Mistra
    export PATH=${PATH}:$KPP_HOME/bin
    ```

   - Execute the command `source ~/.cshrc` (or `.tcshrc`, or `.bashrc`) to make sure these
     changes are in effect. Alternatively, close and reopen the terminal.

5. In the `$KPP_HOME` directory edit the file `Makefile.defs` and follow the instructions
   to specify the compiler, the location of the FLEX library, etc...

6. In the `KPP_HOME` directory build the source files using the command:  
   `make`

__To clean the KPP-Mistra installation:__

1. Delete the KPP object files with the command:  
   `make clean`

2. Delete the whole distribution (including the binaries) with the command:  
   `make distclean`

__To get started with KPP-Mistra:__  read the [KPP User's Manual](./doc/kpp_UserManual.pdf).

# KPP-Mistra

KPP-Mistra is a version of the Kinetics PreProcessor (KPP) software customized for the
[Mistra model](https://github.com/MistraModel/Mistra).

KPP-Mistra should only be used in conjunction with the
[Mistra model](https://github.com/MistraModel/Mistra); for any other
application use the [original version](https://people.cs.vt.edu/~asandu/Software/Kpp/)
or check out the GEOS-Chem [community version](https://github.com/KineticPreProcessor/KPP).

******************************************************************************

## KPP

KPP is a symbolic chemistry Kinetics PreProcessor, developed by
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
FITNESS FOR A PARTICULAR PURPOSE. See the GNU General Public License
for more details.

A copy of the GNU General Public License can be found in the `LICENCE`
file; you can also consult http://www.gnu.org/copyleft/gpl.html or
write to the Free Software Foundation, Inc., 59 Temple Place - Suite
330, Boston, MA 02111-1307, USA.

Adrian Sandu  
Computer Science Department  
Virginia Polytechnic Institute and State University  
Blacksburg, VA 24060, USA  
E-mail: sandu@cs.vt.edu

### Reference

V. Damian, A. Sandu, M. Damian, F. Potra, G.R. Carmichael: "The Kinetic
PreProcessor KPP - A Software Environment for Solving Chemical Kinetics",
Computers and Chemical Engineering, 26, 11, 1567-1579, 2002
[[link](https://doi.org/10.1016/S0098-1354(02)00128-X)].

******************************************************************************

## KPP-Mistra

KPP-Mistra was developed from *KPP v2.2.3* and includes all the bugfixes and
modifications made by R. Sander and J. Bock (see the `f77` and `mistra` branches
at: https://bitbucket.org/gcst/kpp), plus additional modifications specific to Mistra
made by J. Bock. A summary of the changes can be found in the `CHANGELOG.md` file.

The stable version of KPP-Mistra can be downloaded from the
[Releases](https://github.com/MistraModel/KPP-Mistra/releases) page.

### Instructions

#### To install KPP-Mistra:

1. Check that FLEX (open-source lexical analizer) is installed using
   the command: `flex --version`.

2. Find the path of the FLEX library (`libfl.a` or `libfl.so`) using
   the command: `locate -b libfl.*`.

3. Check that BISON (open-source parser generator) is installed using
   the command: `bison --version`.

4. Define the `$KPP_HOME` environment variable to point to the path of KPP-Mistra.
   If, for example, KPP-Mistra is installed in `$HOME/KPP-Mistra`:

  - if using the **C** shell (or the **tcsh** shell), add the following to
    `~/.cshrc` (or `~/.tcshrc`):
    ```shell
    setenv KPP_HOME $HOME/KPP-Mistra
    set PATH=( $PATH $KPP_HOME/bin )
    ```

  - if using the **bash** shell, add the following to `~/.bashrc`:
    ```shell
    export KPP_HOME=$HOME/KPP-Mistra
    export PATH=$PATH:$KPP_HOME/bin
    ```

   - Execute the command `source ~/.cshrc` (or `.tcshrc`, or `.bashrc`) to make
     sure that the changes are in effect. Alternatively, close and reopen the terminal.
     The command `echo $KPP_HOME` should return the correct path of KPP-Mistra.

5. In `$KPP_HOME` edit the `Makefile.defs` file. Follow the
   instructions to specify the compiler (by default, the GNU compiler
   `gcc`), the path of the FLEX library, etc...

6. In `KPP_HOME` build the source files using the `make` command. Check that the
   installation has been successful using the command `which kpp`.

#### To clean the KPP-Mistra installation:

1. Delete the KPP object files with the command: `make clean`.

2. Delete the KPP object files and binaries with the command: `make distclean`.

#### To use KPP-Mistra with the Mistra model:

The *KPP User's Manual* can be found in the `doc/` directory.

Please refer to the *Mistra manual* in the `doc/` directory of the
[Mistra repository](https://github.com/MistraModel/Mistra) for further information.

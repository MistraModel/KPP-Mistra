Changes to KPP-2.2.3 required to use with Mistra
------------------------------------------------

Author: Josue Bock (josue.bock@meteo.fr)

1. In main directory:

   1. create `bin/` directory.
   2. edit `Makefile.defs` according to KPP instructions.

2. In `src/` directory:

   1. edit `code_f77.c` and decrease the number of written columns (integer case) from 12 to 11 (or less):
      - `maxCols = 11`.
      - `if (((i+1) % 11 == 0 ...`.
      - comments starting with `!` instead of `C` (optional, unactivated).
   2. `code_f90.c` from Rolf Sander's version.
   3. edit `gdata.h`, increase `MAX_EQN` (5000, or more) and `MAX_SPECIES` (3000, or more).
      After Rolf Sander changes: also increase `MAX_K` (300).
   4. use `scan.l` from Rolf Sander's version (dimensions increased to 300, related to change in `gdata.h` here).
   5. edit `scan.y` and increase the dimension of the character variable `str` from 80 to 300.
   6. correct `gen.c` subroutine `GenerateJacReactantProd : allocate integer arrays instead of a declaration`.

3. In `int/` directory:

1. use corrected version of `int/rosenbrock.f`:
   - `ode_Fun` is not the correct name, replaced by `FunTemplate`.
   - `ode_Jac` is not the correct name, replaced by `JacTemplate`.


4. In `util/` directory:

1. use empty version of `UserRateLaws.f`.

Further changes to KPP-2.2.3 - after Forcheck-ing the code
----------------------------------------------------------

Further changes in `int/rosenbrock.f`:
- remove all calls to subroutine `WCOPY`.
- remove all calls to subroutine `WSCAL`.

Update: 05/03/2017
------------------

- bugfix in `src/code_f77.c`: in `F77_DeclareData`, a bug arise if the number of species (or reactions) is a multiple of `max_lines` corrected by adding `if( min < max )`.
- in the same routine: dynamic column filling, to take 3-5 digits into account, and avoid too long files (and too numerous continuation lines).
- plus cleaning of the whole file, according to compilation messages.
- in `src/gen.c`, little improvement to print correct file extension when running KPP, plus cleaning of this file according to compilation messages.
- in `util/sutil.f`: bugfix in subroutine `KppDecomp`: there was already a test to prevent `JVS(...) == 0`, but there were 2 mistakes:
  - only `nvar` values were tested, not covering the whole `JVS(:)` values.
  - a strict equality (`== 0`) was used, while `abs < tiny` is safer.

UPDATED: April 2019
-------------------

The changes listed above have been applied and documented with pull requests #1-#5 and #9
in the __KPP-Mistra__ repository (https://github.com/MistraModel/KPP-Mistra).

Additional changes by P. Brauer & R. Sommariva:

- Move license file to main directory and delete `gpl/` directory.
- Update and format files `README.md` and `CHANGELOG.md`.
- Delete file `diff_version_rolf_sander.txt`.
- Delete directory `int.modified_WCOPY/` (backup version of `int/?`).

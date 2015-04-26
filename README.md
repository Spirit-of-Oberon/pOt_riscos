pOtSrc

  The complete source code for the archimedes port of pOt.
  Not all the files from the original pot are here, only the
  ones useful on the archimedes.

  The original sources are available by anon ftp at:

    hades.ethz.ch
  
  in /pub/Oberon/NonETHSystems/pOt


Installation

  Drag the pot directory over the pot directory in the binary
  distribution.
  Note that the Cym., h. and mod. subdirectories in lib and
  lib.Core are identical.


Compiling

  You will have to make your own Makefiles. I use !Make to generate
  them, but I have some tools in there that will probably upset your
  !Make, because !Make doesn't like tools it doesn't know about.
  The MakefileU files show which files *really* should be compiled by
  the C compiler. Don't forget to add pOtLand: to your include path
  and to turn off all warnings (there are mainly complaints about unused
  labels and <pOtRTL.n> not being an ANSI C header with Desktop C v4)
  
  The */rsp files in the src subdirectory are input files for pOt.
  I haven't used them, they are probably easiest to use
  from the command line as
  
    pot !*/rsp

  
Note

  In the src subdirectory are three extra Oberon modules and one extra
  C file compared to the original distribution.

  mod.DDEUtils : just some constants.
  mod.Throwback: Throwback support for !pOt. Note the use of SYSTEM.ADR().
                 The obvious way (taking the address of the RECORD) 
                 doesn't work as expected (at least by me).
  mod.CLib     : Shows the way to call a non-Oberon (E.g C) external 
                 function. Oberon doesn't allow underscores in 
                 identifiers. Therefore the C file c._Clib has a wrapper
                 for _kernel_swi.
  c._CLib      : Wrapper for _kernel_swi.

  The file c.POT_Compil has some bits added as well (the stuff after
  #ifdef __riscos).
  

Contacting me

  email: svdwal ¤ xs4all · nl
  snail mail: Sander van der Wal
              Bevrijdingsplein 39
              2321 BX Leiden
              The Netherlands

# Generated automatically from Makefile.in by configure.
##### User configurable options #####
# This is an example Makefile.in (or Makefile configured with mpireconfig)
# for the programs cpi, pi3, and cpilog.  

CC          = /home/enseign/PPD/mpich/bin/mpicc
CCC         = /home/enseign/PPD/mpich/bin/mpicxx
F77         = /home/enseign/PPD/mpich/bin/mpif77
CLINKER     = /home/enseign/PPD/mpich/bin/mpicc
CCLINKER    = /home/enseign/PPD/mpich/bin/mpicxx
FLINKER     = /home/enseign/PPD/mpich/bin/mpif77
F90         = /home/enseign/PPD/mpich/bin/mpif90
F90LINKER   = /home/enseign/PPD/mpich/bin/mpif90	  
MAKE        = make --no-print-directory
SHELL       = /bin/sh
#

### End User configurable options ###

LIBS =
FLIBS =
EXECS = mandel_para1

default: mandel_para1

# 
# The cp for pi3f90 is needed because different Fortran 90 compilers
# accept *different* suffixes.
# pi3f90 also wants an MPI module.  If modules not supported, don't 
# try to build pi3f90
all: $(EXECS)
	@if [ "1" = 1 -a -s simpleio.c ] ; then $(MAKE) simpleio ; fi
	@if [ "1" = 1 ] ; then $(MAKE) hello++ ; fi
	@if [ "0" = 0 ] ; then  \
		$(MAKE) pi3 ; \
		$(MAKE) pi3p; \
	fi
	@if [ "0" = 0 ] ; then $(MAKE) cpilog ; fi
	@if [ -n "" ] ; then \
	    if [ ! -s pi3f90. ] ; then \
		cp pi3f90.f90 pi3f90. ; fi ; \
	    $(MAKE) pi3f90 ; fi
	@if [ "ignore" != "ignore" ] ; then \
	    MPICH_USE_SHLIB="yes" ; export MPICH_USE_SHLIB ; \
	    $(MAKE) clean ; $(MAKE) cpi  ; \
	    if [ "0" = 0 ] ; then $(MAKE) pi3 ; fi ; \
	    if [ -n "" ] ; then $(MAKE) pi3f90 ; fi ; \
	fi



#
# This uses MPICH's -mpilog option to the mpicc command to add the automatic
# logging interface.
mandel_para1: mandel-para1.o
	$(CLINKER) -o mandel-para1 mandel-para1.o -lm

mandel_para1.o:
	$(CC) -o mandel-para1 mandel-para1.c

#
# The Solaris C++ compiler creates a directory containing miscellaneous
# data.  The action is not documented in the Solaris CC man pages
# IRIX C++ creates ii_files
# pgCC creates .ii and .ti files
# We also remove any copy of pi3f90 that is created (e.g., pi3f90.f; pi3f90.f90
# is the master file)
clean:
	-rm -f *.o *~ PI* $(EXECS) pi3 simpleio hello++ pi3f90 cpilog
	-rm -rf SunWS_cache ii_files pi3f90.f pi3p cpip *.ti *.ii

.c.o:
	$(CC) $(CFLAGS) -c $<
.f.o:
	$(F77) $(FFLAGS) -c $<
.f90.o:
	$(F90) $(F90FLAGS) -c $<
.SUFFIXES: .f90

Big Data in Finance final exam, Part B1, calculating PI using MPI
=================================================================

The MPI program has several bugs. These bugs can be in the C code,
the makefile, or the PBS job file. Your task is to find these bugs,
fix them, compile and run the program, then share your results.

In this file, write any thoughts or comments that might help
improve your grade.

A hint to help you on your way. Remember that make uses tabs to indent
the commands below targets.

And, remember, to use Git you must first load Git:

  module load git
  
These may also be useful commands:

  module list
  
  module avail

what I have done:
makefile:  
mpicc -o mpi mpi.cpp --> mpicc -o mpi mpi.c
change the space before the thrid line and sixth line to a tab

mpi.pbs:
mpirun -np 8 -machinefile $PBS_NODEFILE ./mpi.exe 
-->
mpirun -np 8 ./mpi > result.txt
	
mpi.c:
  if (myid = 0) { --> if (myid == 0) {
change PI formula to :
	mysum += 4.0/(1.0 + x*x); 
change:
  long int npts = 1e10;
-->
  long int npts = 1e9;

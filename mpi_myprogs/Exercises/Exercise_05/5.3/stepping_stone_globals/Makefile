PROG=global_sol
SRC = $(PROG).c
EXE = $(PROG).exe
MPICC = mpicc
MPICXX = mpicxx
MPIEXEC = mpiexec
NPROCS = 2

all: clean release run

debug:
	$(MPICC) $(FLAGS_DEBUG) $(SRC) -o $(EXE) -lm

release:
	$(MPICC) $(FLAGS_FAST) $(SRC) -o $(EXE)  -lm

run:
	@echo "Usage: make run [NPROCS=<#procs> | N=<#intervals>]"
	${MPIEXEC} -np $(NPROCS) $(EXE) $(N)

clean:
	@rm -f $(EXE) core* *.o *.mod a.out 
	@rm -f $(PROG).otf $(PROG).*.z

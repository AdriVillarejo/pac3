Adrian = gcc 
PRACTICA = -Wall -g

calcula: calcula.c calc.o
		$(Adrian) $(PRACTICA) calcula.c calc.o -o calcula
		
calc.o: calc.c calc.h
		$(Adrian) $(PRACTICA) -c calc.c -o calc.o

.PHONY: clean
clean: 
		rm -rf calc.o
		rm -f calcula

.PHONY: dist
dist: clean calcula
		rm -rf ../dist;
		mkdir -p ../dist/usr/bin/calc
		cp calcula ../dist/usr/bin/calc
		
.PHONY: targz
targz: clean
		mkdir -p source
		cp *.c *.h Makefile source
		tar -cvf calcula.tar source
		gzip calcula.tar
		rm -rf calcula.tar
		rm -rf source
		
.PHONY: install
install: dist
		cp -r ../dist/* /

# Copyright (C) 2013, Red Hat, Inc.
# All rights reserved.

# Redistribution and use in source and binary forms, with or without
# modification, are permitted provided that the following conditions are met:

#   Redistributions of source code must retain the above copyright notice,
#   this list of conditions and the following disclaimer.

#   Redistributions in binary form must reproduce the above copyright notice,
#   this list of conditions and the following disclaimer in the documentation
#   and/or other materials provided with the distribution.

#   Neither the name of Red Hat, Inc., nor the names of its
#   contributors may be used to endorse or promote products derived
#   from this software without specific prior written permission.

# THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS "AS IS"
# AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT LIMITED TO, THE
# IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR A PARTICULAR PURPOSE
# ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT HOLDER OR CONTRIBUTORS BE
# LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL, SPECIAL, EXEMPLARY, OR
# CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT LIMITED TO, PROCUREMENT OF
# SUBSTITUTE GOODS OR SERVICES; LOSS OF USE, DATA, OR PROFITS; OR BUSINESS
# INTERRUPTION) HOWEVER CAUSED AND ON ANY THEORY OF LIABILITY, WHETHER IN
# CONTRACT, STRICT LIABILITY, OR TORT (INCLUDING NEGLIGENCE OR OTHERWISE)
# ARISING IN ANY WAY OUT OF THE USE OF THIS SOFTWARE, EVEN IF ADVISED OF THE
# POSSIBILITY OF SUCH DAMAGE.

CWARNS = --std=gnu99 -Wall -Wextra -pedantic
CDEBUG = -O3 # use for maximal warning checks
#CDEBUG = -O0 -ggdb # use for debugging

CFLAGS = $(CWARNS) $(CDEBUG)
LFLAGS =

all: test

asn1.o: asn1.h asn1.c
	gcc -c $(CFLAGS) -o asn1.o asn1.c

cside.o: cside.c cside.h asn1.h
	gcc -c $(CFLAGS) -o cside.o cside.c

test: cside.o asn1.o
	gcc $(LFLAGS) -o test cside.o asn1.o

asn1test: asn1.o asn1test.c
	gcc $(LFLAGS) -o asn1test asn1.o asn1test.c

clean:
	rm -f a.out
	rm -f *.o
	rm -f *.gdb
	rm -f *.gch
	rm -f test
	rm -f asn1test

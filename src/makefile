#CXXFLAGS=-c -Wall -std=c++11 -g -mfpmath=sse -O4 -march=corei7 -pedantic
CXXFLAGS=-Wall -W -std=c++11 -g -msse -mfpmath=sse -ffast-math -O4 -march=corei7-avx -Wa,-q -pedantic
LDFLAGS=
SOURCES= testcase.cpp testcase_iterator.cpp main.cpp diagonals.cpp
OBJECTS=$(SOURCES:.cpp=.o)
EXECUTABLE=../pairhmm

all: $(SOURCES) $(EXECUTABLE)

$(EXECUTABLE): $(OBJECTS)
	$(CXX) $(LDFLAGS) $(OBJECTS) -o $@

diagonals.o: diagonals.cpp diagonals.h
main.o: main.cpp input_reader.h testcase_iterator.h testcase.h read.h \
 utils.h haplotype.h pairhmm.h pairhmm_impl.h constants.h diagonals.h  pairhmm_scalarimpl.h pairhmm_vecimpl.h pairhmm_sseimpl.h pairhmm_avximpl.h
testcase.o: testcase.cpp testcase.h read.h utils.h haplotype.h
testcase_iterator.o: testcase_iterator.cpp testcase_iterator.h testcase.h \
 read.h utils.h haplotype.h

.cpp.o:
	$(CXX) $(CXXFLAGS) -c $< -o $@

clean:
	rm -f *.o ../pairhmm

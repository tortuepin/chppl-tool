COMPILER = gcc
CFLAGS   = -g -std=c++11 -lboost_filesystem
LDFRAGS  = -L /usr/local/pgsql/lib/ -lpq -lcrypt -lstdc++
LIBS     =
INCLUDE  = -I /usr/local/pgsql/include/ -I /usr/local/pgsql/include/server/
TARGET   = ../bin/chppl
OBJDIR   = ./obj
SOURCES  = $(wildcard *.cpp)
OBJECTS  = $(addprefix $(OBJDIR)/, $(SOURCES:.cpp=.o))

$(TARGET): $(OBJECTS) $(LIBS)
	$(COMPILER) -o $@ $^ $(LDFRAGS) $(CFLAGS)

$(OBJDIR)/%.o: %.cpp
	@[ -d $(OBJDIR) ]
	$(COMPILER) $(CFLAGS) $(INCLUDE) -o $@ -c $<

all: clean $(TARGET)

clean: rm -f $(OBJECTS) $(TARGET)


# TEMPLATE_M Makefile
# 

CC					= gcc
CXX					= g++
CFLAGS					= -fdiagnostics-show-location=every-line \
					-std=c89 -Wall -Werror -pedantic \
					-Wfatal-errors -g -iquote include/
LD					= $(CC)
LDFLAGS					= 
STRIP					= strip --strip-unneeded
RM					= rm

# project directories
SRCDIR					= src
OBJDIR					= build
BINDIR					= bin

# files, deduced by make every time it is run
SRCS					= ${wildcard $(SRCDIR)/*.c}
HDRS					= ${wildcard $(SRCDIR)/*.h}
OBJS					= ${patsubst $(SRCDIR)/%.c,$(OBJDIR)/%.o,$(SRCS)}
EXE					= TEMPLATE_M


build/%.o: src/%.c
				$(CC) $(CFLAGS) -c $< -o $@

all: $(EXE)

$(EXE): $(OBJS)
				$(LD) $(CFLAGS) -o $@ $(OBJS) $(LDFLAGS)

# all object files in OBJDIR are purged along with executable
clean:
				$(RM) -f $(EXE) ${wildcard $(OBJDIR)/*.o}

dist: $(EXE)
				$(STRIP) $(EXE)


CC = gcc
CFLAGS = -Wall -g
INCLUDES = -I/usr/include -I.
LFLAGS =
LIBS =
SRCS=$(wildcard *.c)
OBJS = $(patsubst %.c,%.o,$(SRCS))
OBJ = $(OBJS)
TARGET_DIR = ../../../target/bin
MAIN = Hello

.PHONY: depend clean

all: $(MAIN)
	@echo "Successfully compiled Hello project"

$(MAIN): $(OBJS)
	cd $(TARGET_DIR) ; $(CC) $(CFLAGS) $(INCLUDES) -o $(MAIN) $(OBJ) $(LFLAGS) -L$(TARGET_DIR) $(LIBS)

.c.o:
	$(CC) $(CFLAGS) $(INCLUDES) -c $< -o $(TARGET_DIR)/$@

clean:
	$(RM) $(TARGET_DIR)/*.o $(TARGET_DIR)/$(MAIN)

depend: $(SRCS)
	makedepend $(INCLUDES) $^


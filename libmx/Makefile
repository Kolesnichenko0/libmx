OBJS_FOLDER = obj
INCS_FOLDER = inc
SRCS_FOLDER = src
NAME = LIBMX
LIB = libmx.a
SRCS := $(wildcard src/*.c)
OBJS := $(patsubst src/%.c, $(OBJS_FOLDER)/%.o, $(SRCS))
CC = clang
CFLAGS = -std=c11 -Wall -Wextra -Werror -Wpedantic

.PHONY: all clean uninstall reinstall

all: $(NAME)

$(NAME): $(OBJS_FOLDER) $(OBJS)
	ar rsc $(LIB) $(OBJS)

$(OBJS_FOLDER):
	mkdir $(OBJS_FOLDER)

$(OBJS_FOLDER)/%.o:$(SRCS_FOLDER)/%.c
	$(CC) $(CFLAGS) -I $(INCS_FOLDER) -c $< -o $@

uninstall: clean
	rm -f $(LIB)

clean:
	rm -rf $(OBJS_FOLDER)

reinstall: uninstall all

#
#
CPP = c++
CPPFLAGS = -Wall -Wextra -Werror -I$(INCDIR) -std=c++17
MAKEFLAGS += -s

INCDIR = ./inc
SRCDIR = ./src
OBJDIR = ./obj
SRCS = $(SRCDIR)/main.cpp $(SRCDIR)/Span.cpp

OBJS = $(SRCS:$(SRCDIR)/%.cpp=$(OBJDIR)/%.o)

NAME = span

$(NAME): $(OBJDIR) $(OBJS)
	@printf "[.]   📦 Compiling '\033[33m$(NAME)\033[0m'...\r"
	$(CPP) $(CPPFLAGS) $(OBJS) -o $(NAME)
	@echo "🚀 '\033[33m$(NAME)\033[0m' compiled \033[32msuccessfully\033[0m!"

$(OBJDIR)/%.o: $(SRCDIR)/%.cpp | $(OBJDIR)
	$(CPP) $(CPPFLAGS) -c $< -o $@

$(OBJDIR):
	mkdir -p $(OBJDIR)

all: $(NAME)

clean:
	rm -f $(OBJDIR)/*.o
	rm -rf $(OBJDIR)

fclean: clean
	@printf "[.]   🧹 Removing '\033[33m$(NAME)\033[0m' build...\r"
	rm -f $(NAME)
	printf "[✅]  🧹 Removed '\033[33m$(NAME)\033[0m' build...  \n"

re: fclean all

.PHONY: all clean fclean re

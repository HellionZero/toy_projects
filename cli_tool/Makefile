NAME = cli_tool
VERSION = 0.0.1
SRC = main.c \
		utils.c
SRC:= $(addprefix src/, $(SRC))
OBJ_DIR = obj
OBJ = $(patsubst src/%.c, $(OBJ_DIR)/%.o, $(SRC))
CFLAGS = -Wall -Wextra -Werror -O2

all: $(NAME)

$(NAME): $(OBJ)
	@gcc $(CFLAGS) -o $@ $^
	@echo "Built $(NAME) successfully."

$(OBJ_DIR)/%.o: src/%.c | $(OBJ_DIR)
	@gcc $(CFLAGS) -c $< -o $@
	@echo "Compiled $< to $@."

$(OBJ_DIR):
	@mkdir -p $(OBJ_DIR)

clean:
	@rm -rf $(OBJ_DIR)
	@echo "Cleaned object files."

fclean: clean
	@rm -f $(NAME)
	@echo "Removed $(NAME)."

re: fclean all

.PHONY: all clean fclean re


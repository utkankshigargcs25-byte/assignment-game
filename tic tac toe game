#include <stdio.h>

char board[9] = {'1','2','3','4','5','6','7','8','9'};

void drawBoard() {
    printf("\n");
    printf(" %c | %c | %c\n", board[0], board[1], board[2]);
    printf("---|---|---\n");
    printf(" %c | %c | %c\n", board[3], board[4], board[5]);
    printf("---|---|---\n");
    printf(" %c | %c | %c\n", board[6], board[7], board[8]);
    printf("\n");
}

int checkWin() {
    // Horizontal
    if (board[0] == board[1] && board[1] == board[2]) return 1;
    if (board[3] == board[4] && board[4] == board[5]) return 1;
    if (board[6] == board[7] && board[7] == board[8]) return 1;

    // Vertical
    if (board[0] == board[3] && board[3] == board[6]) return 1;
    if (board[1] == board[4] && board[4] == board[7]) return 1;
    if (board[2] == board[5] && board[5] == board[8]) return 1;

    // Diagonal
    if (board[0] == board[4] && board[4] == board[8]) return 1;
    if (board[2] == board[4] && board[4] == board[6]) return 1;

    return 0; // no winner yet
}

int isDraw() {
    for (int i = 0; i < 9; i++) {
        if (board[i] != 'X' && board[i] != 'O')
            return 0;  
    }
    return 1;  // board full ? draw
}

int main() {
    int player = 1, choice;
    char mark;

    while (1) {
        drawBoard();

        player = (player % 2) ? 1 : 2;
        printf("Player %d, enter your choice (1-9): ", player);
        scanf("%d", &choice);

        mark = (player == 1) ? 'X' : 'O';

        if (choice >= 1 && choice <= 9 && board[choice - 1] == ('0' + choice)) {
            board[choice - 1] = mark;
        } else {
            printf("Invalid move! Try again.\n");
            continue;
        }

        if (checkWin()) {
            drawBoard();
            printf("?? Player %d wins!\n", player);
            break;
        }

        if (isDraw()) {
            drawBoard();
            printf("?? Game is a Draw!\n");
            break;
        }

        player++;
    }

    return 0;
}


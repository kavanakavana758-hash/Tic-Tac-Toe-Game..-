# Tic-Tac-Toe-Game..-
#include <iostream>
using namespace std;

// Function to display the game board
void displayBoard(char board[3][3])
{
    cout << "\n";
    cout << "       TIC-TAC-TOE\n";
    cout << "=======================\n";

    for (int i = 0; i < 3; i++)
    {
        cout << "       ";

        for (int j = 0; j < 3; j++)
        {
            cout << " " << board[i][j] << " ";

            if (j < 2)
                cout << "|";
        }

        cout << "\n";

        if (i < 2)
            cout << "       ---+---+---\n";
    }

    cout << "=======================\n";
}

// Function to check winner
bool checkWinner(char board[3][3], char player)
{
    // Check rows
    for (int i = 0; i < 3; i++)
    {
        if (board[i][0] == player &&
            board[i][1] == player &&
            board[i][2] == player)
        {
            return true;
        }
    }

    // Check columns
    for (int j = 0; j < 3; j++)
    {
        if (board[0][j] == player &&
            board[1][j] == player &&
            board[2][j] == player)
        {
            return true;
        }
    }

    // Check main diagonal
    if (board[0][0] == player &&
        board[1][1] == player &&
        board[2][2] == player)
    {
        return true;
    }

    // Check opposite diagonal
    if (board[0][2] == player &&
        board[1][1] == player &&
        board[2][0] == player)
    {
        return true;
    }

    return false;
}

// Function to check draw
bool checkDraw(char board[3][3])
{
    for (int i = 0; i < 3; i++)
    {
        for (int j = 0; j < 3; j++)
        {
            if (board[i][j] != 'X' &&
                board[i][j] != 'O')
            {
                return false
#include <iostream>
#include <cmath>
#include <cstdlib>
#include <ctime>
#include <algorithm>
#include <random>
#include <string>
using namespace std;

void createFirstArray(int arr1[7][7], int size)
{
	int count = 0;
	for (int i = 0; i < size; i++)
	{
		for (int j = 0; j < size; j++)
		{
			arr1[i][j] = count;
		}
	}

	srand(static_cast<unsigned int>(time(nullptr)));

	//rR = randomRow
	//rC = randomColumn

	int rR1 = rand() % 5;
	int rC1 = rand() % 8;
	arr1[rR1][rC1] = 1;
	arr1[rR1 + 1][rC1] = 1;
	arr1[rR1 + 2][rC1] = 1;

	int rR2 = rand() % 6;
	int rC2 = rand() % 8;
	do
	{
		int rR2 = rand() % 6;
		int rC2 = rand() % 8;
	} while (arr1[rR2][rC2] == 1 || arr1[rR2 + 1][rC2] == 1);
	arr1[rR2][rC2] = 1;
	arr1[rR2 + 1][rC2] = 1;

	int rR3 = rand() % 6;
	int rC3 = rand() % 8;
	do
	{
		int rR3 = rand() % 6;
		int rC3 = rand() % 8;
	} while (arr1[rR3][rC3] == 1 || arr1[rR3 + 1][rC3] == 1);
	arr1[rR3][rC3] = 1;
	arr1[rR3 + 1][rC3] = 1;

	int rR4 = rand() % 8;
	int rC4 = rand() % 8;
	do
	{
		int rR4 = rand() % 8;
		int rC4 = rand() % 8;
	} while (arr1[rR4][rC4] == 1);
	arr1[rR4][rC4] = 1;

	int rR5 = rand() % 8;
	int rC5 = rand() % 8;
	do
	{
		int rR5 = rand() % 8;
		int rC5 = rand() % 8;
	} while (arr1[rR5][rC5] == 1);
	arr1[rR5][rC5] = 1;

	int rR6 = rand() % 8;
	int rC6 = rand() % 8;
	do
	{
		int rR6 = rand() % 8;
		int rC6 = rand() % 8;
	} while (arr1[rR6][rC6] == 1);
	arr1[rR6][rC6] = 1;

	int rR7 = rand() % 8;
	int rC7 = rand() % 8;
	do
	{
		int rR7 = rand() % 8;
		int rC7 = rand() % 8;
	} while (arr1[rR7][rC7] == 1);
	arr1[rR7][rC7] = 1;
}

void createSecondArray(char arr2[7][7], int arr1[7][7])
{
	for (int i = 0; i < 7; i++)
	{
		for (int j = 0; j < 7; j++)
		{
			arr2[i][j] = '+';
		}
	}
}

void showSecondArray(char arr2[7][7])
{
	cout << "  ";
	for (int i = 0; i < 7; i++)
	{
		cout << i << " ";
	}
	cout << endl;
	for (int i = 0; i < 7; i++)
	{
		cout << i << "|";
		for (int j = 0; j < 7; j++)
		{
			cout << arr2[i][j] << " ";
		}
		cout << endl;
	}
}

void checkUserInput(int a, int b, int arr1[7][7], char arr2[7][7])
{
	if (arr1[a][b] == 1)
	{
		cout << endl << "Hit";
		arr2[a][b] = 'H';
	}
	else
	{
		cout << endl << "Miss";
		arr2[a][b] = 'M';
	}
}

int main()
{
	const int size = 7;
	int arr1[size][size];
	char arr2[size][size];
	int a, b, victory, moves;
	string username;
	victory = 0;
	moves = 0;
	char playAgain;

	do
	{
		createFirstArray(arr1, size);
		createSecondArray(arr2, arr1);

		cout << "Welcome to the Battleships Game" << endl << "Write your name: ";
		cin >> username;
		cout << endl << "Hello " << username << endl << "Press Enter to continue...";
		cin.ignore();
		cin.get();

		while (victory == 0)
		{
			system("cls");
			showSecondArray(arr2);
			cout << endl;
			do
			{
				cout << "Enter ROW and COLUMN coordinates (0-6). H - Hit, M - Miss" << endl;
				cin >> a >> b;
			} while (a > 6 || a < 0 || b > 6 || b < 0);
			cout << endl;
			checkUserInput(a, b, arr1, arr2);
			moves++;

			cout << endl << "Press Enter to continue...";
			cin.ignore();
			cin.get();

			int countVictory = 0;
			for (int i = 0; i < 7; i++)
			{
				for (int j = 0; j < 7; j++)
				{
					if (arr2[i][j] == 'H')
					{
						countVictory++;
					}
				}
			}
			if (countVictory >= 10)
			{
				victory++;
			}
		}

		cout << endl << "Amount of hits: " << moves << endl;
		cout << "You win! You sank all the ships" << endl << endl;

		cout << "Do you want to play again? (Y/N): ";
		cin >> playAgain;

		victory = 0;
		moves = 0;

	} while (toupper(playAgain) == 'Y');

	return 0;
}

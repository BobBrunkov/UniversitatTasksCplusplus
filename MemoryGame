#include <iostream>
#include <cmath>
#include <cstdlib>
#include <ctime>
#include <algorithm>
#include <random>
#include <string>
using namespace std;

void createFirstArray(int arr[], int size)
{
	int count;

	//First Array creation
	count = 1;
	for (int i = 0; i < size / 2; i++)
	{
		arr[i] = count++;
	}
	count = 1;
	for (int i = size / 2; i < size; i++)
	{
		arr[i] = count++;
	}

	//Randomization
	random_device randomNumber;
	mt19937 engine(randomNumber()); //Mersenne Twister
	shuffle(arr, arr + size, engine);
}

void showIndexes(int size)
{
	int count = 0;
	for (int i = 0; i < size; i++)
	{
		cout << count++ << " ";
	}
	cout << endl;
}

void createSecondArray(char arr2[], int size)
{
	for (int i = 0; i < size; i++)
	{
		arr2[i] = 'X';
	}
}

void showSecondArray(char arr2[], int size)
{
	for (int i = 0; i < size; i++)
	{
		cout << arr2[i] << " ";
	}
}

void checkUserInput(int a, int b, int arr1[], char arr2[], int size)
{
	if (arr1[a] == arr1[b])
	{
		arr2[a] = '0' + arr1[a];
		arr2[b] = '0' + arr1[b];
		cout << "Cards has matched" << endl;
	}
	else
	{
		cout << "Cards has not matched" << endl;
		cout << "Card at index " << a << " is " << arr1[a] << endl;
		cout << "Card at index " << b << " is " << arr1[b] << endl;
	}
}


int main()
{
	const int size = 10;
	int arr1[size];
	char arr2[size];
	int a, b, moves, victory;
	moves = 0;
	victory = 0;

	createFirstArray(arr1, size);
	createSecondArray(arr2, size);

	while (victory == 0)
	{
		system("cls");
		showIndexes(size);
		showSecondArray(arr2, size);
		cout << endl;
		cout << "Enter two indexes: ";
		cin >> a >> b;
		cout << endl;
		checkUserInput(a, b, arr1, arr2, size);
		moves++;

		int countVictory = 0;
		for (int i = 0; i < size; i++)
		{
			if (arr1[i] == (arr2[i] - '0'))
			{
				countVictory++;
			}
		}
		if (countVictory == size)
		{
			victory++;
		}

		cout << "Press Enter to continue...";
		cin.ignore();
		cin.get();
	}
	cout << endl << "Amount of moves: " << moves << endl;
	cout << "You win! All pairs are found" << endl << endl;
}

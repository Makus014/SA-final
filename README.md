# SA-final

#include <iostream>
#include <array>
#include <string>
using namespace std;



void displaymenu();
void displaytea();
void displaycoffee();



int main() {
	/////////
	displaymenu();
	cout << endl;
	/////////
	bool choice = true;
	int user, choicedrink;
	string drinkchoice, sugar;
	char sugarchoice;
	int price = 0;
	int money;
	cout << "Hi, would you like a coffee or tea?" << endl;
	cout << "Press '1' = Coffee\nPress '2' = Tea" << endl;
	cin >> user;
	while (cin.fail() || user == 0 || user != (user >= 1 && user <= 2)) {
		if (user >= 1 && user <= 2) {
			break;
		}
		cout << "Try again" << endl;
		cin.clear();
		cin.ignore(1000, '\n');
		cin >> user;
	}
	while (choice == true) {
		switch (user) {
			
		case 1: {
			system("cls");
			displaycoffee();
			cout << endl << endl;

			cout << "What type of Coffee to you want?" << endl;
			cout << "Press '1' = Ice Coffee\nPress '2' = Milk Coffee\nPress '3' = Black Coffee" << endl;
			cin >> choicedrink;
			while (cin.fail() || choicedrink == 0 || choicedrink != (choicedrink >= 1 && choicedrink <= 3)) {
			if (choicedrink >= 1 && choicedrink <= 3) {
				break;
			}
			cout << "Try again" << endl;
			cin.clear();
			cin.ignore(1000, '\n');
			cin >> choicedrink;
		}
			if (choicedrink == 1) {
				drinkchoice = "Ice Coffee";
				price = 3;
			}
			if (choicedrink == 2) {
				drinkchoice = "Milk Coffee";
				price = 2;
			}
			if (choicedrink == 3) {
				drinkchoice = "Black Coffee";
				price = 1;
			}
			
			choice = false; }
			  break;

		case 2: {
			system("cls");
			displaytea();
			cout << endl << endl;

			cout << "What type of Tea to you want?" << endl;
			cout << "Press '1' = Ice Tea\nPress '2' = Milk Tea\nPress '3' = Black Tea" << endl;
			cin >> choicedrink;
			while (cin.fail() || choicedrink == 0 || choicedrink != (choicedrink >= 1 && choicedrink <= 3)) {
				if (choicedrink >= 1 && choicedrink <= 3) {
					break;
				}
				cout << "Try again" << endl;
				cin.clear();
				cin.ignore(1000, '\n');
				cin >> choicedrink;
			}
			if (choicedrink == 1) {
				drinkchoice = "Ice Tea";
				price = 3;
			}
			if (choicedrink == 2) {
				drinkchoice = "Milk Tea";
				price = 2;
			}
			if (choicedrink == 3) {
				drinkchoice = "Black Tea";
				price = 1;
			}
			choice == false; }
			break;
		default:
			cout << "Try again" << endl;
			cin.clear();
			cin.ignore(1000, '\n');
			cin >> user;
		}
			break;
	}
	cout << drinkchoice << " with sugar? " << endl;
	cout << "Type 'Y' for Yes, 'N' for No" << endl;
	cin >> sugarchoice;
	while (cin.fail() || sugarchoice != 'y' || sugarchoice != 'Y' || sugarchoice != 'n' || sugarchoice != 'N') {
		if (sugarchoice == 'y' || sugarchoice == 'Y' || sugarchoice == 'N' || sugarchoice == 'n') {
			break;
		}
		cout << "Try again" << endl;
		cin.clear();
		cin.ignore(1000, '\n');
		cin >> sugarchoice;
	}
	switch (sugarchoice) {
		{
	case 'y':
	case 'Y':
		sugar = "with sugar";
		break;
		}
		{
	case 'n':
	case 'N':
		sugar = "without sugar";
		break;
		}
	default:
		cout << "Try again" << endl;
		cin.clear();
		cin.ignore(1000, '\n');
		cin >> user;
		break;
	}

	cout << drinkchoice << " " << sugar << " will be " << price << " AED" << endl;
	cout << "Please insert money" << endl;
	cout << "(This machine accept 1-10AED only)" << endl;
	cin >> money;
	
	while (cin.fail() || money != (money >= 1 && money <= 10)) {
		if (money >= 1 && money <= 10) {
			break;
		}
		cout << "Try again" << endl;
		cin.clear();
		cin.ignore(1000, '\n');
		cin >> money;
	}
	if (money >= price && money == price) {
		cout << "Final Order will be " << drinkchoice << " " << sugar << " With the total change of " << (money - price) << " AED" << endl;
	}
	if (money < price) {
		cout << "Order Cancelled." << endl;
	}
		return 0;
	}

//////////////////////////////////////////////////////
void displaymenu() {
	string menu[4][2] = {
	{"Coffee			Price (AED)", "	  Tea			Price (AED)"},
	{ "Ice Coffee		3", "		  Ice Tea		3" },
	{ "Milk Coffee		2", "		  Milk Tea		2" },
	{ "Black Coffee		1", "		  Black Tea		1" }
	};
	for (int i = 0; i < 4; i++) {
		cout << endl;
		for (int x = 0; x < 2; x++) {
			cout << menu[i][x];
		}
	}
}
void displaytea() {
	string menu[4][2] = {
	{"Tea			Price (AED)"},
	{"Ice Tea			3" },
	{"Milk Tea		2" },
	{"Black Tea		1" }
	};
	for (int i = 0; i < 4; i++) {
		cout << endl;
		for (int x = 0; x < 1; x++) {
			cout << menu[i][x];
		}
	}
}
void displaycoffee() {
	string menu[4][1] = {
	{"Coffee			Price (AED)"},
	{ "Ice coffee		3",},
	{ "Milk Coffee		2",},
	{ "Black Coffee		1",}
	};
	for (int i = 0; i < 4; i++) {
		cout << endl;
		for (int x = 0; x < 1; x++) {
			cout << menu[i][x];
		}
	}
}
//////////////////////////////////////////////////////

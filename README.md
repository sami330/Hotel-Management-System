# Hotel-Management-System
The program have certain choices according to their functions

// START OF LMS PROJECT
// HEADER FILES
#include<iostream>
#include<iomanip>
#include<string>

using namespace std;
void add(char);   // RESERVATION OF CUSTOMER
void display(int i); //DISPLAYS THE ROOM PACKAGE 
void gold(int i);   // ROOM PACKAGE
void silver(int i);  // ROOM PACKAGE 
void copper(int i); // ROOM PACKAGE
void check(int roomno); // BOOKING A ROOM
void del(char); // DELETING A CUSTOMER'S ALPHA ID 
void buffet(int sn); // RESERVING SEATS FOR BUFFET


// FUNCTION DEFINITION 
void menu()
{
	int choice;
	cout << "     * MAIN MENU *" << endl;
	cout << " ============================"<<endl ;
	cout << "  1. _ENTER YOUR RECORD_" << endl << endl;
	cout << "  2. _BOOK A PACKAGE_" << endl << endl;
	cout << "  3. _BOOK A ROOM_" << endl << endl;
	cout << "  4. _BOOK A BUFFET_" << endl << endl;
	cout << "  5. _DELETE A RECORD_" << endl << endl;
	cout << "  6. _EXIT_" << endl;
	cout << "  ================================";
	cout << endl;
	cout << "  ENTER YOUR CHOICE:  ";
	cin >> choice;
	cout << endl;
	cout << "  ================================";
	cout << endl;
	switch (choice)
	{
	case 1:
		add(choice);
		break;

	case 2:
		display(choice);
		break;

	case 3:
		check(choice);
		break;

	case 4:
		buffet(choice);
		break;

	case 5:
		del(choice);
		break;

	case 6:
		cout << "  =====================================\n";
		cout << "  THANKYOU FOR CHECKING THE HOTEL OUT \n";
		cout << "  ======================================\n";
		break;

	default:
	{
		cout << "=============================" << endl;
		cout << "  WRONG CHOICE, TRY AGAIN" << endl;
		cout << "=============================" << endl;
		menu();
	}

	}
}
//END OF MENU FUNCTION

//FUNCTION FOR RESERVATION OF CUSTOMER
char filled[16] = { 'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P' };
int personCounter = 0;
void add(char)
{
	cout << "  PLEASE ENTER YOUR CUSTOMER CHARACTER: ";
	int i = 0;
	char empty[9];
	char ex;
	cin >> ex;
	cout << endl;
	if (ex >= 'A' && ex <= 'H') {
		cout << "  YOU ARE CUSTOMER: " << (personCounter + 1) << " YOU HAVE GOLD PACKAGE " << endl;
		cout << endl;
		menu();
	}
	else if (ex >= 'I' && ex <= 'M') {
		cout << "  YOU ARE CUSTOMER: " << (personCounter + 1) << " YOU HAVE SILVER PACKAGE" << endl;
		cout << endl;
		menu();

	}
	else if (ex >= 'N' && ex <= 'P') {
		cout << "  YOU ARE CUSTOMER: " << (personCounter + 1) << " YOU HAVE COPPER PACKAGE" << endl;
		cout << endl;
		menu();
	}
	else if (ex >= 'Q' && ex <= 'Z') {
		empty[i] = ex;
		cout << "  YOU ARE A NEW MEMBER: YOUR CUSTOMER CHARACTER IS: " << ex << endl << endl;
		menu();
	}
	else {
		menu();
	}
}
void check(int roomno)
{
	int arr[50] = { 1,2,3,4,5,6,7,8,9,10,11,12,13,14,15,16,17,18,19,20,21,22,23,24,25,26,27,28,29,30,31,32,33,34,35,36,37,38,39,40,43 };
	cout << "  **********" << endl;
	cout << "  TOTAL NO OF ROOMS - 50 " << endl;
	cout << "  ORDINARY ROOMS FROM 1 - 30 " << endl;
	cout << "  LUXURY ROOMS FROM 31 - 45 " << endl;
	cout << "  ROYAL ROOMS FROM 46 - 50 " << endl;
	cout << "  ************" << endl;
	cout << endl;
	cout << "  ENTER THE ROOM NO YOU WANT TO BOOK:  ";
	cin >> roomno;
	cout << endl;

	if (roomno != arr[roomno])
	{
		cout << "  SORRY THIS ROOM IS ALREADY BOOKED, PLEASE TRY AGAIN." << endl;
		cin >> roomno;
	}   
	else
	{
		if (roomno >= 1 && roomno <= 30) {
			cout << "  YOU HAVE BOOKED ORDINARY CLASS FROM " << roomno << "th & it costs $80" << endl;
			cout << "  SHALL WE CONFIRM YOUR ROOM TO BE BOOKED?" << endl;
			cout << "  Y --> Yes" << endl;
			cout << "  N --> No";
			char choice;
			cout << endl;
			cin >> choice;
			if (choice == 'Y')
			{
				cout << "  NOTED SIR, PLEASE PAY YOUR AMOUNT, YOUR ROOM KEY WILL BE GIVEN TO YOU IN A WHILE." << endl;
				cout << endl;
				cout << "  ENTER ANY KEY FOR MAIN MENU";
				string key;
				cin >> key;
				menu();
			}
			else menu();
		}
		else if (roomno >= 31 && roomno <= 45) {
			cout << "  YOU HAVE BOOKED LUXURY ROOM CATEGORY FROM ROOM NO " << roomno << "th & IT COSTS $120" << endl;
			cout << "  SHALL WE CONFIRM YOUR ROOM TO BE BOOKED?";
			cout << "  Y --> Yes" << endl;
			cout << "  N --> No";
			char choice;
			cin >> choice;
			cout << endl;
			if (choice == 'Y')
			{
				cout << "  NOTED SIR, PLEASE PAY YOUR AMOUNT, YOUR ROOM KEY WILL BE GIVEN TO YOU IN A WHILE." << endl;
				cout << endl;
				cout << "  ENTER ANY KEY FOR MAIN MENU  ";
				string key;
				cin >> key;
				menu();

			}
		}
		else if (roomno >= 46 && roomno <= 50)
			cout << "  YOU HAVE BOOKED ROYAL ROOM CATEGORY FROM ROOM NO " << roomno << "th & IT COSTS $150" << endl;
		cout << "  SHALL WE CONFIRM YOUR ROOM TO BE BOOKED?" << endl;
		cout << "  Y --> Yes" << endl;
		cout << "  N --> No";
		char choice;
		cin >> choice;
		cout << endl;
		if (choice == 'Y')
		{
			cout << "  NOTED SIR, PLEASE PAY YOUR AMOUNT, YOUR ROOM KEY WILL BE GIVEN TO YOU." << endl;
			cout << endl;
			cout << "  ENTER ANY KEY FOR MAIN MENU:  ";
			string key;
			cin >> key;
			menu();

		}
	}
}
//END OF BOOKING FUNCTION

//FUNCTION FOR DISPLAYING A PURTICULAR CUSTOMER`S RECORD DIVISION OF ROOMS, FOR SILV

void display(int i)
{
	cout << "  THERE ARE THREE TYPES OF CLASSES AVAILABLE FOR YOU: \n 1. GOLD \n 2. SILVER \n 3. COPPER" << endl;
	cout << "  PLEASE SELECT THE CATEEGORY TO STAY AT:  ";
	cin >> i;
	cout << endl;

	switch (i)
	{
	case 1:
		gold(i);
		break;

	case 2:
		silver(i);
		break;

	case 3:
		copper(i);
		break;

	default:
		cout << "  SORRY SUCH CLASSES ARE NOT AVAILABLE IN OUR HOTEL!! :) WOULD YOU LIKE TO SEE SOMETHING ELSE??:  ";
		cout << "  Y --> Yes" << endl;
		cout << "  N --> No" << endl;
		char choice;
		cout << "\t\t";
		cin >> choice;
		cout << endl;
		if (choice == 'Y')
		{
			gold(i);
			cout << endl;
			silver(i);
			cout << endl;
			copper(i);
			cout << endl;
		}
		else {
			cout << " **********\n";
			cout << "  THANKYOU FOR VISITING US.\n";
			cout << " **********\n";
			cout << "  HEADING TOWARDS THE MENU.." << endl;
			cout << endl;
			menu();
		}
	}
}
void silver(int i)
{
	char choice;
	cout << "  2. FOR SILVER: \n *FOR REGULAR CUSTOMERS: YOU WILL BE GIVEN DISCOUNT ON AFTERNOON BUFFET AND FREE SAUNA BATH, \n * FOR NEW CUSTOMERS: YOU WILL BE GIVEN FREE BUFFET FOR AFTERNOON AND SWIMMING POOL BATH. ";
	cout << endl;
	cout << "  SHALL WE BOOK YOUR CHOICE ?:  ";
	cout << " \n Y --> Yes" << endl;
	cout << "  N --> No" << endl;

	cin >> choice;
	cout << endl;
	if (choice == 'Y')
	{
		cout << "  NOTED SIR, YOU HAVE BOOKED OUR SILVER PACKAGE, THANKYOU SO MUCH!" << endl;
		cout << endl;
		cout << "  HEADING TOWARDS THE MENNU ..." << endl;
		cout << endl;
		menu();
	}
	else
	{
		cout << "  ***********\n";
		cout << "  PLEASE TRY OUR GOLD OR COPPER " << endl;
		cout << "  ************\n";
		copper(i);
	}

}
// END OF SILVER

// FOR GOLD
void gold(int i)
{
	char opt;
	cout << "  1. FOR GOLD: \n **FOR REGULAR CUSTOMERS: YOU WILL BE GIVEN DISCOUNT ON AFTERNOON AND DINNER BUFFET AND FREE SAUNA BATH. YOU WILL ALSO BE GIVEN FREE SWIMMING FROM 3PM- 5PM EVENING \n **FOR NEW CUSTOMERS: YOU WILL BE GIVEN DISCOUNT TO FOR SWIMMING SERVICES, 30% DISCOUNT ON BUFFET . ";
	cout << endl;
	cout << "  SHALL WE BOOK YOUR CHOICE ?" ;
	cout << "\n  Y --> Yes" << endl;
	cout << "  N --> No" << endl;
	cin >> opt;
	cout << endl;
	if (opt == 'Y')
	{
		cout << "  NOTED SIR, YOU HAVE BOOKED OUR GOLD PACKAGE, THANKYOU SO MUCH!" << endl << endl;
		menu();
	}
	else
	{
		cout << "  *************" << endl;
		cout << "  PLEASE TRY OUR SILVER OR COPPER" << endl;
		cout << "  *************" << endl;
		silver(i);
	}

}
// END OF GOLD

//FOR COPPER
void copper(int i)
{
	char choice;
	cout << "  2. FOR COPPER: \n *FOR REGULAR CUSTOMERS: YOU WILL BE GIVEN FREE AFTERNOON ROOM SERVICE AND FREE SAUNA BATH . \n * FOR NEW CUSTOMERS: YOU WILL BE GIVEN FREE ACCESS TO SUNDAY BRUNCH.";
	cout << endl;
	cout << "  SHALL WE BOOK YOUR CHOICE ?" ;
	cout << " \n Y --> Yes" << endl;
	cout << "  N --> No" << endl;
	cin >> choice;
	cout << endl;
	if (choice == 'Y')
	{
		cout << "  NOTED SIR ,YOU HAVE BOOKED OUR COPPER PACKAGE,THANKYOU SO MUCH!" << endl;
		menu();

	}
	else
	{
		cout << "  ***********" << endl;
		cout << "  PLEASE TRY OUR GOLD OR SILVER" << endl;
		cout << "  ************" << endl;
		gold(i);
	}
}
// END OF COPPER 
		// END OF DISPLAY FUNCTION 

	//FUNCTION TO DISPLAY ALL ROOMS OCCUPIED!

void buffet(int sn)
{
	string res;
	cout << "  ==================================\n";
	cout << "  WELCOME TO THE BUFFET RESERVATION!\n";
	cout << "  ===================================\n";
	cout << "  WE HAVE A TOTAL OF 35 SEATS!\n";
	cout << "  ===================================\n";
	cout << "   OUR BUFFET IS OPEN THREE TIMES DURING THE DAY : \n  **BREAKFAST \n  **LUNCH \n  **DINNER\   WHENN WOULD YOU LIKE TO RESERVE YOUR SEATS?  ";
	cin >> res;
	if (res == "breakfast" || res == "BREAKFAST")
	{
		cout << "\n   PLEASE ENTER YOUR SEAT NUNMBER:  ";
		cin >> sn;
		cout << endl;
		if (sn >= 1 && sn <= 5)
		{
			cout << "\n  SORRY THESE SEATS ARE ALREADY RESERVED FOR OUR BREAKFAST BUFFET:\n ";
			cout << "  PLEASE CHOOSE ANOTHER SEAT:  ";
			cin >> sn;
			cout << "  YOUR SEAT NUMBER " << sn << " HAS BEEN BOOKED FOR BREAKFAST BUFFET!";
		}
		else
		{
			cout << "  YOUR SEAT NUMBER  " << sn << "  HAS BEEN RESERVED FOR BREAKFAST" << endl;

		}
	}

	else if (res == "lunch" || res == "LUNCH")
	{
		cout << "\n  PLEASE ENTER YOUR SEAT NUMBER:  ";
		cin >> sn;
		if (sn >= 1 && sn <= 15)
		{
			cout << "  SORRY THESE SEATS ARE NOT AVAILAIBLE AT THE MOMENT:\n PLEASE LOOK FOR ANOTHER SEAT! ";
			cin >> sn;
			cout << endl;
			cout << "  YOUR SEAT NUMBER  " << sn << "  HAS BEEN BOOKED FOR LUNCH BUFFET!" << endl;
		}
		else
		{
			cout << "YOUR SEAT NUMBER " << sn << "  HAS BEEN RESERVED FOR LUNNCH" << endl;
		}
	}

	else if (res == "dinner" || res == "DINNER")
	{
		cout << "\n  PLEASE ENTER YOUR SEAT NUMBER:  ";
		cin >> sn;
		if (sn >= 1 && sn <= 20)
		{
			cout << "  SORRY THESE SEATS ARE NOT AVAILAIBLE AT THE MOMENT:\n PLEASE LOOK FOR ANOTHER SEAT! ";
			cin >> sn;
			cout << endl;
			cout << "  YOUR SEAT NUMBER  " << sn << "  HAS BEEN BOOKED FOR DINNER BUFFET!";
		}
		else
		{
			cout << endl;
			cout << "  YOUR SEAT NUMBER  " << sn << " HAS BEEN RESERVED FOR DINNER" << endl;
		}

	}
	else {
		cout << "INVALID INPUT, TRY AGAIN:  ";
		cin >> sn;
		cout << endl;
	}
	cout << "\n  WOULD YOU LIKE TO CHECK OUT ANYTHING ELSE? ";
	cout << "yes OR no?:   ";
	cin >> res;
	cout << endl;
	if (res == "yes")
	{
		menu();
	}
	else
	{
		cout << "  THANKYOU FOR CHECKING US OUT!";
	}
}

void del(char alpha)
{
	char delrec[16] = { 'A','B','C','D','E','F','G','H','I','J','K','L','M','N','O','P' };
	char ex;
	cout << endl;
	cout << "  PLEASE ENTER YOUR EXISTING CUSTOMER CHARACTER:  ";
	cin >> ex;
	cout << endl;
	for (int i = 0; i <= 16; i++) {
		if (ex == delrec[i]) {
			delrec[i] = 0;
			cout << "  YOU RECORD HAS BEEN DELETED!" << endl << endl;
			break;
		}
		else {
			cout << "  COUDLN'T FIND YOUR RECORD, TRY AGAIN..";
			cin >> ex;
			cout << endl;
		}
	}

	cout << "  ENTER ANY KEY FOR MAIN MENU:   ";
	string key;
	cin >> key;
	cout << endl;
	menu();
}

int main()
{
	cout << "                           _  _  _ " << endl;
	cout << "                     |_| |   |  |  | |" << endl;
	cout << "                     |  | |_|  |  |_ |__" << endl;
	cout << endl;
	cout << " |\\\     /|   _    |\\\    |   _    _    _  |\\\    /|   _ |\\\   | __" << endl;
	cout << " | \\\   / |  /_\\\   |  \\\  |  /\\\  |  _ |_  | \\\  / |  |_ | \\\  |  |" << endl;
	cout << " |  \\\ /  | /    \\\  |   \\\ | /    \\\ |_|  |_  |  \\\/  |  |__ |  \\\ |  | " << endl;
	cout << endl;
	cout << "                 _      _ _ __" << endl;
	cout << "                |_ \\\ / |_  | |__  |\\\  /|" << endl;
	cout << "                 _| |  _|  | |__  | \\\/ |" << endl;
	cout << endl;
	cout << "  ====================================" << endl;
	cout << "  WELCOME TO THE LMS HOTEL!!!" << endl;
	cout << "  ====================================" << endl;
	cout << "  =====================================" << endl;
	cout << "  I HOPE YOU HAVE A GOOD TIME WITH US!!!!!" << endl;
	cout << "  =====================================";
	cout << endl;
	menu();
	return 0;
}

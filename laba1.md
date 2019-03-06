{
#include "pch.h"
#include <iostream>
#include <Windows.h>

using namespace std;

struct laba1
{
	char name[32];
	char surname[32];
	char patronymic[32];
	char position[32];
	unsigned short salary;
	unsigned short birthday;
};

int main()
{
	setlocale(LC_ALL, "RUS");
	const int n = 3; //  заданиe количества стуктур в массиве
	laba1 arr[n];  // массив структуры

	for (int i = 0; i < n; i++) {
		cout << "Введите имя: ";
		cin >> arr[i].name;
		cin.ignore();
		cout << "Введите фамилию: ";
		cin >> arr[i].surname;
		cin.ignore();
		cout << "Введите отчество: ";
		cin >> arr[i].patronymic;
		cin.ignore();
		cout << "Введите должность: ";
		cin >> arr[i].position;
		cin.ignore();
		cout << "Введите зарплату: ";
		cin >> arr[i].salary;
		cin.ignore();
		cout << "Введите дату рождения: ";
		cin >> arr[i].birthday;
		cin.ignore();
		cout << endl;
	}

	int salary = 0;
	for (int i = 0; i < n; i++) {
		salary = salary + arr[i].salary;
	}

	int averagesalary = salary / n; // средняя зарплата
	cout << "Средняя зарплата : " << averagesalary << endl << endl;

	for (int i = 0; i < n; i++) {
		if (arr[i].salary > averagesalary && 2019 - arr[i].birthday > 30) {
			cout << "\t\tИнформация о сотруднике,зарплата которого превышает среднюю: " << endl;
			cout << "Имя:" << arr[i].name << endl;
			cout << "Фамилия:" << arr[i].surname << endl;
			cout << "Отчество:" << arr[i].patronymic << endl;
			cout << "Должность:" << arr[i].position << endl;
			cout << "Зарплата:" << arr[i].salary << endl;
			cout << "Дата рождения:" << arr[i].birthday << endl << endl;

		}
	}
	return 0;
}
}

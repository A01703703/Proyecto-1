# Proyecto-1
#include "stdafx.h"
#include <iostream>
#include <stdio.h>
#include <string>
#include <fstream>
using namespace std;

int main()
{
	string valores, l, e, s, p1, p2, p3, m, co1;
	char c, opA;
	int cant, i, v0, v1, v2, res;
	cout << "Escriba el nombre del archivo a leer con el .txt ";
	cin >> e;
	cout << "Escriba el nombre del archivo de salida con el .txt ";
	cin >> s;
	ifstream aE;
	aE.open (e);
	ofstream aS;
	aS.open (s);
	getline(aE, valores);
	cant = valores.length();
	for ( i = 1; i < cant; i++)
	{
		valores.erase(i,1);
		cant = valores.length();
	}
	while (!aE.eof())
	{
		aE >> p1 >> p2 >> p3;
		cant = p1.length();
		co1.erase(0);
		for ( i = 0; i < cant; i++)
		{
			v0 = valores.find(p1[i]);
			m = to_string(v0);
			co1 += m;
		}
		v1 = stoi(co1);
		cant = p3.length();		
		co1.erase(0);
		for ( i = 0; i < cant; i++)
		{
			v0 = valores.find(p3[i]);
			m = to_string(v0);
			co1 += m;
		}
		v2 = stoi(co1);
		v0 = valores.find(p2);
		switch (v0)
		{
			case 10:
			{
				res = v1 + v2;
				aS << "(" << v1 << ") + (" << v2 << ") = " << res << endl;
				break;
			}
			case 11:
			{
				res = v1 - v2;
				aS << "(" << v1 << ") - (" << v2 << ") = " << res << endl;
				break;
			}
			case 12:
			{
				res = v1 * v2;
				aS << "(" << v1 << ") * (" << v2 << ") = " << res << endl;
				break;
			}
			case 13:
			{
				res = v1 / v2;
				aS << "(" << v1 << ") / (" << v2 << ") = " << res << endl;
				break;
			}
			default:
			{
				aS << "Error en el problema" << endl;
				break;
			}
		}
	}
	aE.close ();
	aS.close ();
	system("PAUSE");
	return 0;
}

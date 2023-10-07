#include <stdio.h>
#include <stdlib.h>
#include <time.h>
#define BOYUT 1000

int SayiUret()
{
	return rand() % BOYUT + 1;
}

int main() 
{
	int dizi[BOYUT];
	int say = 0;

	srand(time(NULL));
	while (say < BOYUT)
	{
		int x = SayiUret();
		int benzersiz = 1;

		for (int i = 0; i < say; i++)
		{
			if (dizi[i] == x)
			{
				benzersiz = 0;
				break;
			}
		}
		
		if (benzersiz == 1)
		{
			dizi[say] = x;
			say++;
		}
	}
		
	for (int i = 0; i < say; i++)
	{
		printf("%d\n", dizi[i]);
	}

	return 0;
}

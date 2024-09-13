---
layout: project
type: project
image: img/countinjapanese.png
title: "Japanese Number Counter"
date: 2023-10-05
published: true
labels:
  - C
  - Japanese
summary: "A project that I created for an ICS 212 assignment."
---

The purpose of this code is to count from 0-9999 in a different language. For this instance, I decided to go with Japanese. The code creates separate outputs based on the number (ex. ones, hundreds, thousands). By following these steps heres a section of the code where I count in the hundreds category:

```
#include<stdio.h>

void printInJapanese(int number) {
	int thousands = (number / 1000) % 10;
	int hundreds = (number / 100) % 10;
	int tens = (number / 10) % 10;
	int ones = number % 10;

...

	//hundreds
	 if (hundreds > 0) {
                switch (hundreds) {
                        case 1: printf("hyaku");
                        break;
                        case 2: printf("nihyaku");
                        break;
                        case 3: printf("sanpyaku");
                        break;
                        case 4: printf("yonhyaku");
                        break;
                        case 5: printf("gohyaku");
                        break;
                        case 6: printf("rokuhyaku");
                        break;
                        case 7: printf("nanahyaku");
                        break;
                        case 8: printf("hachihyaku");
                        break;
                        case 9: printf("kyuhyaku");
                        break;

	}
}

...

	printf("\n");
}
int main() {
	for (int i = 1; i <= 9999; i++) {
		printf("&4d = ", i);
		printInJapanese(i);
	}
	return 0;
}

```

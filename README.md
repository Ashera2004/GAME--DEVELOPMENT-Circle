# EX 3 : Circle Drawing Algorithm

**AIM :**

To  implement the Bresenham’s  algorithm for circle using a c coding.

---

**ALGORITHM :**

Step 1 : Start.
    
Step 2 : Initialize the graphics header files and functions.
   
Step 3 : Declare the required variables and functions.
 
Step 4 : Get the co-ordinates and radius of the circle.

Step 5 : Draw the circle using the algorithm.

Step  6 : Display the output.
  
Step 7 : stop.

---

**Program :**
```c
#include <stdio.h>
#include <conio.h>
#include <math.h>
#include <graphics.h>

int plotpoints(int xcenter, int ycenter, int x, int y);

int main() {
    int gd = DETECT, gm;
    int xcenter, ycenter, radius;
    int p, x, y;

    initgraph(&gd, &gm, "c:\\turboc3\\bgi");

    printf("Enter The Radius Value:\n");
    scanf("%d", &radius);

    printf("Enter The xcenter and ycenter Values:\n");
    scanf("%d%d", &xcenter, &ycenter);

    x = 0;
    y = radius;
    plotpoints(xcenter, ycenter, x, y);

    p = 1 - radius;

    while (x < y) {
        if (p < 0) {
            x = x + 1;
        } else {
            x = x + 1;
            y = y - 1;
        }

        if (p < 0) {
            p = p + 2 * x + 1;
        } else {
            p = p + 2 * (x - y) + 1;
        }

        plotpoints(xcenter, ycenter, x, y);
    }

    printf("\n\nProgrammed by SIDDARTH A S (212224040316)");
    getch();
    return 0;
}

int plotpoints(int xcenter, int ycenter, int x, int y) {
    putpixel(xcenter + x, ycenter + y, 1);
    putpixel(xcenter - x, ycenter + y, 1);
    putpixel(xcenter + x, ycenter - y, 1);
    putpixel(xcenter - x, ycenter - y, 1);
    putpixel(xcenter + y, ycenter + x, 1);
    putpixel(xcenter - y, ycenter + x, 1);
    putpixel(xcenter + y, ycenter - x, 1);
    putpixel(xcenter - y, ycenter - x, 1);
    return 0;
}

```

---

**Output :**


<img width="643" height="480" alt="GDT_exp3" src="https://github.com/user-attachments/assets/75b00d42-bb2a-4611-84a4-b0442fd9d06c" />

---

**Result :**

 The Bresenham’s algorithm for circle was executed and verified successfully.

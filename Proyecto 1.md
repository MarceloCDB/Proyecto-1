Proyecto-1
==========
#include <curses.h>

void movimiento (int y,int x,int ch)
{
 for(;;)
    {
        mvprintw(y, x, "@");
        ch = getch();
        if (ch == KEY_DOWN)
        {
            y++;
        }
        if (ch == KEY_UP)
        {
            y--;
        }
        if (ch == KEY_LEFT)
        {
            x--;
        }
        if (ch == KEY_RIGHT)
        {
            x++;
        }
        refresh();
    }
}
int main() {
	int x= 20, y = 2;
	initscr();
	noecho();
	keypad(stdscr, TRUE);
	curs_set(0);
	printw("Bienvenido a EL LABERINTO\nPresione cualquier letra para empezar\n");
	int ch = getch();
	char c;int i;
    c=95;
    for(i=2;i<=120;i++)
    {
    move(2,i);
    printw("%c",c);
    move(40,i);
    printw("%c",c);
    }
    c=124 ;
    for(i=3;i<=40;i++)
    {
    move(i,1);
    printw("%c",c);
    move(i,121);
    printw("%c",c);
    }
	movimiento( x, y, ch);
	endwin();
	return 0;
}


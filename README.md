# battleship.h
The header file of the game Battleship

/*********************************************
* Project: Battleship                        *
* Author: Marina Ljuboja                     *
*                                            *
* Description: User plays the computer in a  *
* game of battleship. Each player has a 10 x *
* 10 board with 5 ships. The first to sink   *
* all of the opponents ships wins. Each move *
* and stats will be collected in a separate  *
* file.                                      *
*                                            *
**********************************************/

#ifndef BATTLESHIP_H
#define BATTLESHIP_H
#define MAX_COLS 10
#define MAX_ROWS 10
#define CARRIER 5
#define BATTLESHIP 4
#define CRUISER 3
#define SUBMARINE 3
#define DESTROYER 2

#include <stdio.h>
#include <stdlib.h>
#include <string.h>
#include <time.h>
#include <math.h>

typedef struct
{
	int total_hits,
		total_misses,
		total_shots,
		hits_to_misses;
} player_stats;

void welcome_message (void);
void intialize_gameboard (char gameboard[MAX_ROWS][MAX_COLS], int rows, int cols);
void print_gameboard(char gameboard[MAX_ROWS][MAX_COLS], int rows, int cols, int show);
void p1_ship_placement (char gameboard[MAX_ROWS][MAX_COLS]);
void manually_place_ships_on_board(char gameboard[MAX_ROWS][MAX_COLS]);
void randomly_place_ships_on_board(char gameboard[MAX_ROWS][MAX_COLS], int which_player, int show);
void check_enemy (char gameboard[MAX_ROWS][MAX_COLS], int x1, int y1, player_stats *stats, FILE *outfile);
void check_player (char gameboard[MAX_ROWS][MAX_COLS], int x1, int y1, player_stats *stats, FILE *outfile);
void check_sink (char gameboard[MAX_ROWS][MAX_COLS], int player, player_stats *stats, FILE *outfile, int *win);

#endif

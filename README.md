# Snake_water_gun_game

#include<stdio.h>
#include<stdlib.h>
#include<time.h>

int SnakeWaterGun(char you , char comp){
    // return 1 if you win, return -1 if you lose and return 0 game draw
    // cases for draw game 
    // ss
    // gg
    // ww

    if(you == comp){
        return 0;
    }
    // cases for non-draw game
    // s-w
    // w-s
    // g-w
    // w-g
    // g-s
    // s-g
    if(you=='s' && comp=='w'){
        return 1;
    }
    else if (you=='w' && comp=='s'){
        return -1;
    }

    if(you=='g' && comp=='w'){
        return -1;
    }
    else if (you=='w' && comp=='g'){
        return 1;
    }

    if(you=='g' && comp=='s'){
        return 1;
    }
    else if (you=='s' && comp=='g'){
        return -1;
    }
}
int main(){
    char you , comp;
    int number;
    srand(time(0));  // for generate random number
    number=rand()%100+1;

    if(number <33){
        comp = 's';
    }
    else if(number>33 && number<66){
        comp = 'w';
    }
    else{
        comp = 'g';
    }
    printf("Enter 's' for snake , 'w' for water and 'g' for gun:\n");
    scanf("%c", &you );
    int result =  SnakeWaterGun(you , comp);
    printf("You choose %c and computer choose %c.\n", you , comp);
    if(result == 0){
        printf("game draw\n");
    }
    else if(result == 1){
        printf("You win\n");
    }
    if(result == -1){
        printf("you lose\n");
    }
    return 0;
}

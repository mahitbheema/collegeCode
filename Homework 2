/*****+-***--***-*----*-----*-*--**---***-***----***************************
*
*  Homework #: HW02
*
*  Academic Integrity Statement:
*
*  I have not used source code obtained from any other unauthorized source, 
*  either modified or unmodified.  Neither have I provided access to my code 
*  to another. The effort I am submitting is my own original work.
*
*  Program Description: Determines the type of property, which way the property is facing, and the size of the property for a residential development
*
******+-***--***-*----*-----*-*--**---***-***----**************************/
#include <stdio.h>

int main (void)
{
  //variable declaration
  int propAdd; //user input for property address 
  float propLen; //user input for property length
  float propWid; //user input for property width
  int num; //to get a 1, 2, 3 value for property type
  int num2; //to get 1 or 2 for drive entry
  int numValid; //to get 1 for valid, 0 for invalid for lot size
  int halfLot; //variable for determining half size lot
  char propType; //to get type of property
  char driveEnter; //to get drive entry
  float lotSize; //to get size of lot
  
  //user input
  printf("Enter property address -> ");
  scanf("%d", &propAdd);
  printf("Enter property length -> "); 
  scanf("%f", &propLen); 
  printf("Enter property width -> "); 
  scanf("%f", &propWid);

  //logic for determining property type
  num  = (propAdd - 100) % 3 + 1;  
  propType = ((1 / num) * 'H') + ((1 - num % 2) * 'F') + ((num / 3) * 'I'); 
  //logic above^ -> computes between 1, 2, 3 for determining H, F, or I (half lot, full lot, or invalid) 
  
  //logic for determining property length
  num2 = (propAdd - 100) / 3; 
  driveEnter = (((1 - (num2 % 2)) * 'N') - (((1 - (num2 % 2))) * 'N' * (propType / 'I'))) + (((num2 % 2) * 'S') - (((num2 % 2)) * 'S' * (propType / 'I'))) + (propType / 'I') * 'I';
  //logic above ^ -> computes between N, S, and I (north, south, invalid), cycles through the three based on num2, which can either be 0, 1, or 2. 
 
  //logic for determining property width
  numValid = (1 - ((propAdd - 100) % 3 + 1) / 3);
  halfLot = (1 - ((propAdd - 100) % 3)) * ((propAdd - 100 + 1) % 2);  
  lotSize = numValid * (propLen * propWid * ((1 - halfLot) + (halfLot * 0.5))); 
  //logic above ^ -> first finds if the number is valid by giving 2, which represents invalid. Then finds if the lot is half size or full size. 
                  // Then, half lot calculates respectively based on the conditions above that are set by numValid and halfLot

  //output
  printf("\nProperty Type: %c\n", propType);  
  printf("Drive Entry: %c\n", driveEnter); 
  printf("Lot Size: %.1f", lotSize);  

  return 0;
}

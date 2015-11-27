#include <stdio.h>
#include <stdlib.h>
#include <conio.h>
#include <string.h>
#include <math.h>

// 3
char displayChoices() //menu selection screen function
{
  char choice;
  system ("cls");
  printf("MENU SELECTION SCREEN\n\n");
  printf("1. Add string\n2. Remove string\n3. View string\n4. Search string\n5. Quit");
  printf("\n\nEnter your choice: ");
  choice = getch();
}

//5

float massFlowRate (float p, float v, float A) //mass flow rate
{
      float m;
      m = p*v*A;
      return m;
}

float density (float m, float v, float A) //density
{
      float p;
      p = m / (v*A);
      return p;
}

float velocity (float m, float p, float A) //velocity
{
      float v;
      v = m / (p*A);
      return v;
}

float crossSectionalArea (float m, float p, float v) //cross-sectional area
{
      float A;
      A = m / (p*v);
      return A;
}

float netThrust (float W, float vj, float vo) //net thrust
{
      float F;
      F = W*(vj-vo);
      return F;
}

float massFlowRate2 (float F, float vj, float vo) //mass flow rate 2
{
      float W;
      W = F / (vj-vo);
      return W;
}

float jetVelocity (float F, float W, float vo) //jet velocity
{
      float vj;
      vj = F / W + vo;
      return vj;
}

float flightVelocity (float F, float W, float vj) //flight velocity
{
      float vo;
      vo = vj - (F / W);
      return vo;
}  


//6
double invel(double *Fdis, double *Idis, double *time,double *accel, double *vel )
{
	*vel = ((*Fdis-*Idis)/ *time)-((*accel)*(*time)/2);
	
}

double acc(double *Fdis, double *Idis, double *time,double *accel, double *vel )
{
	*accel = ((((*Fdis-*Idis)*2)/ ((*time)*(*time)))-((*vel*2)/(*time)));
	
}

double findis(double *Fdis, double *Idis, double *time,double *accel, double *vel )
{
	*Fdis = ((*vel)*(*time))+((*accel)*(*time)*(*time)/2)+*Idis;
	
}
double indis(double *Fdis, double *Idis, double *time,double *accel, double *vel )
{
	*Idis = *Fdis-((*vel)*(*time))-((*accel)*(*time)*(*time)/2);
	
}

double tim(double *Fdis, double *Idis, double *time,double *accel, double *vel )
{
	*time=2*(*Fdis-*Idis)/((sqrt(((*vel)*(*vel))+(2*(*accel)*(*Fdis-*Idis))))+(*vel));
	
}

double press(double mole, double RA, double temp, double volume)
{
	double pressure = mole*RA*temp/volume;
	return pressure; 
}

double vol(double mole, double RA, double temp, double pressure)
{
	double volume = mole*RA*temp/pressure;
	return volume; 
}

double Rcon(double mole, double volume, double temp, double pressure)
{
	double RA = pressure*volume/(mole*temp);
	return RA; 
}

double temper(double RA, double volume, double mole, double pressure)
{
	double temp = pressure*volume/(RA*mole);
	return temp; 
}

double n(double RA, double volume, double temp, double pressure)
{
	double mole = pressure*volume/(RA*temp);
	return mole; 
}




int main()
{
    int choice;
    //1 & 5
    int choice1, choice2, choice3;
  float m, p, v, A, F, W, vj, vo;
  //2
  int order, constants[10], a, x, term, data, b, values[10];
  int algorithm, add, mean, radicand, rows1;
  int columns1, rows2, columns2, matrixvalues1[3][3], c, d, matrixvalues2[3][3];
  int operation, matrixvalues3[3][3], e, matrixvalues4[3][3], c1, d1, c2, d2;
  float sd;
  //3
   char stringList[16][128], tempString[128];
      int strcount=0, counter=0, counter1=0, found=0;
      

  //4
	int var= {2}, j[4] = {1,2,3,4};
	int *ptr_p, *ptr_k[4];
	int i, cc, g;
	int tempvar, *ptr_t;  
//6
	int eq, working, solver;
	//eq- equation to be used, working - the variable you want to know the value
	//solver for the variables you have
	double  Id,Fd, Iv, t,aa , vv,  pp, R, T, MW;
	//Id- initial distance(m), Fd- Final distance(m) 
	// Iv- Initial Velocity(m/s), vv- volume(L)/velocity(m/s)
	// t-time(s),aa- acceleration(m/s^2)
	//  pp-pressure(N/m^2), I - current(ampheres), VV- voltage
	// R- Universal Gas Constant ( J/mol*K), T - Temperature (K), 
	//MW- molecular weight- (g/mole)

	double grp1, grp2, grp3;
	// resultants of groups (to simplify equation and debug)

  //7
  int numbers=0,tempID, newID;
  char tempName[128], newName[128];
  typedef struct //structure declaration
  {
    char name[128];
    int id;
  } EMPLOYEE; //custom data type EMPLOYEE
  EMPLOYEE employee[10]; //structure array declaration

    
    
  do{
  system("cls");
  printf("Hello!\n");
  printf("What topic do you want me to do?\n\n");
  printf("1 - Nested Conditional and Iterative Statements\n");
  printf("2 - Single Dimensional and Multidimensional Arrays\n");
  printf("3 - Strings, String Arrays, and String Manipulation Functions\n");
  printf("4 - Pointers\n");
  printf("5 - Functions and Pass-by-Value\n");
  printf("6 - Functions and Pass-by-Reference\n");
  printf("7 - Structures, Structure Arrays, and Complex Data Types\n");
  printf("8 - Exit Program\n\n");
  scanf("%d", &choice);
  
  switch(choice)
  {
  	
  	
  case 1:
  	system("cls");
  printf("FORMULA SELECTION\n\n");
  printf("1. Equation of Continuity\n2. Thrust Equation\n3. Exit\n\n");
  scanf("%d", &choice1);
  
  switch(choice1)
  {
       case 1:  //*****
            {
                 do
                 {
                 system ("cls");
                 printf("EQUATION OF CONTINUITY\n\n   m = pvA\n\n");
                 printf("1. Mass Flow Rate (m)\n2. Density (p)\n3. Velocity (v)\n4. Cross-Sectional Area (A)\n5. Back\n\n");
                 printf("Enter variable to compute for: ");
                 scanf("%d", &choice2);
                 
                 switch(choice2)
                 {
                      case 1:
                           {
                                system ("cls");
                                printf("COMPUTING FOR MASS FLOW RATE");
                                printf("\n\nInput given density: ");
                                scanf("%f", &p);
                                printf("Input given velocity: ");
                                scanf ("%f", &v);
                                printf("Input given cross-sectional area: ");
                                scanf("%f", &A);
                                
                                m = p*v*A;
                                
                                printf("\n\nThe computed mass flow rate is: %.4f", m);
                                getch();
                           } break;
                      case 2:
                           {
                                system ("cls");
                                printf("COMPUTING FOR DENSITY");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &m);
                                printf("Input given velocity: ");
                                scanf ("%f", &v);
                                printf("Input given cross-sectional area: ");
                                scanf("%f", &A);
                                
                                p = m / (v*A);
                                
                                printf("\n\nThe computed density is: %.4f", p);
                                getch();
                           } break;
                      case 3:
                           {
                                system ("cls");
                                printf("COMPUTING FOR VELOCITY");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &m);
                                printf("Input given density: ");
                                scanf ("%f", &p);
                                printf("Input given cross-sectional area: ");
                                scanf("%f", &A);
                                
                                v = m / (p*A);
                                
                                printf("\n\nThe computed velocity is: %.4f", v);
                                getch();
                           } break;
                      case 4:
                           {
                                system ("cls");
                                printf("COMPUTING FOR CROSS-SECTIONAL AREA");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &m);
                                printf("Input given density: ");
                                scanf ("%f", &p);
                                printf("Input given velocity: ");
                                scanf("%f", &v);
                                
                                A = m / (p*v);
                                
                                printf("\n\nThe computed cross-sectional area is: %.4f", A);
                                getch();
                           } break;
                      case 5:
                           return main();
                           break;
                      default:
                              printf("\n\nInvalid Command");
                              getch();
                              break;
                 } 
                 
                 } while (choice2<5);
                 return main();
            } break;
       
       case 2:
            {
                 do
                 {
                 system ("cls");
                 printf("THRUST EQUATION\n\n   F = W (vj - vo)\n\n");
                 printf("1. Net Thrust (F)\n2. Mass Flow Rate (W)\n3. Jet Velocity (vj)\n4. Flight Velocity (vo)\n5. Back\n\n");
                 printf("Enter variable to compute for: ");
                 scanf("%d", &choice3);
                 
                 switch(choice3)
                 {
                      case 1:
                           {
                                system ("cls");
                                printf("COMPUTING FOR NET THRUST");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &W);
                                printf("Input given jet velocity: ");
                                scanf ("%f", &vj);
                                printf("Input given flight velocity: ");
                                scanf("%f", &vo);
                                
                                F = W*(vj-vo);
                                
                                printf("\n\nThe computed net thrust is: %.4f", F);
                                getch();
                           } break;
                      case 2:
                           {
                                system ("cls");
                                printf("COMPUTING FOR MASS FLOW RATE");
                                printf("\n\nInput given net thrust: ");
                                scanf("%f", &F);
                                printf("Input given jet velocity: ");
                                scanf ("%f", &vj);
                                printf("Input given flight velocity: ");
                                scanf("%f", &vo);
                                
                                W = F / (vj-vo);
                                
                                printf("\n\nThe computed mass flow rate is: %.4f", W);
                                getch();
                           } break;
                      case 3:
                           {
                                system ("cls");
                                printf("COMPUTING FOR JET VELOCITY");
                                printf("\n\nInput given net thrust: ");
                                scanf("%f", &F);
                                printf("Input given mass flow rate: ");
                                scanf ("%f", &W);
                                printf("Input given flight velocity: ");
                                scanf("%f", &vo);
                                
                                vj = F / W + vo;
                                
                                printf("\n\nThe computed jet velocity is: %.4f", vj);
                                getch();
                           } break;
                      case 4:
                           {
                                system ("cls");
                                printf("COMPUTING FOR FLIGHT VELOCITY");
                                printf("\n\nInput given net thrust: ");
                                scanf("%f", &F);
                                printf("Input given mass flow rate: ");
                                scanf ("%f", &W);
                                printf("Input given jet velocity: ");
                                scanf("%f", &vj);
                                
                                vo = vj - (F / W);
                                
                                printf("\n\nThe computed flight velocity is: %.4f", vo);
                                getch();
                           } break;
                      case 5:
                           return main();
                           break;
                      default:
                              printf("\n\nInvalid Command");
                              getch();
                              break;
                 } 
                 
                 } while (choice3<5);
                 return main();
            } break;
            
       case 3:
            break;
       default:
               printf("\n\nInvalid Command");
            break;
        }
break;
        
case 2: //*****
                 system ("cls");
  printf("MENU SELECTION SCREEN\n\n");
  printf("1. Polynomial Evaluation\n2. Statistical Algorithm\n3. Matrix Operations\n4. Exit");
  printf("\n\nEnter your choice: ");
  scanf("%d", &choice1);
  
  
  switch(choice1)
  {
      
       case 1:
            {
            do
            {
            system ("cls");
            printf("POLYNOMIAL EVALUATION");
            printf("\n\nEnter order of polynomial: "); //order
            scanf("%d", &order);
            if (order<10)
            {
            printf("\nEnter coefficients:\n"); //coefficients
            for (a=0; a<=order; a++)
            {
                scanf("%d", &constants[a]);
            }
            printf("\nEnter value of x: "); //value of x
            scanf("%d", &x);
            for (a=0, term=0; a<=order, order>=0; a++, order--)
            {
                term = term + constants[a]*pow(x, order);
            }
            printf("\n\nThe answer is: %d", term);
            printf("\n\nDo you want to try again?\n1. Yes\n2. No\n\n");
            scanf("%d", &choice2);
            }
            }
            while (choice2==1);
            }break;
            
       case 2: 
            {
            system ("cls");
            printf("STATISTICAL ALGORITHM");
            printf("\n\nEnter number of data: "); //number of data
            scanf("%d", &data);
            if (data<10)
            {
            printf("\nEnter values of data:\n"); //data
            for (b=0; b<data; b++)
            {
                scanf("%d", &values[b]);
            }
            do
            {
            system ("cls");
            printf("Choose a statistical algorithm\n"); //operation
            printf("1. Mean\n2. Standard Deviation\n3. Summation\n4. Back\n\n");
            scanf("%d", &algorithm);
            
            switch(algorithm)
            {
                 case 1: //mean
                      {
                      system ("cls");
                      printf("MEAN");
                      for (b=0, add=0; b<data; b++)
                      {
                          add = add + values[b];
                      }
                      mean = add / data;
                      printf("\n\nThe mean is: %d", mean);
                      getch();
                      }break;
                      
                 case 2: //standard deviation
                      {
                      system ("cls");
                      printf("STANDARD DEVIATION");
                      for (b=0, add=0; b<data; b++)
                      {
                          add = add + values[b];
                      }
                      mean = add / data;
                      for (b=0, radicand=0; b<data; b++)
                      {
                          radicand = radicand + pow((values[b]-mean), 2);
                      }
                      sd = sqrt(radicand);
                      printf("\n\nThe standard deviation is: %.4f", sd);
                      getch();
                      }break;
                      
                 case 3: //summation
                      {
                      system ("cls");
                      printf("SUMMATION");
                      for (b=0, add=0; b<data; b++)
                      {
                          add = add + values[b];
                      }
                      printf("\n\nThe sum is: %d", add);
                      getch();
                      }break;
                      
                 case 4:
                      {
                      }break;
                      
                 default:
                      {
                      printf("\n\nInvalid Command");
                      getch();
                      }break;
                      
            }
            } while (algorithm!=4);
            }
            else
            {
            printf("\n\nToo much data."); //error message
            getch();
            }
            }break;
            
       case 3: //matrix operation
            {
            do
            {
            system ("cls");
            printf("MATRIX OPERATION");
            printf("\n\n1. Make 1st matrix\n2. Make 2nd matrix\n3. Select matrix operation\n4. Back\n\n");
            scanf("%d", &choice3);
            
            switch(choice3)
            {
                 case 1: //matrix1
                      {
                      system ("cls");
                      printf("MATRIX 1\n\n");
                      printf("Enter number of rows (M): ");
                      scanf("%d", &rows1);
                      printf("\nEnter number of columns (N): ");
                      scanf("%d", &columns1);
                      if ((rows1<=3) && (columns1<=3))
                      printf("\n\nEnter values for matrix 1: \n");
                      for (c=0; c<rows1; c++)
                      {
                          for (d=0; d<columns1; d++)
                          {
                              scanf("%d", &matrixvalues1[c][d]);
                          }
                      }
                      }break;
                      
                 case 2: //matrix2
                      {
                      system ("cls");
                      printf("MATRIX 2\n\n");
                      printf("Enter number of rows (M): ");
                      scanf("%d", &rows2);
                      printf("\nEnter number of columns (N): ");
                      scanf("%d", &columns2);
                      if ((rows1<=3) && (columns1<=3))
                      printf("\n\nEnter values for matrix 2: \n");
                      for (c=0; c<rows2; c++)
                      {
                          for (d=0; d<columns2; d++)
                          {
                              scanf("%d", &matrixvalues2[c][d]);
                          }
                      }
                      }break;
                      
                 case 3: //matrix operation
                      {
                      system ("cls");
                      printf("Choose matrix operation:\n\n");
                      printf("1. Addition\n2. Multiplication\n3. Transpose\n\n");
                      scanf("%d", &operation);
                      
                      switch(operation)
                      {
                           case 1: //addition
                                {
                                if ((rows1==rows2) && (columns1==columns2))
                                {
                                system ("cls");
                                printf("Resulting Matrix: \n\n");
                                     for (c=0; c<rows1; c++)
                                     {
                                         for (d=0; d<columns1; d++)
                                         {
                                             matrixvalues3[c][d] = matrixvalues1[c][d] + matrixvalues2[c][d];
                                             printf("\t%d", matrixvalues3[c][d]);
                                         }
                                         printf("\n");
                                     }
                                getch();
                                }
                                else
                                {
                                system ("cls");
                                printf("Matrices are not compatible. Please repeat.");
                                getch();
                                }
                                }break;
                                
                           case 2: //multiplication
                                {
                                if (columns1==rows2)
                                {
                                system ("cls");
                                printf("Resulting Matrix: \n\n");
                                      for (c=0; c<rows1; c++)
                                      {
                                          for (d=0; d<columns2; d++)
                                          {
                                              for (e=0, matrixvalues3[c][d]=0; e<rows2; e++)
                                              {
                                              matrixvalues3[c][d] = matrixvalues3[c][d]+matrixvalues1[c][e]*matrixvalues2[e][d];
                                              }
                                          printf("\t%d", matrixvalues3[c][d]);
                                          }
                                      printf("\n");
                                      }
                                getch();
                                }
                                else
                                {
                                system ("cls");
                                printf("Matrices are not compatible. Please repeat.");
                                getch();
                                }
                                }break;
                                
                           case 3: //transpose
                                {
                                system ("cls");
                                printf("Resulting Matrices: \n\n");
                                    for (c1=0; c1<columns1; c1++)
                                    {
                                        for (d1=0; d1<rows1; d1++)
                                        {
                                            matrixvalues3[c1][d1] = matrixvalues1[d1][c1];
                                            printf("\t%d", matrixvalues3[c1][d1]);
                                        }
                                    printf("\n");
                                    }
                                    printf("\n\n");
                                    for (c2=0; c2<columns2; c2++)
                                    {
                                        for (d2=0; d2<rows2; d2++)
                                        {
                                            matrixvalues4[c2][d2] = matrixvalues2[d2][c2];
                                            printf("\t%d", matrixvalues4[c2][d2]);
                                        }
                                    printf("\n");
                                    }
                                getch();
                                }break;
                                
                                
                                      
                      }
                                
            }
            }
            } while (choice3!=4);
            }break;
            
       case 4:
            {
            }break;
       
       default:
            {
            printf("\n\nInvalid Command");
            getch();
            }break;
       
  }break;
  case 3: //*****
       {
       	      choice = displayChoices();
       	
       while (choice!='5')
      {
      switch(choice)
      {
           case '1': //add a string
                {
                    system ("cls");
                    if (strcount<16)
                    {
                         printf("ENTER STRING");
                         printf("\n\nEnter a string:\n\n");
                              gets(stringList[strcount]);
                              strcount++;
                    }
                    else
                    {
                         printf("Maximum number of strings reached.");
                         getch();
                    }
                } break;
                
           case '2': //remove a string
                {
                     system ("cls");
                     printf("REMOVE STRING");
                     printf("\n\nEnter string to remove:\n\n");
                     gets(tempString);
                     for (counter=0, found=0; counter<strcount && !found; counter++)
                     {
                          if (!strcmp(stringList[counter],tempString))
                          {
                               found=1;
                               for (; counter<strcount; counter++)
                               {
                                   strcpy(stringList[counter], stringList[counter+1]);
                               }
                               strcount--;
                          }
                     }
                     if (found)
                     printf("\n\n%s deleted.", tempString);
                     else
                     printf("\n\n%s not found.", tempString);
                     getch();
                } break;
                
           case '3': //view all strings
                {
                     system ("cls");
                     printf("VIEW STRING");
                     printf("\n\nYour string(s) is/are:\n\n");
                     for (counter=0; counter<strcount; counter++)
                     {
                         printf("%d) %s\n", counter+1, stringList[counter]);
                     }
                     getch();
                } break;
                
           case '4':  //search for a string
                {
                     system ("cls");
                     printf("SEARCH STRING");
                     printf("\n\nEnter string to search for:\n\n");
                     gets(tempString);
                     for (counter=0, found=0; counter<strcount && !found; counter++)
                     {
                         if (strcmp(stringList[counter], tempString)==0)
                         {
                              found=1;
                         }
                     }
                     if (found)
                     {
                     printf("\n\nString found.");
                     getch();
                     }
                     else
                     {
                     printf("\n\nString not found.");
                     getch();
                     }
                } break;
                
            default:
                {
                    printf("\n\nInvalid Command.");
                    getch();
                } break;
      }
      choice = displayChoices(); //back to menu selection screen
      }
      }
      break;
      
    case 4: //pointers
    {
    system ("cls");
      printf("==========POINTERS=========\n\n");
	
do
{
		
	ptr_p=&var;
		for (i=0; i<4; i++)
		{
			ptr_k[i] = &j[i]; 
		} 

printf("Variable Value\t\t Variable Address\n\n"); 	
	
		for (i=0; i<4; i++)
		{
			printf("Array Value No. %d: %d\t", i+1, j[i]); 
	
			printf("Array Address No. %d: %u\n\n", i+1, ptr_k[i]); 
		}

	printf("\n\n------------------------------------------");
		printf("\n\nCHOOSE: \n1-Input \n2-Exit\n");
		scanf("%d", &c);
		
		switch(c)
		{
			case 1:

				printf("\n\nEnter a given address: "); 
				scanf("%d", &g);
				for(i=0; i<4; i++)
				{
					if((int*)g==&j[i])
					{
					j[i]=g;
					printf("Enter the value for x: ");
					scanf("%d", &j[i]);
					}
				}
				printf("Value of x: %d", x);  	
				system("cls");
				printf("==========POINTERS=========\n\n");
				printf("Variable Value\t\t Variable Address\n\n"); 	
				for (i=0; i<4; i++)
				{
					printf("Array Value No. %d: %d\t", i+1, j[i]); 
			
					printf("Array Address No. %d: %u\n\n", i+1, ptr_k[i]); 
				}
				printf("\n\n------------------------------------------");
				
					printf("\n\nCHOOSE: \n1-Run again \n2-Exit\n");
					scanf("%d", &cc);	
				
				system("cls");	
			break;	
			
			case 2:
				system("cls");
				return 0;
			break;
		}		

}while(cc!=2);
}
break;
    
    case 5:


  {
  system ("cls");
  printf("FORMULA SELECTION\n\n"); //formula selection screen
  printf("1. Equation of Continuity\n2. Thrust Equation\n3. Exit\n\n");
  scanf("%d", &choice1);
  
  switch(choice1)
  {
       case 1: //equation of continuity
            {
                 do
                 {
                 system ("cls");
                 printf("EQUATION OF CONTINUITY\n\n   m = pvA\n\n");
                 printf("1. Mass Flow Rate (m)\n2. Density (p)\n3. Velocity (v)\n4. Cross-Sectional Area (A)\n5. Back\n\n");
                 printf("Enter variable to compute for: ");
                 scanf("%d", &choice2);
                 
                 switch(choice2) //unknown variable
                 {
                      case 1:
                           {
                                system ("cls");
                                printf("COMPUTING FOR MASS FLOW RATE");
                                printf("\n\nInput given density: ");
                                scanf("%f", &p);
                                printf("Input given velocity: ");
                                scanf ("%f", &v);
                                printf("Input given cross-sectional area: ");
                                scanf("%f", &A);
                                
                                printf("\n\nThe computed mass flow rate is: %.4f", massFlowRate(p, v, A));
                                getch();
                           } break;
                      case 2:
                           {
                                system ("cls");
                                printf("COMPUTING FOR DENSITY");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &m);
                                printf("Input given velocity: ");
                                scanf ("%f", &v);
                                printf("Input given cross-sectional area: ");
                                scanf("%f", &A);
                                
                                printf("\n\nThe computed density is: %.4f", density(m, v, A));
                                getch();
                           } break;
                      case 3:
                           {
                                system ("cls");
                                printf("COMPUTING FOR VELOCITY");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &m);
                                printf("Input given density: ");
                                scanf ("%f", &p);
                                printf("Input given cross-sectional area: ");
                                scanf("%f", &A);
                                
                                printf("\n\nThe computed velocity is: %.4f", velocity(m, p, A));
                                getch();
                           } break;
                      case 4:
                           {
                                system ("cls");
                                printf("COMPUTING FOR CROSS-SECTIONAL AREA");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &m);
                                printf("Input given density: ");
                                scanf ("%f", &p);
                                printf("Input given velocity: ");
                                scanf("%f", &v);
                                
                                printf("\n\nThe computed cross-sectional area is: %.4f", crossSectionalArea(m, p, v));
                                getch();
                           } break;
                      default:
                              break;
                 } 
                 
                 } while (choice2<5);
                 

            } break;
       
       case 2: //thrust equation
            {
                 do
                 {
                 system ("cls");
                 printf("THRUST EQUATION\n\n   F = W (vj - vo)\n\n");
                 printf("1. Net Thrust (F)\n2. Mass Flow Rate (W)\n3. Jet Velocity (vj)\n4. Flight Velocity (vo)\n5. Back\n\n");
                 printf("Enter variable to compute for: ");
                 scanf("%d", &choice3);
                 
                 switch(choice3) //unknown variable
                 {
                      case 1:
                           {
                                system ("cls");
                                printf("COMPUTING FOR NET THRUST");
                                printf("\n\nInput given mass flow rate: ");
                                scanf("%f", &W);
                                printf("Input given jet velocity: ");
                                scanf ("%f", &vj);
                                printf("Input given flight velocity: ");
                                scanf("%f", &vo);
                                
                                printf("\n\nThe computed net thrust is: %.4f", netThrust(W, vj, vo));
                                getch();
                           } break;
                      case 2:
                           {
                                system ("cls");
                                printf("COMPUTING FOR MASS FLOW RATE");
                                printf("\n\nInput given net thrust: ");
                                scanf("%f", &F);
                                printf("Input given jet velocity: ");
                                scanf ("%f", &vj);
                                printf("Input given flight velocity: ");
                                scanf("%f", &vo);
                                
                                printf("\n\nThe computed mass flow rate is: %.4f", massFlowRate2(F, vj, vo));
                                getch();
                           } break;
                      case 3:
                           {
                                system ("cls");
                                printf("COMPUTING FOR JET VELOCITY");
                                printf("\n\nInput given net thrust: ");
                                scanf("%f", &F);
                                printf("Input given mass flow rate: ");
                                scanf ("%f", &W);
                                printf("Input given flight velocity: ");
                                scanf("%f", &vo);
                                
                                printf("\n\nThe computed jet velocity is: %.4f", jetVelocity(F, W, vo));
                                getch();
                           } break;
                      case 4:
                           {
                                system ("cls");
                                printf("COMPUTING FOR FLIGHT VELOCITY");
                                printf("\n\nInput given net thrust: ");
                                scanf("%f", &F);
                                printf("Input given mass flow rate: ");
                                scanf ("%f", &W);
                                printf("Input given jet velocity: ");
                                scanf("%f", &vj);
                                
                                printf("\n\nThe computed flight velocity is: %.4f", flightVelocity(F, W, vj));
                                getch();
                           } break;
                      default:
                              break;
                 } 
                 
                 } while (choice3<5);

            } break;
            
       case 3: //exit option
            break;
       default:
            break;
            
  
  }
  if ((choice2!=5) || (choice3!=5))
  {
       printf("\n\nInvalid Command");
       getch();
  }
  
      			
			  }
      		break;
      case 6:
      	{
               system ("cls");
      	
do{
	
	grp1=0;
	grp2=0;
	grp3=0;
	printf( "This program is intended to solve \n engineering equations :");
	printf("\n1-\tEquation for Velocity\n\n2-\tIdeal gas Equation");
	printf("\n\nWhich of the equations do you want to choose?(1/2)\n");
	
	scanf("%d",&eq);
	//scans the equation to be used next
	
	switch(eq)
	{
		
		case 1 :
			printf(" Equation for Velocity \n");
			printf(" The equation is :\n");
			printf("\tIv=((Fd-Id)/t)-((aa(t))/2)");
			printf("where:\n1-\t Iv -\tInitial velocity in meters per second (m/s)");
			printf("\n2-\t Fd -\tFinal distance (m) ");
			printf("\n3-\t Id -\tInitial distance (m) ");
			printf("\n4-\t aa -\tacceleration in meters per second square(m/s^2) ");
			printf("\n5-\t t -\ttime it took in seconds(s) ");
			

			//introducing the equation to the user
			printf("\nWhat is the missing variable?(1-5)\n");
			scanf("%d",&working);
			//selects on the working equation (depends on the missing variable)
			switch(working)
			{
				case 1: 
				//this option is for the missing Initial velocity
				printf("\nThe missing variable is the Initial Velocity ");
				printf("\n\tIv=((Fd-Id)/t)-((aa(t))/2)");
				
				
				
				printf("\nWhat is the Initial distance(meter)?\n");
				scanf("%lf",&Id);
				printf("\nWhat is the Final distance(meters)?\n");
				scanf("%lf",&Fd);
				printf("\nWhat is the acceleration(meters per second square)?\n");
				scanf("%lf",&aa);
				printf("\nHow long did it took(seconds)?\n");
				scanf("%lf",&t);
				//gaining the values
				
				
				
				//checks if can be divided and time can not be negative but can be zero
					if (t>0)
						{
							invel(&Fd, &Id, &t, &aa, &Iv );
							printf("\nThe Initial Velocity is %f m/s\n",Iv);
				
						}
				
					else if (t=0)
						{
							grp3=0;
							printf("\nThe Initial velocity is %f m/s^2\n",grp3);
				
						}
				
				
				
					else
						{
							printf("\nError the value of time is incorrect\n");	
						}
				
				
					;
					break;
				
				case 2:
				//this option is for the missing Final distance
				printf("\nThe missing variable is the Final distance ");
				printf("\n\tFd=Id-(Iv*t)-((aa(t^2))/2)");
				
				
				
				printf("\nWhat is the Initial distance(meter)?\n");
				scanf("%lf",&Id);
				printf("\nWhat is the Initial Velocity(meters per second)?\n");
				scanf("%lf",&Iv);
				printf("\nWhat is the acceleration(meters per second square)?\n");
				scanf("%lf",&aa);
				printf("\nHow long did it took(seconds)?\n");
				scanf("%lf",&t);
				//gaining the values
				
				
				
				//time can not be negative
					if (t>=0)
						{
							findis(&Fd, &Id, &t, &aa, &Iv );
							printf("\nThe Final distance is %f m\n",Fd);
				
						}
				
					else
						{
							printf("\nError the value of time is incorrect\n");	
						}
				
				
					;
					break;
				
				case 3:
				//this option is for the missing Initial distance
				printf("\nThe missing variable is the Initial distance ");
				printf("\n\tId=Fd-(Iv*t)-((aa(t^2))/2)");
				
				
				
				printf("\nWhat is the Final distance(meter)?\n");
				scanf("%lf",&Fd);
				printf("\nWhat is the Initial Velocity(meters per second)?\n");
				scanf("%lf",&Iv);
				printf("\nWhat is the acceleration(meters per second square)?\n");
				scanf("%lf",&aa);
				printf("\nHow long did it took(seconds)?\n");
				scanf("%lf",&t);
				//gaining the values
				grp1=(Iv*t);
				grp2=(aa*t*t); 
				
				
				//time can not be negative 
					if (t>=0)
						{
							indis(&Fd, &Id, &t, &aa, &Iv );
							printf("\nThe Initial distance is %f m\n",Id);
				
						}
				
					else
						{
							printf("\nError the value of time is incorrect\n");	
						}
				
				
					;
					break;
							
				case 4:
				//this option is for the missing acceleration
				printf("\nThe missing variable is the acceleration ");
				printf("\n\ta=2*(((Fd-Id)/(t^2))-(Iv/t))");
				
				
				
				printf("\nWhat is the Final distance(meter)?\n");
				scanf("%lf",&Fd);
				printf("\nWhat is the Initial Velocity(meters per second)?\n");
				scanf("%lf",&Iv);
				printf("\nWhat is the Initial distance(meters)?\n");
				scanf("%lf",&Id);
				printf("\nHow long did it took(seconds)?\n");
				scanf("%lf",&t);
				//gaining the values
				grp1=(Fd-Id);
				grp2=(t*t); 
				
				
				//time can not be negative but may be zero if there is no movement
					if (t>0)
						{
							acc(&Fd, &Id, &t, &aa, &Iv );
							
							printf("\nThe acceleration is %f m/s^2\n",aa);
				
						}
					
					else if (t=0)
						{
							grp3=0;
							printf("\nThe acceleration is %f m/s^2\n",grp3);
				
						}
					
					
					else
						{
							printf("\nError the value of time is incorrect\n");	
						}
				
				
					;
					
					break;
					
					case 5: 
				//this option is for the missing Time
				printf("\nThe missing variable is the time ");
				printf("\n\tt= (2*(Fd-Id)/(Iv+(((Iv^2)+(2*aa(Id-Fd)))^1/2))");
				
				
				
				printf("\nWhat is the Initial distance(meter)?\n");
				scanf("%lf",&Id);
				printf("\nWhat is the Final distance(meters)?\n");
				scanf("%lf",&Fd);
				printf("\nWhat is the acceleration(meters per second square)?\n");
				scanf("%lf",&aa);
				printf("\nWhat is the Initial Velocity(meters per second)?\n");
				scanf("%lf",&Iv);
				//gaining the values
				
				
				//checks if can be divided, acceleration can be zero if there is no displacement
					if (aa>0 && grp1>0)
						{
							
							indis(&Fd, &Id, &t, &aa, &Iv );
							
							printf("\nIt took %f s\n",t);
				
						}
				
					else if (aa=0)
						{
							grp1=(Fd-Id);
							grp3=((grp1)/Iv);

							printf("\nIt took %f s\n",grp3);
				
						}
				
					else if (aa<0 && grp1<0)
						{
							
							indis(&Fd, &Id, &t, &aa, &Iv );
							printf("\nIt took %f s\n",grp3);
				
						}
				
					else
						{
							grp2=(Iv*Iv)+(2*aa*grp1*-1);
							grp3=2*grp1/((sqrt(grp2))+Iv);
							printf("\nIt took %f s\n",grp3);
				
						}
				
					;
					break;
	
				default:
					
					printf("Error! This is not one of the choices. The program will now close");
					eq=0;
					getch();
					return 0;
					//another error occured using switch
					
					break;
				// to end an error
				}
			
			
			break;
		
		case 2 :
			
			printf(" The Ideal Gas State Equation \n");
			printf(" The equation is :\n");
			printf("\tpv = nRT \n");
			printf("where:\n1-\t pp -\tpressure in Newton per meter square(N/(m^2) ");
			printf("\n2-\t vv -\tvolume in Meter cube(m^3) ");
			printf("\n3-\t R -\tUniversal Gas Constant in  \n\t\t joule per mole Kelvin(8.31441 J/(mol*K)) ");
			printf("\n4-\t T -\tTemperature in Kelvin(K) ");
			printf("\n5-\t n-\tnumber of moles(mol) ");
			//introducing the equation to the user
			printf("\nWhat is the missing variable?(1-5)\n");
			scanf("%d",&working);
			//selects on the working equation (depends on the missing variable)
			switch(working)
			{
				case 1: 
					//pressure is missing 
					printf("\nThe missing variable is the pressure");
					printf("\nWhat is the volume in Meter cube(m^3)?\n");
					scanf("%lf",&vv);
					printf("\nWhat is the Universal Gas Constant(joule per mole Kelvin)?\n");
					scanf("%lf",&R);
					printf("\nWhat is the Temperature(Kelvin)?\n");
					scanf("%lf",&T);
					printf("\nWhat is the number of moles(mol)?\n");
					scanf("%lf",&MW);
					
					
					// if MW or vv is zero it cannot be used as aa dividend
					if ((MW>0) && (vv>0))
					{
						pp= press(MW, R, T, vv);
						printf("The pressure is %f N/m^2", pp);
					}
					else
					{
						printf("error the values cannot exist");
					}
					
					;
					break;
				
				case 2:
					//volume is missing 
					printf("\nThe missing variable is the volume");
					printf("\nWhat is the pressure(Newtons per meter square)?\n");
					scanf("%lf",&pp);
					printf("\nWhat is the Universal Gas Constant(joule per mole Kelvin)?\n");
					scanf("%lf",&R);
					printf("\nWhat is the Temperature(Kelvin)?\n");
					scanf("%lf",&T);
					printf("\nWhat is the number of moles?\n");
					scanf("%lf",&MW);
					
					
					// if MW or pp is zero it cannot be used as aa dividend
					if ((MW>0) && (pp>0))
					{
						vv=vol(MW, R, T, pp);
						printf("The velocity is %f m/s",vv);
					}
					else
					{
						printf("error the values cannot exist");
					}
					
					
					break;
				
				case 3:
					//Universal Gas Constant is missing 
					printf("\nThe missing variable is the Universal Gas Constant");
					printf("\nWhat is the volume(meters cube)?\n");
					scanf("%lf",&vv);
					printf("\nWhat is the pressure(Newton per meter square)?\n");
					scanf("%lf",&pp);
					printf("\nWhat is the Temperature(Kelvin)?\n");
					scanf("%lf",&T);
					printf("\nWhat is thenumber of moles?\n");
					scanf("%lf",&MW);
					grp1=T;
					grp2=MW*vv*pp;
					
					// if T is zero it cannot be used as aa dividend but T can be zero or less than zero
					if ((T>0) && (MW>0))
					{
						R= Rcon(MW, vv, T, pp);
						printf("The Universal gas Constant is %f Joules per mole Kelvin",R);
					}
					
					else if ((T<0) && (MW>0))
					//number of moles can not be negative
					{
						R= Rcon(MW, vv, T, pp);
						printf("The Universal gas Constant is %f Joules per mole Kelvin",R);
					}
					
					else
					{
						printf("The value of Temperature is zero \nso the equation can not be used");
					}
					
					;
					break;
							
				case 4:
					//Temperature is missing 
					printf("\nThe missing variable is the Temperature");
					printf("\nWhat is the volume(meters cube)?\n");
					scanf("%lf",&vv);
					printf("\nWhat is the pressure(Newton per meter square)?\n");
					scanf("%lf",&pp);
					printf("\nWhat is the Universal Gas Constant(joule per mole Kelvin)?\n");
					scanf("%lf",&R);
					printf("\nWhat is the number of moles?\n");
					scanf("%lf",&MW);
					grp1=R*MW;

					
					// if R is zero it cannot be used as aa dividend
					if ((grp1>0))
					{
						grp3=temper(R, vv, MW, pp);
						printf("The Temperature is %f Kelvin",grp3);
					}
					else if (grp1<0)
					
					{
						grp3=temper(R, vv, MW, pp);
						printf("The Temperature is %f Kelvin",grp3);
					}
					
					else
					{
						printf("error the values cannot exist");
					}
					
					;
					break;
				
				case 5:
					//Molecular Weight is missing 
					printf("\nThe missing variable is the number of moles");
					printf("\nWhat is the volume(meters cube)?\n");
					scanf("%lf",&vv);
					printf("\nWhat is the pressure(Newton per meter square)?\n");
					scanf("%lf",&pp);
					printf("\nWhat is the Universal Gas Constant(joule per mole Kelvin)?\n");
					scanf("%lf",&R);
					printf("\nWhat is the Temperature(Kelvin)?\n");
					scanf("%lf",&T);
					grp1=R*T;
				
					
					// if R or T is zero it cannot be used as aa dividend temp can be below zero
					if ((grp1>0))
					{
						MW= n(R, vv, T, pp);
						printf("The number of moles is %f mol",MW);
					}
					
					else if (grp1<0)
					
					{
						MW= n(R, vv, T, pp);
						printf("The number of moles is %f mol",MW);
					}
					
					
					else
					{
						printf("error the values cannot exist");
					}
					
					;
					break;
						
				default:
					
					printf("Error! This is not one of the choices. The program will now close");
					
					eq=0;
					
					getch();
					
					return 0;
					
					break;
					//error in switch specifically char
				// to end an error
				}
			
			
			;
			break;
		
		default:
			
			printf("Error! This is not one of the choices. The program will now close");
			working=0;
			getch();
			break;
			//error in switch specifically char
			// can not break the char so close program
		// to end an error
		}
		
		getch();
		//to stop the loop for aa while
	printf("\n\nDo you still want to use the program?");
	printf("\n1-Yes");
	printf("\n2-No\n");	
	scanf("%d",&x);
	//decision of the user to continue or not
	system("cls");
	//to clearscreen upon reuse
	}while(x<2);
	//does looping for reusing the program
}
break; 

		  
		  
	case 7:
		do
{
    system ("cls");
    printf("MENU SELECTION SCREEN\n\n"); //menu selection screen
    printf("1. Add Entry\n2. Display Entries\n3. Remove Entry\n4. Edit Entry\n5. Search Entry\n6. Exit\n\n");
    scanf("%d", &choice);
      
    switch(choice)
    {
      case 1: //add entry
        {
          system ("cls");
          if (numbers<10)
          {
            printf("ADD ENTRY");
            printf("\n\nEnter Name: ");
            scanf("%s", &employee[numbers].name);
            printf("Enter ID Numbers: ");
            scanf("%d", &employee[numbers].id);
            numbers++;
          }
          else
          {
            printf("Maximum numbers of entries reached.");
            getch();
          }
        } break;

      case 2: //view entries
        {
          system ("cls");
          printf("VIEW ENTRIES");
          printf("\n\n\tNAME\t\t\tID NUMBERS\n\n");
          for (counter=0; counter<numbers; counter++)
          {
            printf("\t%s\t\t\t%d\n", employee[counter].name, employee[counter].id);
          }
          getch();
        } break;
                
      case 3: //remove entry
        {
          system ("cls");
          printf("REMOVE ENTRY");
          printf("\n\n1. Remove via Name\n2. Remove via ID Numbers\n");
          scanf("%d", &choice2);
                   
          switch(choice2)
            {
              case 1: //remove via name
                {
                  printf("\nEnter name to remove: ");
                  scanf("%s", &tempName);
                  for (counter=0, found=0; counter<numbers && !found; counter++)
                  {
                    if (strcmp(employee[counter].name,tempName)==0)
                    {
                      found=1;
                      for (; counter<numbers; counter++)
                      {
                        strcpy(employee[counter].name, employee[counter+1].name);
                        employee[counter].id = employee[counter+1].id;
                      }
                      numbers--;
                    }
                  }
                  if (found)
                    printf("\nEmployee %s deleted.", tempName);
                  else
                    printf("\nEmployee %s not found.", tempName);
                    getch();
                } break;
                          
              case 2: //remove via id numbers
                {
                  printf("\nEnter ID Numbers to remove: ");
                  scanf("%d", &tempID);
                  for (counter=0, found=0; counter<numbers && !found; counter++)
                  {
                    if (employee[counter].id == tempID)
                    {
                      found=1;
                      for (; counter<numbers; counter++)
                      {
                        strcpy(employee[counter].name, employee[counter+1].name);
                        employee[counter].id = employee[counter+1].id;
                      }
                      numbers--;
                    }
                  }
                  if (found)
                    printf("\nEmployee with ID Numbers %d deleted.", tempID);
                  else
                    printf("\nEmployee with ID Numbers %d not found.", tempID);
                    getch();
                } break;
                               
              default:
                {
                  printf("\nInvalid Command");
                  getch();
                } break;
            }
        } break;
                
      case 4: //edit entry
        {
          system ("cls");
          printf("EDIT ENTRY");
          printf("\n\n1. Edit Name\n2. Edit ID Numbers\n");
          scanf("%d", &choice2);
                   
          switch(choice2)
            {
              case 1: //edit via name
                {
                  printf("\nEnter name to edit: ");
                  scanf("%s", &tempName);
                  for (counter=0, found=0; counter<numbers && !found; counter++)
                  {
                    if (strcmp(employee[counter].name,tempName)==0)
                    {
                      found=1;
                      printf("Enter new name: ");
                      scanf("%s", &newName);
                      strcpy(employee[counter].name, newName);
                    }
                  }
                  if (found)
                    printf("\nEmployee %s is now %s.", tempName, newName);
                  else
                    printf("\nEmployee %s not found.", tempName);
                    getch();
                } break;
                          
              case 2: //edit via id numbers
                {
                  printf("\nEnter ID Numbers to edit: ");
                  scanf("%d", &tempID);
                  for (counter=0, found=0; counter<numbers && !found; counter++)
                  {
                    if (employee[counter].id == tempID)
                    {
                      found=1;
                      printf("Enter new ID Numbers: ");
                      scanf("%d", &newID);
                      employee[counter].id = newID;
                    }
                  }
                  if (found)
                    printf("\nID Numbers %d is now %d.", tempID, newID);
                  else
                    printf("\nID Numbers %d not found.", tempID);
                    getch();
                } break;
                               
              default:
                {
                  printf("\nInvalid Command");
                  getch();
                } break;
            }
        
        } break;
        
      case 5: //search entry
        {
          system ("cls");
          printf("SEARCH ENTRY");
          printf("\n\n1. Search via Name\n2. Search via ID Numbers\n");
          scanf("%d", choice2);
                   
          switch(choice2)
            {
              case 1: //search name
                {
                  printf("\nEnter name to search for: ");
                  scanf("%s", &tempName);
                  for (counter=0, found=0; counter<numbers && !found; counter++)
                  {
                    if (strcmp(employee[counter].name,tempName)==0)
                    {
                      found=1;
                    }
                  }
                  if (found)
                    printf("\nEmployee %s found.", tempName);
                  else
                    printf("\nEmployee %s not found.", tempName);
                    getch();
                } break;
                          
              case 2: //search id numbers
                {
                  printf("\nEnter ID Numbers to search for: ");
                  scanf("%d", &tempID);
                  for (counter=0, found=0; counter<numbers && !found; counter++)
                  {
                    if (employee[counter].id == tempID)
                    {
                      found=1;
                    }
                  }
                  if (found)
                    printf("\nID Numbers %d found.", tempID);
                  else
                    printf("\nID Numbers %d not found.", tempID);
                    getch();
                } break;
                               
              default:
                {
                  printf("\nInvalid Command");
                  getch();
                } break;
            }
        } break;
  
    }
    
  }while(choice!=6);

      
      
 
      
  }
}while (choice!=8); 
  
  
  
  system("PAUSE");	
  return 0;
}


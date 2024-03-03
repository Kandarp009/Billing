# Billing
#include <stdio.h>
#include <windows.h>

void printmenu(){
    char ch='*';
    printf("%c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c  %c",ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch);
    printf("\n%c\t\t\t IMPRESSO EXPRESSO\t\t\t       %c\n",ch,ch);
    printf("%c\t\t\t\t\t\t\t\t       %c\n%c  COFFEE  \t\t\t\t\tSNACKS\t\t       %c",ch,ch,ch,ch);
    printf("\n%c  1->Americano @200/-\t\t\t\t6->French Fries @300/- %c",ch,ch);
    printf("\n%c  2->Espresso @150/-\t\t\t\t7->Spicy Nachos @270/- %c",ch,ch);
    printf("\n%c  3->Latte @ 130/-\t\t\t\t8->Pasta @230/-        %c",ch,ch);
    printf("\n%c  4->Hot Chocolate @250/-\t\t\t9->Noodles @360/-      %c",ch,ch);
    printf("\n%c  5->Cappuccino @100/-\t\t\t\t10>Sandwich @220/-     %c",ch,ch);
    printf("\n%c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c %c  %c",ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch,ch);
}


int order(){
    char item[20],ans;
    int quantity[20];
    printf("\nHELLO!!! I AM HERE TO TAKE YOUR ORDER:)");
    printf("\nWhat would you like to have?:");
    scanf("%s",&item[0]);
    printf("How much quantity?");
    scanf("%d",&quantity[0]);
    for(int i=1;i<=20;i++){
        printf("Do you need something else?(y/n)");
        scanf("%c",&ans);
        if(ans=='y'){
            printf("What item?");
            scanf("%s",&item[i]);
            printf("How much quantity?");
            scanf("%d",&quantity[i]);
        }
        else if(ans=='n'){
            break;
        }
    }
    return 0;
}



void loadingbar(){
    //O - BLACK BACKGROUND
    //A - GREEN BACKGROUND

    system("color 0A");

    //Initialize char for printing
    //loading bar
    char a=177,b=219;
    printf("\n\n\n\n");
    printf("\n\n\n\n\t\t\t\t\tLoading...\n\n");
    printf("\t\t\t\t\t");

    //Print initial loading bar
    for (int i=0;i<26;i++){
        printf("%c",a);
    }

    //set the cursor again to starting
    //point of loading bar
    printf("\r");
    printf("\t\t\t\t\t");

    //Print loading bar progress
    for (int i=0;i<26;i++){
        printf("%c",b);

        //Sleep for 1 second
        Sleep(1000);

    }
}

/*BILL STRUCTURE:
        ~~~~~~~~~~~~~[IMPRESSO EXPRESSO]~~~~~~~~~~~~~~~
        Add: 123, Sindhu bahavan road, Ahmedabad-3800xx 
        Web: impexp.com
        Contact: 98754850xx
        Email: info@impexp.com
        ----------------------------------------------
                        *INVOICE*
        (+) BASE AMOUNT: {}
        (+) CGST: {} 
        (+) SGST: {}

        [*] FINAL AMOUNT: RS. {} /- ONLY
        ----------------------------------------------
                THANKS FOR VISITING!!
        COPYRIGHT (C) IMPRESSO EXPRESSO 20xx. 
        ALL RIGHTS RESERVED
        ----------------------------------------------
                GSTIN: 8897606704593xx
*/


int generatebill(){
    int n,q;
    printf("\n\n\n\nEnter the number of item:");
    scanf("%d",&n);
    printf("Quantity:");
    scanf("%d",&q);
    int BA,cgst,sgst,FA;
    switch (n){
        case 1:
        BA=200;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 2: BA=150;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 3: BA=130;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 4: BA=250;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 5: BA=100;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 6: BA=300;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 7: BA=270;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 8: BA=230;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 9: BA=360;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;

        case 10: BA=220;
        cgst=(BA/100)*9;
        sgst=(BA/100)*9;
        FA=BA+cgst+sgst;
        break;
    }
    printf("\n~~~~~~~~~~~~~~~~~~~[IMPRESSO EXPRESSO]~~~~~~~~~~~~~~~~~~~~");
    printf("\nAdd: 123, Sindhu bahavan road, Ahmedabad-3800xx");
    printf("\nWeb: impexp.com");
    printf("\nContact: 98754850xx");
    printf("\nEmail: info@impexp.com");
    printf("\n----------------------------------------------------------");
    printf("\n\t\t*INVOICE*");
    printf("\n(+)BASE AMOUNT: Rs.%d",BA);
    printf("\n(+)CGST: Rs.%d",cgst);
    printf("\n(+)SGST: Rs.%d",sgst);
    printf("\n\n[*]Final Amount: Rs.%d/- only",FA*q);
    printf("\n----------------------------------------------------------");
    printf("\n\t\tTHANKS FOR VISITING!!!");
    printf("\nCOPYRIGHT (C) IMPRESSO EXPRESSO 20xx.");
    printf("\nALL RIGHTS RESERVED");
    printf("\n----------------------------------------------------------");
    printf("\nGSTIN: 8897606704593xx");
    return 0;
}


int main(){
    printmenu();
    order();
    loadingbar();
    generatebill();
    return 0;
}

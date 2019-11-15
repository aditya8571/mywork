#include<iostream.h>
#include<conio.h>
#include<stdio.h>
#include<iomanip.h>
#include<stdlib.h>
void create_account();
void depo(double,int);
void withd(double,int);
void balance_enq();
void display(int);
float deposit,withdraw;
int n=0;
double acc_d=0,z;
struct bank
{ double acc_no;
  char name[25];
  double amount;
}s[100];
void main()
{ clrscr();
 cout<<"WELCOME\n*ACCOUNT MANAGEMENT SYSTEM*\n";
 int choice;
 for(;;)
 {
 cout<<"****MENU****\n";
 cout<<"1.Create new account\n";
 cout<<"2.Deposit amount\n";
 cout<<"3.Withdraw amount\n";
 cout<<"4.Balamce enquiry\n";
 cout<<"5.All account holder's list\n";
 cout<<"6.display account info\n";
 cout<<"7.Exit\n";
 cout<<"Select your choice\n";
 cin>>choice;

 switch(choice)
   { case 1: create_account();
			 break;
	 case 2: cout<<"Enter account number\n";
			 cin>>z;
			 for(int k=0;k<n;k++)
			 { if(z==s[k].acc_no)
			   goto label;
			 }
			 cout<<"Account not found\n";
			 goto label1;
			 label:
			 cout<<"Enter the amount to be deposited\n";
			 cin>>deposit;
			 depo(deposit,k);
			 label1:
			 break;
	 case 3: cout<<"Enter account number\n";
			 cin>>z;
			 for(int l=0;l<n;l++)
			 { if(z==s[l].acc_no)
			   goto jump;
			 }
			 cout<<"Account not found\n";
			 goto fly;
			 jump:
			 cout<<"Enter the amount to be withdrawn\n";
			 cin>>withdraw;
			 if(withdraw>s[l].amount)
			 { cout<<"Insufficient Balance\n";
			   cout<<"Current Balance "<<s[l].amount;
			   goto fly;
			 }
			 else
			 { withd(withdraw,l);
			 }
			  fly:
			  break;
	 case 4: balance_enq();
			 break;
	 case 5: for(int j=0;j<n;j++)
			 { cout<<j+1<<".";
			   puts(s[j].name);
			   cout<<"\n";
			 }
			  break;
	 case 6: cout<<"enter account number: \n";
			 cin>>z;
			 for(int v=0;v<n;v++)
			 { if(z==s[v].acc_no)
			   goto hi;
			 }
			 cout<<"account not found\n";
			 goto yo;
			 hi:
			 display(v);
			 yo:
			 break;
	 case 7: exit(0);
	 default:cout<<"Wrong choice\n";
   } getch();
 }

}
void create_account()
{ acc_d++;
  cout<<"Enter your name\n";
  gets(s[n].name);
  cout<<"ACCOUNT CREATED SUCESSFULLY\n";
  cout<<"Your account number is: "<<setw(8)<<setfill('0')<<acc_d<<endl;
  s[n].acc_no=acc_d;
  s[n].amount=0;
  cout<<"Initial balance is: "<<s[n].amount<<endl;
  n++;
}
void depo(double p,int q)
{
  cout<<"previos balance: "<<s[q].amount<<endl;
  s[q].amount+=p;
  cout<<"current balance: "<<s[q].amount<<setw(15)<<endl;
}
void withd(double p,int q)
{
  cout<<"previos balance: "<<s[q].amount<<endl;
  s[q].amount-=p;
  cout<<"current balance: "<<s[q].amount<<setw(15)<<endl;
}
void balance_enq()
{ cout<<"enter account number:\n";
  cin>>z;
  for(int m=0;m<n;m++)
  { if(z==s[m].acc_no)
	goto hello;
  }
  cout<<"Account not found\n";
  exit(0);
  hello:
  cout<<"your current balance is "<<s[m].amount<<endl;
}
void display(int x)
{ cout<<"Account holder's name: ";
  puts(s[x].name);
  cout<<"Account number: "<<setw(8)<<setfill('0')<<s[x].acc_no<<endl;
  cout<<"Current Balance: "<<s[x].amount<<endl;
}






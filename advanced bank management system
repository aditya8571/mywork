			/* BANK  MANAGEMENT */
#include<iostream.h>
#include<fstream.h>
#include<ctype.h>
#include<iomanip.h>    //***** header file used    ******
#include<conio.h>
#include<stdio.h>
		     //*****
		    // CLASS USED
		    //******
class account
{
int acno;
char name[50];
int deposit;
char type;
public:
void create_account()    //FUNCTION TO GET DATA FROM USER
{
cout<<"\n\n ENTER THE ACCOUNT NO.:-";
cin>>acno;
cout<<"\n \n ENTER THE NAME OF ACCOUNT HOLDER:-";
gets(name);
cout<<"\n \n ENTER THE TYPE OF ACCOUNT(C/S):-" ;
cin>>type;
type=toupper(type);
cout<<"\n \n Enter The Intial amount(>=1000 for Saving and for Current) >=2000):";
cin>>deposit;
cout<<"\n \n  Account Created.... " ;
}
void show_account()     //FUNCTION TO SHOW DATA
{
cout<<"\n Account no.  : " <<acno;
cout<<"\n \n The account holder’s  name is :- " ;
puts(name);
cout<<" \n \n Enter the type of account :-";
cout<<type;
cout<<"\n \n Balance amount: "<<deposit;
}
void modify()       //FUNCTION TO GET NEW DATA FROM USER
{cout<<"\n Account no.:"<<acno;
cout<<"\n \n Enter the name of account holder:" ;
gets(name);
cout<<"\n \n  Enter the type of account :";
cin>>type;
type=toupper(type);
cout<<"\n \n Enter the amount :";
cin>>deposit;
}
void dep(int x)    // function to accept amount and add to balance amount
{
deposit+=x;
}
void draw(int x)   // function to accept amount and subtract from  balance amount
{
deposit-=x;
}
void report()  //function to show data in tabular format 
{
cout<<acno<<setw(10)<<" "<<gets(name)<<setw(10)<<" "<<type<<setw(6)<<" "<< deposit <<endl;
}
int retacno()  //function to return account number 
{
return acno;
}
int redeposi()  // function to return balance amount
{
return deposit;
}
char rettype()  //function to return type of account 
{
 return type;
}

};
	    //**
	    //END OF CLASS
	    //**
     //********** FUNCTION DECLARATION**********//

void write_account(); //function record in a binary file
void display_sp(int); //function to display account details given by user
void modify_account(int); //function to modify record of a file
void delet_account(int);  //function to delete record of a file 
void display_all(); //function to display account details 
void deposit_withdraw(int,int); //function to deposit /withdraw amount for given account 
void intro();  //introductory screen function
	//********** MAIN FUNCTION OF A PROGRAM *******//

int main()
{
char ch, oho;
int num;
clrscr();
intro();
do
{
clrscr();
cout<<"\n MAIN MENU:-";
cout<<"\n \n \t 1. NEW ACCOUNT:-";
cout<<"\n \n \t 2.DEPOSIT AMOUNT:-";
cout<<"\n \n \t 3.WITHDRAW AMOUNT:-";
cout<<"\n \n \t 4. BALANCE ENQUIRY:-";
cout<<"\n \n \t 5.ALL ACCOUNT HOLDER LISTt:-";
cout<<"\n \n \t 6.CLOSE ACCOUNT:-";
cout<<"\n \n \t 7.MODIFY ACCOUNT:-";
cout<<"\n \n \t 8.EXIT:-";
cout<<"\n \n SELECT (1-8) FROM LIST:-";
cin>>oho;
cin>>ch;

switch(ch)
{case 1:
	 write_account();
	  break;
case 2:
       cout<<"\n Enter the account no.:-";
       cin>>num;
       deposit_withdraw(num,1);
       break;
case 3:
       cout<<"\n Enter the account no:-" ;
       cin>>num;
       deposit_withdraw(num,2);
       break;
case 4:
       cout<<"\n Enter the account no.:-";
       cin>>num;
       display_sp(num);
       break;
case 5:
       display_all();
       break;
case 6:
       cout<<"\n Enter the account no. :-";
       cin>>num;
       delet_account(num);
       break ;
case 7:
       cout<<"\n Enter the account no.:-";
       cin>>num;
       modify_account(num) ;
       break;
case 8:
       cout<<"\n THANK YOU";
       break;

default:
       cout<<"\a";
}
getch();
}while(ch!=8);
return 0;
}
		   //****
void write_account()
{
ofstream f;
f.open("account.dat",ios::binary|ios::app);
account ac;
f.write((char*)&ac,sizeof(ac)) ;
ac.create_account();
f.close();
}
		 //****
void display_sp(int n)
{
ifstream g;
g.open("account.dat",ios::binary);
account ac;
int flag=0;
cout<<"\n BALANCE ENQUIRY" ;
while(g.read((char*) & ac,sizeof(ac)))
{
g.read((char*)&ac,sizeof(ac));
if(ac.retacno()==n)
{
ac.show_account();
flag=1;
}
}
g.close();
if(flag==0)
cout<<"\n \n Account no. does not exist";
}
	    //****

void modify_account(int n)
{
fstream d;
d.open("account.dat",ios::binary|ios::in|ios::out);
account ac;
int found=0;
while(d.read((char*)&ac,sizeof(ac))&&found==0)
{
if(ac.retacno()==n)
{
ac.show_account();
cout<<"\n \n Enter the new details of account:";
ac.modify();
int pos=((-1)*sizeof(ac));                     
d.seekp(pos,ios::cur);                       
d.write((char*)&ac,sizeof(ac));                   
cout<<"\n \n Record Updated...";                     
found=1;                                              
}
}
d.close();
if(found==0)
cout<<"\n \n Record not found...";
}

			 //****
void delet_account(int n)
{
ifstream l;
ofstream m;
l.open("account.dat",ios::binary);
m.open("temp.dat",ios::binary);
l.seekg(0,ios::beg);
account ac;
while(l.read((char*)&ac,sizeof(ac)))
{
if(ac.retacno()!=n)
{
m.write((char*)&ac,sizeof(ac));
}
}
l.close();
m.close();
remove("account.dat");
rename("temp.dat","account.dat");
cout<<"\n \n Record Deleted...";


		      //****
void display_all()
{
ifstream c;
c.open("account.dat",ios::binary);
cout<<"\n \n \t ACCOUNT HOLDER LIST \n \n";
cout<<"=======================================";
cout<<" A/C no.        Name          Type           Balance  \n";
cout<<"=======================================";
account ac;
while(c.read((char*)&ac,sizeof(ac)))
{
ac.report();
}
c.close();
}

		   //****
void deposit_withdraw(int n,int option)
{
fstream e;
e.open("account.dat",ios::binary|ios::in|ios::out);
account ac;
int amt;
int found=0;
while(e.read((char*)&ac,sizeof(ac))&&found==0)
{
if(ac.retacno()==n)
{
ac.show_account();
if(option==1)
{
cout<<"\n \n \t TO  DEPOSIT AMOUNT";
cout<<"\n Enter the amount to be deposited-:";
cin>>amt;
ac.dep(amt);
}
if(option==2)
{
cout<<"\n \n TO WITHDRAW AMOUNT";
cout<<"\n \n Enter the amount to be to be withdraw:-";
cin>>amt;
int bal=ac.redeposi()-amt;
if((bal<500 && ac.rettype()=='s')||(bal<1000 && ac.rettype()=='c'))
cout<<"Insuffience balance";
else
ac.draw(amt);
}
int pos=((-1)*sizeof(ac));
e.seekp(pos,ios::cur);
e.write((char*)& ac,sizeof(ac));
cout<<"\n \n Record Updated"  ;
found=1;
}
}
e.close();
if (found==0)
cout<<"\n Record not found......";
}
			//****
void intro()
{
cout<<"\n \t BANK ";
cout<<"\n \t MANAGEMENT";
cout<<"\n \t SYSTEM";

};
}		 //end of project

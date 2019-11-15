
#include<iostream.h>
#include<conio.h>     
#include<stdlib.h>
void main()
{
int a,b=0,i,t,score=0,d=0,e,f,g,score1=0;
char p;
clrscr();
cout<<"Welcome to Cricket Game\n";
cout<<"Instructions\n1.You can't choose numbers greater than 6\n";
cout<<"2.You'll be choosing numbers in order to score runs\n";
cout<<"3.If your number and computer's number clashes then the batsman is out\n";
cout<<"4.Computer will choose random numbers\n";
cout<<"Get ready for toss\nPRESS ANY KEY TO CONTINUE\n";
getch();
cout<<"Choose Even or Odd\n";
cout<<"Enter e for even and o for odd\n";
cin>>p;
label:
cout<<"Enter a number\n";
cin>>a;
if(a>6)
{ cout<<"Invalid Entry\n";
  goto label;
}
randomize();
t=rand()%7;
cout<<"Computer's number is "<<t<<"\n";
switch(p)
{ case 'o':
  if((t+a)%2==0)
  cout<<"Computer won the tose\n";
	  else
		 { cout<<"User won the tose\n";
		  b=1;
		 } break;
  case 'e':
  if((t+a)%2==0)
 { cout<<"User won the tose\n";
   b=1;
   }
	 else
		 cout<<"Computer won the tose\n";
		 break ;
}
if(b==0)
{ int c;
  randomize();
 c=rand()%2;
  if(c==0)
  {
   cout<<"Computer chose to bat\n";
   d=1;
  }
   else
   {
	   cout<<"Computer chose to ball\n";
	   d=2;
   }
}
 else
	{label1:
	 cout<<"What will you choose ?\n";
	 cout<<"ball or bat?\nEnter 1 to bat and 0 to ball\n";
	 cin>>e;
	 if(e>1)
	 {cout<<"Invalid Entry\n";
	  goto label1;
	 }
	 if(e==1)
	  d=3;
	 else
		d=4;
	 }
	  if(d==1||d==4)
	  {
	   cout<<"Computer is batting first\n";
	   while(f!=g)
	   { label2:
		 cout<<"Enter a number\n";
		 cin>>f;
		 if(f>6)
		 { cout<<"Invalid Entry\n";
		   goto label2;
		 }
		 randomize();
		 g=rand()%7;
		 cout<<"PC\t"<<g<<"\n";
		 if(g!=f)
		 score+=g;
		 else
		 {	cout<<"THAT'S OUT\n";
		 }
	   cout<<"Computer's score is "<<score<<"\n";
	  }
	   cout<<"It's your batting now\n";
	   f=0;
	   g=1;
	   while(f!=g)
	   { label3:
		 cout<<"Enter a number\n";
		 cin>>f;
		 if(f>6)
		 { cout<<"Indalid Entry\n";
		   goto label3;
		 }
		 randomize();
		 g=rand()%7;
		 cout<<"PC\t"<<g<<"\n";
		 if(g!=f)
		 score1+=f;
		 if(g==f)
		 { cout<<"THAT'S OUT\n";
		   break;
		 }cout<<"Your score is "<<score1<<"\n";
		  if(score1>score)
		  break;
		}
		 if(score1>score)
		 cout<<"**CONGRATULATIONS**\nYOU WON\n";
		 if(score1<score)
		 cout<<"COMPUTER WON\n";
		 if(score==score1)
		 cout<<"Match Draw!!!!\n";
		}
		if(d==2||d==3)
		{ cout<<"User will bat first\n";
		  while(f!=g)
		  { label4:
			cout<<"Enter a number\n";
			cin>>f;
			if(f>6)
			{ cout<<"Invalid Entry\n";
			  goto label4;
			}
			randomize();
			g=rand()%7;
			cout<<"PC\t"<<g<<"\n";
			if(f!=g)
			{ score1+=f;
			}
			 else
			 cout<<"THAT'S OUT\n";
		   cout<<"User's score is "<<score1<<endl;
		   }
		   cout<<"Computer will bat now\n";
		   f=1;
		   g=0;
		   while(f!=g)
		   { label5:
			 cout<<"Enter a number\n";
			 cin>>f;
			 if(f>6)
			 { cout<<"Invalid Entry\n";
			   goto label5;
			 }
			 randomize();
			 g=rand()%7;
			 cout<<"PC\t"<<g<<"\n";
			 if(f!=g)
			 { score+=g;
			 }
			 if(f==g)
			 { cout<<"THAT'S OUT\n";
			 }
			 if(score>score1)
			 { break;
			 }
		   cout<<"Computer's score is "<<score<<"\n";
		   }
		   if(score>score1)
		   cout<<"COMPUTER WON\n";
		   if(score<score1)
		   cout<<"**CONGRATULATIONS**\nYOU WON\n";
		   if(score==score1)
		   cout<<"Match Draw!!!!\n";
		}  cout<<"Thank You For Playing\n";
		getch();
}











<div align="center">

## Hotel Management Program


</div>

### Description

This is simple program to handle the reservation of rooms and to handle the bills for customers in hotel
 
### More Info
 
works in boroland c++ only you need to miodify the code if you want to use it in visual c++


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[jasbir singh](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jasbir-singh.md)
**Level**          |Intermediate
**User Rating**    |4.0 (16 globes from 4 users)
**Compatibility**  |C\+\+ \(general\), Borland C\+\+
**Category**       |[Complete Applications](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/complete-applications__3-7.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jasbir-singh-hotel-management-program__3-5323/archive/master.zip)





### Source Code

```
#include<iostream.h>
#include<conio.h>
#include<ctype.h>
#include<string>
#include<stdlib.h>
#include<fstream.h>
#include<iomanip.h>
#include<time.h>
#include<string.h>
#include<dos.h>
#include<stdio.h>
const char *filename="information.txt";
const char *file="rooms.txt";
const char *account="accounting.txt";
const char *ship="shipping.txt";
const char *party="party.txt";
using namespace std;
class hotel
{
private:
//string name;
//string family;
//string city;
//string telephone;
//int time;
//char type_room;
//double cost_perday;
int single;
int doubler;
int triple;
public:
ifstream infile,in,inp;
ofstream outfile,out,outp;
//ifstream in;
//ofstream out;
//ifstream inp;
//ofstream outp;
//ifstream partin;
//ofstream partout;
void menu(void);
void submenu(void);
void accounting(void);
void bill(void);
void shipping(void);
void display(void);
hotel(){single=100;doubler=200;triple=100;};
~hotel(){};
};
class information:public hotel
{
public:
string name;
string family;
string city;
string telephone;
int time;
char type_room;
double cost_perday;
//int single;
//int doubler;
//int triple;
};
void hotel::menu(void)
{
clrscr();
char selection;
//display();
textcolor(YELLOW);
gotoxy(5,2);
cprintf("****************************************************************");
gotoxy(28,3);
cprintf("International Relaxon Hotal.");
gotoxy(28,4);
cprintf("R-> Reservation.");
gotoxy(28,5);
cprintf("A-> Accounting.");
gotoxy(28,6);
cprintf("S-> Shipping.");
gotoxy(28,7);
cprintf("B-> Bill.");
gotoxy(28,8);
cprintf("Q-> Quit.");
gotoxy(5,9);
cprintf("This software is licensed to Relaxon Hotel by College,Offfice of");
gotoxy(28,10);
cprintf("Software Development");
gotoxy(5,11);
cprintf("****************************************************************");
gotoxy(5,12);
cprintf("Enter your choose: ");
cin>>selection;
cin.get();
selection=(char)toupper(selection);
switch(selection)
{
case 'R':
{
 submenu();
 break;
}
case 'A':
{
accounting();
break;
}
case 'S':
{
shipping();
break;
}
case 'B':
{
bill();
break;
}
case 'Q':
{
exit(1);
break;
}
default:
{
menu();
}
}
}
void hotel::submenu(void)
{
information n;
char choose;
int number=0;
int room;
char continues;
outfile.open (filename,ios::out|ios::app);
outfile.close();
do
{
int single=100;
int doubler=200;
int triple=100;
clrscr();
textcolor(YELLOW);
//display();
//gotoxy(55,1);
//cout<<system("date");
gotoxy(30,3);
cprintf("*******************");
gotoxy(30,4);
cprintf("  Reservation  ");
gotoxy(30,5);
cprintf(" --------------- ");
gotoxy(30,6);
cprintf("  S->Single  ");
gotoxy(30,7);
cprintf("  D->Double  ");
gotoxy(30,8);
cprintf("  T->Triple  ");
gotoxy(30,9);
cprintf("  C->Salon   ");
gotoxy(30,10);
cprintf("  Q->Quit   ");
gotoxy(30,11);
cprintf("*******************");
gotoxy(25,13);
cprintf("Enter the Type of Room you want: ");
cin>>choose;
cin.get();
choose=(char)toupper(choose);
n.type_room=choose;
int account_s=0;
int account_d=0;
int account_t=0;
int r_number;
char type;
string r_name;
string r_family;
string r_city;
string r_telephone;
int r_time;
double r_price;
if (choose=='S'||choose=='D'||choose=='T')
{
infile.open(filename,ios::in);
if (infile==NULL)
cout<<"Error opening the file"<<endl;
while(!infile.eof())
{
infile>>r_number>>r_name>>r_family>>r_city>>r_telephone>>type>>r_price>>r_time;
if(type=='S')
{
account_s++;
}
if (type=='D')
{
account_d++;
}
if (type=='T')
{
account_t++;
}
}
single=single-account_s;
doubler=doubler-account_d;
triple=triple-account_t;
infile.close();
if (type=='S')
{
single=single+1;
}
if (type=='D')
{
doubler=doubler+1;
}
if (type=='T')
{
triple=triple+1;
}
if (n.type_room=='S')
{
 if (single!=0)
 {
 cout<<"Total single bed available is "<<single;
 cout<<"\nHow many single bed you need?";
 cin>>number;
 }
 else
 {
 cout<<"\nSorry,No Room available,Try at YMCA";
 }
}
if (n.type_room=='D')
{
 if (doubler!=0)
 {
 cout<<"Total double bed available is "<<doubler;
 cout<<"\nHow many double bed you need?";
 cin>>number;
 }
 else
 {
 cout<<"\nSorry,no room available,try at YMCA";
 }
}
if (n.type_room=='T')
{
 if (triple!=0)
 {
 cout<<"Total triple bed available is "<<triple;
 cout<<"\nHow many bed you need?";
 cin>>number;
 }
 else
 {
 cout<<"Sorry,no any room Available,Try at YMCA";
 }
}
cin.get();
cout<<"First Name : ";
cin>>n.name;
cout<<"Family Name : ";
cin>>n.family;
cout<<"City : ";
cin>>n.city;
cout<<"Tel : ";
cin>>n.telephone;
cout<<"Charge :";
cin>>n.cost_perday;
cout<<"Days : ";
cin>>n.time;
int flag=0;
for (int i=1;i<=number;i++)
{textcolor(YELLOW);
cprintf("Room NO.: ");
cin>>room;
if (n.type_room=='S')
{
 if(room<100 || room>199)
 {textcolor(YELLOW);
  cprintf("You Should Choose The Number Between 100 And 199");
  cout<<endl;
  i=i-1;
  continue;
 }
infile.open(filename,ios::in);
while (!infile.eof())
{
infile>>r_number>>r_name>>r_family>>r_city>>r_telephone>>type>>r_price>>r_time;
if (room==r_number)
 {textcolor(YELLOW);
 cprintf("You Should Choose Other Room.This is occupied.");
 cout<<endl;
 flag=1;
 i=i-1;
 break;
 }
else
{flag=0;}
}
infile.close();
if (flag==1)
{
continue;
}
}
if (n.type_room=='D')
{
 if(room<200 || room>399)
 {textcolor(YELLOW);
  cprintf("YOU Should Choose The Number Between 200 And 399");
  cout<<endl;
  i=i-1;
  continue;
 }
infile.open(filename,ios::in);
while (!infile.eof())
{
infile>>r_number>>r_name>>r_family>>r_city>>r_telephone>>type>>r_price>>r_time;
if (room==r_number)
 {textcolor(YELLOW);
 cprintf("You must choose other room.This is occupied.");
 cout<<endl;
 flag=1;
 i=i-1;
 break;
 }
else
{flag=0;}
}
infile.close();
if (flag==1)
{
continue;
}
}
if (n.type_room=='T')
{
 if(room<400 || room>499)
 { textcolor(YELLOW);
  cprintf("You should Choose The Number Between 400 And 499");
  cout<<endl;
  i=i-1;
  continue;
 }
infile.open(filename,ios::in);
while (!infile.eof())
{
infile>>r_number>>r_name>>r_family>>r_city>>r_telephone>>type>>r_price>>r_time;
if (room==r_number)
 { textcolor(YELLOW);
 cprintf("You Should choose other room.This is occupied.");
 cout<<endl;
 flag=1;
 i=i-1;
 break;
 }
else
{flag=0;}
}
infile.close();
if (flag==1)
{
continue;
}
}
outfile.open (filename,ios::out|ios::app);
outfile<<room<<" ";
outfile<<n.name<<" ";
outfile<<n.family<<" ";
outfile<<n.city<<" ";
outfile<<n.telephone<<" ";
outfile<<n.type_room<<" ";
outfile<<n.cost_perday<<" ";
outfile<<n.time<<endl;
outfile.close();
}
cprintf("The Reservation Is Finished");
cout<<endl;
}
double party_price,party_time;
string party_date;
double cost,duration,total=0;
string pdate,ptime;
outp.open(party,ios::out|ios::app);
outp.close();
int different=0;
if (choose=='C')
{
cout<<endl;
cout<<"Duration: ";
cin>>party_time;
cout<<"Price(per hour): ";
cin>>party_price;
cout<<"Date(DD/MM): ";
cin>>party_date;
cout<<endl<<endl;
total=party_time*party_price*(1+0.05);
cout<<"**********************"<<endl;
cout<<"Total: "<<total<<endl;
cout<<"**********************"<<endl;
inp.open(party,ios::in);
if (inp==NULL)
cout<<"Error opening the file"<<endl;
while(!inp.eof())
{
inp>>duration>>cost>>pdate;
if (pdate==party_date)
{
different=1;
textcolor(RED);
cprintf("The party time is conflicted.Please choose another time.");
cout<<endl;
break;
}
}
inp.close();
if (different==0)
{
outp.open(party,ios::out|ios::app);
outp<<party_time<<" ";
outp<<party_price<<" ";
outp<<party_date<<endl;
outp.close();
}
}
if (choose=='Q')
{
menu();
}
clrscr();
cout<<"First Name of Customer is:"<<n.name<<endl;
cout<<"Family Name of Customer : "<<n.family<<endl;
cout<<"City Name : "<<n.city<<endl;
cout<<"Telephone number : "<<n.telephone<<endl;
cout<<"Charge Per Day :"<<n.cost_perday<<endl;
cout<<"Number of Days of Reservation : "<<n.time<<endl;
cout<<"The Room Number Which is Reserved is:"<<room<<endl;
textcolor(YELLOW);
total=party_time*party_price*(1+0.05);
//cout<<"**********************"<<endl;
//cout<<"Total: "<<total<<endl;
//cout<<"**********************"<<endl;
cprintf("Another Reservation? (Y/N)");
cin>>continues;
}while (continues=='y'||continues=='Y');
menu();
}
void hotel::bill(void)
{
int temp_room,n=3,r_number,amount;
char type;
string temp_name;
string r_name;
string r_family;
string r_city;
string r_telephone;
int r_time;
double r_price;
double total,discount,sum=0,tax;
double service_tax,sub_total;
int i;
textcolor(YELLOW);
cout<<endl;
gotoxy(5,15);
cprintf("How many rooms you want to pay ? ");
cin>>amount;
for (int k=0;k<amount;k++)
{
gotoxy(5,16+i);
cprintf("Please input the room number: ");
cin>> temp_room;
}
clrscr();
infile.open(filename,ios::in);
//display();
gotoxy(33,n);
cout<<"Customer Information"<<endl;
gotoxy(0,n++);
 for (int i=0;i<78;i++)
 {cout<<"_";}
 cout<<endl;
 gotoxy(0,n++);
 cout<<"|"<<setw(4)<<"NO."<<"|"<<setw(12)<<"First Name"<<"|"<<setw(12)<<"Family Name"<<"|"<<setw(10)<<"City"<<"|"<<setw(15)<<"Telephone"<<"|"<<setw(5)<<"Type"<<"|"<<setw(6)<<"Price"<<"|"<<setw(6)<<"Days"<<"|";
 cout<<endl;
 gotoxy(0,n++);
 cout<<"|";
 for (int l=1;l<78;l++)
 {cout<<"_";}
 cout<<"|";
int nobody=0;
for (int m=0;m<amount;m++)
{
while (!infile.eof())
{
infile>>r_number>>r_name>>r_family>>r_city>>r_telephone>>type>>r_price>>r_time;
if (temp_room==r_number )
 {
 cout<<endl;
 gotoxy(0,n++);
 cout<<"|"<<setw(4)<<r_number<<"|"<<setw(13-r_name.length())<<r_name<<"|"<<setw(13-r_family.length())<<r_family<<"|"<<setw(11-r_city.length())<<r_city<<"|"<<setw(16-r_telephone.length())<<r_telephone<<"|"<<setw(5)<<type<<"|"<<setw(6)<<r_price<<"|"<<setw(6)<<r_time<<"|";
 cout<<endl;
 gotoxy(0,n++);
 cout<<"|";
 for (int i=0;i<77;i++)
 {cout<<"_";}
 cout<<"|";
 sum=sum+r_price*r_time;
 nobody=1;
 break;
 }
 else
 {
 nobody=0;
 }
}
if (nobody==0)
{
cout<<"\nThe room "<<temp_room<<" is empty.";
}
}
infile.close();
if (sum>0 && sum<=500)
{total=sum*(1+0.15+0.05);
 discount=0;
 tax=sum*0.15;
 service_tax=sum*0.05;
}
else
{
if (sum<=1000)
{discount=sum*0.1;
 total=sum*(1+0.15+0.05-0.1);
 tax=sum*0.15;
 service_tax=sum*0.05;
}
else
{
if (sum<=5000)
{discount=sum*0.15;
 total=sum*(1+0.15+0.05-0.15);
 tax=sum*0.15;
 service_tax=sum*0.05;
}
else
{discount=sum*0.2;
 total=sum*(1+0.15+0.05-0.2);
 tax=sum*0.15;
 service_tax=sum*0.05;
}
}
}
cout<<endl<<endl<<endl;
cout<<"----------------------"<<endl;
cout<<"Sub Total : "<<sum<<endl;
cout<<"Discount : "<<discount<<endl;
cout<<"Tax : "<<tax<<endl;
cout<<"Service Tax : "<<service_tax<<endl;
cout<<"Total : "<<total<<endl;
cout<<"----------------------"<<endl;
cout<<"\nPress any key to return main menu.";
getch();
int comp=0;
for (int i=0;i<amount;i++)
{infile.open(filename,ios::in);
while (infile)
{
infile>>r_number>>r_name>>r_family>>r_city>>r_telephone>>type>>r_price>>r_time;
if (temp_room!=r_number && r_number!=comp )
 {
  out.open(file,ios::out|ios::app);
  out<<r_number<<" ";
  out<<r_name<<" ";
  out<<r_family<<" ";
  out<<r_city<<" ";
  out<<r_telephone<<" ";
  out<<type<<" ";
  out<<r_price<<" ";
  out<<r_time<<endl;
  out.close();
 }
 else
 {continue;}
 comp=r_number;
}
infile.close();
system ("del information.txt");
system ("ren rooms.txt information.txt");
}
menu();
}
void hotel::accounting(void)
{
char choose;
double price_hour;
double hours,deduction=0,total_payroll=0;
char employee_type;
double employee_hour;
double employee_deduction;
double employee_pay;
int temp=0;
clrscr();
out.open(account,ios::out|ios::app);
out.close();
//display();
textcolor(YELLOW);
gotoxy(25,4);
cprintf("********************************");
gotoxy(25,5);
cprintf("*     Accounting     *");
gotoxy(25,6);
cprintf("* -------------------------- *");
gotoxy(25,7);
cprintf("*     Secretary->S     *");
gotoxy(25,8);
cprintf("*     Security->C     *");
gotoxy(25,10);
cprintf("* Maintenance & Cleaners->M  *");
gotoxy(25,9);
cprintf("*     Quit->Q       *");
gotoxy(25,11);
cprintf("********************************");
gotoxy(25,12);
cprintf("Enter the type of jobs. ");
cin>>choose;
choose=(char)toupper(choose);
switch (choose)
{
case 'S':
{
 price_hour=8;
 break;
}
case 'C':
{
price_hour=6.75;
break;
}
case 'M':
{
price_hour=10;
break;
}
case 'Q':
{
menu();
}
default:
{
cout<<"Please try again";
getch();
menu();
}
}
gotoxy(25,14);
cprintf("Enter the work hours: ");
cin>>hours;
deduction=hours*price_hour*0.2;
total_payroll=hours*price_hour*(1-0.2);
in.open(account,ios::in);
if (in==NULL)
cout<<"Error opening the file"<<endl;
char flag;
while(!in.eof())
{
in>>employee_type>>employee_hour>>employee_deduction>>employee_pay;
if (employee_type==choose && temp==0)
{
hours=employee_hour+hours;
deduction=employee_deduction+deduction;
total_payroll=employee_pay+total_payroll;
temp++;
}
if (employee_type!=choose && flag!=employee_type )
{
 outp.open(file,ios::out|ios::app);
 outp<<employee_type<<" ";
 outp<<employee_hour<<" ";
 outp<<employee_deduction<<" ";
 outp<<employee_pay<<endl;
 outp.close();
}
flag=employee_type;
}
in.close();
outp.open(file,ios::out|ios::app);
outp<<choose<<" ";
outp<<hours<<" ";
outp<<deduction<<" ";
outp<<total_payroll<<endl;
outp.close();
system ("del accounting.txt");
system ("ren rooms.txt accounting.txt");
clrscr();
int n=3;
in.open(account,ios::in);
gotoxy(33,2);
cout<<"Employee Accounting"<<endl;
 gotoxy(15,n++);
 for (int i=0;i<51;i++)
 {cout<<"_";}
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|"<<setw(15)<<"Employee Type"<<"|"<<setw(12)<<"Hours Worked"<<"|"<<setw(10)<<"Deduction"<<"|"<<setw(10)<<"Pay Roll"<<"|";
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|";
 for (int i=1;i<51;i++)
 {cout<<"_";}
 cout<<"|";
 char flag1;
 while(!in.eof())
{
in>>employee_type>>employee_hour>>employee_deduction>>employee_pay;
if (employee_type=='S' && flag1!='S' )
{
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|"<<setw(15)<<"Secretary"<<"|"<<setw(12)<<employee_hour<<"|"<<setw(10)<<employee_deduction<<"|"<<setw(10)<<employee_pay<<"|";
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|";
 for (int i=0;i<50;i++)
 {cout<<"_";}
 cout<<"|";
 flag1=employee_type;
 continue;
}
if (employee_type=='C' && flag1!='C')
{
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|"<<setw(15)<<"Security"<<"|"<<setw(12)<<employee_hour<<"|"<<setw(10)<<employee_deduction<<"|"<<setw(10)<<employee_pay<<"|";
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|";
 for (int i=0;i<50;i++)
 {cout<<"_";}
 cout<<"|";
 flag1=employee_type;
 continue;
}
if (employee_type=='M' && flag1!='M')
{
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|"<<setw(15)<<"Maintenance"<<"|"<<setw(12)<<employee_hour<<"|"<<setw(10)<<employee_deduction<<"|"<<setw(10)<<employee_pay<<"|";
 cout<<endl;
 gotoxy(15,n++);
 cout<<"|";
 for (int i=0;i<50;i++)
 {cout<<"_";}
 cout<<"|";
 flag1=employee_type;
 continue;
}
}
in.close();
getch();
cout<<"Press any key to return main menu.";
cin.get();
menu();
}
void hotel:: shipping(void)
{
char choose;
string type,branch;
double charge;
double taxi_money,ship_money,total_taxi=0,total_ship=0;
double claimed,fee;
int j;
out.open(ship,ios::out|ios::app);
out.close();
clrscr();
//display();
textcolor(YELLOW);
gotoxy(33,4);
cprintf("****************");
gotoxy(33,5);
cprintf("  Shipping  ");
gotoxy(33,6);
cprintf(" ------------ ");
gotoxy(33,7);
cprintf("  Taxi->T  ");
gotoxy(33,8);
cprintf(" Shipping->S ");
gotoxy(33,9);
cprintf("  Quit->Q  ");
gotoxy(33,10);
cprintf("****************");
gotoxy(33,11);
cprintf("Enter Your Choice. ");
cin>>choose;
choose=(char)toupper(choose);
gotoxy(33,13);
cprintf("Enter The money to be Charged.");
cin>>charge;
switch (choose)
{
case 'T':
{
 type="Taxi";
 taxi_money=charge*0.1;
 break;
}
case 'S':
{
type="Shipper";
ship_money=charge*(1+0.1);
break;
}
case 'Q':
{
//exit(1);
menu();
}
default:
{
cout<<"Wrong key pressed, Try again";
getch();
menu();
exit(1);
}
}
out.open(ship,ios::out|ios::app);
if (choose=='T')
{out<<type<<" ";
 out<<charge<<" ";
 out<<taxi_money<<endl;
}
if (choose=='S')
{
out<<type<<" ";
out<<charge<<" ";
out<<ship_money<<endl;
}
//if(choose=='Q')
//{
//exit(1);
//}
out.close();
clrscr();
int n=3;
gotoxy(33,2);
cout<<"Taxi and Shipping"<<endl;
 gotoxy(12,n++);
 for (int i=0;i<58;i++)
 {cout<<"_";}
 cout<<endl;
 gotoxy(12,n++);
 cout<<"|"<<setw(30)<<"Branches(Taxi,Shipping)"<<"|"<<setw(15)<<"Amount Claimed"<<"|"<<setw(10)<<"Hotel Fee"<<"|";
 cout<<endl;
 gotoxy(12,n++);
 cout<<"|";
 for (int i=1;i<58;i++)
 {cout<<"_";}
 cout<<"|";
in.open(ship,ios::in);
 while(!in.eof())
{
 in>>branch>>claimed>>fee;
 if (branch=="Taxi" )
 {
 total_taxi=total_taxi+fee;
 }
 if (branch=="Shipper" )
 {
 total_ship=total_ship+fee;
 }
 cout<<endl;
 gotoxy(12,n++);
 j=n ;
 cout<<"|"<<setw(31-branch.length())<<branch<<"|"<<setw(15)<<claimed<<"|"<<setw(10)<<fee<<"|";
 cout<<endl;
 gotoxy(12,n++);
 cout<<"|";
 for (int i=0;i<57;i++)
 {cout<<"_";}
 cout<<"|";
}
 cout<<endl;
 gotoxy(12,j-1);
 cout<<"|"<<setw(30)<<" "<<"|"<<setw(15)<<" "<<"|"<<setw(10)<<" "<<"|";
 cout<<endl;
 gotoxy(12,j+1);
 cout<<"|";
 for (int i=0;i<57;i++)
 {cout<<"_";}
 cout<<"|";
 cout<<endl;
 gotoxy(12,j++);
 cout<<"|"<<setw(30)<<"Total taxi income"<<"|"<<setw(15)<<""<<"|"<<setw(10)<<total_taxi<<"|";
 cout<<endl;
 gotoxy(12,j++);
 cout<<"|";
 for (int i=0;i<57;i++)
 {cout<<"_";}
 cout<<"|";
 cout<<endl;
 gotoxy(12,j++);
 cout<<"|"<<setw(30)<<"Total ship income"<<"|"<<setw(15)<<""<<"|"<<setw(10)<<total_ship<<"|";
 cout<<endl;
 gotoxy(12,j++);
 cout<<"|";
 for (int i=0;i<57;i++)
 {cout<<"_";}
 cout<<"|";
 cout<<endl<<"Press any key to return main menu.";
getch();
menu();
}
void display(void)
{
time_t t;
time(&t);
gotoxy(55,1);
textcolor(YELLOW);
cprintf("%s",ctime(&t));
}
int main()
{
hotel custom;
custom.menu();
getch();
return 0;
}
```


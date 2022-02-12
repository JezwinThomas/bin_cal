#include <LiquidCrystal.h>

LiquidCrystal lcd(7, 6, 5, 4, 3, 2); 

int buttonState = LOW;
int dispMode = 1;
int lightMode=1;

int a[4]={0,0,0,0};
int b[4]={0,0,0,0};
int a_dec=0;
int b_dec=0;
int sum_bin[4];
int sum_dec=0;

void setup() 
{
  pinMode(13,INPUT); //button 1
  pinMode(12,INPUT); //button 2
  pinMode(11,INPUT); //button 3
  pinMode(10,INPUT); //button 4
  pinMode(9,INPUT);  //button 5
  lcd.begin(16, 2);
  pinMode(1,OUTPUT);
  delay(100);
  digitalWrite(1,HIGH);
  lcd.print("bin_cal");
  delay(2000);
  lcd.clear();
}

void loop() 
{
 
  buttonState = digitalRead(9); //LED
  if(buttonState==HIGH)
  {
    toggle();
  }
  
  
  buttonState = digitalRead(10); 
  if(buttonState==HIGH)
  {
    disp();
  }
  
  button3:
  buttonState = digitalRead(11); 
  if(buttonState==HIGH)
  {
    if(dispMode==2)
    {
      if(a[3]==0) a[3]=1;
      else a[3]=0;
      lcd.clear();
      lcd.print("No 1 : ");
      lcd.print(a[1]);
      lcd.print(a[2]);
      lcd.print(a[3]);
      a_dec=a[1]*4+a[2]*2+a[3];
      lcd.setCursor(0,1);
      lcd.print("Dec : ");
      lcd.print(a_dec);
      delay(250);
      goto button3;
      
    }
    if(dispMode==3)
    {
      if(b[3]==0) b[3]=1;
      else b[3]=0;
      lcd.clear();
      lcd.print("No 2 : ");
      lcd.print(b[1]);
      lcd.print(b[2]);
      lcd.print(b[3]);
      b_dec=b[1]*4+b[2]*2+b[3]; 
      lcd.setCursor(0,1);
      lcd.print("Dec : ");
      lcd.print(b_dec);
      delay(250);
      goto button3;
      
    }
  }

  button2:
  buttonState = digitalRead(12); 
  if(buttonState==HIGH)
  {
    if(dispMode==2)
    {
      if(a[2]==0) a[2]=1;
      else a[2]=0;
      lcd.clear();
      lcd.print("No 1 : ");
      lcd.print(a[1]);
      lcd.print(a[2]);
      lcd.print(a[3]);
      a_dec=a[1]*4+a[2]*2+a[3];
      lcd.setCursor(0,1);
      lcd.print("Dec : ");
      lcd.print(a_dec);
      delay(250);
      goto button2;
      
    }
    if(dispMode==3)
    {
      if(b[2]==0) b[2]=1;
      else b[2]=0;
      lcd.clear();
      lcd.print("No 2 : ");
      lcd.print(b[1]);
      lcd.print(b[2]);
      lcd.print(b[3]);
      b_dec=b[1]*4+b[2]*2+b[3]; 
      lcd.setCursor(0,1);
      lcd.print("Dec : ");
      lcd.print(b_dec);
      delay(250);
      goto button2;
      
    }
  }

  button1:
  buttonState = digitalRead(13); 
  if(buttonState==HIGH)
  {
    if(dispMode==2)
    {
      if(a[1]==0) a[1]=1;
      else a[1]=0;
      lcd.clear();
      lcd.print("No 1 : ");
      lcd.print(a[1]);
      lcd.print(a[2]);
      lcd.print(a[3]);
      a_dec=a[1]*4+a[2]*2+a[3];
      lcd.setCursor(0,1);
      lcd.print("Dec : ");
      lcd.print(a_dec);
      delay(250);
      goto button1;
      
    }
    if(dispMode==3)
    {
      if(b[1]==0) b[1]=1;
      else b[1]=0;
      lcd.clear();
      lcd.print("No 2 : ");
      lcd.print(b[1]);
      lcd.print(b[2]);
      lcd.print(b[3]);
      b_dec=b[1]*4+b[2]*2+b[3]; 
      lcd.setCursor(0,1);
      lcd.print("Dec : ");
      lcd.print(b_dec);
      delay(250);
      goto button1;
      
    }
  }
  
  delay(200);
}    

void toggle() 
{
  if(lightMode==1)
  {
    digitalWrite(1,LOW);
    lightMode=2;
  }  
  else if(lightMode==2)
  {
    digitalWrite(1,HIGH);
    lightMode=1;
  }
  delay(100);
}

void disp() 
{
  a_dec=a[1]*4+a[2]*2+a[3];
  b_dec=b[1]*4+b[2]*2+b[3]; 
  if(dispMode==1)
  {
   lcd.clear();
   lcd.print("No 1 : ");
   lcd.print(a[1]);
   lcd.print(a[2]);
   lcd.print(a[3]);
   lcd.setCursor(0,1);
   lcd.print("Dec : ");
   lcd.print(a_dec);
   dispMode=2;
  }
  else if(dispMode==2)
  {
   lcd.clear();
   lcd.print("No 2 : ");
   lcd.print(b[1]);
   lcd.print(b[2]);
   lcd.print(b[3]);
   lcd.setCursor(0,1);
   lcd.print("Dec : ");
   lcd.print(b_dec);
   dispMode=3;
  }
  else if(dispMode==3)
  {
   lcd.clear();
   sum();
   lcd.print("sum = ");
   for(int i=3;i>=0;i--)
   {
     lcd.print(sum_bin[i]);
   }
   lcd.setCursor(0,1);
   lcd.print("Dec : ");
   lcd.print(sum_dec);
   dispMode=1;
  }
}

void sum() 
{
  a_dec=a[1]*4+a[2]*2+a[3];
  b_dec=b[1]*4+b[2]*2+b[3];  
  sum_dec=a_dec+b_dec;

  int i=0;
  int temp = sum_dec;
  while(temp>0)
  {
    sum_bin[i]=temp%2;
    temp/=2;
    i++;
  }
}

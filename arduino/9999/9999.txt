
#include <GyverTimers.h>
//заняты все цифровые пины от 2 до 13
int a = 2;
int b = 3;
int c = 4;
int d = 5;
int e = 6;
int f = 7;
int g = 8;
int p = 9;
int d4 = 10;
int d3 = 11;
int d2 = 12;
int d1 = 13;
volatile static int z = 0;
volatile static int t = 0;

void setup()
{
  DDRB = B11111111;
  PORTB = B11111100;
  Serial.begin(9600);
  Timer1.setFrequency(100);
  Timer1.enableISR(CHANNEL_A);
  Timer0.setFrequency(1000000000);
  Timer0.enableISR(CHANNEL_A);
  pinMode(13, OUTPUT);
  //пины на вывод
  pinMode(d1, OUTPUT);
  pinMode(d2, OUTPUT);
  pinMode(d3, OUTPUT);
  pinMode(d4, OUTPUT);
  pinMode(a, OUTPUT);
  pinMode(b, OUTPUT);
  pinMode(c, OUTPUT);
  pinMode(d, OUTPUT);
  pinMode(e, OUTPUT);
  pinMode(f, OUTPUT);
  pinMode(g, OUTPUT);
  pinMode(p, OUTPUT);
}


void loop()
{

}

void pickNumber2(int t)
{ 
  int data2 = (t % 100 / 10); // десятки
//  static int x = 0;
//  x++;
  Serial.print("десятки = ");
  Serial.println(data2);
  switch(data2)
  {
    case 0: 
    zero();
    break;
    case 1: 
    one();
    break;
    case 2: 
    two();
    break;
    case 3: 
    three();
    break;
    case 4: 
    four();
    break;
    case 5: 
    five(); 
    break;
    case 6: 
    six(); 
    break;
    case 7: 
    seven(); 
    break;
    case 8: 
    eight(); 
    break;
    case 9:
    nine();
    data2 = 0;
    break;

  }
} 

// определение символа (цифры)
void pickNumber1(int t){ 
  int data1 = t % 10; // единицы
//  static int x = 0;
//  x++;
  Serial.print("единицы = ");
  Serial.println(data1);
  switch(data1)
  {
    case 0: 
    zero();
    break;
    case 1: 
    one();
    break;
    case 2: 
    two();
    break;
    case 3: 
    three();
    break;
    case 4: 
    four();
    break;
    case 5: 
    five(); 
    break;
    case 6: 
    six(); 
    break;
    case 7: 
    seven(); 
    break;
    case 8: 
    eight(); 
    break;
    case 9:
    nine();
    data1 = 0;
    break;

  }
} 

void pickNumber3(int t){ 
  int data1 = (t % 1000 / 100); // сотни
//  static int x = 0;
//  x++;
  Serial.print("единицы = ");
  Serial.println(data1);
  switch(data1)
  {
    case 0: 
    zero();
    break;
    case 1: 
    one();
    break;
    case 2: 
    two();
    break;
    case 3: 
    three();
    break;
    case 4: 
    four();
    break;
    case 5: 
    five(); 
    break;
    case 6: 
    six(); 
    break;
    case 7: 
    seven(); 
    break;
    case 8: 
    eight(); 
    break;
    case 9:
    nine();
    data1 = 0;
    break;

  }
} 
void pickNumber4(int t){ 
  int data1 = t / 1000; // тысячи
//  static int x = 0;
//  x++;
  Serial.print("единицы = ");
  Serial.println(data1);
  switch(data1)
  {
    case 0: 
    zero();
    break;
    case 1: 
    one();
    break;
    case 2: 
    two();
    break;
    case 3: 
    three();
    break;
    case 4: 
    four();
    break;
    case 5: 
    five(); 
    break;
    case 6: 
    six(); 
    break;
    case 7: 
    seven(); 
    break;
    case 8: 
    eight(); 
    break;
    case 9:
    nine();
    data1 = 0;
    break;

  }
} 

// вывод 0
void zero()
{
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, LOW);
  digitalWrite(f, LOW);
  digitalWrite(g, HIGH);
}

// вывод 1
void one()
{
  digitalWrite(a, HIGH);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, HIGH);
  digitalWrite(e, HIGH);
  digitalWrite(f, HIGH);
  digitalWrite(g, HIGH);
}

// вывод 2
void two()
{
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, HIGH);
  digitalWrite(d, LOW);
  digitalWrite(e, LOW);
  digitalWrite(f, HIGH);
  digitalWrite(g, LOW);
}
	
// вывод 3
void three()
{
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, HIGH);
  digitalWrite(f, HIGH);
  digitalWrite(g, LOW);
}

// вывод 4
void four()
{
  digitalWrite(a, HIGH);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, HIGH);
  digitalWrite(e, HIGH);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);
}

// вывод 5
void five()
{
  digitalWrite(a, LOW);
  digitalWrite(b, HIGH);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, HIGH);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);
}
	
// вывод 6
void six()
{
  digitalWrite(a, LOW);
  digitalWrite(b, HIGH);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, LOW);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);
}

// вывод 7
void seven()
{
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, HIGH);
  digitalWrite(e, HIGH);
  digitalWrite(f, HIGH);
  digitalWrite(g, HIGH);
}

// вывод 8
void eight()
{
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, LOW);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);
}

// вывод 9
void nine()
{
  digitalWrite(a, LOW);
  digitalWrite(b, LOW);
  digitalWrite(c, LOW);
  digitalWrite(d, LOW);
  digitalWrite(e, HIGH);
  digitalWrite(f, LOW);
  digitalWrite(g, LOW);
}

ISR(TIMER1_A){
  z++;
  if (z == 50){
    ++t;
    z = 0; 
  }
  if (t == 10000){
    t = 0;
  }

}
ISR(TIMER0_A){
  static int m = 0;
  PORTB &=~((1<<5)|(1<<4)|(1<<3)|(1<<2));
  if (m == 0){
    pickNumber2(t);
    PORTB |=(1<<2);
  }
  if (m == 1){
    pickNumber1(t);
    PORTB |=(1<<3);
  }
  if (m == 2){
    pickNumber3(t);
    PORTB |=(1<<4);
  }
  if (m == 3){
    pickNumber4(t);
    PORTB |=(1<<5);
  }
  m++;
  if (m == 4){
    m = 0;
  }
}



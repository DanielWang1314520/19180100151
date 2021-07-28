```c
#include<MsTimer2.h>
#define a1 8
#define a2 9
#define a3 10
#define a4 11
#define locks 12
#define lockg 13
#define buttonInterrupt 2

int tickg=0;
int ticks=0;
void buttonchange()
{
  if ( digitalRead(buttonInterrupt) == 1 )
  {
    ticks=0;
  	tickg=0;
  	Serial.println("ok");
  }
}

void timedo()
{
  Serial.print(ticks);
  Serial.println(tickg);
  digitalWrite(locks,LOW);
  digitalWrite(lockg,HIGH);
  digitalWrite(a1,(ticks&0x1));
  digitalWrite(a2,((ticks>>1)&0x1));
  digitalWrite(a3,((ticks>>2)&0x1));
  digitalWrite(a4,((ticks>>3)&0x1));
  digitalWrite(lockg,LOW);
  digitalWrite(locks,HIGH);
  digitalWrite(a1,(tickg&0x1));
  digitalWrite(a2,((tickg>>1)&0x1));
  digitalWrite(a3,((tickg>>2)&0x1));
  digitalWrite(a4,((tickg>>3)&0x1));
  tickg++;
  if(tickg>9)
  {
    ticks++;
    tickg=0;
    if(ticks>9)
    {
      ticks=0;
    }
  }  
}

void setup()
{
  pinMode(a1, OUTPUT);
  pinMode(a2, OUTPUT);
  pinMode(a3, OUTPUT);
  pinMode(a4, OUTPUT);
  pinMode(locks, OUTPUT);
  pinMode(lockg, OUTPUT);
  pinMode(2,INPUT);
  Serial.begin(9600);
  MsTimer2::set(1000, timedo); 
  MsTimer2::start(); 
  attachInterrupt( digitalPinToInterrupt(buttonInterrupt),buttonchange, RISING);//监视引脚变化以实现通过按钮清零
}

void loop()
{
}
```

![](https://i.loli.net/2021/07/29/ntBY4q9fIQUL8CZ.png)


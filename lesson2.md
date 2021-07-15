```c++
//流水灯
int i=13;
void setup()
{
  pinMode(13, OUTPUT);
  pinMode(12, OUTPUT);
  pinMode(11, OUTPUT);
  pinMode(10, OUTPUT);
  pinMode(9, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(7, OUTPUT);
}

void loop()
{
  while(i>6){
  digitalWrite(i, HIGH);
    
  delay(1000); // Wait for 1000 millisecond(s)
    digitalWrite(i, LOW);
     delay(1000);
    i--;
    if(i<=6){
      i=13;
    }
  }
}
```

**lesson2_1**

![lesson2_1](https://i.loli.net/2021/07/15/tj1oaNK6svezO4i.png)

```c++
//7段晶体管显示
int i=9;
void setup()
{
  pinMode(2, OUTPUT);
  pinMode(3, OUTPUT);
  pinMode(4, OUTPUT);
  pinMode(5, OUTPUT);
  pinMode(6, OUTPUT);
  pinMode(8, OUTPUT);
  pinMode(7, OUTPUT);
  Serial.begin(9000);
}
void loop()
{
  if(Serial.available()>0){
    i=Serial.read();
    i=i-'0';
  }
  switch(i){
    case 0:
      digitalWrite(2,HIGH);
      digitalWrite(3,HIGH);
      digitalWrite(4,HIGH);
      digitalWrite(5,HIGH);
      digitalWrite(6,HIGH);
      digitalWrite(7,HIGH);
      digitalWrite(8,LOW);
      break;
    case 1:
     digitalWrite(3,HIGH);
      digitalWrite(4,HIGH);
    digitalWrite(2,LOW);
    digitalWrite(5,LOW);
    digitalWrite(6,LOW);
    digitalWrite(7,LOW);
    digitalWrite(8,LOW);
    
      break;
    case 2:
      digitalWrite(2,HIGH);
      digitalWrite(3,HIGH);
      digitalWrite(5,HIGH);
      digitalWrite(6,HIGH);
      digitalWrite(8,HIGH);
    digitalWrite(4,LOW);
    digitalWrite(7,LOW);
      break;
    case 3:
      digitalWrite(2,HIGH);
      digitalWrite(3,HIGH);
      digitalWrite(4,HIGH);
      digitalWrite(5,HIGH);
      digitalWrite(8,HIGH);
    digitalWrite(7,LOW);
    digitalWrite(6,LOW);
      break;
    case 4:
      digitalWrite(3,HIGH);
      digitalWrite(4,HIGH);
      digitalWrite(7,HIGH);
      digitalWrite(8,HIGH);
    digitalWrite(2,LOW);
    digitalWrite(5,LOW);
    digitalWrite(6,LOW);
      break;
    case 5:
      digitalWrite(2,HIGH);
      digitalWrite(4,HIGH);
      digitalWrite(5,HIGH);
      digitalWrite(7,HIGH);
      digitalWrite(8,HIGH);
    digitalWrite(3,LOW);
    digitalWrite(6,LOW);
      break;
    case 6:
      digitalWrite(2,HIGH);
      digitalWrite(4,HIGH);
      digitalWrite(5,HIGH);
      digitalWrite(6,HIGH);
      digitalWrite(7,HIGH);
      digitalWrite(8,HIGH);
    digitalWrite(3,LOW);
      break;
    case 7:
      digitalWrite(2,HIGH);
      digitalWrite(3,HIGH);
      digitalWrite(4,HIGH);
    digitalWrite(5,LOW);
    digitalWrite(6,LOW);
    digitalWrite(7,LOW);
    digitalWrite(8,LOW);
      break;
    case 8:
      digitalWrite(2,HIGH);
      digitalWrite(3,HIGH);
      digitalWrite(4,HIGH);
      digitalWrite(5,HIGH);
      digitalWrite(6,HIGH);
      digitalWrite(7,HIGH);
      digitalWrite(8,HIGH);
      break;    
  }
}
```

**lesson2_2**

![lesson2_2](https://i.loli.net/2021/07/15/8vlzqxNEGSBaiQb.png)
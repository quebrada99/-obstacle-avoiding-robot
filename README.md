# -obstacle-avoiding-robot

```javascript

//source code
//obstacle avoiding robot
const int echopin = 12;
const int trigpin = 13;


const int mr1 = 4;
const int mr2 = 5;
const int ml3 = 9;
const int ml4 = 8;
const int mre = 3;
const int mle = 10;

 long sure = 0 ;
 long mesafe = 0  ;
 
void setup() {
  pinMode(echopin,INPUT);
  pinMode(trigpin,OUTPUT);
  
 
  
  pinMode(mr1,OUTPUT);
  pinMode(mr2,OUTPUT);
  pinMode(ml3,OUTPUT);
  pinMode(ml4,OUTPUT);

  pinMode(mre,OUTPUT);
  pinMode(mle,OUTPUT);

  Serial.begin(9600);
}

void loop() {

  digitalWrite(trigpin,HIGH);
  delayMicroseconds(1000);
  digitalWrite(trigpin,LOW);

  sure = pulseIn(echopin,HIGH);
  mesafe = sure/29.1/2;
  Serial.println(mesafe);

 if (mesafe < 25) 
  {
    geri();  
    delay(150);
   
    sag();
    delay(200);
  }
  else {  
    ileri(); 
    delay(250); 
  }


}

void ileri(){
  digitalWrite(mr1,HIGH);
  digitalWrite(mr2,LOW);
  analogWrite(mre,250);

  digitalWrite(ml3,HIGH);
  digitalWrite(ml4,LOW);
  analogWrite(mle,250);
  Serial.println("ileri fonk calisiyor");
}

void sag(){
  digitalWrite(mr1,HIGH);
  digitalWrite(mr2,LOW);
  analogWrite(mre,0);

  digitalWrite(ml3,HIGH);
  digitalWrite(ml4,LOW);
  analogWrite(mle,150);
   Serial.println("sag fonk calisiyor");
  
}
void geri(){
  digitalWrite(mr1,LOW);
  digitalWrite(mr2,HIGH);
  analogWrite(mre,200);

  digitalWrite(ml3,LOW);
  digitalWrite(ml4,HIGH);
  analogWrite(mle,200);
   Serial.println("geri fonk calisiyor");
  
}
```

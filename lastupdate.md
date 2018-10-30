# asensio
int EN1=8;
int EN2=9;
int EN3=3;
int EN4=4;

int PWMLF=5;
int PWMLR=6;

int PWMRF=11;
int PWMRR=10;

int ms=200;
int ts=150;

void lmfor() {
  analogWrite(PWMLF,ms);
  analogWrite(PWMLR,0);
}

void lmrev() {
  analogWrite(PWMLF,0);
  analogWrite(PWMLR,ms);
}

void lmstop() {
  analogWrite(PWMLF,0);
  analogWrite(PWMLR,0);
}

void rmfor() {
  analogWrite(PWMRF,ms);
  analogWrite(PWMRR,0);
}

void rmrev() {
  analogWrite(PWMRF,0);
  analogWrite(PWMRR,ms);
}

void rmstop() {
  analogWrite(PWMRF,0);
  analogWrite(PWMRR,0);
}

void forward() {
  rmfor();
  lmfor();
}

void reverse() {
  rmrev();
  lmrev();
}

void vehstop() {
  rmstop();
  lmstop();
}

void rspin() {
  lmfor();
  rmrev();
}

void lspin() {
  lmrev();
  rmfor();
}

void rturn(){
  lmfor();
  rmstop();
}

void lturn() {
  rmfor();
  lmrev();
}

void blturn() {
  rmrev();
  lmstop();
}

void brturn() {
  lmrev();
  rmstop();
}


void setup() {
  pinMode(EN1,OUTPUT);
  pinMode(EN2,OUTPUT);
  pinMode(EN3,OUTPUT);
  pinMode(EN4,OUTPUT);
  pinMode(PWMRF,OUTPUT);
  pinMode(PWMRR,OUTPUT);
  pinMode(PWMLF,OUTPUT);
  pinMode(PWMLR,OUTPUT);
  digitalWrite(EN1,HIGH);
  digitalWrite(EN2,HIGH);
  digitalWrite(EN3,HIGH);
  digitalWrite(EN4,HIGH);
  Serial.begin(9600);
  // put your setup code here, to run once:

}

void loop() {
  /*forward();
  delay(2000);
  reverse();
  delay(2000);
  vehstop();
  delay(2000);
  
  /*lmstop();
  rmstop();
  //lmfor();
  /*analogWrite(PWMRF,255);
  analogWrite(PWMRR,0);
  /*lmfor();
  delay(2000);
  lmrev();
  delay(2000);
  /*analogWrite(PWMRF,255);
  analogWrite(PWMRR,0);
  /*analogWrite(PWMLF,255);
  analogWrite(PWMLR,0);*/
  // put your main code here, to run repeatedly:

}

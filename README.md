# Project-A
#define IR0 0 
#define IR1 1 
#define IR2 2 
#define IR3 3 
#define IR4 4
 #define MOTOR_SPEED 150 
//Right motor 
int enableRightMotor=6;
 int rightMotorPin1=7;
 int rightMotorPin2=8; 
//Left motor 
int enableLeftMotor=5; 
int leftMotorPin1=9; 
int leftMotorPin2=10; 
void setup() 
{ pinMode(enableRightMotor, OUTPUT); 
pinMode(rightMotorPin1, OUTPUT);
 pinMode(rightMotorPin2, OUTPUT); 
pinMode(enableLeftMotor, OUTPUT); 
pinMode(leftMotorPin1, OUTPUT); 
pinMode(leftMotorPin2, OUTPUT); 
pinMode(IR0, INPUT); 
pinMode(IR1, INPUT); 
pinMode(IR2, INPUT); 
pinMode(IR3, INPUT); 
pinMode(IR4, INPUT); } 
void forward() {  
digitalWrite(leftMotorPin1, HIGH); 
digitalWrite(leftMotorPin2,LOW); 
digitalWrite(rightMotorPin1, HIGH); 
digitalWrite(rightMotorPin2, LOW); }
void stopp() { 
digitalWrite(leftMotorPin1, LOW); 
digitalWrite(leftMotorPin2,LOW); 
digitalWrite(rightMotorPin1, LOW); 
digitalWrite(rightMotorPin2, LOW); }
void right() {
digitalWrite(leftMotorPin1, HIGH); 
digitalWrite(leftMotorPin2,LOW); 
digitalWrite(rightMotorPin1, LOW); 
digitalWrite(rightMotorPin2, HIGH); }
 void left() { 
digitalWrite(leftMotorPin1, LOW); 
digitalWrite(leftMotorPin2,HIGH); 
digitalWrite(rightMotorPin1, HIGH); 
digitalWrite(rightMotorPin2, LOW); } 
void loop() { 
int R0 = digitalRead(IR0); 
int R1 = digitalRead(IR1); 
int R2 = digitalRead(IR2); 
int R3 = digitalRead(IR3); 
int R4 = digitalRead(IR4); 
analogWrite(enableRightMotor,MOTOR_SPEED); analogWrite(enableLeftMotor,MOTOR_SPEED);
 if ((R0 == HIGH || R1 == HIGH) && R2 == LOW && (R3 == HIGH || R4 == HIGH)) 
{ 
forward();
}
 if ((R0 == LOW && R1 == LOW) && R2 == LOW && (R3 == LOW && R4 == LOW))
 { 
stopp();
}
 if ((R0 == HIGH || R1 == HIGH) && R2 == HIGH && (R3 == LOW|| R4 == LOW))
 { 
right();
}
 if (R0 == HIGH && R1 == HIGH && R2 == LOW && R3 == LOW && R4 == HIGH) 
{ 
right(); 
}
if ((R0 == LOW || R1 == LOW) && R2 == HIGH && (R3 == HIGH || R4 == HIGH)) 
{ 
left(); 
}
 }

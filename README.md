# Multiple-Ultrasonic-Security-System
https://myownblog-ashwin.blogspot.com/2021/01/multiple-ultrasonic-sensor.html


long duration;
int distance;

int const trigPin1=8;
int const echoPin1=9;
int const buzzPin=2;

int const trigPin2=10;
int const echoPin2=11;


int const trigPin3=12;
int const echoPin3=13;


void setup()
{
  pinMode(trigPin1,OUTPUT);
  pinMode(echoPin1,INPUT);
  pinMode(buzzPin,OUTPUT);
    Serial.begin(9600);
  Serial.println("Ultrasonic Sensor");
  Serial.println("with Arduino UNO");


  pinMode(trigPin2,OUTPUT);
  pinMode(echoPin2,INPUT);
  pinMode(buzzPin,OUTPUT);


  pinMode(trigPin3,OUTPUT);
  pinMode(echoPin3,INPUT);
  pinMode(buzzPin,OUTPUT);
  
}
void loop()
{
  int duration,distance;
  digitalWrite(trigPin1,HIGH);
  delay(1);
  digitalWrite(trigPin1,LOW);
  duration = pulseIn(echoPin1,HIGH);
 distance = (duration/2)/29.1;
   Serial.print("sensor 1 Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
 if(distance <= 50 && distance >= 0)
 {
  digitalWrite(buzzPin,HIGH);
 }
 else
 {
  digitalWrite(buzzPin,LOW);
 }
 delay(60);
 
 digitalWrite(trigPin2,HIGH);
  delay(1);
  digitalWrite(trigPin2,LOW);
  duration = pulseIn(echoPin2,HIGH);
 distance = (duration/2)/29.1;
   Serial.print("sensor 2 Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
 if(distance <= 50 && distance >= 0)
 {
  digitalWrite(buzzPin,HIGH);
 }
 else
 {
  digitalWrite(buzzPin,LOW);
 }
 delay(60);

   digitalWrite(trigPin3,HIGH);
  delay(1);
  digitalWrite(trigPin3,LOW);
  duration = pulseIn(echoPin3,HIGH);
 distance = (duration/2)/29.1;
   Serial.print("sensor 3 Distance: ");
  Serial.print(distance);
  Serial.println(" cm");
  
 if(distance <= 50 && distance >= 0)
 {
  digitalWrite(buzzPin,HIGH);
 }
 else
 {
  digitalWrite(buzzPin,LOW);
 }
 delay(60);
}

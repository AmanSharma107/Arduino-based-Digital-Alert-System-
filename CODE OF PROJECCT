#include <RTClib.h>
#include <Wire.h>
#include <LiquidCrystal.h>
LiquidCrystal lcd(12, 11, 5, 4, 3, 2);
RTC_DS1307 RTC;
char daysOfTheWeek[7][5] = {"Sun", "Mon", "Tue", "Wed", "Thu", "Fri", "Sat"};
void setup() {
Serial.begin(9600);
pinMode(13, OUTPUT);
lcd.begin(16, 2);
Wire.begin();
RTC.begin();
lcd.setCursor(0, 0);
lcd.print("Department of");
delay(1000);
lcd.setCursor(0, 1);
lcd.print("Electronics Engg");
delay(1000);
lcd.setCursor(0, 0);
lcd.print("AMAN SHARMA ");
delay(2000);
lcd.clear();
delay(500);
// Check to see if the RTC is keeping time.
if (!RTC.isrunning()) {
Serial.println("RTC is NOT running!");
// This will reflect the time that your sketch was compiled
RTC.adjust(DateTime(__DATE__, __TIME__));
}
}
void loop() {
DateTime now = RTC.now();
// Check if today is Sunday
if (now.dayOfTheWeek() == 0) {
// Sunday-specific logic here
lcd.setCursor(0, 0);
lcd.print("No Classes");
lcd.setCursor(0, 1);
lcd.print("Class off");
delay(1000);
lcd.clear();
} else {
// Print date and time
lcd.setCursor(0, 0);
lcd.print(now.day(), DEC);
lcd.print('/');
lcd.print(now.month(), DEC);
lcd.print('/');
lcd.print(now.year(), DEC);
lcd.setCursor(11, 0);
lcd.print(daysOfTheWeek[now.dayOfTheWeek()]);
lcd.setCursor(0, 1);
lcd.print(now.hour(), DEC);
lcd.print(':');
lcd.print(now.minute(), DEC);
lcd.print(':');
lcd.print(now.second(), DEC);
delay(30);
// Check for different lectures
int h = now.hour();
int m = now.minute();
int s = now.second();
// Lecture timings
if (h == 9 && m == 0 && s == 1) {
lcd.setCursor(9, 1);
lcd.print("LecStart");
digitalWrite(13, HIGH);
delay(5000);
digitalWrite(13, LOW);
}
if (h == 9 && m >= 0 && s > 2) {
lcd.setCursor(10, 1);
lcd.print("Lec 1");
delay(1000);
}
//second lecture
if (h==10 && m==0 && s==1)
{
lcd.setCursor(9,1);
lcd.print("Lec ove");
digitalWrite(13,HIGH);
delay(5000);
digitalWrite(13,LOW);
}
if (h==10 && m>=0 && s>2 )
{
lcd.setCursor(10,1);
lcd.print("Lec 2");
delay(1000);
}
//Third lecture
if (h==11 && m==0 && s==1)
{
lcd.setCursor(9,1);
lcd.print("LecOver");
digitalWrite(13,HIGH);
delay(5000);
digitalWrite(13,LOW);
}
if (h==11 && m>=0 && s>2 )
{
lcd.setCursor(9,1);
lcd.print("Lec 3");
delay (1000);
}
//Lunch
if (h==12 && m==0 && s==1)
{
lcd.setCursor(9,1);
lcd.print("Lec Over");
digitalWrite(13,HIGH);
delay(5000);
digitalWrite(13,LOW);
}
if (h==12 && m<=39 && s>2 )
{
lcd.setCursor(9,1);
lcd.print("Lunch");
delay (1000);
}
//Fourth lecture
if (h==12 && m==40 && s==1)
{
lcd.setCursor(9,1);
lcd.print("Lunch Over");
digitalWrite(13,HIGH);
delay(5000);
digitalWrite(13,LOW);
}
if (h==12 && m>=40 && s>2 )
{
lcd.setCursor(9,1);
lcd.print("Lec 4");
delay (1000);
}
//Fifth lecture
if (h==13 && m==40 && s==1)
{
lcd.setCursor(9,1);
lcd.print("Lec ove");
digitalWrite(13,HIGH);
delay(5000);
digitalWrite(13,LOW);
}
if (h==13 && m>=40 && s>2 )
{
lcd.setCursor(10,1);
lcd.print("Lec 5");
delay (1000);
}
//sixth lecture
if (h==14 && m==35 && s==1)
{
lcd.setCursor(9,1);
lcd.print("Lec ove");
digitalWrite(13,HIGH);
delay(5000);
digitalWrite(13,LOW);
}
if (h==14 && m>=35 && s>2 )
{
lcd.setCursor(9,1);
lcd.print("Lec 6");
delay (1000 )
}
// College over
if (h == 15 && m == 30 && s == 1) {
lcd.setCursor(9, 1);
lcd.print("Class Over");
digitalWrite(13, HIGH);
delay(5000);
digitalWrite(13, LOW);
}
if (h == 15 && m >= 30 && s > 2) {
lcd.setCursor(8, 1);
lcd.print("No Class");
delay(1000);
}
}
lcd.clear();

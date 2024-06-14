# RFID-Based-Campus-Entry-Informer-System-For-Parental-Engagement
//$0013222614

//$0002602465

//$0002604995

#include <Arduino.h>


#include <LiquidCrystal_I2C.h> #include <Wire.h> LiquidCrystal_I2C lcd(0x27, 16, 2);

char input[11];


int	count = 0; void setup ()
{


Wire.begin(); Serial.begin(9600); lcd.begin(16,2);
lcd.init(); lcd.backlight(); lcd.setCursor(0, 0);
lcd.print("Campus Entry"); lcd.setCursor(0, 1); lcd.print("informer system"); delay (4000);
lcd.clear();
}


void loop()
{
lcd.setCursor(0, 0); lcd.print("Waiting for "); lcd.setCursor(0,1); lcd.print(" scanning	");

if(Serial.available())
{
count = 0;
while(Serial.available() && count < 11)
{
input[count] = Serial.read(); count++;
delay(5);
}
//$0013222614
if(input[0] == '$' && input[1] == '0' && input[2] == '0' && input[3] == '1' && input[4] == '3' && input[5] == '2'&& input[6] == '2' && input[7] == '2' && input[8] == '6' && input[9] == '1' && input[10] == '4' )
{
lcd.setCursor(0, 0);
lcd.print("---Parent 1---");
Serial.print("Parent 1"); lcd.setCursor(0,1);
lcd.print("..SMS Sending	");
Serial.print("AT"); //Start Configuring GSM Module delay(5000);	//One second delay Serial.println();
Serial.println("AT+CMGF=1"); // Set GSM in text mode delay(5000);	// One second delay Serial.println();
Serial.print("AT+CMGS="); Serial.print("\"+919626115744\"");// Enter the receiver number Serial.println();
delay(5000); lcd.setCursor(0,1); lcd.print("..SMS to staff	");
Serial.print("Parents-1 is visiting. contact No:+919361845648 "); // SMS body - Sms Text delay(5000);
Serial.println();
Serial.write(26);	//CTRL+Z Command to send text and end session lcd.setCursor(0,1);

lcd.print("..SMS Sent..."); delay(1000); lcd.setCursor(0, 1);
lcd.print("--SMS to Parents--"); Serial.print("Parent 1");
lcd.setCursor(0,1); lcd.print("..SMS Sending	");
Serial.print("AT"); //Start Configuring GSM Module delay(5000);	//One second delay Serial.println();
Serial.println("AT+CMGF=1"); // Set GSM in text mode delay(5000);	// One second delay Serial.println();
Serial.print("AT+CMGS="); Serial.print("\"+919361845648\"");// Enter the receiver number Serial.println();
delay(5000); lcd.setCursor(0,1); lcd.print("..SMS to Parents	");
Serial.print("Thanks for Visiting. your Appointment is Booking to staff. contact No:+919626115744 "); // SMS body - Sms Text
delay(5000); Serial.println();
Serial.write(26);	//CTRL+Z Command to send text and end session lcd.setCursor(0,1);
lcd.print("..SMS Sent	");
delay(1000);


}
//$0002602465


if(input[0] == '$' && input[1] == '0' && input[2] == '0' && input[3] == '0' && input[4] == '2' && input[5] == '6'&& input[6] == '0' && input[7] == '2' && input[8] == '4' && input[9] == '6' && input[10] == '5' )
{


lcd.setCursor(0, 0);

lcd.print("---Parent 2---");
Serial.print("Parent 2"); lcd.setCursor(0,1);
lcd.print("..SMS Sending	");
Serial.print("AT"); //Start Configuring GSM Module delay(5000);	//One second delay Serial.println();
Serial.println("AT+CMGF=1"); // Set GSM in text mode delay(5000);	// One second delay Serial.println();
Serial.print("AT+CMGS="); Serial.print("\"+919626115744\"");// Enter the receiver number Serial.println();
delay(5000); lcd.setCursor(0,1); lcd.print("..SMS to staff	");
Serial.print("Parents-2 is visiting. contact No:+917397085259 "); // SMS body - Sms Text delay(5000);
Serial.println();
Serial.write(26);	//CTRL+Z Command to send text and end session lcd.setCursor(0,1);
lcd.print("..SMS Sent	");
delay(1000); lcd.setCursor(0, 1);
lcd.print("--SMS to Parents--"); Serial.print("Parent 1");
lcd.setCursor(0,1); lcd.print("..SMS Sending	");
Serial.print("AT"); //Start Configuring GSM Module delay(5000);	//One second delay Serial.println();
Serial.println("AT+CMGF=1"); // Set GSM in text mode delay(5000);	// One second delay Serial.println();
Serial.print("AT+CMGS="); Serial.print("\"+917397085259\"");// Enter the receiver number

Serial.println(); delay(5000); lcd.setCursor(0,1);
lcd.print("..SMS to Parents...");
Serial.print("Thanks for Visiting. your Appointment is Booking to staff. contact No:+919626115744 "); // SMS body - Sms Text
delay(5000); Serial.println();
Serial.write(26);	//CTRL+Z Command to send text and end session lcd.setCursor(0,1);
lcd.print("..SMS Sent..."); delay(1000);
}
//$0002604995
if(input[0] == '$' && input[1] == '0' && input[2] == '0' && input[3] == '0' && input[4] == '2' && input[5] == '6'&& input[6] == '0' && input[7] == '4' && input[8] == '9' && input[9] == '9' && input[10] == '5' )
{
lcd.setCursor(0, 0);
lcd.print("---Parent 3---");
Serial.print("Parent 3"); lcd.setCursor(0,1);
lcd.print("..SMS Sending	");
Serial.print("AT"); //Start Configuring GSM Module delay(5000);	//One second delay Serial.println();
Serial.println("AT+CMGF=1"); // Set GSM in text mode delay(5000);	// One second delay Serial.println();
Serial.print("AT+CMGS="); Serial.print("\"+919626115744\"");// Enter the receiver number Serial.println();
delay(5000); lcd.setCursor(0,1); lcd.print("..SMS to staff	");
Serial.print("Parents-3 is visiting. contact No:+919842976513 "); // SMS body - Sms Text delay(5000);

Serial.println();
Serial.write(26);	//CTRL+Z Command to send text and end session lcd.setCursor(0,1);
lcd.print("..SMS Sent..."); delay(1000); lcd.setCursor(0, 1);
lcd.print("--SMS to Parents--"); Serial.print("Parent 1");
lcd.setCursor(0,1); lcd.print("..SMS Sending	");
Serial.print("AT"); //Start Configuring GSM Module delay(5000);	//One second delay Serial.println();
Serial.println("AT+CMGF=1"); // Set GSM in text mode delay(5000);	// One second delay Serial.println();
Serial.print("AT+CMGS="); Serial.print("\"+919842976513\"");// Enter the receiver number Serial.println();
delay(5000); lcd.setCursor(0,1); lcd.print("..SMS to Parents	");
Serial.print("Thanks for Visiting. your Appointment is Booking to staff. contact No:+919626115744 "); // SMS body - Sms Text
delay(5000); Serial.println();
Serial.write(26);	//CTRL+Z Command to send text and end session lcd.setCursor(0,1);
lcd.print("..SMS Sent	");
delay(1000);


}
}
}
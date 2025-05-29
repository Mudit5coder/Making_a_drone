#basic code I did in tinkercad, once I got stuff for all this I will try on actual board
// PWM pins
const int motor1PWM = 3;
const int motor2PWM = 5;
const int motor3PWM = 6;
const int motor4PWM = 9;

int userInput = -1; // Default to invalid
int acc = 0;
int speed1 = 0;
void setup() {
  Serial.begin(9600); // Open serial at 9600 baud
  pinMode(motor1PWM, OUTPUT);
  pinMode(motor2PWM, OUTPUT);
  pinMode(motor3PWM, OUTPUT);
  pinMode(motor4PWM, OUTPUT);

  Serial.println("Enter a number (0-3) to control motors:");
  Serial.println("0: up");
  Serial.println("1: down");
  Serial.println("2: FAST");
  Serial.println("3: OFF");
  Serial.println("4: Front");
  Serial.println("5: Back");
}

void loop() {
  if (Serial.available() > 0) {
    userInput = Serial.parseInt(); // Read integer from Serial
     
    switch (userInput) {
      case 0:
        Serial.println("up mode");
        setAllMotorsup();
        break;
      case 1:
        Serial.println("down mode");
        setAllMotorsdown();
        break;
      case 2:
        Serial.println("FAST mode");
        setAllMotors(255);
        break;
      case 3:
        Serial.println("OFF mode");
        setAllMotors(0);
        break;
      case 4:
        Serial.println("Front mode");
        setAllMotorsFront();
        break;
      case 5:
        Serial.println("Back mode");
        setAllMotorsBack();
        break;
      default:
        Serial.println("Invalid input. Enter 0, 1, 2, 4, 5or 3.");
        break;
    }
    
  }
  
}

void setAllMotors(int speed) {
  analogWrite(motor1PWM, speed);
  analogWrite(motor2PWM, speed);
  analogWrite(motor3PWM, speed);
  analogWrite(motor4PWM, speed);
}
void setAllMotorsup() {
  speed1 = speed1 + 10;
  speed1 = constrain(speed1, 0, 255);
  analogWrite(motor1PWM, speed1);
  analogWrite(motor2PWM, speed1);
  analogWrite(motor3PWM, speed1);
  analogWrite(motor4PWM, speed1);
  Serial.print(" speed1 ");
Serial.println(speed1);
}
void setAllMotorsdown() {
  speed1 = speed1 - 10;
  speed1 = max(speed1, 0);
  analogWrite(motor1PWM, speed1);
  analogWrite(motor2PWM, speed1);
  analogWrite(motor3PWM, speed1);
  analogWrite(motor4PWM, speed1);
  Serial.print(" speed1 ");
Serial.println(speed1);
}

void setAllMotorsFront() {
  int speed = 0;
  speed = speed1;
  speed = constrain(speed, 0, 255);
  analogWrite(motor1PWM, speed-10);
  analogWrite(motor2PWM, speed-10);
  analogWrite(motor3PWM, speed+10);
  analogWrite(motor4PWM, speed+10);
  Serial.print(" speed ");
  Serial.println(speed);}

void setAllMotorsBack() {
  int speed = 0;
  speed = speed1;
  speed = constrain(speed, 0, 255);
  analogWrite(motor1PWM, speed+10);
  analogWrite(motor2PWM, speed+10);
  analogWrite(motor3PWM, speed-10);
  analogWrite(motor4PWM, speed-10);
  Serial.print(" speed ");
  Serial.println(speed);}

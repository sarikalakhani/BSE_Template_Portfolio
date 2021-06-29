# Obstacle Avoiding Car
Using the Arduino chip and application, I code my robot to not encounter any objects without any remote control.

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Sarika Lakhani | Henry M. Gunn High school | NA | Incoming Junior

![Add pic of final project](https://bluestampengineering.com/wp-content/uploads/2016/05/improve.jpg)

# Materials
1. Arduino
2. Mini wheel and motor kit
3. Wires
4. Sensor 
5. Piezo Buzzer 
6. Pliers 
7. Soulder 
8. Souldering Wires

# Building Steps 

1. Make the Arduino blink. 
  a. Download the Arduino software on the website arduino.cc 
  b. Connect the USB cord from a computer to an Arduino. (Adapters may be needed depending on computer model). 
  c. Open the Arduino software
  d. Go to the top left of your screen. File → Examples → Basics → Blink. This opens a new Arduino window with the code to make an Arduino board blink. 
  e. Go to the top left of your screen. Tools → Board → Arduino/Genuino Uno. This ensures that the code will go to the Arduino Board. 
  f. Go to the top left of your screen. Tools → Port → (Arduino/Genuino Uno). This also ensures that the code will go to the Arduino Boards. 
  g. Upload the code. 
  h. If the Arduino Board is not blinking go to the website. https://support.arduino.cc/hc/en-us
2. Run ultrasonic sensor 
  a. Collect materials (Female to male jumper wires, Arduino board, and buzzer). 
  b. Using the ultrasonic sensor, the Arduino, and the jumper wires:
  c. Connect VCC on the ultrasonic sensor to 5V on the Arduino. 
  d. Connect the Trig pin on the ultrasonic sensor to pin 2 on the Arduino.
  e. Connect the Echo pin on the ultrasonic sensor to pin 3 on the Arduino.
  f. Connect the GND on the ultrasonic sensor to the GND on the Arduino.
  g. Using the buzzer, the Arduino, and the jumper wires:
  h. Connect the positive pin on the buzzer to pin - 10 on the Arduino. 
  i. Connect the negative pin on the buzzer to pin GND on the Arduino. 
  j. Copy and paste the following code to your Arduino application. There are comments in the code for clarification. 
 '''
 // initiallized trigger pin and echo
 // initialized trigger pin to 2 and echo pin to 3 because they are connected to those pins on the arduino 
 // initialized the busser pin and the variable that calculates distance 
  int trigger_pin = 2;
  int echo_pin = 3;
  int buzzer_pin = 10;
  int time;
  int distance;

 // the trigger pin is set as output becasue it sends the ultrasonic wave
 // the  echo pin is set as input because it recieves the ultrasonic wave
void setup() {
  
  Serial.begin (9600);
  pinMode (trigger_pin, OUTPUT);
  pinMode (echo_pin, INPUT);
  pinMode (buzzer_pin, OUTPUT);

}

void loop() {
  // Made the trigger pin and echo pin "HIGH" to send and recieve the ultrasonic wave
  // Added the equation to get the distance
  digitalWrite (trigger_pin, HIGH);
  delayMicroseconds (10);
  digitalWrite (trigger_pin, LOW);
  time = pulseIn (echo_pin, HIGH);
  distance = (time * 0.034) / 2;

  if (distance <= 15) {
    // If statement translates to "if there is an object in a distance of 15 or less the buzzer will go off" 
    Serial.println (" Door Open ");
    Serial.println (" Distance= ");
    Serial.println (distance);
    digitalWrite (buzzer_pin, HIGH);
    delay (500);
  }

  else {
    Serial.println (" Door closed ");
    Serial.print (" Distance = ");
    Serial.println (distance);
    digitalWrite (buzzer_pin, LOW);
    delay (500);
  }

}
'''
  k. Run the code. Make sure to save it as well. Use this video to check if your board looks and works the same: https://youtu.be/-ZwjPb01SVY


# Final Milestone
My final milestone is the increased reliability and accuracy of my robot. I ameliorated the sagging and fixed the reliability of the finger. As discussed in my second milestone, the arm sags because of weight. I put in a block of wood at the base to hold up the upper arm; this has reverberating positive effects throughout the arm. I also realized that the forearm was getting disconnected from the elbow servo’s horn because of the weight stress on the joint. Now, I make sure to constantly tighten the screws at that joint. 

[![Final Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1612573869/video_to_markdown/images/youtube--F7M7imOVGug-c05b58ac6eb4c4700831b2b3070cd403.jpg )](https://www.youtube.com/watch?v=F7M7imOVGug&feature=emb_logo "Final Milestone"){:target="_blank" rel="noopener"}

# Second Milestone
My final milestone is the increased reliability and accuracy of my robot. I ameliorated the sagging and fixed the reliability of the finger. As discussed in my second milestone, the arm sags because of weight. I put in a block of wood at the base to hold up the upper arm; this has reverberating positive effects throughout the arm. I also realized that the forearm was getting disconnected from the elbow servo’s horn because of the weight stress on the joint. Now, I make sure to constantly tighten the screws at that joint.

[![Third Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1612574014/video_to_markdown/images/youtube--y3VAmNlER5Y-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://www.youtube.com/watch?v=y3VAmNlER5Y&feature=emb_logo "Second Milestone"){:target="_blank" rel="noopener"}

# First Milestone
My first milestone is testing my ultrasonic sensor. My first step was to learn about how an ultrasonic sensor functions. The sensor emmits ultrasonic sound waves to an object and times the emission and reception of the wave; therefore, the sensor is able to derive the distance from the sensor to the object. After, I was able to code my arduino. My last step was assembly. I connected wires from by sensor to my arduino and the same for my buzzer. 

[![First Milestone][![First Milestone](https://res.cloudinary.com/marcomontalbano/image/upload/v1624634012/video_to_markdown/images/youtube---ZwjPb01SVY-c05b58ac6eb4c4700831b2b3070cd403.jpg)](https://youtu.be/-ZwjPb01SVY "First Milestone") {:target="_blank" rel="noopener"}

//Defines the pin the photoresistor is connected to
int PhotoR = D2;


//Sets PhtotR as input
void setup() {
    pinMode(PhotoR, INPUT);

}

//Flag to trigger sun vs no sun actions
bool flag = false;

void loop() {
    //Defines variable SunlightLevel which will read signals from the photo resistor
    int SunlightLevel = analogRead(PhotoR);
    
    //Base case for sunlight detected at the start of the program 
    if(SunlightLevel > 1.5 && flag == false)
    {
        flag = true;
        Particle.publish("Sun", "Sunshine detected", PRIVATE);
    }
    //Base case for no sunlight detected at the start of the program
    if(SunlightLevel < 1.5 && flag == false)
    {
        flag = true;
        Particle.publish("No Sun", "No sunshine detected", PRIVATE);
    }
    //Final case for no sunlight detected and flag is true
    else if (SunlightLevel < 1.5 && flag == true)
    {
        flag = false;
        Particle.publish("No Sun", "No sunshine detected", PRIVATE);
    }
    //Delay before re running to avoid constant email onslaught shortened for testing purposes
    delay(30000);
    

}

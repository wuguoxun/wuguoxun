**
import processing.serial.*;
Serial myPort;
String myText="";
void setup(){
size(300, 300);
myPort = new Serial(this, Serial.list()[1], 9600);
//myPort = new Serial(this, "COM4", 9600);
myPort.bufferUntil('n');
}
void serialEvent (Serial myPort){
myText = myPort.readStringUntil('n');
}
void draw(){
background(0,0,0);
text(myText, 150, 150);
myText="";
//if(mousePressed && (mouseButton == LEFT)){
//myPort.write('1');
//}
//if (mousePressed && (mouseButton == RIGHT)){
//myPort.write('0');
//}
}

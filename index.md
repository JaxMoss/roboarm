# User-Controlled Robot Arm
I constructed a robotic arm capable of being both controlled by a phone with bluetooth or ran automatically on a Raspberry Pi. The orginal design fo rthe arm was to run it with Arduino, however, I chose to transfer to a Raspberry Pi to allow for more complex automation. I spent multiple days conducting research on how to utilize a Pi with servos and code it in Python. 

<!---You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Jackson M | Wellesley High School | Mechanical Engineering | Incoming Senior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**

![Headstone Image](logo.svg)
  
# Final Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/dA2eTj6e8Xg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

To finalize my project, I disconnected the servos from the Arduino, instead directing them into a breadboard that led to a Raspberry Pi. I also connected a 7 inch lcd screen directly into the Pi. As I had not worked with servos in conjunction with a Pi before, I spent multiple days reading recources on how servos are controlled, how they are connected to a Pi, and how to program them in Python. Then following a guide online, I created loops in Python for each servo to run on. Because the project now has a more capable setup in the Raspberry Pi, I plan to use image recognition and a Pi camera to program the arm to mimic the movement of a human arm in front of it.



# Second Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/y3VAmNlER5Y" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

For my second milestone, I finished the functionality included in the kit by enabling the Bluetooth module and allowing the arm to be controlled by Bluetooth via an app on my phone. The Bluetooth module connects directly into the Arduino board and then connects to the phone and the app recognizes it from there. The preloaded code then translates each instruction from the app back into servo movement. The main challenge in this milestone was getting Bluetooth to connect properly as we had to order a new Android phone in order to properly use the app. Once that had arrived, the Bluetooth was up and running quickly! For my final milestone, I plan to transition the arm to run on a Raspberry Pi rather than Arduino so I can further experiment with the functionality of the arm next session!


# First Milestone

<iframe width="560" height="315" src="https://www.youtube.com/embed/bEWdnR8CKhA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
For my first milestone, I chose to complete the entire construction of the arm, including enabling servo movement. The main components of the project are the arduino board and shield, the acrylic pieces and screws, and the servos. The board connects via usb to a power source or a computer. The servos then connect to that board and are told how to move through the arduino IDE. The acrylic pieces are screwed into each servo and move accordingly. Some challenges I faced were the fragility of the acrylics and dexterity required for the nuts. It required a lot of patience and attention to detail. In the future, I plan to add modifications connecting an external sensor that will move the robotic arm according to my own arm movements. 


# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. 

# Code
Here's where you'll put your code. The syntax below places it into a block of code. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize it to your project needs. 

```Python
from gpiozero import AngularServo
from time import sleep

servo = AngularServo(3, min_pulse_width=0.0006, max_pulse_width=0.0023)
servo2 = AngularServo(2, min_pulse_width=0.0006, max_pulse_width=0.0023)
servo3 = AngularServo(4, min_pulse_width=0.0006, max_pulse_width=0.0023)
servo4 = AngularServo(5, min_pulse_width=0.0006, max_pulse_width=0.0023)

while (True):
    servo.angle = -45
    sleep(1)
    servo.angle = 0
    sleep(1)
    servo2.angle = -45
    sleep(1)
    servo2.angle = 0
    sleep(1)
```

# Bill of Materials
Here's where you'll list the parts in your project. To add more rows, just copy and paste the example rows below.
Don't forget to place the link of where to buy each component inside the quotation marks in the corresponding row after href =. Follow the guide [here]([url](https://www.markdownguide.org/extended-syntax/)) to learn how to customize this to your project needs. 

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| LAFVIN Arduino Arm Kit | Kit with acryllics for arm construction | $35.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/LAFVIN-Acrylic-Mechanical-Compatible-Tutorial/dp/B07ZYZVNY4#customerReviews"> Link </a> |


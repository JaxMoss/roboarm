# Hand-Controlled Robotic Arm
I constructed a robotic arm capable of being both controlled by a phone with bluetooth or ran automatically on a Raspberry Pi. The orginal design for the arm was to run it with Arduino, however, I chose to transfer to a Raspberry Pi to allow for more complex automation. I spent multiple days conducting research on how to utilize a Pi with servos and code it in Python. Then, I used image recognition with Tensorflow and OpenCV to control the arm through movements of my hand.

<!---You should comment out all portions of your portfolio that you have not completed yet, as well as any instructions:
```HTML 
<!--- This is an HTML comment in Markdown -->
<!--- Anything between these symbols will not render on the published site -->

| **Engineer** | **School** | **Area of Interest** | **Grade** |
|:--:|:--:|:--:|:--:|
| Jackson M | Wellesley High School | Mechanical Engineering and Computer Science | Incoming Senior

**Replace the BlueStamp logo below with an image of yourself and your completed project. Follow the guide [here](https://tomcam.github.io/least-github-pages/adding-images-github-pages-site.html) if you need help.**
 
![Headstone Image](logo.svg)

# First Milestone - Arm Built

<iframe width="560" height="315" src="https://www.youtube.com/embed/bEWdnR8CKhA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>
 For my first milestone, I chose to complete the entire construction of the arm, including enabling servo movement. The main components of the project are the arduino board and shield, the acrylic pieces and screws, and the servos. The board connects via usb to a power source or a computer. The servos then connect to that board and are told how to move through the arduino IDE. The acrylic pieces are screwed into each servo and move accordingly. Some challenges I faced were the fragility of the acrylics and dexterity required for the nuts. It required a lot of patience and attention to detail. In the future, I plan to add modifications, connecting an external sensor that will move the robotic arm according to my own arm movements. 

# Second Milestone - Arm with Bluetooth

<iframe width="560" height="315" src="https://www.youtube.com/embed/dA2eTj6e8Xg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

 For my second milestone, I finished the functionality included in the kit by enabling the Bluetooth module and allowing the arm to be controlled by Bluetooth via an app on my phone. The Bluetooth module connects directly into the Arduino board and then connects to the phone and the app recognizes it from there. The preloaded code then translates each instruction from the app back into servo movement. The main challenge in this milestone was getting Bluetooth to connect properly as we had to order a new Android phone in order to properly use the app. Once that had arrived, the Bluetooth was up and running quickly! For my final milestone, I plan to transition the arm to run on a Raspberry Pi rather than Arduino so I can further experiment with the functionality of the arm next session!
  
# Third Milestone - Arm on Pi

<iframe width="560" height="315" src="https://www.youtube.com/embed/5yEJCYnlMCA" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

 To finalize the first half of my project, I disconnected the servos from the Arduino, instead directing them into a breadboard that led to a Raspberry Pi. I also connected a 7 inch lcd screen directly into the Pi. As I had not worked with servos in conjunction with a Pi before, I spent multiple days reading recources on how servos are controlled, how they are connected to a Pi, and how to program them in Python. Then following a guide online, I created loops in Python for each servo to run on. Because the project now has a more capable setup in the Raspberry Pi, I plan to use image recognition and a Pi camera to program the arm to mimic the movement of a human arm in front of it.


# Fourth Milestone - Camera

<iframe width="560" height="315" src="https://www.youtube.com/embed/dA2eTj6e8Xg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

 Moving on to the programming aspect of my project, I was first tasked with setting up a camera so I can begin my image recognition work. I first downloaded all the depenedencies I would need to use Tensorflow and OpenCV on my Pi. Unfortunately, once I had enabled the Pi camera and installed dependencies, I ran into low current issues. To solve this, I ordered a powered USB hub to provide extra current to the camera. This fixed the problem and the computer vision was up and running swiftly. 

# Fifth Milestone - Image Recognition

<iframe width="560" height="315" src="https://www.youtube.com/embed/dA2eTj6e8Xg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

 With the camera set up, it was now time to program the Raspberry Pi to recognize and track my hand. Using online resources on OpenCV and Mediapipe, I learned how to divide the tracking into 21 landmarks on my hand. Each frame from the camera is processed, and once a hand, or hands, are detected on the screen, landmarks are created at the centerpoint of each significant area of the hand including the knuckles, the finger tips, and the wrist. New landmarks are drawn each time the Pi is able to process a frame, hence the appearence that the hand is being contuinously tracked across the screen. With this completed, it was now time to finalize the project by combining servo movement with the corresponding hand information. 

# Final Milestone - Arm Moved By Hand

<iframe width="560" height="315" src="https://www.youtube.com/embed/dA2eTj6e8Xg" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" allowfullscreen></iframe>

&nbsp The first step in implementing the servos into the loop was just to ensure they could run at the same time the image recognition did. And lo and behold, they could not. The issue was that similar to the USBs, the servos were drawing too much current. To resolve this, I made a final part order for a HAT that was specifically made for actuating servos with a Pi. Once I got it, I soldered on the header pins and attatched it to my Pi. Another plus side of the hat was I no longer had to complicate my build with a breadbard as the middle man, as the hat was built specifically to allow easy use with servos. Finally, both the servos and hand recognition could run synchronously. Now it was just a matter of making corresponding servo movements for the incoming hand information. <br>
 After a few hours of programming, I had made a key that translated the x and y coordinates of my wrist and finger tips into servo angles. This meant that when I moved my hand, the servos on the arm would change their angle to match the new position of my hand. I was extremely happy to see my project finally working after weeks of hard work. However I still had a lingering feeling of disappointment. <br>
 The problem was that because of the large toll the image processing took on the Pi, there was a large amount of latency from the time when I would move my hand to the time the servos would move. I was determined to improve it. With the help of my instructor and online guides on threading, I was eventually able to divy up the task of image proceessing to multiple parts of the Pi, increasing the speed and effectively halving the latency. Finally, I had a project that had not only met, but exceeded my intitial designs. 
<!---# Schematics 
Here's where you'll put images of your schematics. [Tinkercad](https://www.tinkercad.com/blog/official-guide-to-tinkercad-circuits) and [Fritzing](https://fritzing.org/learning/) are both great resoruces to create professional schematic diagrams, though BSE recommends Tinkercad becuase it can be done easily and for free in the browser. -->

# Code

```Python
import cv2
import mediapipe as mp
import time
import threading
import numpy as np
from adafruit_servokit import ServoKit

kit = ServoKit(channels=16)

kit.servo[0].angle = 90
kit.servo[3].angle = 90
kit.servo[4].angle = 90
kit.servo[8].angle = 90

pos0 = 90
pos3 = 90
pos4 = 90

spd = 10

def sqr(num):
    return num * num

def control_servos(lmlist):
    global pos4, pos3

    if len(lmlist) != 0:
        lmlist_np = np.array(lmlist)
        cx0, cy0 = lmlist_np[0, 1:]
        cx4, cy4 = lmlist_np[4, 1:]
        cx8, cy8 = lmlist_np[8, 1:]

        # Calculate distance between index finger and pinky finger
        distance = np.sqrt(sqr(cx4 - cx8) + sqr(cy4 - cy8))

        if distance < 22:
            kit.servo[0].angle = 20
        if distance > 50:
            kit.servo[0].angle = 90

        pos4 = (cy0 - 500) / 3 * -1
        kit.servo[4].angle = pos4

        pos3 = cx0 / 3.5
        kit.servo[3].angle = pos3

        print(pos4)

def main():
    global pTime
    cap = cv2.VideoCapture(0)

    # Set camera resolution to reduce computational load
    cap.set(cv2.CAP_PROP_FRAME_WIDTH, 640)
    cap.set(cv2.CAP_PROP_FRAME_HEIGHT, 480)

    detector = mp.solutions.hands.Hands(
        min_detection_confidence=0.5, min_tracking_confidence=0.5, static_image_mode=False, max_num_hands=1
    )

    while True:
        success, img = cap.read()

        imgRGB = cv2.cvtColor(img, cv2.COLOR_BGR2RGB)
        results = detector.process(imgRGB)

        lmlist = []
        if results.multi_hand_landmarks:
            for handLms in results.multi_hand_landmarks:
                for id, lm in enumerate(handLms.landmark):
                    h, w, c = img.shape
                    cx, cy = int(lm.x * w), int(lm.y * h)
                    lmlist.append([id, cx, cy])
                    cv2.circle(img, (cx, cy), 3, (255, 0, 255), cv2.FILLED)

        # Control servos based on hand landmarks
        t1 = threading.Thread(target=control_servos, args=(lmlist,))
        t1.start()
        t1.join()

        cTime = time.time()
        fps = 1 / (cTime - pTime)
        pTime = cTime

        cv2.putText(img, str(int(fps)), (10, 70), cv2.FONT_HERSHEY_PLAIN, 3, (255, 0, 255), 3)

        cv2.imshow("Image", img)
        cv2.waitKey(1)

if __name__ == "__main__":
    pTime = 0
    main()

```


# Bill of Materials

| **Part** | **Note** | **Price** | **Link** |
|:--:|:--:|:--:|:--:|
| LAFVIN Arduino Arm Kit | Acryllic pieces | $35.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/LAFVIN-Acrylic-Mechanical-Compatible-Tutorial/dp/B07ZYZVNY4#customerReviews"> Acryllic </a> |
| Servos x4 | Servos for arm actuation | $9.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/LAFVIN-Acrylic-Mechanical-Compatible-Tutorial/dp/B07ZYZVNY4#customerReviews](https://www.amazon.com/Micro-Servos-Helicopter-Airplane-Controls/dp/B07MLR1498/ref=sr_1_7?crid=2MVLNTZVWSX8F&keywords=arduino+servos&qid=1691178664&sprefix=arduino+servos%2Caps%2C95&sr=8-7)https://www.amazon.com/Micro-Servos-Helicopter-Airplane-Controls/dp/B07MLR1498/ref=sr_1_7?crid=2MVLNTZVWSX8F&keywords=arduino+servos&qid=1691178664&sprefix=arduino+servos%2Caps%2C95&sr=8-7"> Servos </a> |
| Raspberry Pi 4 (4 GB)| Single board computer | $54.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/LAFVIN-Acrylic-Mechanical-Compatible-Tutorial/dp/B07ZYZVNY4#customerReviews](https://www.adafruit.com/product/4296)"> Pi </a> |
| Adafruit Servo HAT | HAT for servos | $20.99 | <a href="https://www.amazon.com/Arduino-A000066-ARDUINO-UNO-R3/dp/B008GRTSV6/](https://www.amazon.com/LAFVIN-Acrylic-Mechanical-Compatible-Tutorial/dp/B07ZYZVNY4#customerReviews](https://www.amazon.com/2327-Raspberry-Servo-Development-Board/dp/B00SI1SPHS/ref=sr_1_5?adgrpid=1332608862879986&hvadid=83288255921130&hvbmt=be&hvdev=c&hvlocphy=103397&hvnetw=o&hvqmt=e&hvtargid=kwd-83288539673259%3Aloc-190&hydadcr=24329_13514992&keywords=rpi+servo+hat&qid=1690564018&sr=8-5)https://www.amazon.com/2327-Raspberry-Servo-Development-Board/dp/B00SI1SPHS/ref=sr_1_5?adgrpid=1332608862879986&hvadid=83288255921130&hvbmt=be&hvdev=c&hvlocphy=103397&hvnetw=o&hvqmt=e&hvtargid=kwd-83288539673259%3Aloc-190&hydadcr=24329_13514992&keywords=rpi+servo+hat&qid=1690564018&sr=8-5"> HAT </a> |

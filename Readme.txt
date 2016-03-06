The major drawback in today’s surveillance rests on the involvement of human operators which can easily be distracted, so we need a system which can autonomously monitor regions continuously, making decisions while identifying unwanted or obnoxious things and respond accordingly. Object tracking using computer vision is crucial in achieving automated surveillance. 

I made this project in order to build a basic ball tracking car. Here, my bot uses camera to take frames and do image processing to track down the ball. The features of the ball such as color, shape, size can be used.

But my objective was to make a basic prototype for such a bot which can sense color and shape and follow it. My robot tries to find a color which is hard coded, if it finds a ball of that color it follows it.

I have chosen raspberry pi as micro-controller for this project as it gives great flexibility to use Raspberry Pi camera module and allows to code in Python which is very user friendly and OpenCV library, for image analysis.

For controlling the motors, I have used an H-Bridge to switch from clockwise to counter-clockwise or to stop the motors. This I have integrated via code when direction and speed has to be controlled in different obstacle situations.

Crucial thing while detecting images frame by frame was to avoid any frame drops as then the bot can go into a limbo state if the bot is unable to predict direction of ball after few frame drops. Even if it manage the frame drops then also if the ball goes out of scope of the camera, it will go into a limbo state, in that case, then I have made my bot take a 360 degree view of it's environment till the ball comes back in the scope of the camera and then start moving in it's direction.

For the image analysis, I am taking each frame and then masking it with the color needed. Then for noise reduction, I am eroding the noise and dilating the major blobs. Then I find all the contours and find the largest among them and bound it in a rectangle. And show the rectangle on the main image and find the coordinates of the center of the rectangle.I have attached the algorithm (pseudo-code) of the image analysis part and demonstrated this part in the video also. 

Finally my bot tries to bring the coordinates of the ball to the center of its imaginary coordinate axis. This is how my robo works. I enjoy a lot working on this project and its a nice experience.

You can watch the video at url: https://youtu.be/jQ0FqnQZXF0
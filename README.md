# Ai-bse-self-driving-car-training-model-

In this section self-driving car fully training and running in a simulated environment. Audacity
was recently open source their simulation so the build a simulator specifically for self-driving cars.
It was built for their self-driving car an inner degree any people. So it was built with unity and
could recommend most of research papers. So it was added a bunch of pre-built scripts. Also
control things, momentum and acceleration and all sorts of things would be in a selfdriving car
simulation. Programmer could modified that things as well as could can change in code. Step
process of this simulation have three steps.

• Data generating part

• Training part

• Testing part

Thus, first part was data generation part. Fist NVidia car simulation was studied. So nine layer
convolutional network was built by them and attached three cameras to the head of car. While
human driver was driven the car while the cameras were attached and all the car has to do was
collect data and steering command. That the human driver was inputting as well as the camera
feed so the three set of camera images were come from all three cameras at the same time and that
was the data generation part. There were images from the center, left and right cameras with the
associated steering angle speed throttle and break. So there was four physics variables as well as
the static images that were come in and it was saved.

Second part was training part. So the human driver was driven around and recoded all that data.
After data was get a machine to clone that behavior. So this process was Behavioral cloning. So
doing the behavioral cloning, nine layers were built of convolutional network. Nine layers was in 
63keras. There was nine lines of code and it would base off of NVidias and to end learning for
selfdriving paper. That car model was trained whole 72 hours in different driving conditions (sleet,
rain hail, wet rain all such things). Therefore here is a hardware design. 

So hard ware design was obviously a steering wheel. But the steering wheels was attached to a
controller. That was the so many acronyms here because the controller area network bus and it
was feeding in those four variables. Three cameras were feeding in continuous streams. All the
images (frame by frame) were seeing by the car and those were fed in to this NVidia drive PX
computer. It was essentially like a motherboard with a cluster of jeep on board GPUs attached to
it and stored the results.

So regarding the research paper was recorded instead of inputting the steering command directly.
So it was inputted 1/R (R= training radius for driving straight). Now can found it may be turn
smoother and it was made autonomous angle that the car moved independent of the geometry of
the car. So the car was faced left or right not matter. It was deepened on what the cameras see. So
that steering angle was moved by signal. It was independent of the car directions. So software was
designed that it was depend on a code. 

There were have two inputs (Steering angle and sets of cameras) and three set of images (left, right
and center). So input labels were images and output labels were steering angle. So let’s assuming
the generated dates were 72 hours of human generated driving data. So both of result (our data and
NVidia data) could compared together. So error or loss could computed between the two. So cameras
Angles and the steering wheel variable were human generated data and compressed both this value
in to one value. There had error value between that dataset and used propagation to update weights
base on that error value. So images were faded in to CNN (Convolutional neural network) then it
was computed a proposed during commit. That was predicted steering command. So difference
between the predicted steering command and actual steering command were depended of training
data. Then proposed command was expected to command right label the target versus the actual
output. The weights of the CNN were adjusted to bring the CNN output closer to the desired output
and the weight adjustment were accomplished via back propagation. So in the CNN, prediction was
the angle of the steering with just one output. So that was for training.


For testing, this Autonomous model could think of the terms of a simulator as a server client
architecture. Server was gone to be the simulator itself. It mean app was downloaded and client
was gone to be python program that write. So it was gone just feedback loop. Client was piped in
steering angles and throttles to the server and the server was typed backup images from car and
steering angles. So it could train right it was a feedback loop. 

Then the augmented images were fed through the network which is configured with 10 layers and
resulting in the steering angle as the required output. 

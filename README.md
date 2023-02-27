# Doom_Neural_Network

This is a repo for my exploration into Neural networks within the relm of visual only video game control.
I am mimicking "real world" control as in reality a robot or system will only have access to visual features (primarily) and not access to ram locations or precise accurate locations of targets.  As the use of open source video games has a much lower barrier to entry than producing a physical robot I have chosen to use vizdoom as a testbed for AI and machine learning networks.

The ubiquitous game Doom has been a part of engineering culture since it’s creation in 1993, and as such has been included in many software and hardware projects.  One such software library is the “vizdoom” library that allows for python interfacing, using both vizdoom and pytorch, a common Machine learning library I was able to train a neural network to play doom.  Included in this report is both a ‘solo’ network and a network that is trained against itself in adversarial training, both are examples of Reinforcement Learning (RL) training.  Reinforcement learning is a fascinating topic as it is suited well for robotics training, which is my field of interest.

# Network Architecture

The Network in question is comprised of lightweight CNN layers, fed into a RNN and then compared with a Linear Fully Connected layer (FC), pictured below in figure 1.
![image](https://user-images.githubusercontent.com/87808632/221710214-ae3345ca-e4d8-4873-a503-05729dff7c91.png)
Network printout [1].

The networks were trained using a Learning rate (Lr) scheduler which will decrease the Learning rate once the network plateaus in performance.  This drastically decreases the training time as it can “learn quick and dirty” at the start without causing divergent behavior where network performance oscillates around the optimal performance without converging.
The weights in a network are typically updated with the following formula:

ω^(t+1)= ω-η*gradient

Clearly a larger learning rate (η) will increase the change in weights.

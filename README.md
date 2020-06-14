# ARGoS-Buzz Boilerplate
A minimal setup to run Buzz scripts within the ARGoS simulator

# Prerequisites
In order for this code to work properly, ARGoS and Buzz should already be installed on your computer. This repository was built on Ubuntu 20.04 LTS.

The installation instructions for both ARGoS and Buzz can be found here : https://the.swarming.buzz/wiki/doku.php?id=buzz_argos

There is no need to follow the instructions on how to define an ARGoS experiment file, since this boilerplate already has one. You may want to learn the syntax, though.

# How to start the "hello_buzz" experiment
The `hello_buzz.argos` file located in the `experiments` folder contains some minimal configuration which spawns one buzz foot-bot robot in the middle of a simple map. As of now, it does not have any behavior logic.

To start "hello_buzz" within ArgOS, run

```
argos3 -c experiments/hello_buzz.argos
```
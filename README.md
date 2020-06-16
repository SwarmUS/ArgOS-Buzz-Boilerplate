# ARGoS-Buzz Boilerplate
A minimal setup to run Buzz scripts within the ARGoS simulator

# Prerequisites
In order for this code to work properly, ARGoS and Buzz should already be installed on your computer. The installation instructions for both ARGoS and Buzz can be found here: https://the.swarming.buzz/wiki/doku.php?id=buzz_argos

_Make sure you install ARGoS prior to installing Buzz, as recommended in the documentation._

There is no need to follow the instructions on how to define an ARGoS experiment file, since this boilerplate already has one. You might want to learn the syntax, though.

This repository was built and tested on Ubuntu 20.04 LTS.

# How to start the "hello_buzz" experiment
The `hello_buzz.argos` file located in the `experiments` folder contains some minimal configuration which runs some basic Buzz examples (see: https://the.swarming.buzz/wiki/doku.php?id=buzz_examples).

By default, `hello_buzz.argos` is set to spawn 4 Buzz Foot-Bots controllers programmed with the `square.bzz` example. However, you can edit the experiment file to load any compiled Buzz bytecode on your robot controllers (this repo also contains `gradient.bzz` and `hexagon.bzz` for you to try).

To run the basic `hello_buzz` experiment, follow these steps.

## 1. Build your Buzz code using the toolset

You might want to read mode about the Buzz toolset: https://the.swarming.buzz/wiki/doku.php?id=buzz_toolset

For now, let's focus on simply compiling the code:

```
$ bzzc -I /path/to/buzz/src buzz_code/square/square.bzz
```

The `-I` argument is only necessary for the `hexagon` and `square` scripts, since they include the `vec2d.bzz` library. The folder where you downloaded Buzz contains a number of libraries which you might need to reference to `bzzc` upon building, depending on you scripts.

Building the code using `bzzc` should produce two files : `square.bo` and `square.bdb`. Both are referenced in the `hello_buzz.argos` experiment file at the line:

```xml
<params bytecode_file="buzz_code/square/square.bo" debug_file="buzz_code/square/square.bdb" />
```
## 2. Start the experiment

To start "hello_buzz" within ARGoS, run

```
$ argos3 -c experiments/hello_buzz.argos
```

The ARGoS simulator should render 4 robots on a map. Click `Play` and they should move to create a square.

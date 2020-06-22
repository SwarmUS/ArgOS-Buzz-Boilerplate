# ARGoS-Buzz Boilerplate
A minimal setup to run Buzz scripts within the ARGoS simulator

# Hierarchy

Each folder under `src/` is a Buzz script and yields a corresponding folder under `build/` when the project is built.

The `experiments` folder contains the ARGoS experiment files.

```
ArgOS-Buzz-Boilerplate
|-- build/
|-- experiments/
|   |-- square.argos            # Example ARGoS experiment file which uses some Buzz binary code
|-- src/
|   |-- CMakeLists.txt
|   |-- square/
|   |   | square.bzz                # Example Buzz scripts

```

# Prerequisites
In order for this code to work, ARGoS and Buzz should already be installed on your computer. The installation instructions for both ARGoS and Buzz can be found here: https://the.swarming.buzz/wiki/doku.php?id=buzz_argos

_Make sure you install ARGoS prior to installing Buzz, as recommended in the documentation._

There is no need to follow the instructions on how to define an ARGoS experiment file, since this boilerplate already has one. You might want to learn the syntax, though.

This repository was built and tested on Ubuntu 20.04 LTS.

# How to build the project
Building the project goes as follows :

```
mkdir build
cd build
cmake ../src
make
```

This generates two files for each buzz script : a `.bo` file and a `.bdb` file. Both these files should be referenced in your `.argos` experiment file, upon declaring your robot controllers. You must specify the files in the `<params>` tag.

For example, in the `square.argos` experiment file, the files are specified at the line

```xml
<params bytecode_file="build/square/square.bo" debug_file="build/square/square.bdb" />
```

# How to start the "hello_buzz" experiment
The `square.argos` file located in the `experiments` folder contains some minimal configuration which runs the basic Buzz examples found in `src/`.

By default, `square.argos` is set to spawn 4 Buzz Foot-Bots controllers programmed with the `square.bzz` example. However, you can edit the experiment file to load any compiled Buzz bytecode on your robot controllers.

Assuming you have already built the project, you can start the experiment with

```
$ argos3 -c experiments/square.argos
```

The ARGoS simulator should render 4 robots on a map. Click `Play` and they should move to create a square.

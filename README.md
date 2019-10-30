# Eva
## What is ***Eva***?
  Eva - is ***planning*** to be project built with Scala and Akka Aktors, which will handle requests from ***MicroController***. Furhermore, ***Eva*** will be MVP for smart home solutions.


## What is ***MicroController***?
  MicroController - is ***planning*** to be simple microcontroller (most likely based on **AVR**) connected to Wifi module (most likely based on **ESP**) and/or with sensor. MicroController will deal with income information from sensor and send it to ***Eva*** via Wifi module. There are two types of MC: Acting and Sensoring.

### Sensoring Modules: (SM)
  - Always alive
  - Notifying ***Eva*** if something has happened
  - Could be placed in groups to notify with the same kind of event

### Acting Modules: (AM)
  - Alive only for some time (during time of action)
  - Reacting on what has happened (by ***Eva***'s opinion)
  - Could be placed in groups to react on the same kind of event

## Why?
  - Improve `scala` skills (***Eva*** will be built on `scala`)
  - Improve `Clang` skills (Every firmware on ***AVR*** will be build on `Clang` or `Arduino lang`)
  - Improve `Soldering Iron` skill
  - Improve `Archicture building` skill
  - Too lazy for doing staff (especially at night)

## How it ***will*** work (in code)?
  SM groups will be paired with AM groups (so it mean's that there must always be SM for AM).
  We create AM and SM, then we have to introduce them to ***Eva*** (most likely it would be on SM/AM side)

  ### Simple flow:
  - Pair of SM and AM connect to ***Eva***
  - ***Eva*** register SM as `SensoringWorker` and AM as `Acting Worker`
  - Client app configure sensor **Dead zones** via ***Eva***
  - Sensor detects value in dead zone and notify ***Eva***
  - ***Eva*** spawns `ActingWorker` which would act to SM event


## How it ***will*** work (in your user experience)?
  - You will be able to buy/build your own modules. It will be rather simple
  - You will have a real nice and great configuration manager that will config all flows with
  - Monitoring 24/7
  - Metrics
  - Beautiful graphs and charts build on top of those metrics
  - API

## What I want at all?
  - HMR - (Hot module replacement) it means that in any time you could replace any of AM/SM and nothing bad will happen
  - Private - it will run only on local machine, no clouds
  - Config - it will be easy to configure (any flows you want, any slates), in some further time there will DSL available for configuration and ofc real nice UserInterface
  - Fault tolerance
  - HFR - (Hot firmware replacement) it means that ***Eva** will be able to update any of modules firmwares (Dont know to deal with both privacy and hfr)


## Code Base:
  ![Arch](https://github.com/7challenger/eva/blob/master/docs/eva-arch-scheme.png?raw=true)

## RoadMap:
### Eva: ETA: December 2019
  - [ ] Create simple ActingWorkers
  - [ ] Create simple SensoringWorkers
  - [ ] Create simple master ***Eva***

### Modules: ETA: December - March (2019 - 2020)
  - [ ] Create simlpe Acting module
  - [ ] Create simlpe Sensoring module
  - [ ] Create firmwares for them

### Helpers Services: (ETA: N/A)
  - [ ] Create Logging service
  - [ ] Create Metrics service
  - [ ] Create HFR server
  - [ ] Create HelthCheck service

### Interfaces: (ETA: N/A)
  - [ ] Create interface for introducing them to ***Eva***
  - [ ] Create public interface(WS) for client app

### Deployment: (ETA: N/A)
  - [ ] Deploy locally
  - [ ] Deploy on WDS
  - [ ] Deploy on Raspberry
  - [ ] Create `solution-box`

### Heplers:
  - [ ] Create boilerplate for firmware
  - [ ] Create boilerplate for hardware module

# TODO:
- Deal with data storage
- Deal with deployment (mqtt, other solutions)


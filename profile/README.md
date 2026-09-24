# Daydream Robotics

Daydream is the University of Central Florida's VEX U robotics team at Robotics Club of Central Florida.

This GitHub organization contains the software infrastructure used to develop, simulate, localize, control, and test our competition robots. Our current focus is building a unified autonomous robotics stack that can operate consistently across both simulation and physical hardware.

## Autonomous Systems

Our software is organized around two primary repositories:

### Robot Core

**Robot Core** contains the software that runs and supports the physical robot.

This includes:

* Autonomous routine execution
* Motion control and trajectory following
* Embedded robot systems
* Wheel odometry
* IMU integration
* LiDAR-based localization using Monte Carlo Localization (MCL)
* Sensor fusion and pose estimation
* Mechanism control
* Robot hardware interfaces
* Autonomous platform infrastructure
* Telemetry and debugging tools

Robot Core acts as the primary runtime for the real robot and defines much of the shared architecture used throughout our autonomous stack.

> For implementation details, architecture, setup, and subsystem documentation, see the **Robot Core repository**.

---

### DreamSim

**DreamSim** is our simulation and digital-twin environment built around NVIDIA Isaac Sim.

Its purpose is to provide a repeatable environment for developing and testing autonomous behavior before deploying it onto physical hardware.

DreamSim includes:

* Robot digital twin
* Competition field simulation
* Programmatic simulation control
* Repeatable autonomous testing
* Simulated robot execution
* Ground-truth state for validation
* Sim-to-real testing infrastructure
* Integration with the autonomous platform used by Robot Core

The long-term goal is for autonomous routines and higher-level planning systems to operate against a common interface, allowing behavior to move between simulation and the physical robot with minimal changes.

> For simulation setup, robot models, Isaac Sim tooling, and digital-twin documentation, see the **DreamSim repository**.

---

## Platform Architecture

The larger goal of the UCF7 software stack is to treat simulation and the physical robot as two execution environments for the same autonomous system.

At a high level:

```text
             Autonomous Routine / Plan
                       |
                       v
              Platform / Execution
                       |
            +----------+----------+
            |                     |
            v                     v
       DreamSim               Robot Core
      Isaac Sim              Physical Robot
            |                     |
            +----------+----------+
                       |
                       v
               Telemetry / Results
```

This architecture allows us to develop autonomous functionality independently from the environment in which it runs.

A routine should ultimately be able to define **what the robot should accomplish**, while the underlying platform handles execution, localization, motion control, and hardware or simulation-specific behavior.

## Current Development Direction

Our current development work is focused on building the infrastructure required for increasingly automated autonomous routines.

Major areas include:

* Reliable localization and pose estimation
* LiDAR-based MCL localization
* Embedded odometry and sensor fusion
* Robust motion-control infrastructure
* Standardized autonomous routine execution
* Shared interfaces between simulation and hardware
* Isaac Sim digital-twin development
* Automated and repeatable simulation testing
* Sim-to-real validation and telemetry

These systems form the foundation for future autonomous planning tools capable of generating increasingly complete robot behavior from higher-level objectives.

## Repository Guide

For most development work:

* **Working on the physical robot, localization, controls, embedded systems, or autonomy infrastructure?**
  Start with **Robot Core**.

* **Working on Isaac Sim, the digital twin, simulation tooling, or sim-to-real testing?**
  Start with **DreamSim**.

Each repository contains its own setup instructions, architecture documentation, development guidelines, and subsystem-specific information.

---

## Daydream

Daydream competes in **VEX U** under the banner DYDRM, previously known as UCF7.

Our software team works across robotics, controls, embedded systems, localization, simulation, computer vision, and autonomous systems with the goal of building reliable competition-ready robotics infrastructure.

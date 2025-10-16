# 🟡 PacMan on LandTiger Board

A complete PacMan implementation for the LandTiger LPC1768 development board.
This project was written in C using Keil µVision.

## 📘 Overview

This project reproduces the iconic PacMan game on an embedded system, demonstrating how game logic, real-time rendering, and peripheral management can be implemented on a microcontroller.

Platform: LandTiger LPC1768 board

Environment: Keil µVision (SW_Debug & Hardware modes)

Language: C

Peripherals used: LCD display, joystick, interrupt buttons, speaker, CAN bus

## 🎮 Base Game

Implemented using the LandTiger emulator (SW_Debug target).
Features:

Full labyrinth with 240 standard pills and 6 randomly generated power pills

Joystick control for PacMan movement

Score system:

+10 points for normal pills

+50 points for power pills

Lives system: +1 life every 1000 points

Teleport points on both sides of the maze

Pause mode: via INT0 interrupt

Countdown timer: 60 seconds

Game over / Victory screens

Fully rendered on the board’s LCD display

## 👻 Advanced Features

Implemented on the physical LandTiger board.
Extends the base game with new functionalities:

### 🧠 AI Ghost (Blinky)

Implements two behavior modes:

Chase Mode: follows PacMan using a pathfinding algorithm (A*)

Frightened Mode: triggered when PacMan eats a power pill — Blinky turns blue, runs away, and can be eaten for extra points

Respawns after 3 seconds in the center of the maze

### 🔊 Sound System

Background music and sound effects via on-board speaker

### 🛰️ CAN Bus Communication (Loopback Mode)

Periodically transmits the current score, remaining lives, and countdown time through the CAN1 controller

CAN2 receives and decodes the same message

32-bit message encoding:

[8 bits remaining time | 8 bits remaining lives | 16 bits score]


## ⚙️ Technical Highlights

Real-time game loop with collision and timer management

Interrupt-based pause/resume system

Structured code with configuration headers and modular logic

Use of Keil debugging tools for development and testing

Integration of multimedia and communication protocols in an embedded context

## 🧑‍💻 Credits

Developed by Lorenzo Iantosca
Under the supervision of the Computer Systems Architecture course (PoliTo) — Academic Year 2024/2025.
Inspired by PacMan (Namco, 1980).

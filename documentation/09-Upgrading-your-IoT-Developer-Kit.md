# Upgrading your IoT Developer Kit

## Introduction
This document provides instructions on how to upgrade your T-Mobile DevEdge IoT Developer Kit's Zephyr SDK, also known as the tmo_shell. To learn more about the tmo_shell, please read the Interacting with the Kit at CLI via tmo_shell document. 

## Prerequisites
- The T-Mobile DevEdge IoT Developer Kit. 
- Git installed
- Zephyr west installed if you are going to install the upgrade using west.
   - An FTDI cable.
- The J-Flash Lite app from SEGGER. If you do not have J-Flash Lite installed, please go here. 
   - Two USB-C to USB A cables.
- A serial app like Tera Term, PuTTY, or Serial. 
- An Internet connection over Wi-Fi.

## Why would I want to implement the instructions in this document?
- When you receive your beta T-Mobile DevEdge IoT Developer Kit the tmo_shell will be at version 1.8.0. However, version 1.9.x will be available for you to flash onto your IoT Developer Kit. If you would like the latest version of the tmo_shell, you should follow the configurations below. Version 1.9.x includes the following features:
   - Direct download of firmware updates to the kit. 
      - `tmo dfu download` 
   -  Buzzer API calls at CLI
      - `tmo buzzer jingle`
   - Connecting to the Web App
      - Version 1.9.x can connect to the web app found here https://devkit.devedge.t-mobile.com/.
      - To connect to your IoT Developer Kit to the web app, please read the document Accompanying Apps.

## What are the ultimate goals of this documentat?
- To teach the reader how to upgrade their beta T-Mobile DevEdge IoT Developer Kit tmo_shell from 1.8.0 1o 1.9.x.

## Configuration

### Step A Flash your Developer Kit
There are three way to flash the 1.9.x image onto your kit. You can use Zephyr west, the SEGGER J-Flash Lite app, or do a full install of Zephyr. All three options are covered below.

#### Option A.1 - Zephyr west
If you already have Zephyr west installed on your computer, follow the configurations below. 
1. Go to
2. Download the

***
[<< Go back](08-Driver-Configurations.md) &nbsp; | &nbsp; [Up next >>](10-Accompanying-Apps.md)


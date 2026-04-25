[![forthebadge](/badges/gluten-free.svg)](https://forthebadge.com)

# Lime Scooter GPS Notifier

A lightweight tool that locates nearby Lime scooters and alerts you when one enters a defined radius.

## Overview
This project queries the Lime API to:
- Retrieve nearby scooters based on your location
- Continuously monitor scooter proximity
- Notify you (via sound) when a scooter is within range

It’s designed for situations where you want to passively wait for a nearby scooter instead of repeatedly checking the app.

---

## Setup

**Requirements**
- Lime account
- C++ compiler (`g++`)
- Python 3

**Steps**

1. Run the setup script to authenticate:
   g++ setup.cpp && ./a.out

2. This generates:
   LimeUser.txt  
   (stores your session/auth info)

---

## Configuration

Before running the main script, update your location:

- Open `getNearestScooter.py`
- Set your coordinates on line 12:
  currLocation = (latitude, longitude)

You can convert an address to coordinates here:  
https://www.gps-coordinates.net/

---

## Usage

Run the script:
python3 getNearestScooter.py

---

## Key Parameters

- `radius`  
  Distance (in meters) used to detect nearby scooters  
  Recommended: ~300m

- `outputAllScooters`  
  outputAllScooters = False  
  - False: Continuous monitoring + notification mode  
  - True: Returns a list of all scooters within `radius`

---

## How It Works

- Continuously polls the Lime API
- Calculates distance using geospatial math (accounts for Earth curvature)
- Compares scooter locations against your defined radius
- Triggers a sound alert when a scooter enters range

---

## Use Case

Ideal if:
- You want to grab a scooter without constantly checking the app
- You're waiting before leaving and want real-time availability
- You want a simple proximity-based alert system for scooters

---

## Notes

- Excessive API polling may result in rate limiting
- Use responsibly and in accordance with Lime’s terms of service

---

If you find this useful, consider starring the repo.

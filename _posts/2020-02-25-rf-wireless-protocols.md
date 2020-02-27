---
layout: "post"
title: "RF wireless protocols"
date: "2020-02-25 09:39"
category: Backend
---

I just started reading this book "IoT for Architects" and it started on RF wireless protocols. The range of transmission depends upon: distance, frequency, and power. To improve transmission you either increase the power or decrease the loss. It's important to take these into considerations when picking a WAN solution where you'll be picking a radio spectrum or band over another.

The 2.4 GHz spectrum is unlicensed and available in a lot of countries plus it has more data bandwidth but covers short distances. (IoT, Bluetooth and 802.11 Wi-Fi)

The 900 MHz can go further, penetrate most materials but has a limited data rate.

The goal in communication is to maximize bitrate and distance given the spectrum and noise.

The spectrum ranges from 3Hz to 3THz and the ITU decides on who gets what. A band is a portion of the spectrum that is allocated or sold.

Bluetooth is non IP communication system (cost and energy efficient) whereas the Wi-Fi is IP based (with fewer constraints).

Wi-Fi uses the 802.11 protocol pervasively, there's the 802.11ah spec which is targeted for IoT devices.

Worth remembering the Network layer uses the IP protocol, TCP is used for the transport layer.

What is Neighbor discovery anyway?

WLAN is everything in a local net with WAN it's with the 'internet'. 

+++
title = "MQTT: I heard its over-rated"
author = ["Sean Terrell"]
date = 2020-06-29T07:32:00-05:00
lastmod = 2020-06-29T14:14:51-05:00
tags = ["SCADA", "IIoT", "Comms", "network"]
draft = false
+++

**Appaently the first rule of MQTT is we dont talk about MQTT**

Sure, its all over LinkedIN. Its the first thing anyone mentions in a conversation about IoT or the future of automation. But what the hell is it?

**Message Queing Telemetry Transport** - the words MQTT is supposed to represent dont mean a whole helluvlot to me. Messages are pretty standard communications between .. fucking anything. And Queing sounds like there is either a time slot to transmit which means asyncronus data out and that blows, or that the state of the connection can hold message delivery in a que.. and that would be ok.

**MQ Telemetry Transport** Ok so we know that Message Queing is happening and **Telemetry** ok thats sensor data. Now we are getting into an automation monkey's wheel house. Telemetry almost always refers to sensors and devices sending reporting data. Often times Telemetry is commutated values packed into a very tiny message and booted out in a single frame called fire and forget... just hoping that the receiver catches the message. And of course transport means this data can be shipped on multiple network types as the transport layer abstracts from the actual transmission layer of most protocols.

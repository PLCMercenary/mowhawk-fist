+++
title = "MQTT: I heard its over-rated"
author = ["Sean Terrell"]
date = 2020-07-09T04:17:00-05:00
lastmod = 2020-07-09T04:18:39-05:00
tags = ["SCADA", "IIoT", "Comms", "network"]
topics = ["MQTT", "SCADA"]
draft = false
+++

**Appaently the first rule of MQTT is we dont talk about MQTT**

Sure, its all over LinkedIN. Its the first thing anyone mentions in a conversation about IoT or the future of automation. But what the hell is it?

**Message Queing Telemetry Transport** - the words MQTT is supposed to represent dont mean a whole helluvlot to me. Messages are pretty standard communications between .. fucking anything. And Queing sounds like there is either a time slot to transmit which means synchronous data out and that blows, or that the state of the connection can hold message delivery in a que.. and that would be ok.

**MQ Telemetry Transport** Ok so we know that Message Queing is happening and **Telemetry** ok that is sensor data. Now we are getting into an automation monkey's wheel house. Telemetry almost always refers to sensors and devices sending reporting data. Often times Telemetry is commutated values packed into a very tiny message and booted out in a single frame called fire and forget... just hoping that the receiver catches the message. And of course transport means this data can be shipped on multiple network types as the transport layer abstracts from the actual transmission layer of most protocols.

So what I have learned is that MQTT is the best of all this jargon.

A little history: MQTT protocol was developed by Arlan Nipper (Cirrus Link) and Andy Sanford-Clark (IBM) while trying to get midstream data from extremely remote exxon-mobile sites over ViaSat connections. So they needed a way to pack data into a constrained message that cost mega $$$ every transmission. The MQ moniker was added with the IBM MQseries even though the MQTT Publish and Subscribe model dont actually use a message que

Pub Sub - why this is the key. MQTT (depending on version and protocol specifics) defines several types of node. Basically arranged into Brokers and Clients. Clients are everything that isnt a Broker and Brokers are the hubs that clients connect too. Clients to these brokers can both publish and subscribe. or just publish or just subscribe. but the basic framework is pretty simple.

The broker is hub as we said above and its role is pretty simple 1)know the status of all connected clients, and 2)broker out published messages incoming from clients to subscribed clients looking for those messages. It does this based on the messages that each client hands the broker upon connection

The beauty of MQTT is the simplicity of how it works. Each client connecting to the broker states what its there for, and what actions to take if it disconnects. The state of each connection is then monitored and as long as its alive the broker simply assumes the last message sent is the current state.

This is a pretty basic overview of MQTT and hopefully gives some insight into what the hell it is. in the next article in this series Ill break down the message types and provide a simple tutorial to start publishing and subscribing with free tools.

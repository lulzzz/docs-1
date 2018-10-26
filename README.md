# Introduction

The purpose of the Laboratory Information System \(LIS\) Connector project is to provide an electronic system to facilitate the following:

* Allow medical testing devices to communicate electronically with the system
* To decode HL7, ASTM and POCT messages received from medical testing devices
* To save decoded data from medical devices to a cloud database
* Provide access to the cloud data via REST APIs

### System Description

The system is comprised of the following software components:

#### Health IoT Edge

Computing at the edge allows medical IoT devices to transmit data electronically to the local network server or a local computer on premise. The IoT devices will communicate directly with the computer system via a TCP connection with ethernet or a serial connection. In addition, the devices communicate with lower level protocols such a MLLP. To accommodate device connection an architecture was designed to support connectivity of devices via TCP using low level protocols defined by the relevant HL7, ASTM or POCT standards that the device supports for connectivity. Health IoT Edge is a series of Windows Services that listens for HL7, ASTM and POCT messages on a specified TCP port listening at a specified IP Address. At this point, Healt IoT Edge supports the following operating systems:

* Windows 7
* Windows 8, 8.1
* Windows 10

The functions of Health IoT edge are to:

* Receive messages over a TCP connection from the medical IoT devices
* Read the message from the low level protocols
* Package and send the message to a cloud service for decoding
* After receiving the decoded message, save the data to a cloud database via another cloud service

**Health IoT Hub**

Decoding of messages and saving data to a cloud database is done in the cloud with the Health IoT Hub. The hub a set of REST APIs that allow for the processing of messages and data storage. The functions of the Health IoT Hub are to:

* Decode HL7, ASTM and POCT messages
* Save data to a cloud database

The Health IoT Hub enforces a secured TLS/HTTPS connection for data security. In addition, the REST APIs can only be accessed through OAuth 2 authorized requests.




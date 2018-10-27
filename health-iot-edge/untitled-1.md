# Receive a message

In this section, you will lean how to receive and view a message sent from a medical testing device.

Ensure that the TCP Listener has been set up and is running as described in the last section. Take note of the **Port** number and **IP address** of the TCP Listener.

![](../.gitbook/assets/create-tcp-listener-started.PNG)

Connect the medical testing device to the computer or network server where you installed Health IoT Edge. The device can be connected with an ethernet cable, serial connector, usb, or wi-fi. Some manufacturers may provide hubs or other electrical equipment to connect their device to a computer system.

Configure the medical device to connect to the **Port** number and **IP Address** of your TCP Listener. Take readings on the device and send the messages to your TCP Listener.

In the following example, we will use a simulator to send messages to the TCP Listener.

You can download and install the **Smart HL7 Sender** at the following link.

{% embed url="http://smarthl7.com/tools.html" %}

Load a sample HL7 message into the simulator, you can use the following message :

```text
MSH|^~\&amp;|cobasIT1000|HIS Location|LISConnectorApp|LIS Connector Facility|20180910114647||ORU^R01|13051421939BD4333|P|2.3|||NE|SU
PID|1||0003||Fab^Cesc^||19890811|M||||||||||V003
PV1|1||A1||||||||||||||||V003
ORC|NW|^HIS|||CM||||20180910114059
OBR||^HIS||||||||||||||||||||20180910114122|||F
OBX|1|ST|PATID|1|0003||||||F
OBX|2|ST|VISIT|1|V003||||||F
OBX|3|ST|LASTNAME|1|Fab||||||F
OBX|4|ST|FIRSTNAME|1|Cesc||||||F
OBX|5|ST|SEX|1|M||||||F
OBX|6|ST|DATEOFBIRTH|1|19890811||||||F
OBX|7|ST|ANALYZERNAME|1|ACI II UU13013667||||||F
OBX|8|ST|ANALYZEDATETIME|1|20180910114122||||||F
OBX|9|ST|OPID|1|ROCHE||||||F
OBX|10|ST|Glu2|1|67|mg/dL|-||||F|||20180910114122
OBX|11|ST|COMMENT1|1|Doctor Notified||||||F
```

Configure the sender to send the message to your TCP Listener's  **Port** number and **IP Address**. 

![](../.gitbook/assets/hl7-sender.PNG)

After you send the message, you can view the received message in the Health IoT Edge logs. To view the logs, select the TCP Listener and then click on the 'Logs' button.

![](../.gitbook/assets/view-logs.PNG)

In the 'Logs' window, select a log item to view the detailed log entries. You can view the HL7 message sent by the simulator in the log entries.

![](../.gitbook/assets/logs-messages.PNG)


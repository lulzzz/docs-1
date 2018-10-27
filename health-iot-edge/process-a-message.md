# Process a message

In this section we will decode a message using a cloud service from the Health IoT Hub.

The Health IoT Edge application will receive messages from medical devices using TCP Listeners. It will then post the the HL7,  ASTM or POCT message to a REST API in the Health IoT Hub for decoding.

### Client Credentials

The REST API required use OAuth 2 to provide security access to the APIs. HTTPS is also enforced. To access the API you will require the following credentials:

* **Token URL** - The endpoint URL to acquire a short lived JWT access token
* **Client Id** - An id to identify your client application
* **Client Secret** - A secret key to be used your client application

You will configure these parameters in your Health IoT Edge application that will act as your client to access the secured APIs. In the main screen, select the TCP Listener, and then click on the 'Edit' button. Enter your credentials in the 'Client Credentials' tab.

![](../.gitbook/assets/cleint-credentials.PNG)

You can request client credentials for Sandbox Testing by following the instructions outlined in the following link:

[Request client credentials](../sandbox-testing/request-client-credentials.md)

### Processing Service

After configuring the client credentials you must add the Service URL for the processing service and the Service Id. You will add these parameters in the 'Processing Service' tab.

![](../.gitbook/assets/processing-service.PNG)

Devices are grouped within categories for message processing. Each category will contain devices and tests supported by the message processor. You can view the Device Category of this guide section to find your device and clinical tests that are supported. If you do not see your device andclinical test, follow the instructions in the link below to send us a request to create a new processor for your device:

[Request a new processor category](../sandbox-testing/request-a-new-processor-category.md)

### Device Category

In the 'Device' tab, add the device category that contains your device and clinical test.

![](../.gitbook/assets/device-category.PNG)

{% hint style="info" %}
You must **stop** and **restart** the TCP Listener for the new configuration to take effect. Please wait for about 30 seconds before re-starting the service since you may experience a 'socket in use' error.
{% endhint %}

### Processing A Sample Message

The following message is generated from a **Category A** device. We will use the Smart HL7 Sender simulator to send this message to our  TCP Listener for message processing. 

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

First the message will be read by the Health IoT Edge application, the message will then be posted to the Health IoT Hub message processing service. The processing service API will return a JSON of the processed message. You can view the processed message in the Logs.

The image below shows the message that is posted to the API.

![](../.gitbook/assets/post-device-message.PNG)

The response from the API is a JSON representation of the processed message.

![](../.gitbook/assets/processed-message.PNG)

You can learn more about the APIs and message processing at the following link:

[Message Processor](../health-iot-hub/untitled.md)






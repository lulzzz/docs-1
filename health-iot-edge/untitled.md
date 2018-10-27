# Installation

Health IoT Edge is installed on windows using the .msi installation file. Please note that the application does not have an installation certificate and will be identified by the Windows UAC as from an 'unknown publisher'. You will encounter the Windows installation warning similar to the one below. Click the 'More Info' and click on the 'Run anyway' button to install. You may experience a different warning in different versions of windows / server.

![](../.gitbook/assets/unknown_publisher.PNG)



After installation, you will see the Health IoT Edge shortcut on the desktop and the Program folders menu.

![](../.gitbook/assets/health_iot_edge_icon.PNG)

If you would prefer a self-signed certificate for installation, please refer to the support section.

### **Download the installation file**

You can download the file from the following link:

{% embed url="https://raw.githubusercontent.com/rcl-lab-connector/installations/master/health-iot-edge/Setup.msi" caption="Setup.msi \(3.7 Mb\)" %}

Health IoT Edge is a utility used to create and manage several Windows Services on your computer to connect with medical IoT devices. You must run the application with Administrator privileges.

If you want, you can also manage the Windows Service using the 'Services' tool in Windows. You can view the event logs in the Windows Event Viewer in the 'Application and Service Logs'.


# 4.1. Switching Communication Paths

## 1. Overview
This chapter describes the rule of priority if the system connects the multiple connection methods at the concurrent on the same device, and the status notification of when the system switches the communication paths.

## 2. Background/Purpose/Reason for Standardization
Regarding the switching from BT to USB on the same device, is proposed and accepted by the "SDL 0053 - Connectivity via iAP-BT and Transport Switch" to the SDL Evolution on the SDL Consortium.
Currently, the switching from BT to USB applies only to the iOS system.
However, since the behavior of switching communication paths is not explicitly defined in the SDL standard specification, it is necessary for the OEMs to define it by themselves.
Hence, the purpose of this document is to standardzie such cases/issues using the TOYOTA specification, in order to be able to contribute to the SDL Ecosystem.

## 3. Function Details
### 3.1. Specification for Switching Communication Paths
As the basic rule of specification for switching communication paths, there are the followings:
- Priority of the communication methods : USB > BT
Note : Since WiFi can not communicate by alone, therefore WiFi is excepted from the priority.
- If the SDL connects the multiple terminal(mobile)s,  then the device which is already connected to the SDL is priority.

The following Table1 describes the specification for switching the multiple Transport, in order to be able to use such as status notification of when the system switches the connection methods for adding the connection method.

**Table1.** Table for switching multiple Transport

<table align="left">
<tr><th colspan="2" rowspan="2"></th><th colspan="3"> Additional Connection Method </th></tr>

<tr><th> BT </th><th> USB </th><th> WiFi </th></tr>

<tr><td rowspan="4"> Current <br>Connection </td><td> BT </td><td> - </td><td> USB<br>*1 </td><td> BT + WiFi<br>*2 </td></tr>

<tr><td> USB </td><td> USB<br>*3 </td><td> - </td><td> USB<br>*3 </td></tr>

<tr><td> WiFi </td><td> BT + WiFi </td><td> USB </td><td> - </td></tr>

<tr><td> BT + WiFi </td><td> - </td><td> USB<br>*4 </td><td> - </td><tr>
</table>
<br>
*1 : If the SDL App is able to judge as the same device, it should switch Transport to USB.<br>
*2 : If the SDL App will use the VPM after detecting WiFi tranport(which judge to be same with the device using BT), <br>the SDL App will start the VPM.<br>
*3 : USB connection path is priority, even if the same device.<br>
*4 : If the SDL App is able to judge as the same device, it should switch the connection method to USB.

### 3.2. Logic for switching communication paths in iOS
Process the switching communication path from BT to USB:
1. When the switching transport occurs, the SDL Core starts the timer by setting in timeout value in the configuration file
2. Cache the HMI Level of current running SDL App, after the SDL App switched the device, then, perform the following process
- Create the list of SDL Apps which is waitting for re-registering<br>
- Terminate the current BT Transport<br>
- Copy the current BT status to the USB device
3. If the timeout of switching transport occurs : Clear the list of SDL Apps which are waitting for the re-registering, and perform "Unregisterd()" against the SDL Apps which are not registered within the switching time, then, notify them to the HMI.
If the process finishes within the timeout of switching transprt : If the SDL App is included in the list of SDL Apps which is waitting for the re-registering when the SDL App receives the RegisterApp notification, the HMI goes back the SDL App to the previous HMILevel and notifies the success to launch the SDL App to the Mobile.

## 4. Differences from SDL standard specification
The specification for the switching communication paths is not explicitly defined in the SDLC Official document.
Therefore, the contents described in Table1 above differ from the existing SDL standard specification.

## 5. Implementation Methods
The system has implemented them on "SDL 0053 - Connectivity via iAP-BT and Transport Switch" in the SDL Consortium.

## 6. Impacted Platforms
There is no impact for the platforms.


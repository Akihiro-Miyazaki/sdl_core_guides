# 2.6. Change screen to SDL App from other smartphone linkage functions (CarPlay/Android Auto)
## 1. Overview
This chapter describes the method to switch between the SDL App and other smartphone linkage functions(CarPlay (CP)/ Android Auto(AA)).
## 2. Background/Purpose/Reason for Standardization
The SDL standard specification covers information about Apps that support SDL.
However, the switching screen with other smartphone linkage functions such as CP, AA(, Car Life and WeLink) is not explicitly defined by the SDL standard specification, therefore, it is necessary for the OEMs to define it by themselves.
Hence, the purpose of this document is to standardize such cases/issues using the TOYOTA specification, in order to be able to contribute to the SDL Ecosystem.
## 3. Function Details
### 3.1. Function overview
Due to the competition of communication path such as USB, and the restrictions on CPU load depending on the system, the smartphone linkage functions including the SDL (, CP, AA (, Car Life, WeLink)) is mutually exclusive.
Therefore, since it can not be used at the same time, it is necessary to disable other smartphone linkage functions when using the SDL function.
### 3.2. Switching screen to the smartphone linkage functions
Enable/disable SDL is set.

- SDL set to ENABLE:CP/AA does NOT work
- SDL set to DISABLE:CP/AA works

## 4. Differences from the SDL standard specification
The switching smartphone linkage(CP, AA(, Car Life, WeLink) is not explicitly defined in the SDL specification, because it is processed in the HMI.
Additionally, the switching between similar functions and related exclusive functions needs, that need to be desclibe in the HU specification, however, there is no definition about it in the SDL standard specification itself.
Therefore, all of the contents describe in "3. Function Details" differ from the existing SDL standard specification.
## 5. Sequence Diagrams
Table1 shows the behavior when each smartphone linkage functions are switched.

<table border="1" align="left">

<caption>**Table1** Switching behavior Matrix</caption>

<tr><th  rowspan="2" colspan="2" bgcolor=lightblue></th><th colspan="3" bgcolor=lightblue> Turn on "Use for SDL" </th><th colspan="2" bgcolor=lightblue> Turn on "Use for Android Auto" </th><th colspan="3" bgcolor=lightblue> Turn on "Use for Apple CarPlay" </th></tr>

<tr><th bgcolor=lightblue> BT<br>(HFP/AVP) </th><th bgcolor=lightblue> USB </th><th bgcolor=lightblue>WiFi+BT<br>(HFP/AVP) </th><th bgcolor=lightblue>USB+BT<br>(HFP) </th><th bgcolor=lightblue>WiFi+BT<br>(HFP) </th><th bgcolor=lightblue>USB </th><th bgcolor=lightblue>WiFi<br>(2.4GHz) </th><th bgcolor=lightblue>WiFi<br>(5GHz) </th></tr>

<tr><td rowspan="3" bgcolor=lightblue> **SDL** </td><td bgcolor=lightblue> **BT<br>(HFP/AVP)** </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>No combination </td><td> Start AA session<br>End SDL session </td><td bgcolor=gray> NA<br>No combination </td><td> Start CP session<br>End SDL session </td><td> Start CP session<br>End SDL session </td></tr>

<tr><td bgcolor=lightblue> **USB** </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td> Start AA session<br>End SDL session </td><td bgcolor=gray> NA<br>No combination </td><td> Start CP session<br>End SDL session </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td></tr>

<tr><td bgcolor=lightblue> **WiFi+BT<br>(HFP/AVP)** </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>No combination </td><td> Start AA session<br>End SDL session </td><td bgcolor=gray> NA<br>No combination </td><td> Start CP session<br>End SDL session </td><td> Start CP session<br>End SDL session </td></tr>

<tr><td rowspan="2" bgcolor=lightblue> **AA** </td><td bgcolor=lightblue> **USB+BT<br>(HFP)** </td><td bgcolor=gray> NA<br>No combination </td><td> Start SDL session<br>End AA session </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td></tr>

<tr><td bgcolor=lightblue> **WiFi+BT<br>(HFP)** </td><td> Start SDL session<br>End AA session </td><td bgcolor=gray> NA<br>No combination </td><td> Start SDL session<br>End AA session </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td></tr>

<tr><td rowspan="3" bgcolor=lightblue> **CP** </td><td bgcolor=lightblue> **USB** </td><td bgcolor=gray> NA<br>No combination </td><td> Start SDL session<br>End CP session </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td></tr>

<tr><td bgcolor=lightblue> **WiFi<br>(2.4GHz)** </td><td> Start SDL session<br>End CP session </td><td bgcolor=gray> NA<br>No combination </td><td> Start SDL session<br>End CP session </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td></tr>

<tr><td bgcolor=lightblue> **WiFi<br>(5GHz)** </td><td> Start SDL session<br>End CP session </td><td bgcolor=gray> NA<br>No combination </td><td> Start SDL session<br>End CP session </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>No combination </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td><td bgcolor=gray> NA<br>Same Service </td></tr>

</table>

**Table1** Switching behavior Matrix
![table1_switching_behavior_matrix.png](./assets/table1_switching_behavior_matrix.png)


## 6. Impacted Platforms
Changes impact the following platform/s:
- HMI

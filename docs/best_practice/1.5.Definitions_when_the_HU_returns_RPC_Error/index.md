# 1.5. Definitions when the HU returns RPC Error

## 1. Overview
This chapter describes the RPC in MOBILE_API.xml and HMI_API.xml that has a lack of or incorrect description.
In addition, we have modified the incorrect definition and complemented the missing details on these RPC parameters.

## 2. Background/Purpose/Reason for Standardization
There is a lack of or incorrect description in the current RPC documents of MOBILE_API.xml and HMI_API.xm.
Hence, the purpose of this document is to standardize such issue using the results of operations confirmed from source code, etc, in order to be able to contribute to the SDL Ecosystem.

## 3. Function Details
### 3.1. Lack of definition in the RPC parameter
Below is RPC parameter description in MOBILE_API.xml that are added/modified.

(1) HMILevel (Type : enum)
The enum value is defined because it was not included in the current definition.

```xml
 <enum name="HMILevel" since="1.0">
     <description>Enumeration that describes current levels of HMI.</description>

     <element name="FULL" internal_name="HMI_FULL">
+　　　   <description> The application has full use of the SDL HMI. The app can output via TTS, display,
+            or streaming audio and receive notifications via VR, Menu, and button presses. </description>
     </element>

     <element name="LIMITED" internal_name="HMI_LIMITED" >
+       <description> This HMI Level is only defined for a media application using an HMI with an 8 inch touchscreen
+           (Navi) system.
+           The application can display text by "Show" and receives button presses from media-oriented buttons
+           (SEEKRIGHT, SEEKLEFT, TUNEUP, TUNEDOWN, PRESET_0-9). </description>
     </element>

     <element name="BACKGROUND" internal_name="HMI_BACKGROUND" >
+        <description> The application cannot interact with user via TTS, VR, Display or Button Presses. </description>
     </element>

     <element name="NONE" internal_name="HMI_NONE" >
+        <description> The application has been discovered by SDL, but the app cannot send any requests or receive any 
+            notifications. </description>
     </element>

 </enum>
```

### 3.2. Incorrect definition in the RPC parameter
Below are RPC parameters description in HMI_API.xml that are modified.

(1) Show (Type : request)
mainfield3 and mainField4 are added because they are also affected by the parameter.

```xml
 <function name="Show" messagetype="request">
      ...
     <param name="alignment" type="Common.TextAlignment" mandatory="false">
-        <description> Specifies how mainField1 and mainField2 texts should be aligned on the display. </description>
+        <description> Specifies how mainField1, mainField2, mainField3 and mainField4 texts should be aligned on 
+            display. If omitted, texts will be centered. </description>
         <description>If omitted, texts must be centered</description>
     </param>
      ...
 </function>
```

Add description in case of the parameter is omitted.
If the parameter is omitted custom preset does not change, same as other Show parameter like "alignment" above.

```xml
 <function name="Show" messagetype="request">
     ...
     <param name="customPresets" type="String" maxlength="500" minsize="0" maxsize="10" array="true" mandatory="false">
         <description> App labeled on-screen presets (i.e. GEN3 media presets or dynamic search suggestions).</description>
-        <description> If omitted on supported displays, the presets will be shown as not defined. </description>
+        <description> If omitted on supported displays, the presets will not change. </description>
     </param>
      ...
 </function>
```


(2) PerformInteraction (Type : request)
The default value is added because it was not described in the "interactionLayout" parameter.




### 3.3. RPC Invalid Data Error
Below are RPCs that returns an "error: Invalid Data" if the length of the string is 0.
The definition of minlength is added because it was not included in the current definition.

#### 1. RPC Invalid data error notification items (HMI_API .xml)
(1) Choice (Type : suruct)




(2) VrHelpItem (Type : suruct)




(3) SeatControlCapabilities (Type : struct)




(4) MenuParams (Type : struct)




(5) TextFieldStruct (Type : struct)




(6) ButtonPress (Type : request)




(7) DialNumber (Type : request)




(8) SetDisplayLayout (Type : request)




(9) ChangeRegistration (Type : request)




(10) SystemRequest (Type : request)




(11) Slider (Type : request)




(12) SendLocation (Type : request)




(13) SeatMemoryAction (Type : struct)




(14) Image (Type : struct)




(15) TTSChunk (Type : struct)




(16) EqualizerSettings (Type : struct)




(17) ModuleData (Type : struct)




(18) CreateWindow (Type : request)




(19) GetInteriorVehicleData (Type : request)




(20) GetInteriorVehicleDataConsent (Type : request)





#### 2. RPC Invalid data error notification items (MOBILE_API .xml)
(1) CloudAppProperties (Type : struct)




(2) Choice (Type : struct)




(3) VrHelpItem (Type : struct)




(4) AppInfo (Type : struct)




(5) MenuParams (Type : struct)




(6) Turn (Type : struct)




(7) SeatMemoryAction   (Type : struct)




(8) KeyboardProperties (Type : struct)




(9) LocationDetails: (Type : struct)




(10) EqualizerSettings  (Type : struct)




(11) ModuleData (Type : struct)




(12) RegisterAppInterface (Type : request)




(13) CreateWindow (Type : request)




(14) SetGlobalProperties (Type : request)




(15) AddCommand (Type : request)




(16) AddSubMenu (Type : request)




(17) PerformInteraction (Type : request)




(18) Alert (Type : request)




(19) Show (Type : request)




(20) ScrollableMessage (Type : request)





(21) Slider (Type : request)




(22) ChangeRegistration:   (Type : request)





(23) PutFile (Type : request)




(24) GetFile (Type : request)




(25) DeleteFile (Type : request)




(26) SetAppIcon (Type : request)




(27) SetDisplayLayout (Type : request)




(28) SystemRequest (Type : request)




(29) SendLocation (Type : request)




(30) DialNumber (Type : request)




(31) ButtonPress (Type : request)




(32) GetInteriorVehicleData (Type : request)




(33) GetInteriorVehicleDataConsent (Type : request)




(34) ReleaseInteriorVehicleDataModule (Type : request)




(35) GetCloudAppProperties (Type : request)




## 4. Differences from SDL standard specification
The definitions of the RPC parameters that are modified/complemented in Function Details differ from the existing SDL official documents.

# 3. Switching SDL Apps

## 1. Overview
This chapter describes the sequence of switching SDL Apps.

In addition, regarding the behavior of "Pressing other SDL App Icon on the HU screen" and "The launch by pressing HardSW" please refer to the following:

<ol>
"2.1. Press the SDL App Icon on the SDL Menu screen"
"2.2. Launch by  Voice Recognition"
"2.3. Launch by choosing the Audio source on the Audio screen"
"2.4. Launch by HardSW"
</ol>

In this chapter, the overall sequence of switching SDL Apps for each type is described.

## 2. Background/Purpose/Reason for Standardization
Currently, switching to other SDL App while an (existing) SDL App is running, is an SDL standard behavior.
However, since the behavior of switching Apps is not explicitly defined in the SDL standard specification, it is necessary for the OEMs to define it by themselves.
Hence, the purpose of this document is to standardize such cases/issues using the TOYOTA specification, in order to be able to contribute to the SDL Ecosystem.

## 3. Function Details
### 3.1. Function overview
Table 1 shows the 9 patterns for switching SDL Apps.

**Table1.** Sequence pattern of switching SDL Apps
<table>
<tr><th> No. </th><th> 1st Launched App	</th><th> 2nd launched App </th></tr>
<tr><td> 1 </td><td rowspan="3"> "MEDIA" type SDL App </td><td> "MEDIA" type SDL App </td></tr>
<tr><td> 2 </td><td> "NAVIGATION"/"PROJECTION" type SDL App </td></tr>
<tr><td> 3 </td><td> Normal type SDL App </td></tr>
<tr><td> 4 </td><td rowspan="3"> "NAVIGATION"/"PROJECTION" type SDL App </td><td> "MEDIA" type SDL App </td></tr>
<tr><td> 5 </td><td> "NAVIGATION"/"PROJECTION" type SDL App </td></tr>
<tr><td> 6 </td><td> Normal type SDL App </td></tr>
<tr><td> 7 </td><td rowspan="3"> Normal type SDL App </td><td> "MEDIA" type SDL App </td></tr>
<tr><td> 8 </td><td> "NAVIGATION"/"PROJECTION" type SDL App </td></tr>
<tr><td> 9 </td><td> Normal type SDL App </td></tr>
</table>

App types are determined by 'AppHMIType' in Table2 :

**Table2.** AppType Categorized by each AppHMIType
<table>
<tr><th> app type </th><th> AppHMIType </th></tr>
<tr><td rowspan="9"> Normal type SDL App </td><td> DEFAULT </td></tr>
<tr><td> COMMUNICATION </td></tr>
<tr><td> MESSAGING </td></tr>
<tr><td> INFORMATION </td></tr>
<tr><td> SOCIAL </td></tr>
<tr><td> BACKGROUND_PROCESS </td></tr>
<tr><td> TESTING </td></tr>
<tr><td> SYSTEM </td></tr>
<tr><td> REMOTE_CONTROL </td></tr>
<tr><td> "MEDIA" type SDL App </td><td> MEDIA </td></tr>
<tr><td rowspan="2"> "NAVIGATION"/"PROJECTION" type SDL App </td><td> NAVIGATION </td></tr>
<tr><td> PROJECTION </td></tr>
</table>

## 4. Differences from SDL standard specification
There is no provided description about the sequences of switching between the SDL Apps in the SDL official documents.
Therefore, all of the following sequences  describe in "5. Sequence Diagrams" differ from the existing SDL standard specifications.

## 5. Sequence Diagrams
### 5.1. Switching from "MEDIA" type SDL App to "MEDIA" type SDL App

<div style="text-align: center;">

![figure1.from_media_sdl_app_to_media_sdl_app.png](./assets/figure1.from_media_sdl_app_to_media_sdl_app.png)<br>
**Figure1.** Sequence of switching from "MEDIA" type SDL App to "MEDIA" type SDL App

</div>

### 5.2. Switching from "MEDIA" type SDL App to "NAVIGATION"/"PROJECTION" type SDL App

<div style="text-align: center;">

![figure2.from_media_sdl_app_to_navipro_sdl_app.png](./assets/figure2.from_media_sdl_app_to_navipro_sdl_app.png)<br>
**Figure2.** Sequence of switching from "MEDIA" type SDL App to "NAVIGATION/PROJECTION" type SDL App

</div>

### 5.3. Switching from "MEDIA" type SDL App to Normal type SDL App

<div style="text-align: center;">

![figure3.from_media_sdl_app_to_other_sdl_app.png](./assets/figure3.from_media_sdl_app_to_other_sdl_app.png)<br>
**Figure3.** Sequence of switching from "MEDIA" type SDL App to Normal type SDL App

</div>

### 5.4. Switching from "NAVIGATION"/"PROJECTION" type SDL App to "MEDIA" type SDL App

<div style="text-align: center;">

![figure4.from_navipro_sdl_app_to_media_sdl_app.png](./assets/figure4.from_navipro_sdl_app_to_media_sdl_app.png)<br>
**Figure4.** Sequence of switching from "NAVIGATION/PROJECTION" type SDL App to "MEDIA" type SDL App

</div>

### 5.5. Switching from "NAVIGATION"/"PROJECTION" type SDL App to "NAVIGATION"/"PROJECTION" type SDL App

<div style="text-align: center;">

![figure5.from_navipro_sdl_app_to_navipro_sdl_app.png](./assets/figure5.from_navipro_sdl_app_to_navipro_sdl_app.png)<br>
**Figure5.** Sequence of switching from "NAVIGATION/PROJECTION" type SDL App to "NAVIGATION/PROJECTION" type SDL App

</div>

### 5.6. Switching from "NAVIGATION"/"PROJECTION" type SDL App to Normal type SDL App

<div style="text-align: center;">

![figure6.from_navipro_sdl_app_to_other_sdl_app.png](./assets/figure6.from_navipro_sdl_app_to_other_sdl_app.png)<br>
**Figure6.** Sequence of switching from "NAVIGATION/PROJECTION" type SDL App to Normal type SDL App

</div>

### 5.7. Switching from Normal type SDL App to "MEDIA" type SDL App

<div style="text-align: center;">

![figure7.from_other_sdl_app_to_media_sdl_app.png](./assets/figure7.from_other_sdl_app_to_media_sdl_app.png)<br>
**Figure7.** Sequence of switching from Normal type SDL App to "MEDIA" type SDL App

</div>

### 5.8. Switching from Normal SDL App to "NAVIGATION"/"PROJECTION" type SDL App

<div style="text-align: center;">

![figure8.from_other_sdl_app_to_navipro_sdl_app.png](./assets/figure8.from_other_sdl_app_to_navipro_sdl_app.png)<br>
**Figure8.** Sequence of switching from Normal type SDL App to "NAVIGATION/PROJECTION" type SDL App

</div>

### 5.9. Switching from Normal type SDL App to Normal type SDL App

<div style="text-align: center;">

![figure9.from_other_sdl_app_to_other_sdl_app.png](./assets/figure9.from_other_sdl_app_to_other_sdl_app.png)<br>
**Figure9.** Sequence of switching from Normal type SDL App to Normal type SDL App

</div>

## 6. Impacted Platforms
Changes impact the following platform/s:
- HMI

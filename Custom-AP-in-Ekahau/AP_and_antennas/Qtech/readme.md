В файл accessPointTypes.xml необходимо добавить конфигурационные строки следующим образом:

```
<?xml version="1.0"?>
<accessPointTypes>

[..] 
  <accessPointType vendor="QTECH" model="QWP-65-AC-VC">
    <radioType technology="n" frequencyBand="2.4" mimo="2x2" spatialStreams="2"/>
    <radioType technology="ac" frequencyBand="5" mimo="2x2" spatialStreams="2" maxSupportedBandwidth="80MHz" defaultAntenna24="QTECH QWP-65 2.4GHz" defaultAntenna5="QTECH QWP-65 5GHz-1"/>
    <radioType technology="ac" frequencyBand="5" mimo="2x2" spatialStreams="2" maxSupportedBandwidth="80MHz" defaultAntenna24="QTECH QWP-65 2.4GHz" defaultAntenna5="QTECH QWP-65 5GHz-2"/>
  </accessPointType>
  <accessPointType vendor="QTECH" model="QWP-82">
    <radioType technology="ax" frequencyBand="2.4" mimo="2x2" spatialStreams="2" />
    <radioType technology="ax" frequencyBand="5" mimo="2x2" spatialStreams="2" maxSupportedBandwidth="80MHz"/>
  </accessPointType>
  <accessPointType vendor="QTECH" model="QWP-82E">
    <radioType technology="ax" frequencyBand="2.4" mimo="2x2" spatialStreams="2"/>
    <radioType technology="ax" frequencyBand="5" mimo="2x2" spatialStreams="2" maxSupportedBandwidth="80MHz"/>
  </accessPointType>
<accessPointType vendor="QTECH" model="QWP-88" >
  <radioType technology="ax" frequencyBand="2.4" mimo="4x4" spatialStreams="4"/>
  <radioType technology="ax" frequencyBand="5" mimo="4x4" spatialStreams="4"/>  
</accessPointType>
  <accessPointType vendor="QTECH" model="QWO-820">
    <radioType technology="ax" frequencyBand="2.4" mimo="2x2" spatialStreams="2"/>
    <radioType technology="ax" frequencyBand="5" mimo="2x2" spatialStreams="2" maxSupportedBandwidth="80MHz"/>
  </accessPointType>
<accessPointType vendor="QTECH" model="QWO-820E + QANT-OD245805M">
    <radioType technology="ax" frequencyBand="2.4" mimo="2x2" spatialStreams="2" defaultAntenna24="QTECH QANT-OD245805M 2.4GHz" defaultAntenna5="QTECH QANT-OD245805M 5GHz"/>
    <radioType technology="ax" frequencyBand="5" mimo="2x2" spatialStreams="2" maxSupportedBandwidth="80MHz" defaultAntenna24="QTECH QANT-OD245805M 2.4GHz" defaultAntenna5="QTECH QANT-OD245805M 5GHz"/>
  </accessPointType>
<accessPointType vendor="QTECH" model="QWO-880E + QANT-OD245805M">
    <radioType technology="ax" frequencyBand="2.4" mimo="4x4" spatialStreams="4" defaultAntenna24="QTECH QANT-OD245805M 2.4GHz" defaultAntenna5="QTECH QANT-OD245805M 5GHz"/>
    <radioType technology="ax" frequencyBand="5" mimo="4x4" spatialStreams="4" defaultAntenna24="QTECH QANT-OD245805M 2.4GHz" defaultAntenna5="QTECH QANT-OD245805M 5GHz"/>
  </accessPointType>
  </accessPointTypes>
```
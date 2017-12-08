---
UID: NC.sensorscx.EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
title: EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
author: windows-driver-content
description: Used to stop a state change notification.
old-location: sensors\evt_sensor_driver_stop_state_change_notification.htm
old-project: sensors
ms.assetid: 53B064AF-D06B-46A0-9D77-2DA72F0B47D6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: ISensorDriver, OnSetProperties, ISensorDriver::OnSetProperties
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
req.header: sensorscx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: PFN_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION
req.alt-loc: sensorscx.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: _requires_same_
req.iface: ISensorDriver
req.product: Windows 10 or later.
---

# EVT_SENSOR_DRIVER_STOP_STATE_CHANGE_NOTIFICATION callback



## -description
<p>Used to stop a state change notification.</p>


## -prototype

````
NTSTATUS EvtSensorDriverStopStateChangeNotification(
   SENSOROBJECT Sensors
);
````


## -parameters
<dl>

### -param Sensors 

<dd>
<p>Holds information on the sensor being handled by the driver.</p>
</dd>
</dl>

## -returns
<p>Returns STATUS_SUCCESS if completed successfully.</p>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Sensorscx.h</dt>
</dl>
</td>
</tr>
<tr>
<th width="30%">
<p>IRQL</p>
</th>
<td width="70%">
<p>_requires_same_
</p>
</td>
</tr>
</table>
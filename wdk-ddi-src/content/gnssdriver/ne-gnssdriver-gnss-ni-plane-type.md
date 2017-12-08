---
UID: NE.gnssdriver.GNSS_NI_PLANE_TYPE
title: GNSS_NI_PLANE_TYPE
author: windows-driver-content
description: This enumeration indicates the plane type of a network initiated (NI) request represented by the GNSS_NI_REQUEST_PARAM structure.
old-location: sensors\gnss_ni_plane_type.htm
old-project: sensors
ms.assetid: F06FFABA-D7AB-4301-9F73-CE4BBB0B8AA6
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: FWPS_VSWITCH_EVENT_DISPATCH_TABLE0_, FWPS_VSWITCH_EVENT_DISPATCH_TABLE0
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: gnssdriver.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: GNSS_NI_PLANE_TYPE
req.alt-loc: gnssdriver.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.iface: 
---

# GNSS_NI_PLANE_TYPE enumeration



## -description
<p>This enumeration indicates the plane type of a network initiated (NI) request represented by the <a href="sensors.gnss_ni_request_param">GNSS_NI_REQUEST_PARAM</a> structure.</p>


## -syntax

````
typedef enum  { 
  GNSS_NI_SUPL   = 0x01,
  GNSS_NI_CP     = 0x02,
  GNSS_NI_V2UPL  = 0x03
} GNSS_NI_PLANE_TYPE;
````


## -enum-fields
<dl>

### -field GNSS_NI_SUPL

<dd>
<p>Indicates the plane type of the request is SUPL.</p>
</dd>

### -field GNSS_NI_CP

<dd>
<p>Indicates the plane type of the request is CP.</p>
</dd>

### -field GNSS_NI_V2UPL

<dd>
<p>Indicates plane type of the request is V2UPL.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Gnssdriver.h</dt>
</dl>
</td>
</tr>
</table>
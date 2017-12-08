---
UID: NE.gnssdriver.GNSS_NI_USER_RESPONSE
title: GNSS_NI_USER_RESPONSE
author: windows-driver-content
description: This enumeration indicates the user’s response to a network initiated (NI) request, which is represented by the GNSS_NI_RESPONSE structure.
old-location: sensors\gnss_ni_user_response.htm
old-project: sensors
ms.assetid: FD4A244D-641C-46A7-8777-8F64A5400D23
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
req.alt-api: GNSS_NI_USER_RESPONSE
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

# GNSS_NI_USER_RESPONSE enumeration



## -description
<p>This enumeration indicates the user’s response to a network initiated (NI) request, which is represented by the <a href="sensors.gnss_ni_response">GNSS_NI_RESPONSE</a> structure.</p>


## -syntax

````
typedef enum  { 
  GNSS_Ni_UserResponseAccept   = 0x01,
  GNSS_Ni_UserResponseDeny     = 0x02,
  GNSS_Ni_UserResponseTimeout  = 0x03
} GNSS_NI_USER_RESPONSE;
````


## -enum-fields
<dl>

### -field GNSS_Ni_UserResponseAccept

<dd>
<p>Indicates that the user accepted the NI request.</p>
</dd>

### -field GNSS_Ni_UserResponseDeny

<dd>
<p>Indicates that the user denied the NI request.</p>
</dd>

### -field GNSS_Ni_UserResponseTimeout

<dd>
<p>Indicates that the request timed out without a user response.</p>
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
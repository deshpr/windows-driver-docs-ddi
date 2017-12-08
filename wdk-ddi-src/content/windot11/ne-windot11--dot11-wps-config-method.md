---
UID: NE.windot11._DOT11_WPS_CONFIG_METHOD
title: DOT11_WPS_CONFIG_METHOD
author: windows-driver-content
description: The DOT11_WPS_CONFIG_METHOD enumeration specifies the Wi-Fi Protected Setup methods.
old-location: netvista\dot11_wps_config_method.htm
old-project: netvista
ms.assetid: FFA5B3FF-57AF-4701-97FB-E1182CDE8F7A
ms.author: windowsdriverdev
ms.date: 11/30/2017
ms.keywords: PRINTER_EVENT_ATTRIBUTES_INFO, PRINTER_EVENT_ATTRIBUTES_INFO, *PPRINTER_EVENT_ATTRIBUTES_INFO
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: windot11.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with  Windows 8.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DOT11_WPS_CONFIG_METHOD
req.alt-loc: Windot11.h
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
req.iface: 
req.product: Windows 10 or later.
---

# DOT11_WPS_CONFIG_METHOD enumeration



## -description

## -syntax

````
typedef enum _DOT11_WPS_CONFIG_METHOD { 
  DOT11_WPS_CONFIG_METHOD_NULL        = 0,
  DOT11_WPS_CONFIG_METHOD_DISPLAY     = 0x0008,
  DOT11_WPS_CONFIG_METHOD_PUSHBUTTON  = 0x0080,
  DOT11_WPS_CONFIG_METHOD_KEYPAD      = 0x0100
} DOT11_WPS_CONFIG_METHOD;
````


## -enum-fields
<dl>

### -field DOT11_WPS_CONFIG_METHOD_NULL

<dd>
<p>No setup method is configured.</p>
</dd>

### -field DOT11_WPS_CONFIG_METHOD_DISPLAY

<dd>
<p>Setup is configured by a software user interface.</p>
</dd>

### -field DOT11_WPS_CONFIG_METHOD_PUSHBUTTON

<dd>
<p>Setup is configured by push button enablement.</p>
</dd>

### -field DOT11_WPS_CONFIG_METHOD_KEYPAD

<dd>
<p>Setup is configured by a keypad action.</p>
</dd>
</dl>

## -remarks


## -requirements
<table>
<tr>
<th width="30%">
<p>Version</p>
</th>
<td width="70%">
<p>Supported starting with  Windows 8.</p>
</td>
</tr>
<tr>
<th width="30%">
<p>Header</p>
</th>
<td width="70%">
<dl>
<dt>Windot11.h</dt>
</dl>
</td>
</tr>
</table>